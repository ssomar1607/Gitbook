# Player & Target Commands

{% hint style="warning" %}
You need to know that by default all commands are run by the console, so if you want that the player run the command add [**SUDO**](player-and-target-commands.md#sudo) or [**SUDOOP**](player-and-target-commands.md#sudoop) before.&#x20;

_(Click on SUDO or SUDOOP for more infos)_

\
**Don't use this option for vanilla commands and CUSTOM COMMANDS, to use vanilla commands properly go to FAQ and "How to use vanilla commands",**
{% endhint %}

{% hint style="success" %}
"Multi-world" compatibility for the vanilla commands.

`execute in <<NAME`_`OF`_`YOUR_WORLD>> run ...`

Example, you want summon a Zombie in the world SsomarWorld:

`execute in <<SsomarWorld>> run summon zombie 100 50 100`

Example with a placeholder`:`

`execute in <<%player_world%>> run summon zombie 100 50 100`
{% endhint %}

{% hint style="info" %}
You want keep the brut HEX form in your command ? add the tag **BRUT\_HEX** in your command. It works anywhere in the command line but it's recommended to put it in the first part of the cmd to make it less confusing
{% endhint %}

{% hint style="info" %}
By default all commands aren't executed if the player is offline. (the commands will be executed at the connection of the player)

But you can add the tag **\[\<OFFLINE>]** in your commands to remove this restriction.

_(Very useful for broadcast, boost, giveall commands, ...)_

Example:

* \[\<OFFLINE>] broadcast hello !
* \[\<OFFLINE>] execute at %player% run setblock %block\_x\_int%+3 %block\_y\_int%-1 %block\_z\_int%-14 minecraft:air


{% endhint %}

{% hint style="info" %}
You can use \[\<CLEAR\_IF\_DISCONNECT>] if you want to clear commands if the player disconnects

Example:

* \[\<CLEAR\_IF\_DISCONNECT>] say meow
{% endhint %}

## Mixed Commands

In addition of the following list of commands you can also use:

{% content-ref url="mixed-commands-player-and-entity.md" %}
[mixed-commands-player-and-entity.md](mixed-commands-player-and-entity.md)
{% endcontent-ref %}

These commands can be used in the Player related commands OR Entity related commands.

## Custom commands

_Sorted by alphabetical order_

### +++ (Command Connector)

* Info: Allows you to add more commands in one command line. Should be used only when you use the custom command `RANDOM RUN` .
* Example:

```
- give %player% diamond 1 +++ SENDMESSAGE &eYou got 1 diamond!
```

```
- 'RANDOM RUN: 1'
- SENDMESSAGE &4You got nothing...
- SENDMESSAGE &eYou got dirt! +++ give %player% dirt 1
- SENDMESSAGE &bYou got diamond! +++ give %player% diamond 1
- RANDOM END
```

### <+> (Around Command Connector)

* Info: Allows you to add more commands in one command line. Will only work well with `AROUND` and `MOB_AROUND` but also with `ALL_PLAYERS` _,_ `ALL_MOB`, `NEAREST` and `MOB_NEAREST`.
* Example:&#x20;

```
- AROUND 10 false execute at %around_target% run summon lightning_bolt ~ ~ ~ <+> SENDMESSAGE &You got smited!
```

```
- MOB_AROUND 7 true STUN_ENABLE <+> DELAY 5 <+> STUN_DISABLE
```

### <+::step1> (Around Command Connector when many AROUND, MOB\_AROUND, NEAREST, MOB\_NEAREST, ALL\_PLAYERS, ALL\_MOBS AND IF are nested)

```
- AROUND 5 false say &a(0)&e%around_target% <+> DELAY 3 <+> AROUND 5 false say &a(1)&e%around_target::step1% <+::step1> DELAY 3 <+::step1> AROUND 5 false say &a(2)&e%around_target::step2%
```

```
- AROUND 5 false say &a(0)&e%around_target% <+> DELAY 3 <+> NEAREST 10 say &a(1)&e%around_target::step1%
```

```
- AROUND 5 false say &a(0)&e%around_target% <+> DELAY 3 <+> AROUND 5 false say &a(1)&e%around_target::step1% and x &c%around_target_x::step1% <+::step1> IF %around_target_x::step1%>10 say &aThe target &e%around_target_x::step2% <+::step2> effect give %around_target::step2% slowness 20
```

### ABSORPTION

* Info: Gives absorption effect to the player
* Command:
  * ABSORPTION {amount} \[time in ticks]
    * {amount}: amount of absorption half hearts. Supports negative values to remove.
    * \[time in ticks]: time of the effect. Set it empty or "0" if want to be infinite.
* Example:

```
- ABSORPTION 5 20
```



### ACTIONBAR

* Info: Display the action bar with your text + the time remaining (59, 58, 57...).
* Command:&#x20;
  * `ACTIONBAR {Your text} {delay}`
*   Example:

    ```
    - `ACTIONBAR &6Hey &e%player% ! 10`
    ```



### ADDENCHANTMENT

* Info: It adds an enchantment on an item on a specific slot with certain level
* Command: ADDENCHANTMENT {slot} {enchantment} {level}
  * {slot}: The slot where it will be applied. -1 for mainhand
  * {enchantment}: The enchantment that you want to be applied, don't use spaces, use the minecraft enchantments not the display ones.
  * {level}: The level for the enchantment
* Example:

```
- ADDENCHANTMENT -1 unbreaking 3
```



### ADDITEMATTRIBUTE

* Info: It adds an attribute to an item as sum or rest operation.
* Command: ADDITEMATTRIBUTE {slot} {Attribute} {value} {equipment slot}
  * {slot}: The slot where it will be applied. -1 for mainhand
  * {attribute}: The attribute you want to add
  * {value}: The value for the operation
  * {equipment slot}: The slot for the attribute
* Example:

```
- ADDITEMATTRIBUTE %slot% GENERIC_ATTACK_DAMAGE 1 HAND
```

{% hint style="info" %}
You can find the attributes here [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html)

And the slots here

[https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/EquipmentSlot.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/EquipmentSlot.html)
{% endhint %}



### AROUND

* Info: Targets players in a specific radius and makes them run commands
* Command:&#x20;
  * `AROUND {distance} {msgPlayerAffected true/false} {command}`
    * {distance}: To how far in radius the command will select players
    * {msgPlayerAffected true/false}: To notify the affected players that they are tagged by the command and to notify the user of the item if it managed to target players or not
    * {command}: The command that the targeted players will execute
* Example:

This summons lightning at players in a 20 block radius

```
- AROUND 20 false execute at %around_target% run summon lightning_bolt
```

This gives players slowness in a 10 block radius

```
- AROUND 10 false effect give %around_target% slowness 50 5
```

Damages nearby players by 20 player damage in a 7 block radius

```
- AROUND 7 false DAMAGE 20
```

Many around in the same command

```
- AROUND 5 false say &a(0)&e%around_target% <+> DELAY 3 <+> AROUND 5 false say &a(1)&e%around_target::step1% <+::step1> DELAY 3 <+::step1> AROUND 5 false say &a(2)&e%around_target::step2%
```

```
- AROUND 5 false say &a(0)&e%around_target% <+> DELAY 3 <+> NEAREST 10 say &a(1)&e%around_target::step1%
```

```
- AROUND 5 false say &a(0)&e%around_target% <+> DELAY 3 <+> AROUND 5 false say &a(1)&e%around_target::step1% and x &c%around_target_x::step1% <+::step1> IF %around_target_x::step1%>10 say &aThe target &e%around_target_x::step2% <+::step2> effect give %around_target::step2% slowness 20
```

```
- AROUND 10 false CONDITIONS(%::parseother_{% raw %}
{%player%}
{% endraw %}_{betterteams_name}::%!=%::betterteams_name::%) effect give %around_target% weakness 10 10 true
```

#### You can add conditions to AROUND command

* The condition looks like AROUND \<distance> \<msg> CONDITIONS(\<conditions>) \<command>
* Conditions works with placeholders but need to be %::\_::% instead of %\_%
  * For example %::player\_health::%
* To add MORE than 1 condition use "&&" between the conditions
* Example:

```
- AROUND 10 false CONDITIONS(%::player_health::%>10&&%::player_name::%=2Ssomar) SENDMESSAGE &eclick
```

(Mainly in blockCommands/entityCommands) where you want the owner of the block/projectile won't harm the user of the item (Requires PlaceholderAPI's Player Expansion)

