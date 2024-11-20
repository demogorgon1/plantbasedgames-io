+++
title = "The Road Ahead"
date = "2024-11-20"
author = "Rasmus"
cover = ""
description = ""
+++

Trolddom has now been in Early Access for a few weeks, Zuthyg the Golden killed 324 times, 9622 quests have been completed, and crab men have claimed 572 lives. This might be a good time to write a little about what's next for the game. It kinda hurts me to write this as it feels a bit like wasting time, that would be better used working on the game, so I'll try to keep this short and concise.

## Introducing Attack Power
If you've played the game for a while you've probably noticed that I haven't paid too much attention to balancing it. From the very beginning I kinda decided to not worry too much about balance and just let things unfold naturally and do some random left-handed tuning here and there. Unfortunately, it turns out that approach might not be enough. In short, the current state of things is that melee is extremely overpowered compared to spell casters, in terms of raw damage output. The strongest sorcerer and priest builds center on their respective melee talent trees and fighters reign supreme.

The primary reason for this situation is that a lot of melee abilities base their damage directly on the weapon you have equipped. Abilties like Envenom, Rend, Wizard Strike and Dragon Punch scale directly with the damage of your weapon. A while ago I introduced scaling based on *normalized weapon damage* (damage per second rather than top-end damage), which helped a bit by making slow two-handed weapons less powerful, but weapon damage is still way overpowered.

So, yet again, I'll reduce myself to copy the homework of World of Warcraft. *Attack Power* is an intermediate stat between your primary offensive stats and the damage added to your weapon. Currently Strength translates directly to more weapon damage, but this role will be taken over by Attack Power. So how do you get Attack Power? It depends on your class:

* Fighters and paladins gain +2 Attack Power for each point of Strength.
* Priests, sorcerers, and witches gain +1 Attack Power for each point of Strength and +1 Attack Power for each point of Dexterity.

You always get +1 weapon damage per second from 10 points of Attack Power. 

In the future you'll find some items that grant Attack Power directly and you'll find that some buffs and talents will be changed to work with Attack Power instead of Strength.

## Huh, isn't this just the same?
Well, yes, a fighter will still get the same amount of weapon damage from one point of Strength as he did before, but now we've got a new stat to play around with. Most melee abilities will no longer be based on weapon damage, but instead on Attack Power. Some abilities like Mortal Strike will still be based on weapon damage because big crits are fun, but Rend, Envenon and others will be based solely on Attack Power.

## Next Patch
These changes will be rolled out in the next patch, together with a few other updates, including the long awaited option to increase the capacity of your stash. 

![More bananas!](/blog/images/more_bananas.png)

Now you'll finally have a place to put all your bananas or whatever it is you guys are hoarding. Other quality-of-life improvements include shortcuts to loot everything with a single click or key press.

## So when are we getting more levels?
The main issue with Trolddom at the moment is obviously a lack of stuff to do. A lot of players have already collected most of the best loot in the game, completed every quest, leveled multiple characters, and hunted down all the achievement points. It's very understandable that many of you have kinda stopped logging into the game and are just waiting for the level cap to be increased. Good news is that I've started working on the new content. The bad news is that I have no idea how long it's going to take. I've decided to increase the graphical fidelity of the game ever so slightly with a bit more animations and terrain variations to make the world a bit more interesting, so the entire process is going to be a bit more time consuming (not much though, the vast amount of work is related to coding stuff).

Nothing is set in stone, but this is roughly how it's going to look:

* You'll be able to take the boat to the mainland, arriving in the main city of *Valoris*, the seat of the King. Here you'll find that parts of the city have been taken over by rebels and you will assist in quelling the uprising. This will include instanced group content (i.e. the next dungeon). Roads from the city will lead you to different leveling zones.
* The mainland will not be an island, but an area that will be expanded as more stuff is added.
* If you're in good standing with The Light or The Underworld, you're already able to take a portal to *The Shrouded Lands*. Unfortunately you'll quickly be stopped by a closed gate that won't be opened before the level cap is increased. This area is a place where The Light and The Underworld fights an eternal battle against each other. 

![The Shrouded Lands.](/blog/images/shroud.gif)

*The Shrouded Lands* and the mainland will offer somewhat parallel leveling experiences so the whole thing will be a bit less linear. There is a catch though. 

## Oh no, not that!
Part of *The Shrouded Lands* will be a designated player-versus-player zone. Players aligned with The Light and those aligned with The Underworld will be hostile to each other. There will be normal quests mixed with various PvP objectives. Players who don't want to risk getting ganked can avoid it by steering around those areas. There will be daily quests revolving around your chosen pantheon and most activities in the zone will allow you to gain tokens that can be traded for various items or consumables.

I know that world PvP can be a bit divisive, but as I said, it's not going to be a mandatory activity. There will be plenty of other stuff to do, for example farming gold to buy one of these bad boys:

![Giddy up!](/blog/images/giddyup.png)

Mounted up in glorious 16x16 pixels.

Anyway, back to coding. If you have any questions, comments, or feedback, please don't hesitate reaching out on discord!



