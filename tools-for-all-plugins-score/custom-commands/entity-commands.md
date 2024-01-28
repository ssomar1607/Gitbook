# Entity Commands

{% hint style="success" %}
"Multi-world" compatibility for the vanilla commands.

`execute in <<NAME`_`OF`_`YOUR_WORLD>> run ...`

Example, you want summon a Zombie in the world SsomarWorld:

`execute in <<SsomarWorld>> run summon zombie 100 50 100`

Example with a placeholder`:`

`execute in <<%entity_world%>> run summon zombie 100 50 100`
{% endhint %}

{% hint style="info" %}
Entity commands now supports NPCs from Citizens
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

* Info: Allows you to add more commands in one command line. Will not work well with `AROUND` and `MOB_AROUND`.
* Example:

```
- give %player% diamond 1 +++ SENDMESSAGE &eYou got 1 diamond!
```

```
- 'RANDOM RUN: 1'
- SENDMESSAGE &4You got nothing...
- SENDMESSAGE &eYou got dirt! +++ give %player% dirt 1
- SENDMESSAGE &bYou got diamond! +++ give %player% diamond 1
```



### AROUND

* Info: Targets players in a specific radius and makes them run commands
* Command:&#x20;
  * `AROUND {distance} {command}`
    * {distance}: To how far in radius the command will select players
    * {command}: The command that the targeted players will execute
* Example:

This summons lightning at players in a 20 block radius

```
- AROUND 20 execute at %around_target% run summon lightning_bolt
```

This gives players slowness in a 10 block radius

```
- AROUND 10 effect give %around_target% slowness 50 5
```

Damages nearby players by 20 player damage in a 7 block radius

```
- AROUND 7 DAMAGE 20
```

#### You can add conditions to AROUND command

* The condition looks like AROUND \<distance> CONDITIONS(\<conditions>) \<command>
* Conditions works with placeholders but need to be %::\_::% instead of %\_%
  * For example %::player\_health::%
* To add MORE than 1 condition use "&&" between the conditions
* Example:

```
- AROUND 10 false CONDITIONS(%::player_health::%>10&%::player_name::%=2Ssomar) SENDMESSAGE &eclick
```

{% hint style="info" %}
Keep in mind that the CONDITIONS() part parses the placeholders in it with the player selected by the AROUND command. So what actually happened in the placeholders above is that it checks if the target's health is greater than 10 and if that player who got selected by the AROUND command is named "2Ssomar"
{% endhint %}



### ANGRYAT

* Info: Sets the entity target to a specific UUID
* Command: ANGRYAT {UUID}
  * {UUID}: UUID of the entity
* Example:

```
- ANGRYAT %player_uuid%
```



### CHANGETO

* Info: Replaces the mob with a different typ_e_

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html" %}

* Command: CHANGETO {entityType}
  * {entityType}: Type of entity.
* Example:

```
- CHANGETO CHICKEN
```

### CHANGETOMYTHICMOB

* Info: Change the mob to a MythicMob mob.
* Command: CHANGETOMYTHICMOB \<id>
* Example:

```
- CHANGETOMYTHICMOB SkeletonHelper
```



### DROPEXECUTABLEITEM

* Info: Drops an Executable Item in the entity's location
* Command: DROPEXECUTABLEITEM {id} {quantity}
  * {id}: Item id of the ExecutableItem
  * {quantity}: The amount of the executable item that will drop
* Example:

```
- DROPEXECUTABLEITEM ElytraTrail 1
```



### DROPEXECUTABLEBLOCK

* Info: Drops an Executable Block in the entity's location
* Command: DROPEXECUTABLEBLOCK {id} {quantity}
  * {id}: Item id of the ExecutableBlock
  * {quantity}: The amount of the executable block that will drop
* Example:

```
- DROPEXECUTABLEBLOCK House 1
```

### DROPITEM

* Info: Drops an item in the entity's location
* Command: DROPITEM {material} {quantity}
  * {material}: The item type. [Reference](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html) **(MUST BE AT ALL CAPS)**
  * {quantity}: The amount of the item that will drop
* Example:

```
- DROPITEM DIAMOND 1
```



### HEAL

* Info: Heals the entity with a specific amount
* Command: HEAL {amount}
  * {amount}: Per half hearts
* Example:

```
- HEAL 13
```



### KILL

* Info: Kills the mob without the death animation
* Command: KILL
* Example:

```
- KILL
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
- MOB_AROUND 5 BLACKLIST(ZOMBIE,ARMORSTAND) DAMAGE 20
- MOB_AROUND 5 true effect give %around_target_uuid% poison 10 10
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



### PARTICLE

* Info: Spawns particles in the player/target's location

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Particle.html" %}

* Command: PARTICLE {type} {quantity} {offset} {speed}
  * {type}: The type of particle. (ALL CAPS)
  * {quantity}: The amount of particles that will spawn
  * {offset}: The radius of the area where the particles may spawn in the player/target's location
  * {speed}: To how fast or how big particles will be
* Example:

```
- PARTICLE FIREWORKS_SPARK 10 0.1 0.5
```

### PLAYER\_RIDE\_ENTITY

* Info: Makes the player to ride the entity targeted.
* Command: PLAYER\_RIDE\_ON\_ENTITY
* Example:

```yaml
    entityCommands:
    - PLAYER_RIDE_ON_ENTITY
```



### SET\_AI

* Info: Sets the AI state
* Command: SET\_AI {true/false}
* Example:

```
- SET_AI false
```

### SETADULT

* Info: Sets the entity in it's "adult" state
* Command: SETADULT
* Example:

```
- SETADULT
```

* Example Situation:
  * If this command is executed on a baby chicken, it will turn into its adult form.



### SETBABY

* Info: Sets the entity in it's "baby" state
* Command: SETBABY
* Example:

```
- SETBABY
```

* Example Situation:
  * If this command is executed on a adult chicken, it will turn into its baby form.



### SETNAME

* Info: Forcefully sets the entity's name
* Command: SETNAME {name}
  * {name}: The name you want the entity to have
* Example:

```
- SETNAME FLAG
```



### SHEAR

* Info: Shear the entity
* Command: SHEAR
* Example:

```
- SHEAR
```



### TELEPORT ENTITY TO PLAYER

* Info: Teleports the entity to the user of the item
* Command: TELEPORT ENTITY TO PLAYER
* Example:

```
- TELEPORT ENTITY TO PLAYER
```



### TELEPORT PLAYER TO ENTITY

* Info: Teleports the user of the item to the entity
* Command: TELEPORT PLAYER TO ENTITY
* Example:

```
- TELEPORT PLAYER TO ENTITY
```



### TELEPORT POSITION

* Info: Teleports the entity in a specific location
* Command: TELEPORT POSITION {x} {y} {z}
  * {x}: X-Coordinate
  * {y}: Y-Coordinate
  * {z}: Z-Coordinate
* Example:

```
- TELEPORT POSITION %target_x% %target_y% %target_z%
```



## Mixed Commands

In addition of the following list of commands you can also use:

{% content-ref url="mixed-commands-player-and-entity.md" %}
[mixed-commands-player-and-entity.md](mixed-commands-player-and-entity.md)
{% endcontent-ref %}

These commands can be used in the Player related commands OR Entity related commands.
