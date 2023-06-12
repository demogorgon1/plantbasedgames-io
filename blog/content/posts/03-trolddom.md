+++
title = "Trolddom"
date = "2023-06-12"
author = "Rasmus"
cover = ""
description = ""
+++

Finding time to ramble on a blog can be quite tricky when you feel that any minute you spend on it, might be better spent actually working on your project. If I was just
following my nature, I'd long ago crawled into a mountain cave, just to sit there to crank out code, only to come down from the mountain occasionally to stock up on canned beans. 
However, I'm quite aware that such a lifestyle can be quite detrimental to the grand scheme of things, so let this sunny day be the occasion for another blog post.

# Off-shoot side project of an off-shoot side project
Like I mentioned in a past blog post, I've been working on an MMORPG as a personal project for a couple of years now. From the start I decided to keep it quite simple,
as otherwise it would obviously be too much work for a mortal man, mountain cave dweller or not. Especially in the terms of graphics I wanted to keep it on an absolute minimum, 
in order to make content creation for the game as simple and efficient as possible. Also, I'm not an artist, I'm a programmer. I can generate a lot of code quite fast.

Anyway, when trying to hack together an MMORPG, or any online game in general, you quite quickly need to start worrying about how player progress should be stored in a database. 
This is a topic I find very interesting and is also something I've worked on a lot back in the good old days, when someone actually paid me to work on games. Back then I had a lot of 
ideas regarding data storage, but when you're on the clock and your team has a long backlog of issues, you can't really over-engineer things too much, unfortunately. Now, on the 
other hand, I get to over-engineer the living *beep* out of everything, which is amazing.

So, I ended up making [Jelly](https://github.com/demogorgon1/jelly), my home-cooked database engine specifically designed for storing data for online games. This became a bit of a project
in itself and, as things go, the game itself took the backseat for a while. 

Eventually *Jelly* got to point where I felt it was quite robust, but I also felt I needed to test it in a more real-world'ish environment. My MMORPG project was an obvious candidate to 
facilitate this testing, but it would take quite a lot of work to reach that point. I wanted to be able to release some kind of game as quickly as possible, try to get people to play it,
see what would happen. The game, unfortunately, wasn't anywhere near that level of completion. Instead I decided to make a new extremely minimal game, which could serve as a testing
platform for my database engine. Luckily, a lot of the code from the first project could be carried over.

Eventually I got carried away, again.

# Introducing Trolddom
![Sequence diagram with more boom](/blog/images/trolddom.gif)
*Brave adventurer venturing into a dungeon to kill a foul goblin. Huzzah.*

As you can probably infer, the game is completely tile-based to make it nice and simple. This makes it look like an old rogue-like (with some graphics painted on),
but it's real-time and you'll find most of the mechanics you expect to find in a typical World of Warcraft-clone. Dungeons, raids, talents, loot, gear, classes, guilds, trading, crafting, gathering, etc.

I've named it *Trolddom*, meaning "Magic" in Danish. The first D is silent.

# Procedurally generated worlds, or not
The original project relied heavily on procedural generation to make vast worlds with lots of detail (a la Dwarf Fortress), but it turned to be an insane amount of work. For Trolddom, I kinda
scrapped that idea, as I want it to be playable as soon as possible. Eventually, I might revisit procedural worlds again (after all the game looks like a rogue-like), but for now it's going to stay
on the shelf.

But where is all the content going to come from? An MMORPG requires a *large* world with a lot of stuff to do. Sure, with these extremely simple graphics I can make things really fast, but there is a limit.

# Half-open source
I considered that if I made the project completely open source, maybe people would start making stuff for it. People probably would. It worked great for [X-Moto](https://en.wikipedia.org/wiki/X-Moto), a game I 
made many years ago. 

Unfortunately, I have this crazy idea that I want to try and make a living from this and I also want to retain some degree of creative control of the project. Furthermore, hosting an MMORPG isn't free (even if 
nobody is playing it). Furthermore, anyone would be able to host their own servers if open source, which would obviously fragment the (potential) playerbase, which is bad.

But what about just opening the source, just a little bit? 

Okay, let's try that: [https://github.com/demogorgon1/trolddom-public](https://github.com/demogorgon1/trolddom-public)

*trolddom-public* is essentially an open source (MIT licensed) software library which includes all the data (game content) and large parts of the gameplay code. This will allow anyone to make new dungeons, classes,
monsters, whatever. 

Simply fork the repository, add or change stuff, make a pull request, and it might eventually end up in the game. Don't go crazy just yet, though, things are still getting refactored quite heavily.

I hope to make some kind of public "alpha test" soon('ish) and eventually, if it seems like anyone actually wants to play the game, I'll throw it on Steam for a few bucks.

Stay tuned for periodical updates on this blog. I'll also need to write some more technical documentation about how to navigate and extend *trolddom-public*.




