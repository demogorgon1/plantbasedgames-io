+++
title = "C++ Pitfalls of Online Procedural Worlds"
date = "2024-09-11"
author = "Rasmus"
cover = ""
description = ""
+++

\**Crickets*\*

Okay, maybe it's time for me to make a blog post about something. Let me see... Well, maybe I should talk a bit
about some interesting bugs I've had fun with while working on my pet MMORPG project. These bugs were 
related to procedural world generation and they were really kinda annoying to track down. They were caused by some silly misconceptions and wrong assumptions I had about the C++ standard library. I would have loved to have known about these things before, so consider this post a public service announcement for other people planning to dabble in procedural world generation for an online game, or more generally, writing code that always generate the same results across multiple platforms.

## The basic premise of generating random stuff
So, let's imagine a game. More specifically an online game with a server-client architecture. Let's say that we want some kind of RPG (or whatever) set in a randomly generated world. That's pretty neat, right, then we don't have to make it ourselves by hand. Big brain move. Furthermore, it allows us to keep generating new worlds to provide more variety for the players. 	

How are we going to implement it? The simplest way would be to generate the world on the server and then send it to the clients when they connect. This could very well work, but it seems quite wasteful. If we let the clients generate the world as well, only the seed for the random number generator needs to be sent by the server.

That's all rainbows and unicorns while running everything, both server and client, locally on your Windows computer while developing your game. In the real world when releasing your game, however, you probably want to run your servers on some nice cheap Linux system in the cloud. You can use WSL and Docker to make it really nice and easy for yourself. 

The problem materializes in front of you when you try to connect your Windows client (built with Visual Studio) to your Linux server (built with something like clang).

## Lesson 0: Make debugging easier
> TL;DR: Hashes. Hashes everywhere.

In my case, all I knew was that *something was wrong* and I didn't notice it before playing the game. The server and the client were in slight disagreement regarding how the world looked. I'd be able to catch this much earlier if I had been a better prepared:

- Provide some kind of master hash value of your generated world. The server should send this to the client, which will then be able to quickly see if it's getting the expected result.
- Procedural world generation often happens in a series of discrete steps. For example, maybe the landscape is created first, then the trees are added, then monsters, etc. Make it easy to generate a hash of each of these steps, which will make it obvious to see when results diverge.

## Lesson 1: Sorting
> TL;DR: std::sort() isn't completely platform independent.

One of my steps for world generation is identifying all the walkable parts of the world and make sure all of them are accessible. This involves taking all the different unconnected parts and sort them by size. Now, it turns out, it's very common to have many parts of the exact same size. This doesn't matter at all for the algorithm, it really just wants them roughly sorted to get the best results. What does matter, however, is that the same parts always get sorted in the same way. 

Imagine these unsorted world parts:

|Size|Part  |
|:---|:-----|
|4   |A     |
|2   |B     |
|1   |C     |
|2   |D     |
|6   |E     |
|5   |F     |
|2   |G     |

Sorted by size on my Windows client:

|Size|Part  |
|:---|:-----|
|1   |C     |
|2   |D     |
|2   |B     |
|2   |G     |
|4   |A     |
|5   |F     |
|6   |E     |

Same parts sorted on my Linux server:

|Size|Part  |
|:---|:-----|
|1   |C     |
|2   |D     |
|2   |*__G__* <--|
|2   |*__B__* <--|
|4   |A     |
|5   |F     |
|6   |E     |

Whoops. That's not good. 

Solution 1: Cook your own sorting implementation and don't use std::sort. 

Solution 2: Don't only use the size for sorting. Basically make sure that no items are ever equal. In my case I didn't have anything else to sort by, so I added an unique identifier to each part.

```cpp
    std::sort(parts.begin(), parts.end(), [](
	    const Part& aLHS,
	    const Part& aRHS)
	{
	    if(aLHS.m_size == aRHS.m_size)
			return aLHS.m_id < aRHS.m_id;
		return aLHS.m_size < aRHS.m_size;
	});
```	

## Lesson 2: Hash tables
> TL;DR: std::unordered_set and std::unordered_map are unordered (d'oh!)

A bunch of places I put things into std::unordered_sets and std::unordered_maps and then later I'll iterate over them. This is nice and convenient and you always get the same order, at least while running your code on your own workstation. Turns out these data structures aren't implemented exactly the same on all platforms, so you don't get the same order when iterating. This should be quite obvious, but never really occuered to me. Note that this isn't just about the hash function used. You can use a custom hash function and you'll still get different order on different platforms.

Solution 1: Use std::set and std::map instead. These aren't based on hash tables, but rather binary search trees and are sorted by definition. Beware that this can easily come at a performance cost and that Lesson 1 applies here as well. 

Solution 2: Bring your own hash table implementation. Either make your own or use one of the many Open Source ones you can find online.

## Lesson 3: Honorable mentions
> TL;DR: std::uniform_int_distribution doesn't work the same on all platforms.

When generating random numbers you usually want them to be uniformly distributed. The C++ standard library offers the convenient std::uniform_int_distribution for this, but according to the specifications it's not platform independent. I thought this was yet another source of my problems, but actually in my case it was making the same numbers on both client and server. Nonetheless I replaced it with my own version, just to be sure.

## Conclusion
Be careful when using the C++ standard library and you need your code to do exactly the same thing across platforms. Look hard at your code and make sure you don't rely on something that's not defined by the C++ specifications.  