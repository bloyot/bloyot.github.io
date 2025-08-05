---
title: Devlog#1 Starting something new...
date: 2025-08-03 05:42:16 +0800
categories: [warbands-of-shadowmere]
tags: [gamedev, godot]     # TAG names should always be lowercase
---


### Introduction
I've been dabbling in game dev for a little while now, and though I've made a [few small games](https://bloyot.itch.io/) and cloned a few arcade classics (in the spirit of the [20 games challenge](https://20_games_challenge.gitlab.io/)) I've been wanting to try and build something a bit more ambitious. However, like most software engineers, my personal github is a graveyard of half finished prototypes and side projects that seemed interesting at first but never got off the ground. So with that in mind, I thought I would create a dev log for my next project with the hopes that it would keep me a little bit more on track, as well as providing a nice snapshot of the work over time. 

### The game
So what do I actually want to build? I've only got a very loose conception of a game right now, a lot of which could very well change as I start building, but I've got a couple core ideas I want to try and meld together.

First, I've been kicking around the idea of making a turn based tactics game inspiried by things like Into the Breac` and Tactical Breach Wizards. I particularly like the way these games present on a very small scale (single rooms that function almost like puzzles, that are visually detached from the world) but provide a ton of depth through choice. This style of game is also very appealing as mainly a programmer who is not much of an artist, as it requires much less art and animation than a 3d game or even a more complex 2D game like a platformer. plex Instead I can keep the art intentionally simple and lean much more heavily into the systems design and mechanics. 

Secondly, I've been playing a ton of Path of Exile lately, and while not at all mechanically or visually similar to a tactics game, the itemization and the way the procedural endgame and meta-progression works is something that would be particularly cool to try and bring to a tactics game. While I certainly don't expect to build out the entire 15 years of complex systems in PoE's endgame (nor do I think it would work with the structure of tactics game), I am inspired by one particular piece: the way you roll maps to generate the content that you want to play. The key idea here being that you have control over the maps you can run, rolling them to find affixes that are good for your build, juicing them to make them tougher but more rewarding, etc. 

Finally, I'd love to have some roguelike/progression based systems in place to give players goals and structure to work towards (yes I know, just like every game these days). Having a home base to come back to spend the loot and currency you get from completing encouters gives some nice overall structure and incentive to keep playing.

So what does this all shape into? The core game loop would look something like:
* Generate a dungeon: a set of turn based tactics encounters. Spend your currency and other resources to influence the dungeon, affecting things like the types of enemies found, the difficulty, the number of floors, the types of loot, etc
* Run the dungeon: complete all floors of the dungeon, with each floor being a mini turn based tactics map, culminating with a boss encounter. Collect your rewards (gear, currencies, etc)
* Spend your resources at your home base, to upgrade your characters, buy items, get access to new types of npcs who can provide you with various benefits etc. 

Obviously this is both a bit vague, and a bit ambitious, but it's at least something to start with. 

### Theme 
A collection of game mechanics is a well and good, but every game needs a theme. While I'm definitely not much of a writer or a world builder, I've got at least a few ideas to shape the world the game will take place in. The core of the game revolves around exploring dungeons so we need some narrative structure that incentives that. My initial thought is the game will take place in a loosely post apocaplytic fantasy where, where some catastrophe has decimated most of the land (original I know). This has left the world filled with ruins, containing both treasure and dangers. Roving warbands have sprung up, groups of heroes and mercenaries who survive by travelling the land and exploring these ruins. You will play as one such band, exploring these dungeons and plunder the ancient ruins, growing the strength and renown of your group in the process. 

Taking this concept of warbands, and after a few minutes of generating random names with a fantasy name generator, I've come up with "Warbands of Shadowmere" as a working title. 

### Where to start and where to go next
All I've done so far is bootstrapped the project, getting a basic tilemap and some characters in place. I'm using these wonderful 32x32 pixel assets [32 rogues](https://sethbb.itch.io/32rogues), which are inspired by old roguelike games and dungeon crawlers. I love this art style and it reminds a lot of the steam Dwarf Fortress art (which also has an amazing lo-fi aesthetic). The tileset and character sprites, combined with some simple pixel based vfx should be more than enough to build out a prototype with. 

And on the subject of prototypes, what is my initial goal? While it's fun to dream about the world, the procedural dungeon generation, character stats and warband progress and such, the first step is to prototype the actual tactics gameplay. I'm going to keep it very simple to start, but the goal is to have a simple, playable tactics map, with a handful of characters. No stats or actual combat system yet, just being able to move the characters around and maybe do an "attack" just logged to the console should be sufficient. Even this tiny slice is going to require:
* a tilemap and grid manager with pathing
* a unit entity (possibly with player and enemy sub classes)
* a player controller to collect input and track where on the grid the player is hovering and clicking
* a game manager to track the units and the game state 
* some kind of basic UI (or possibly a debug console) to allow issue move/attack commands

Plenty of work to do, so time to get started!