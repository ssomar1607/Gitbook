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



### ANGRY\_AT

* Info: Sets the entity target to a specific UUID
* Command settings:
  * entityUUID: The entity UUID of the target
* Example:

```
- ANGRY_AT entityUUID:%player_uuid%
# To reset the angry set null
- ANGRY_AT entityUUID:null
```



### AWARENESS

* Info: Sets whether this mob is aware of its surroundings. Unaware mobs will still move if pushed, attacked, etc. but will not move or perform any actions on their own. Unaware mobs may also have other unspecified behaviours disabled, such as drowning.

{% hint style="info" %}
it only works for 1.16.5+
{% endhint %}

* Command settings:
  * value: true or false
* Example:

```
- AWARENESS value:true
```



### CHANGE\_TO

* Info: Replaces the mob with an entity of another type. It will keep the current velocity of the current entity.
  * You can specify an [EntityType](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html)
  * Or an entity definition example: {HasVisualFire:1b,id:"minecraft:bee"} (1.21.+)
  * Or a MythicMob ID
* Command settings:
  * entity: The entity specification
* Example:

<pre><code><strong># With EntityType
</strong><strong>- CHANGE_TO entity:CHICKEN
</strong># With EntitySnapshot
- CHANGE_TO entity:{HasVisualFire:1b,id:"minecraft:bee"}
# Or using variable
- CHANGE_TO entity:%var_myvar%
# With MythicMob ID
- CHANGE_TO entity:MyCustomBossID
</code></pre>



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

* Info: Heals the entity with a specific amount, if not specified it will full heal the entity.
* Command settings:
  * amount: The amount of the heal
* Example:

```
# Full heal
- HEAL
# Amount specific heal
- HEAL amount:5
# Remove heal
- HEAL amount:-5
```



### KILL

* Info: Kills the mob without the death animation
* No command setting
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



### PLAYER\_RIDE\_ENTITY

* Info: Makes the player to ride the entity targeted.
* No command setting
* Example:

```yaml
- PLAYER_RIDE_ON_ENTITY
```



### SET\_AI

* Info: Sets the AI state of the entity
* Command settings:
  * value: true to enable the AI of the entity and false to disable.
* Example:

```
- SET_AI value:false
```

### SET\_ADULT

* Info: Sets the entity in it's "adult" state
* No command setting
* Example:

```
- SET_ADULT
```

* Example Situation:
  * If this command is executed on a baby chicken, it will turn into its adult form.



### SET\_BABY

* Info: Sets the entity in it's "baby" state
* No command setting
* Example:

```
- SET_BABY
```

* Example Situation:
  * If this command is executed on a adult chicken, it will turn into its baby form.



### SET\_ENTITY\_NAME

* Info: Forcefully sets the entity's name
* Command settings:
  * name: the new name of the entity
* Example:

```
- SET_ENTITY_NAME name:&6Final &cBoss
```



### SHEAR

* Info: Shear the entity
* No command setting
* Example:

```
- SHEAR
```



### TELEPORT\_ENTITY\_TO\_PLAYER

* Info: Teleports the entity to the user of the item
* No command setting
* Example:

```
- TELEPORT_ENTITY_TO_PLAYER
```



### TELEPORT\_PLAYER\_TO\_ENTITY

* Info: Teleports the user of the item to the entity
* No command setting
* Example:

```
- TELEPORT_PLAYER_TO_ENTITY
```



### TELEPORT\_POSITION

* Info: Teleports the entity in a specific location
* Command settings:
  * x: X-Coordinate
  * y: Y-Coordinate
  * z: Z-Coordinate
* Example:

```
- TELEPORT_POSITION x:%target_x% y:%target_y% z:%target_z%
```



## Mixed Commands

In addition of the following list of commands you can also use:

{% content-ref url="mixed-commands-player-and-entity.md" %}
[mixed-commands-player-and-entity.md](mixed-commands-player-and-entity.md)
{% endcontent-ref %}

These commands can be used in the Player related commands OR Entity related commands.
