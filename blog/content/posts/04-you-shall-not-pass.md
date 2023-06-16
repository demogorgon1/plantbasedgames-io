+++
title = "You shall not pass!"
date = "2023-06-16"
author = "Rasmus"
cover = ""
description = ""
+++

Even though Trolddom might lack in the flashy graphics department, you'll find that in terms of baseline game mechanics, it is very similar to traditional MMORPGs. Anyone who has played a game like World of Warcraft, should be able to intuitively
understand how most things work. The *2D grid* nature of the game, however, leads to some fundamental differences, one of them being how movement is blocked by other players, enemies, and NPCs. This post will introduce some of the implications of
this.

## Your path is blocked
In your standard variety 3D MMORPG, you can usually walk straight through other players and enemies, only being stopped when your face hits a wall. This is usually a result of collision detection between players in a 
real-time 3D multiplayer game being quite wonky by nature, and if you have hundreds of players who want to be at the same spot, it's not going to be any easier. Furthermore, old-school MMORPGs were designed with old-school internet connections
in mind, which would make player collisions practically impossible. 

On the other hand, if your game is aligned on a 2D grid, it suddenly becomes extremely simple to do collision detection. In fact, it kinda becomes necessary, as it would be really confusing to have multiple players or enemies occupying the same
tile. You can't pan or rotate your camera, like in a 3D game, to get a better idea of what you're looking at, so overlapping elements on the screen are generally bad.

What does this mean? It adds some depth to the game if you're playing in a party or a raid. You need to think more about how you place yourself in relation to your comrades: tougher melee characters can shield the more fragile, or tanks can
use doorways as natural choke points.

## Which way are we looking, again?
Another simplification that goes hand-in-hand with the 2D grid is how players and monsters don't face in some specific direction. You can't walk around and attack someone from the back - you're always attacking from the front. Technically, I 
could have added support for this quite easily, but I felt the controls would lose some intuitiveness. Without character animations we'd need some kind of UI arrow to indicate what way someone is facing, which gets really hard to fit on the screen
in a nice way. Alas, no backstabbing.

## Anti-cheese
These collisions, however, also add a whole new dimension of cheesing. For the uninitiated, *cheesing* is a form of cheating, especially in dungeons or raids, where you defeat challenges in ways you weren't supposed to do. For example, maybe you
find out that if you fight the dragon in a specific spot, it won't be able to use some special attack, or whatever. With collisions, the potential for coming up with unintended strategies becomes much higher. In the simplest form, it would be
way too easy to just place the dragon in such a way that it can't move, neutralizing it. 

So, expect most big monsters and bosses to have ways to get around your roadblocks, usually tied to special abilities.

## Griefers and AFK'ers
![Not moving.](/blog/images/pass_1.gif)

Unfortunately, we're also giving a new tool to griefers, the players who get joy out annoying others as much as possible. One of these fine specimens could potentially just hang out in a doorway, preventing anyone from coming through - or even more 
maliciously, a bunch of griefers could single someone out and harass them by preventing that person from going anywhere. It could also be that someone just parked their character in an unfortunate spot while away from their computer.

![I see, so be it.](/blog/images/pass_2.gif)

You usually have the option of starting a fight, but you also have a more peaceful possibility.

![Get out of my way.](/blog/images/pass_3.gif)

All classes have the *Push* ability, which will gently move another player, a enemy, or an NPC out of the way, without engaging in combat. It's also useful in raids and dungeons if you really need to reposition yourself urgently and one of your 
friends is blocking your way.

Any good griefer will obviously look at pushing as another tool in the griefing toolbox, but it's going to be quite hard to use it reliably for that purpose: pushing always happens in a random direction. In other words, you can't push someone
across the world.

Stay tuned for the next update on the development of Trolddom, which will happen at, hmm, some point.

If you're so inclined, don't forget to check out [trolddom-public](https://github.com/demogorgon1/trolddom-public) on github.

