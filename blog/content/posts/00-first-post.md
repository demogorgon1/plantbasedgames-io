+++
title = "First Post"
date = "2023-03-05"
author = "Rasmus"
cover = ""
description = ""
+++

Last time I made anything resembling a blog, I don't think the word blog had been invented yet. In order words, it's been 
a while. What's the occasion, you might ask? Well, long story short, for a couple of years I've been dabbling with solo gamedev, 
and I think it's about time I start sharing with the world what I'm up to.

No, I'm not gonna try to sell you my game (yet). Rather, I'll talk about some nerdy aspects of gamedev that interests me greatly. 

# No, it's not science-based or 100% dragon
So, what's the personal project I've been been working on for a couple years? Yeah, it's an MMORPG. And, yeah, it's a solo project. 

What kind of madman thinks he can make an MMORPG alone? I hope I'm somewhere on the right side of the Dunning-Kruger curve, but who knows, 
as it sounds an awful lot like something someone on the left side would say.

Would-be MMORPG developers will eventually run into a bunch of problems:

* The sheer scale of things. The amount of content and assets that needs to be created, a huge world that needs to be designed in detail. 
* No matter how you tackle it, you'll need a vast quantity of code. A lot of this will be quite hairy and require experience and specialized knowledge.
* How and where are the servers going to run? What will it cost?

To tackle the first point, I'm employing a bunch of coping strategies, the most important one being procedural generation of pretty much everything. 
I'm also keeping the graphical fidelity of the game as low as possible. Kids these days call it pixel art. Recent advances in text-to-image AI technology
also makes everything a lot easier. If I have to spend more 30 minutes on one thing, it's too much.

The second point, code. This is amplified by the fact that the world generation is getting more and more complex all the time. It's important to 
me avoiding the common problem of procedurally generated worlds, where everything tend to look kinda samey and uninteresting. None the less, I'm fairly
good at writing a lot of code, fast, so it all seems to be working out just fine.

Finally, servers. As just one guy, with a very limited budget, it's absolutely essential that I make running the servers as cheap as possible. Eventually
there will be an open beta, which will be paid for out of my own pocket and I want to maximize bangs for the bucks. Obviously, I'm not going to be able
to convince anyone to pay a monthly subscription fee to play my game, ever, and I don't want to ruin it with pay-to-win microtransactions. You'll pay a few bucks
up front and that's it. Minimizing the cost of operating the game is essential. 

This brings my ramblings closer to what is going to be the main point of this blog, at least for now. No, I'm not really going to talk about 
my game yet, it's a bit too early for that.

# Haven't we seen that tree before?

I have a proud history of re-inventing the wheel, repeatedly. Especially when it comes to my personal projects, I tend to chase
some tangent, spending a lot of time doing things that might not be particularly productive in the grand scheme of things. I see
a squirrel, I chase it. I'm, however, very much aware that this is the only way I can really keep myself motivated long term,
when it comes to personal projects, so I try not to be too harsh on myself.

As mentioned, it's very important that server hosting gets as cheap as possible. 
There are two main components to this that will be the primary drivers of cost:

* Game servers, which run all the game logic, simulating the world. 
* The database where player progress will be stored.

The latter part is what the blog will focus on for now, as data storage has been my proverbial squirrel recently. 

# Are you insane?

To get to the point, not only am I silly enough to try to make my own MMORPG, I'm also writing a database system from scratch. This is obviously not very productive,
but I just can't help myself. I found it way too interesting. A sane man would use existing building blocks, not make his own.

So there you have it, we're going to talk about data storage for online video games. While the game itself probably isn't going to be Open Source, I've decided to 
release my database system under the MIT license in the hope that someone might find it useful or interesting. 

I've named it [Jelly](https://github.com/demogorgon1/jelly), because you know, it's all about blobs. The name sounds kinda blobby.

Next up, we'll look into the general server architecture of an MMORPG and eventually we'll see how Jelly might fit into all of this.