# Command Block Language

## Gamepedia
Before we jump right into this, at the [minecraft gamepedia](https://minecraft.gamepedia.com/Command_Block) there is a site that would be wise to know.

## What Is A Command Block?
A command block is a block that you can insert a special code that mojang created. A command block can be powered by redstone, which can be useful in minigames or servers. Although a command block doesn't have a limit of characters, chat has a limit of 100 characters.

## The Different Types Of Command Blocks
There are 3 types of command blocks and each one has it's own property. Here they Are:
- Impulse command blocks are the default, and the only ones in 1.8. They simply execute the command once, and nothing else.
- Chain command blocks act as a chain. (Hence its name). The arrow points in the direction that the redstone source will    come out of, so make sure that's where you put your next command block. 
- Repeating command blocks repeat the command on always active, or a constant redstone signal if on needs redstone.

## DataTags
Some commands can inclued dataTags. DataTags are special NBT tags to add to some commands. A useful one about armor stands is at [digminecraft](https://www.digminecraft.com/data_tags/armor_stand.php). When you get there you can click on the tab the upper-left corner that says dataTags to cover the rest of dataTags.

## Summon
Summon summons an entity (an entity is anything that moves in the game, even an arrow or eye of ender). We type in /summon into the chat, and here's what we get:

```
/summon <EntityName> [X] [Y] [Z] [dataTag]
``` 
At [grahamedgecombe](https://minecraft-ids.grahamedgecombe.com/entities) there is a good set of entities.
For X Y Z lets use **relative coordinates**. **Relative coordinates** are coordinates, but what ever is executing the command thinks it is in the center of the world. The command block/player has to have tildes (~ ~ ~) for it to use **relative coordinates**. If you don't want to target the thing that the command is being executed in, you can type in the number of blocks in that direction after the tilde with no spaces.

## Title
Titles are giant words that pop up into a player's screen. we type in /title, and here's what we get:
```
/title <player> title:subtitle:actionbar:clear:reset:times...
```
We see the elipses (...), wich indicates there's more to it. Right now we want a title to all players, so here's what we type:
```
tile @a title
```
and heres what it gives us:

```
title <player> <raw json title>
```

Let's say we want to make it say in red "hello". We type:

```
 /title @a title ["",{"text":"Hello","color":"red"},""]
```

## scoreboard

Scoreboard is a good way to keep track of what's going on  in the game. We type in /scoreboard, and here's what we get:

```
/scoreboard <objectives:players:teams>...
```

We know by the elipses there's more; but let's focus the command. We want to add an objective, so let's type

```
/scoreboard objectives
```

and here's what we get:

```
/scoreboard objectives <list:add:remove:setdisplay>...
```

We want to add an objective, so we type in:

```
/scoreboard objectives add
```

, and here's what we get:

```
/scoreboard objectives add <name> <criteriaType> [displayName...]

```.
We want to keep track of our deaths, so we type:

```
/scoreboard obbjectives add deaths deathCount deaths
```.

Now, we need to set its display. We type:

```
/scoreboard objectives setdisplay

```

, and it gives us:

```
/scoreboard objectives setdisplay <slot> [objective]
```

There are many slots, but let's use sidebar. We type:

```
/scoreboard objectives setdisplay sidebar deaths
```

As far as we can see, nothing's there! That's because it has no players to list. You can do the same setdisplay, but with list and press tab; or you can do 

```
/scoreboard players
```

,but if you made it this far, the **syntax** should be easy enough to understand.

## Execute
You might somtimes want to only execute a command if the command block detects something, or you might want to have something have near to a player, regaurdless of their location. The anwser? Execute.

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/dragon6810/dragon6810.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
