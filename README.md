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
Summon summons an **entity**. (an **entity** is anything that moves in the game, even an arrow or eye of ender). We type in /summon into the chat, and here's what we get:

```
/summon <EntityName> [X] [Y] [Z] [dataTag]
```
At [grahamedgecombe](https://minecraft-ids.grahamedgecombe.com/entities) there is a good set of **entities**.
For X Y Z lets use **relative coordinates**. **Relative coordinates** are coordinates, but what ever is executing the command thinks it is in the center of the world. The command block/player has to have tildes (~ ~ ~) for it to use **relative coordinates**. If you don't want to target the thing that the command is being executed in, you can type in the number of blocks in that direction after the tilde with no spaces.

## Title
Titles are giant words that pop up into a player's screen. we type in /title, and here's what we get:

```
/title <player> title:subtitle:actionbar:clear:reset:times...
```

We see the elipses (...), wich indicates there's more to it. Right now we want a title to all players, so here's what we type:
```
title @a title
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

and here's what we get:

```
/scoreboard objectives add <name> <criteriaType> [displayName...]

```

We want to keep track of our deaths, so we type:

```
/scoreboard objectives add deaths deathCount deaths
```

Now, we need to set its display. We type:

```
/scoreboard objectives setdisplay
```

and it gives us:

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

But if you made it this far, the **syntax** should be easy enough to understand.

## Execute
You might sometimes want to only **execute** a command if the command block detects something, or you might want to have something have near to a player, regardless of their location. The answer? **Execute.** There are two versions of execute here they are:

```
/execute <entity> <x> <y> <z> <command> OR /execute <entity> <x> <y> <z> detect <x> <y> <z> <block> <datValue:-1:state:*> <command>
```

The first **execute** command can detect where an **entity** is, an execute the command based on that. The second **execute** command is like a detecter for blocks, and we'll cover those later.

## DataValues
If you want to get a color of glass, like red, you wouldn't type

```
/give @p  minecraft:red_glass
```

You'd use **dataValues**. **DataValues** specify details of a block. If you press f3+h you will get a bunch of **dataValues** when you select a block that has one.

## Give
Many of you are probobaly farmiliar with /give. We type it in, and get:

```
/give <player> <item> [amount] [data] [dataTag]
```
There's a good of item data tags at [HyPixel](https://hypixel.net/threads/guide-data-tags-in-commands.34772/).

## Tellraw
**Tellraw** is a command that might as well be right next door to title. **Tellraw** gives a special Json message to a player. As you might have noticed in title all Json messages in 1.12.2 are typed like this:

```
/<Json command> <player> ["",{"text":"<text>","<dataTag>":"<dataTagSetting>"},""]
```

For **tellraw** you can do many settings, like _clickEvent_, and _color_. DataTagSettings are sometimes true or false, or what color its in, or the click event etc. 

## Particle
You might want particles somewhere, but nothings creating them. Then, you can use particle. We type /particle, and get:

```
/particle <name> <x> <y> <z> <xd> <yd> <zd> <speed> [count] [mode] [player] [params]
```

There is a big list of particle names at the [minecraft wiki](https://minecraft.gamepedia.com/Particles). The <xd> <yd> <zd>
 are the **volumeDemensions** of the particles. It means that many blocks in that direction. The speed is how fast the particles move. The count is how many particles there are. The mode is more complicated, so you can learn about it in a different guide. The params are also cmplicated, so you can learn about it in a different guide.
 
## Advancement
You might make a map that has an item that you can get advancement when using/crafting. We type /advancement, and get:

```
/advancement <grant:revoke:test> <player>
```

We want to grant advancements to our selves, so we tpye: 

```
/advancement grant @p
```

and it gives us:

```
/advancement grant <player> <only:until:from:through:everything>
```

We want to grant everything to ourselves, so we type:

```
/advancement grant @p everything
```

and there we go! We were given every advancement in minecraft.

## Weather
You are probobaly all farmiliar with weather, but may not. We type n /weather, and get:

```
/weather <clear:rain:thunder> [duration in seconds]
```
It means by duration in seconds how long it will be like this, 99999 means forever.

## Time
Time is similar to weather, exept it toggles the time. We type /time, and get:

```
/time <add:query:set> <value>
```


The **syntax** should now be understandable.

## Gamerule
Gamerule toggles a gamerule. We type /gamerule, and get:

```
/gamerule <rule> [value]
```

Here are a few of the gamerules:
   
   gamerule | defenition
------------|------------------
keepInventory | toggles wether you keep your inventory when you die
doMobSpawning | toggles wether hostile or nutral mobs spawn
randomTickSpeed | how fast everything like grass growing happens
doMobLoot | toggles wether mobs drop their loot or not
commandBlockOutput | toggles wether or not command blocks say if they successfully executed their command
doLimitedCrafting | toggles wether or not players have limited crafting or not
doLimited crafting