```
- AROUND 2 CONDITIONS(%::player_name::%!=%player%) DAMAGE 15
```

{% hint style="info" %}
Keep in mind that the CONDITIONS() part parses the placeholders in it with the player selected by the AROUND command. So what actually happened in the placeholders above is that it checks if the target's health is greater than 10 and if that player who got selected by the AROUND command is named "2Ssomar"
{% endhint %}

{% hint style="info" %}
Placeholders that came from plugins like ExecutableItems, ExecutableBlocks will be parsed not by the player affected by the AROUND command.

For example, with ExecutableBlocks, CONDITIONS(%var\_faction%=%::factionsuuid\_faction\_name::%) works through checking if the block's factions variable value is equal to the targetted player's faction\
Placeholder Source: ([https://factions.support/placeholderapi/](https://factions.support/placeholderapi/))
{% endhint %}

### ADDLORE

* Info: Adds a line of lore
* Command: ADDLORE {slot of the player} {text dont need brackets}
* Example:

```
- ADDLORE %slot% &7Item of %player%
```



### AWARENESS

* Info: Sets to true or false the awareness of a mob.
* Command: AWARENESS {DEFAULT TRUE}
* Example:

```
- AWARENESS true
```

{% hint style="info" %}
it only works for 1.16.5+
{% endhint %}



### BOOTS

* Info: Puts the item in your main hand to your boots slot. (Will not work if the item has "Curse of Binding")
* Command: BOOTS
* Example:

```
- BOOTS
```



### BOSSBAR

* Info: Creates a bossbar text for a certain duration time.
* Command: {duration} {color} {text}
  * {duration}: duration of the bossbar text
  * {color}: Color of bossbar text
  * {text}: text on the bossbar
* Example:

```
- BOSSBAR 20 RED This is a bossbar text
```



### CANCELPICKUP

* Info: Disables pickup on a player for a set amount of time
* Command: CANCELPICKUP {time\_in\_ticks} \[material]
  * {time\_in\_ticks}: The duration of how long till the player can pickup items again
* Example:

```yaml
- CANCELPICKUP 600
#You can also specify a material
- CANCELPICKUP 600 stone
```

{% hint style="info" %}
The only wait to RESET this command after setting a time in ticks is reloading or restarting the server. If would like a way to reset this suggest it in #suggestion-bugs channel on Discord.
{% endhint %}



### CHAT

* Info: Send a message from the player to the chat
* Command: CHAT {text}
  * {text}: Text to send
* Example:

```
- CHAT Hello !!
```



### CHESTPLATE

* Info: Puts the item in your main hand to your chestplate slot. (Will not work if the item has "Curse of Binding")
* Command: CHESTPLATE
* Example:

```
- CHESTPLATE
```



### CLOSE\_INVENTORY

* Info: It closes the inventory to the player
* Command: CLOSE\_INVENTORY
* Example:

```yaml
- CLOSE_INVENTORY
```



### CROPS\_GROWTH\_BOOST

* Info: It boost the growth of the crops around you
* Command: CROPS\_CROPS\_GROWTH {radius} {delay between two growths in ticks} {total duration in ticks} {chance 0-100}
* Example:

```yaml
- CROPS_GROWTH_BOOST 5 10 100 50
```



### DISABLE\_FLY\_ACTIVATION

* Info: Deny the usage of the fly for a player (Gliding in Elytra is not considered as flying)
* Command: DISABLE\_FLY\_ACTIVATION {timeinsecs}
  * {timeinsecs}: The duration of the effect
* Example: (The command below disable the activation of the fly during 1 minute)

```
- DISABLE_FLY_ACTIVATION 60
```

###

### DISABLE\_GLIDE\_ACTIVATION

* Info: Deny the use of elytra for a period of time
* Command: DISABLE\_GLIDE\_ACTIVATION {timeinsecs}
* Example: (the command below disable the use of elytra for 20 secs)

```
- DISABLE_GLIDE_ACTIVATION 20
```

###

### DROPSPECIFICEI

* Info: It drops all the EI in your inventory with the id specified
* Command: DROPSPECIFICEI {id}
* Example:&#x20;

```
- DROPSPECIFICEI excalibursword
```



### EICOOLDOWN

* Info: It applys a cooldown to a specific ExecutableItems
* Command: EICOOLDOWN {PLAYER} {ID} {SECONDS} {boolean TICKS} \[optional activator id]
  * {PLAYER}: The player to target the command
  * {ID}: The id of the ExecutableItem
  * {Seconds}: The amount of time
  * {boolean TICKS}: If you want the time to be in ticks
  * \[optional activator id]: You can apply it to a specific activator id
* Example:&#x20;

```
- EICOOLDOWN %player% thisismyid 10 true
```



### EECOOLDOWN

* Info: It applys a cooldown to a specific ExecutableItems
* Command: EECOOLDOWN {PLAYER} {ID} {SECONDS} {boolean TICKS} {optional activator}
  * {PLAYER}: The player to target the command
  * {ID}: The id of the ExecutableItem
  * {Seconds}: The amount of time
  * {boolean TICKS}: If you want the time to be in ticks
  * \[optional activator id]: You can apply it to a specific activator id
* Example:&#x20;

```
- EECOOLDOWN %player% thisismyid 10 true
```



### FORMAT\_ENCHANTMENTS

* Info: It formats all enchantments in your lore
* Command: FORMAT\_ENCHANTMENTS {slot}
* Example:

```
- FORMAT_ENCHANTMENTS %slot%
```

![](<../../.gitbook/assets/image (393).png>) -> ![](<../../.gitbook/assets/image (382).png>)



### FLY

*   FLY ON

    * Info: Gives the player creative flight
    * Command: FLY ON
    * Example:

    ```
    - FLY ON
    ```
*   FLY OFF

    * Info: Disables creative flight on the player and if the player's flight get's disabled midair, the player will be teleported on the possible block under the player.
    * Command: FLY OFF {teleportOnTheGround true or false}
    * {teleportOnTheGround true or false}: Whether the player would get teleported to the ground or not
    * Example:

    ```
    - FLY OFF true
    ```



### GRAVITY ENABLE/DISABLE

* Info: It stops the gravity for the player, stopping the player to "fall" down or going up.
* Command:&#x20;
  * GRAVITY\_ENABLE
  * GRAVITY\_DISABLE
* Example:

```
- GRAVITY_DISABLE
- DELAY 5
- GRAVITY_ENABLE
```

### HEAD

* Info: Puts the item in your main hand to your head slot. (Will not work if the item has "Curse of Binding")
* Command: HEAD
* Example:

```
- HEAD
```



### LAUNCH

* Info: Launches a custom projectile. [Reference](https://github.com/ssomar1607/ExecutableItems/wiki/%E2%9E%A4-Custom-Projectiles#type)
* List:&#x20;

<details>

<summary>Projectile Types</summary>

* ARROW
* DRAGONFIREBALL
* EGG
* ENDERPEARL
* FIREBALL
* LARGEFIREBALL
* LINGENRINGPOTION
* LLAMASPIT
* SHULKERBULLET
* SIZEDFIREBALL
* SNOWBALL
* TRIDENT
* WITHERSKULL

</details>

* Command: LAUNCH {projectile} \[angle rotation y] \[angle rotation z]
  * {projectile}: the type of the projectile
  * \[angle rotation y]: (only for 1.14 and +) (not necessary) (default = 0) (in degrees) Define the direction where the entity will be launched
  * \[angle rotation z]: (only for 1.14 and +) (not necessary) (default = 0) (in degrees) Define the direction where the entity will be launched
* Example:

```
- LAUNCH DRAGONFIREBALL
```

* Example multiple shoots:

```
- LAUNCH WITHERSKULL
- LAUNCH WITHERSKULL 20
- LAUNCH WITHERSKULL -20
```

{% hint style="info" %}
If you use the LAUNCH COMMAND in the activator PLAYER\_LAUNCH\_PROJECTILE, and the projectile has been launched by a bow, the projectile launch with the custom LAUNCH command will keep the same velocity.
{% endhint %}



### LEGGINGS

* Info: Puts the item in your main hand to your leggings slot. (Will not work if the item has "Curse of Binding")
* Command: LEGGINGS
* Example:

```
- LEGGINGS
```



### LOCATED\_LAUNCH

* Info: Launches a projectile at a specific location
* Command: LOCATED\_LAUNCH {projectileType} {frontValue positive=front , negative=back} {rightValue right=positive, negative=left} {yValue} {velocity} \[vertical rotation] \[horizontal rotation]
  * {projectileType}: The id of the projectile that you want to launch
  * {frontValue positive=front , negative=back}: Front/Back Position. For example, if you want to spawn the projectile 5 blocks far from where you're facing, use a higher positive value
  * {rightValue right=positive, negative=left}: Right/Left Position. For example, if you want the projectile to spawn to your left, use a higher negative value
  * {yValue}: To how high up from your Y position will the projectile will spawn.
  * {velocity}: To how fast will the projectile fly. Set the value to 0 for the projectile to fall downwards upon spawning the projectile.
  * \[vertical rotation]  (Optional) you can add a vetical rotation for your projectile (in degrees)
  * \[horizontal rotation]  (Optional) you can add a horizontal rotation for your projectile (in degrees)
* Example:

```
- LOCATED_LAUNCH ARROW 3 0 4 2 45 45
```

### MINECART\_BOOST

* Info: It boost you when riding a minecart (Effect close to when you go up of a powered rail)
* Command: MINECART\_BOOST {number boost}
* Example:

```
MINECART_BOOST 10
```



### MOB\_AROUND

* Info: Targets entities in a specific radius and makes them run commands
* Command: MOB\_AROUND {distance} {mute or not} (command)
  * {distance}: To how far in radius the command will select entities
  * {mute or not}: (true or false) To notify the user of the item if it didn't manage to target any mobs.
    * **Set to true to hide the message**
  * You can BLACKLIST or WHITELIST entities adding one of these ones in anyplace of the command:
    * BLACKLIST(ZOMBIE,ARMOR\_STAND)
    * WHITELIST(CHICKEN)
* Example:

```
- MOB_AROUND 3 false BURN 10
- MOB_AROUND 5 execute at %around_target_uuid% run summon lightning_bolt
- MOB_AROUND 5 BLACKLIST(ZOMBIE,ARMOR_STAND) DAMAGE 20
- MOB_AROUND 5 true effect give %around_target_uuid% poison 10 10
- MOB_AROUND 10 WHITELIST(ZOMBIE{CustomName:"*"}) say HELLO
```

To use entity nbt on the WHITELIST/BLACKLIST field, you need to install NBT API plugin

{% embed url="https://www.spigotmc.org/resources/nbt-api.7939/" %}

It supports NBT Tags so you can add for example something like: `ZOMBIE{IsBaby:1}`

{% embed url="https://minecraft.fandom.com/wiki/Tutorials/Command_NBT_tags#Entities" %}

```
- MOB_AROUND 7 BLACKLIST(ZOMBIE{CustomName:"Test Test"},ZOMBIE{CustomName:"Miyamoto"}) false BURN 3
- MOB_AROUND 5 WHITELIST(ZOMBIE{IsBaby:1}) DAMAGE 20
- MOB_aROUND 9 WHITELIST(WOLF{Owner:"%player%"}) HEAL 5
- MOB_aROUND 9 WHITELIST(WOLF{Owner:%player_uuid%}) HEAL 5
```

### MODIFYDURABILITY

* Modifies the durability of a specific item in a specific slot
* Command: MODIFYDURABILITY {number} {slot} {supportUnbreaking true or false}
  * {number}: Positive value to increase the durability. Negative value to decrease the durability
  * {slot}: The slot number of the item (-1 for the held slot)
  * {supportUnbreaking true or false}: If it supports the unbreaking enchantment or not
* Example:

```
- MODIFYDURABILITY -1 %slot% true
```

### MIX\_HOTBAR

* Info: it mixes the hotbar of the player
* Command: MIX\_HOTBAR
* Example:

```
- MIX_HOTBAR
```

###

### MOB\_NEAREST

* Info: Targets the nearest mob from the player/target.
* Command:&#x20;
  * `MOB_NEAREST` {max accepted distance} `{command}`
    * {max accepted distance}:  Max distance accepted that the "entity" can be.
    * {command}: The command that will be executed
* Example:

Damages nearest player

```
- MOB_NEAREST 10 DAMAGE 5
```



### NEAREST

* Info: Targets the nearest player from the player/target.
* Command:&#x20;
  * `NEAREST` {max accepted distance} `{command}`
    * {max accepted distance}: Max distance accepted that the "target" can be.
    * {command}: The command that will be executed
* Example:

Damages nearest player

```
- NEAREST 8 DAMAGE 5
```

### OPEN\_WORKBENCH

* Info: It opens a workbench for the player that runs the activator
* Command: OPEN\_WORKBENCH
* Example:

```yaml
- OPEN_WORKBENCH
```

### OPEN\_ENDERCHEST

* Info: It opens the ender chest for the player that runs the activator
* Command: OPEN\_ENDERCHEST
* Example:

```yaml
- OPEN_ENDERCHEST
```



### OPENCHEST

* Info: It opens a chest in the selected location
* Command: OPENCHEST {world} {x} {y} {z}
* Example:

```
- OPENCHEST VanillaWorld 100 100 100
```



### OXYGEN

* Info: It gives oxygen to the target
* Command: OXYGEN {timeinticks}
* Example:

```
- OXYGEN 100
```



### PARTICLE

* Info: Spawns particles in the player/target's location

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Particle.html" %}

* Command: PARTICLE {type} {quantity} {offset} {speed}
  * {type}: The type of particle (ALL CAPS)
  * {quantity}: The amount of particles that will spawn
  * {offset}: The radius of the area where the particles may spawn in the player/target's location
  * {speed}: To how fast or how big particles will be
* Example:

```
- PARTICLE FIREWORKS_SPARK 10 0.1 0.5
```



### PROJECTILE\_CUSTOMDASH1

* Info: Similar to CUSTOMDASH1 but the xyz will be replaced with the xyz coords of the nearest projectile from you.
* Command: PROJECTILE\_CUSTOMDASH1 {fallDamage}
  * {fallDamage}: Whether you will get fall damage or not (If you forgot to set whether it's true or false, the default will be false. To get fall damage, set this to true)
* Example:

```
- PROJECTILE_CUSTOMDASH1 false
```



### REGAIN FOOD

* Info: Gives you a specific amount of food/saturation
* Command: REGAIN FOOD {amount}
  * {amount}: The amount of saturation points you want to gain. Use negative values to reduce hunger points
* Example:

```
- REGAIN FOOD 5
```



### REGAIN MAGIC

* Info: Gives the player specific values of a specific magic&#x20;
* Command: REGAIN MAGIC {ecoskills magic ID} {amount}
  * {ecoskills magic ID}: The ID of the Ecoskills's magic.
  * {amount}: The amount to get.
* Example:

```
- REGAIN MAGIC mana 15
```

{% hint style="info" %}
It supports negative values.
{% endhint %}



### REGAIN SATURATION

* Info: Gives you a specific amount of saturation
* Command: REGAIN SATURATION \<value>
* Example:

```
- REGAIN SATURATION 10
```



### REMOVEENCHANTMENT

* Info: Remove an enchantment from a slot
* Command: REMOVEENCHANTMENT {slot} {enchantment}
  * {slot}: Slot to remove the enchantment from
  * {enchantment}: Enchantment to remove (ALL for every enchantment)
* Example:

```
- REMOVEENCHANTMENT -1 ALL
```

###

### REPLACEBLOCK

* Info: Replaces the block the player is looking at into a different one
* Command: REPLACEBLOCK {material}
  * {material}: Block ID (Block states are supported) _(ALL CAPS)_
* Example:

```
- REPLACEBLOCK STONE_BRICKS
- REPLACEBLOCK WATER[LEVEL=0]
```



### SENDBLANKMESSAGE

* Info: Sends you a blank message
* Command: SENDBLANKMESSAGE
* Example:

```
- SENDBLANKMESSAGE
```



### SENDMESSAGE

* Info: Sends you a message
* Command: SENDMESSAGE (message)
* Example:

```
- SENDMESSAGE &fThis is a somewhat random text.
```

{% hint style="info" %}
You can use minimessages color codes, like using gradient and stuff from this site: [https://docs.adventure.kyori.net/minimessage/format.html](https://docs.adventure.kyori.net/minimessage/format.html)\
\
You can only use one type of formatting at once in the same SENDMESSAGE command, either the classic color codes format or minimessage format.
{% endhint %}



### SETARMORTRIM

* Info: Set the specific armor trim with the specific pattern for the specified slot
* Command: SETARMORTRIM {slot} {PATTERN} {MATERIAL OF PATTERN}
  * {slot}: The slot to apply the command
  * {PATTERN}: The pattern of the trim
  * {MATERIAL OF PATTERN}: The material of the pattern
* Example:

```
- SETARMORTRIM 38 vex netherite
```



### SETBLOCK

* Info: **(FOR ACTIVATORS THAT INVOLVES TARGETTING BLOCKS) Adds blocks in the block's location. (Only replaces air)**
* Command: SETBLOCK {material}
  * {material}: Block ID (Block states are supported) _(ALL CAPS)_
* Example:

```
- SETBLOCK OAK_WOOD
- SETBLOCK FURNACE[LIT=TRUE]
```



### SETTEMPBLOCKPOS

* Command: SETTEMPBLOCKPOS {x} {y} {z} {material} {time} \[bypassProtection true or false] \[blocks list]
  * {material}: Block ID
  * {time}: Time in ticks
  * \[bypassProtection true or false]: Whether to ignore 3rd party intervention or not
  * \[blocks list]: List of blocks to watch out for
    * Examples:
    * AIR, WATER
    * !STONE, !COBBLESTONE

```
 - SETTEMPBLOCKPOS %entity_x% %entity_y% %entity_z% BEDROCK 40 true !AIR,!WATER
```

{% hint style="warning" %}
It doesn't replace blocks that have extra datas (inventory, rotation, etc)
{% endhint %}



### SETBLOCKPOS

* Info: Set a block in a specific position
* Command: SETBLOCKPOS {x} {y} {z} {material} \[bypassProtection true-false] \[replace true or false]
* Example:

```
- SETBLOCKPOS %entity_x% %entity_y% %entity_z% BEDROCK true
```



### SETEXECUTABLEBLOCK

* Info: Setblock but for Executable Blocks. **(EXECUTABLE BLOCKS MUST BE INSTALLED)**
* Command: SETEXECUTABLEBLOCK {id} {x} {y} {z} {world} {replace true or false} \[ownerUUID]
  * {id}: ID of the executable block you are trying to place down
  * {x}: X-Coordinate
  * {y}: Y-Coordinate
  * {z}: Z-Coordinate
  * {world}: Name of the world
  * {replace true or false}: true or false. Whether it will replace the existing block in the said coordinates or not
  * \[bypassProtection true or false]: (Optional) if you want bypass the protections like worldguard (default false)
  * \[ownerUUID]: (Optional) The uuid of the supposed owner of the executable block
* Example:

```
-  SETEXECUTABLEBLOCK Mithril_Ore %block_x_int% %block_y_int% %block_z_int% %block_world% false true %player_uuid%
```



### SETITEMNAME

* Info: Sets a custom name for your item in a specific slot
* Command: SETITEMNAME {slot} {text}
* Example:

```
- SETITEMNAME %slot% This is the new name of the item
```



### SETITEMCOLOR

* Info: Sets a specific color for the item (item colorables as leather armor)
* &#x20;Command: SETITEMCOLOR {slot} {color in number}
* Example:

```
- SETITEMCOLOR 1 0
```



{% hint style="info" %}
Use the website: [https://www.tydac.ch/color/](https://www.tydac.ch/color/) for the leather color
{% endhint %}

### SETITEMATTRIBUTE

* Info: It sets an attribute to an item.
* Command: SETITEMATTRIBUTE {slot} {Attribute} {value} {equipment slot}
  * {slot}: The slot where it will be applied. -1 for mainhand
  * {attribute}: The attribute you want to add
  * {value}: The value for the operation
  * {equipment slot}: The slot for the attribute
* Example:

```
- SETITEMATTRIBUTE %slot% GENERIC_ARMOR 10 CHEST
```

{% hint style="info" %}
You can find the attributes here [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html)
{% endhint %}



### SETITEMCUSTOMMODELDATA

* Info: Sets a specific custom model data to the specific item
* Command: SETITEMCUSTOMMODELDATA {slot} {customModelData}
* Example:

```
- SETITEMCUSTOMMODELDATA 10 10
```

{% hint style="info" %}
It supports -1 to mainhand
{% endhint %}



### SETMATERIALCOOLDOWN

* Gives the player/target cooldown on an item
* Command: SETMATERIALCOOLDOWN {material} {delay in secs}
  * {material}: The type of material
  * {delay in secs}: Cooldown
* Example:

```
- SETMATERIALCOOLDOWN ENDER_PEARL 10
```



### SETITEMMATERIAL&#x20;

{% hint style="info" %}
Only works at 1.20.5 and above
{% endhint %}

* Replaces the material of the item with a different material while keeping the nbt of the target item
* Commands: SETITEMMATERIAL {slot} {material}
  * {slot}: Slot number&#x20;
  * {material}: The material you want the item to become into
* Example:

```
SETITEMMATERIAL 10 DIAMOND_HOE
```

### SETLORE

* Info: Sets a line of lore
* Command: SETLORE {slot of the player} {line} {text}
  * {line} : If you want to set the lore of the first line, type 0
* Example:

```
- SETLORE %slot% 3 &6LEGENDARY SWORD
```



### SPAWNENTITYONCURSOR

{% embed url="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html" %}

* Info: Spawn entities on your cursor
* Command: SPAWNENTITYONCURSOR {entityType} {amount}
  * {entityType}: Mob ID (ALL CAPS)
  * {amount}: The amount of mobs that will spawn in that spot
* Example:

```
- SPAWNENTITYONCURSOR CREEPER 1
```



### SUDO

* Info: Forces you to run a command
* Command: SUDO (command)
* Example:

```
- SUDO sit
- SUDO say hi
```



### SUDOOP

* Info: Gives the player OP, SUDOs the player and DEOPs it
* Extra Info: During the OP, the player can only run the specified command after the SUDOOP, all other commands are blocked when the player is OP, and if the server crashes, no problem. The player will be DEOPed when the player reconnects.
* Command: SUDOOP (command)
* Example:

```
- SUDOOP summon zombie
- SUDOOP fly
- SUDOOP god
- SUDOOP /replacenear 20 tnt
```

{% hint style="danger" %}
It is not recommended to use this **a lot**. As it is explained on the top of this page, if want to run vanilla commands use the execute command (Explained on the FAQ "How to use vanilla commands").

If have another way to achieve what you want use it.

And if you have no other way but using SUDOOP, then use this command. This shouldn't be your first option.
{% endhint %}

### SWAPHAND

* Info: Swaps the current item with your offhand item
* Command: SWAPHAND
* Example:

```
- SWAPHAND
```



### TRANSFER\_ITEM

* Info: Swaps 2 items in the inventory by slot
* Command: TRANSFER\_ITEM {slot of launcher} {slot of receiver} \[boolean drop]
  * {slot of launcher}: Target slot for slot no.1
  * {slot of receiver}: Target slot for slot no.2
  * \[boolean drop]: (default = false) Whether {slot of launcher} gets dropped during the swap or not

### XPBOOST

* Info: Boost the xp gain for a time.
* Command: XPBOOST {multiplier} {timeinsecs}
* Example:

```yaml
- XPBOOST 2 10
```

{% hint style="info" %}
Be careful ! This command can get stacked, so if you run this command multiple times you will get more and more multipliers if the time between them is not enough for the last boost to disappear.\
\
XPBOOST 2 5\
DELAY 1\
XPBOOST 2 5\
\
This means the XP will be boosted in this order:\
1 second: x2\
4 seconds: x4 \
1 second: x2
{% endhint %}

### WHILE

* Info: It constantly executes the commands written as long as the condition matches
* Command: WHILE {condition\_without\_spaces} {delay\_in\_ticks} {command}
  * {condition\_without\_spaces}: The condition that need to match for the commands to run
    * Condition supports these symbols: != ; <= ; >= ; < ; > ; =
  * {delay\_in\_ticks}: The delay between each moment to run the commands
    * Condition support double placeholders, example %player\_x%>%player\_z%
  * {command}: The command that you want to run as long as the condition matches
* Example:

```
- WHILE %player_health%>10 20 SENDMESSAGE &eHello &6While
```

{% hint style="info" %}
It supports more than one command
{% endhint %}

```
WHILE %player_health%>10 20 SENDMESSAGE &eHello &6While <+> effect give %player% speed 1 1
```

{% hint style="info" %}
You can force to remove the WHILE command with "/score clear {player} WHILE"
{% endhint %}



## Mixed Commands

In addition of the following list of commands you can also use:

{% content-ref url="mixed-commands-player-and-entity.md" %}
[mixed-commands-player-and-entity.md](mixed-commands-player-and-entity.md)
{% endcontent-ref %}

These commands can be used in the Player related commands OR Entity related commands.
