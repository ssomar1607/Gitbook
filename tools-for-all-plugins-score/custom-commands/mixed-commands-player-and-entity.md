# Mixed Commands (Player & Entity)

{% hint style="info" %}
These custom commands work for PLAYER but also for ENTITY

So in:

* playerCommands
* targetCommands
* entityCommands
* ownerCommands
* ...
{% endhint %}

_Sorted by alphabetical order_

### ALL\_PLAYERS

* Info: Targets all players.
* Command:&#x20;
  * `ALL_PLAYERS {command}`
    * {command}: The command that will be executed
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - ALL_PLAYERS SEND_MESSAGE Hello %parseother_{% raw %}
{%around_target%}
{% endraw %}_{player_name}%
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - ALL_PLAYERS SEND_MESSAGE %target% has been hit by %player%
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - ALL_PLAYERS SEND_MESSAGE %entity% has been hit by %player%
```

Run multiple commands : Give a random item to all player, all players will not have the same.

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - ALL_PLAYERS RANDOM RUN:1 <+> ei give %around_target% candy1 1 <+> ei give %around_target% candy2 1 <+> ei give %around_target% candy3 1 <+> RANDOM END
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - ALL_PLAYERS RANDOM RUN:1 <+> ei give %around_target% candy1 1 <+> ei give %around_target% candy2 1 <+> ei give %around_target% candy3 1 <+> RANDOM END
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - ALL_PLAYERS RANDOM RUN:1 <+> ei give %around_target% candy1 1 <+> ei give %around_target% candy2 1 <+> ei give %around_target% candy3 1 <+> RANDOM END
```



### ALL\_MOBS

* Info: Targets all players.
* Command:&#x20;
  * `ALL_MOBS {command}`
    * {command}: The command that will be executed
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - ALL_MOBS DAMAGE 5
    - ALL_MOBS BLACKLIST(ZOMBIE,ARMORSTAND) DAMAGE 20
    - ALL_MOBS WHITELIST(ZOMBIE) DAMAGE 20
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - ALL_MOBS DAMAGE 5
    - ALL_MOBS BLACKLIST(ZOMBIE,ARMORSTAND) DAMAGE 20
    - ALL_MOBS WHITELIST(ZOMBIE) DAMAGE 20
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - ALL_MOBS DAMAGE 5
    - ALL_MOBS BLACKLIST(ZOMBIE,ARMORSTAND) DAMAGE 20
    - ALL_MOBS WHITELIST(ZOMBIE) DAMAGE 20

```

Run multiple commands:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - ALL_MOBS DAMAGE 5 <+> effect give %around_target_uuid% strength 10 1
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - ALL_MOBS DAMAGE 5 <+> effect give %around_target_uuid% strength 10 1
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - ALL_MOBS DAMAGE 5 <+> effect give %around_target_uuid% strength 10 1

```

{% hint style="info" %}
It supports blacklist and whitelist
{% endhint %}



### BACKDASH

* Info: Launches the player/target at the opposite direction of where they are facing at **(YOU CANNOT BE LAUNCHED IN THE AIR)**
* Command: BACKDASH {number}
  * {amount}: The value to how strong the launch will be
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - BACKDASH 5
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - BACKDASH 5
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - BACKDASH 5
```



### BURN

* Info: Burns the player/target
* Command: BURN {timeinsecs}
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - BURN 200
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - BURN 200
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - BURN 200
```



### CONSOLEMESSAGE

* Info: Sends a message to the console
* Command: CONSOLEMESSAGE {text}
  * {text}: Text to send tho the console
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CONSOLEMESSAGE This is a debug message sent to the %player%
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - CONSOLEMESSAGE This is a debug message sent to the %player% triggered by %target%
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - CONSOLEMESSAGE This is a debug message sent to the %player% triggered by %entity%
```



### COPYEFFECTS

* Info: Copy the effects of the target
* Command: COPYEFFECTS \[limitDuration]
  * \[limitDuration]: it means if the target has for example 3 mins of poison effect, if you limit it to 5 secs, you will only receive a poison effect of 5 seconds
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - COPYEFFECTS 5 # Using this will copy the player's own effects
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - COPYEFFECTS 5 # Using this will copy the target effects into the player
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - COPYEFFECTS 5 # Using this will copy the entity effects into the player 

```

### CUSTOMDASH1

* Info: Launches you to a specific location
* Command: CUSTOMDASH1 {x} {y} {z} {fallDamage}
  * {x}: X-Coordinate
  * {y}: Y-Coordinate
  * {z}: Z-Coordinate
  * {fallDamage}: true or false. Whether the player will take fall damage or not after getting launched by it.
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CUSTOMDASH1 %player_x% %player_y%+5 %player_z% true # This will dash up the player
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - CUSTOMDASH1 %target_x% %target_y%+5 %target_z% true # This will dash up the target
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - CUSTOMDASH1 %entity_x% %entity_y% %entity_z% true # This will dash up the entity
```

If you have activators that are related between two type of targets then you can do

* Example 1 | Instance of player - entity | Dash the player towards the entity

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Activator instance of player and entity
    commands:
    - CUSTOMDASH1 %entity_x% %entity_y% %entity_z% true
    entityCommands: []
```

* Example 2 | Instance of player - entity | Dash the entity towards the player

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong><strong>  activator0: # Activator ID, you can create as many activators on the activators list
</strong>    option: # Activator instance of player and entity
    commands: []
    entityCommands: 
    - CUSTOMDASH1 %player_x% %player_y% %player_z% true
</code></pre>

* Example 3 | Instance of player - block | Dash the player towards the block

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong><strong>  activator0: # Activator ID, you can create as many activators on the activators list
</strong>    option: # Activator instance of player and block
    commands: 
    - CUSTOMDASH1 %block_x% %block_y% %block_z% true
    blockCommands: []    
</code></pre>

You can increase the strength of the command running many times the command (but not on the same tick they must be differentiated in time otherwise it won't make sense since you are making the player dash from the same position against the location), examples:

* Running it many times manually

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CUSTOMDASH1 %player_x% %player_y%+5 %player_z% true # This will dash up the player
    - DELAYTICK 1
    - CUSTOMDASH1 %player_x% %player_y%+5 %player_z% true # This will dash up the player
    - DELAYTICK 1
    - CUSTOMDASH1 %player_x% %player_y%+5 %player_z% true # This will dash up the player
```

* Using LOOP START Utility command

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - 'LOOP START: 3'
    - CUSTOMDASH1 %player_x% %player_y%+5 %player_z% true # This will dash up the player
    - DELAYTICK 1
    - LOOP END
```

### CUSTOMDASH2

* Info: Launches you away from a specific location
* Command: CUSTOMDASH2 {x} {y} {z} {strength}
  * {x}: X-Coordinate
  * {y}: Y-Coordinate
  * {z}: Z-Coordinate
  * {strength}: Strength of the dash
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CUSTOMDASH2 %player_x% %player_y%+5 %player_z% 5 # This will dash down the player with strength 5
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - CUSTOMDASH2 %target_x% %target_y%+5 %target_z% 5 # This will dash down the target with strength 5
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - CUSTOMDASH2 %entity_x% %entity_y% %entity_z% 5 # This will dash down the entity with strength 5
```

If you have activators that are related between two type of targets then you can do

* Example 1 | Instance of player - entity | Dash the player away from the entity

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Activator instance of player and entity
    commands:
    - CUSTOMDASH1 %entity_x% %entity_y% %entity_z% 5
    entityCommands: []
```

* Example 2 | Instance of player - entity | Dash the entity away from the player

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong><strong>  activator0: # Activator ID, you can create as many activators on the activators list
</strong>    option: # Activator instance of player and entity
    commands: []
    entityCommands: 
    - CUSTOMDASH1 %player_x% %player_y% %player_z% 5
</code></pre>

* Example 3 | Instance of player - block | Dash the player away from the block

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong><strong>  activator0: # Activator ID, you can create as many activators on the activators list
</strong>    option: # Activator instance of player and block
    commands: 
    - CUSTOMDASH1 %block_x% %block_y% %block_z% 5
    blockCommands: []    
</code></pre>

### CUSTOMDASH3

* Info: Dashes the target following a specific math function
* Command: CUSTOMDASH3 {function} {max x value} {front z default true}
  * {function}: The math function to follow
  * {max x value}: Max x value of the function
  * {front z}: If the dash is frontward or backwardsti
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CUSTOMDASH3 cosx 10 true
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - CUSTOMDASH3 cosx 10 true
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - CUSTOMDASH3 cosx 10 true
```

{% hint style="info" %}
You can see how function works here [https://www.geogebra.org/calculator](https://www.geogebra.org/calculator)
{% endhint %}



### DAMAGE

* Info: Damages the player with a specific amount. (Damage dealt with the help of this command is counted as player damage)
  * This command triggers the activators related to damage of ExecutableItems and ExecutableEvents
  *   The spigot damage type is ENTITY\_ATTACK if there is a player involved on the activator.

      Otherwise, the spigot damage type is CUSTOM
* Command: DAMAGE {amount} {amplified If Strength Effect} {amplified with attack attribute} \[damageType]
  * {amount}: Amount of damage in hitpoints (Not in hearts)
  * {amplified If Strength Effect}: true or false, Strength 1 -> + 1.5 damage, ....
  * {amplified with attack attribute}: true or false, player with 500% bonus damage, the command will do 5 x "\<damage>".
  * \[damageType]: The type of damage -> [List](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/damage/DamageType.html)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - DAMAGE 20 true true # Apply 20 of damage to the player
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - DAMAGE 20 true true # Apply 20 of damage to the target
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - DAMAGE 20 true true # Apply 20 of damage to the entity 
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - DAMAGE 25% # Will apply 25% of the max health of the player as damage
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - DAMAGE 25% # Will apply 25% of the max health of the target as damage
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - DAMAGE 25% # Will apply 25% of the max health of the entity as damage
```

{% hint style="info" %}
To apply real damage you can use:\
\- 1.20.5++ use /minecraft:damage command, for example\
minecraft:damage %target% 10 by %player%\
\
\- 1.20.5-- use REGAIN HEALTH command, is not the best but its a workaround.
{% endhint %}



### DAMAGE\_NO\_KNOCKBACK

* Info: Damages the player with a specific amount without applying knockback. (Damage dealt with the help of this command is not counted as player damage and more of an indirect damage)
  * This command triggers the activators related to damage of ExecutableItems and ExecutableEvents
  *   The spigot damage type is ENTITY\_ATTACK if there is a player involved on the activator.

      Otherwise, the spigot damage type is CUSTOM
* Command: DAMAGE\_NO\_KNOCKBACK {amount} {amplified If Strength Effect} {amplified with attack attribute}
  * {amount}: Amount of damage in hitpoints (Not in hearts)
  * {amplified If Strength Effect}: true or false, Strength 1 -> + 1.5 damage, ....
  * {amplified with attack attribute}: true or false, player with 500% bonus damage, the command will do 5 x "\<damage>".
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - DAMAGE_NO_KNOCKBACK 20 true true # Apply 20 of damage to the player
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - DAMAGE_NO_KNOCKBACK 20 true true # Apply 20 of damage to the target
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - DAMAGE_NO_KNOCKBACK 20 true true # Apply 20 of damage to the entity 
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - DAMAGE_NO_KNOCKBACK 25% # Will apply 25% of the max health of the player as damage
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - DAMAGE_NO_KNOCKBACK 25% # Will apply 25% of the max health of the target as damage
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - DAMAGE_NO_KNOCKBACK 25% # Will apply 25% of the max health of the entity as damage
```



### DAMAGE\_BOOST

* Info: Allows you to give yourself custom damage boost
  * This command boost the damage of custom commands too e.g. (DAMAGE, DAMAGE\_NO\_KNOCKBACK)
  * This command doesn't boost the damage for projectiles
* Command: DAMAGE\_BOOST {modification in percentage example 100} {timeinticks}
  * {modification in percentage example 100}: Amount of the boost. Example below:
    * 50 = Makes you deal +50% damage
    * -80 = Makes you deal -80% damage
  * {timeinticks}: The duration of the custom damage boost
* Example: (The command below gives you +50% damage dealen for 10s)

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - DAMAGE_BOOST 50 200 # This will boost the damage of the player
  activator1: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - DAMAGE_BOOST 50 200 # This will boost the damage of the target
  activator2: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of entity
    entityCommands:
    - DAMAGE_BOOST 50 200 # This will boost the damage of the entity

```

This command can be used many time and the boost will get stacked, on this example you will see that \[0-10] seconds the player will apply 50% more damage then on \[10-20] seconds will apply 100% more damage and then on \[20-30] seconds of 50% more damage, due that on \[10-20] two commands were stacked of DAMAGE\_BOOST.

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - DAMAGE_BOOST 50 200 # This will boost the damage of the player by 50% for 200 ticks (10 seconds)
    - DELAY 10 # Delay of 10 seconds
    - DAMAGE_BOOST 50 200 # This will boost the damage of the player by 50% for 200 ticks (10 seconds)
```



### DAMAGE\_RESISTANCE

* Info: Allows you to give yourself custom damage resistance by giving yourself customized damage intake magnifications
* Command: DAMAGE\_RESISTANCE {modification in percentage example 100} {timeinticks}
  * {modification in percentage example 100}: Amount of the magnification. Example below:
    * 50 = Makes you take +50% damage\
      -80 = Makes you take -80% damage
  * {timeinticks}: The duration of the custom damage resistance
* Example: (The command below gives you +50% damage taken for 10s)

```
- DAMAGE_RESISTANCE 50 200
```



### EQUIPMENT\_VISUAL\_REPLACE

* Info: Replaces VISUALLY (there is no risk for losing items) a equipment slot with certain material
* Command: EQUIPMENT\_VISUAL\_REPLACE {EquipmentSlot} {material or EI:} {amount} {timeinticks}
  * {EquipmentSlot}: The slot
    * Options:
      * -1
      * 40
      * 36
      * 37
      * 38
      * 39
  * {material}: The item id of the material you want to replace with or the EI id
  * {amount}: The stack amount&#x20;
  * {timeinticks}: How long the disguise is gonna last for
*   Example:&#x20;



```
- EQUIPMENT_VISUAL_REPLACE 39 CARVED_PUMPKIN 1 100
```

<pre><code><strong>- EQUIPMENT_VISUAL_REPLACE 39 EI:test 1 100
</strong></code></pre>



### EQUIPMENT\_VISUAL\_CANCEL

* Info: Cancel the EQUIPMENT\_VISUAL\_REPLACE command
* Command: EQUIPMENT\_VISUAL\_CANCEL {EquipementSlot}
* Example:

```
- EQUIPMENT_VISUAL_CANCEL 39
```



### FORCEDROP

* Info: It forces the player to drop the item that he has in a specific slot.
* Command: FORCEDROP {slot}&#x20;
  * {slot}: number, -1 for main hand



![](https://i.imgur.com/KAwW8N0.png)

* Example:

```
- FORCEDROP -1
```



### FRONTDASH

* Info: Launches the player/target at the direction of where they are facing at
* Command: FRONTDASH {number} \[custom\_y] \[falldamage]
  * {number}: The value to how strong the launch will be
  * \[custom\_y] : To set a vertical boost (I advice you to set a little value like 0.5 - 1 if you dont want a big jump.)
  * \[falldamage]: set to enable or disable the fall damage
* Example:

```
- FRONTDASH 5 0.5 false
```



### GLACIAL\_FREEZE

* Info: It applies the freeze of Minecraft 1.18 snow
* Command: GLACIAL\_FREEZE {time in ticks}
* Example:

```yaml
- GLACIAL_FREEZE 160
```

### GLOWING

* Info: Applies glowing to the player
* Command: {time in ticks} \[color]
  * {time in ticks}: Duration of the glow in ticks
  * \[color]: To what color will the glow have
    * Color Reference: [https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Color.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Color.html)
* Example:

```
- GLOWING 100 BLUE
```



### HITSCAN\_PLAYERS

* Info: It allows to run a command at certain direction to players
* Command: HITSCAN\_PLAYERS range:5 radius:0 pitch:0 yaw:0 leftRightShift:0 yShift:0 throughBlocks:true throughEntities:true COMMANDS HERE
  * Range: how far an entity can be to be targetted by the HITSCAN command
  * RadiusOfHitscan: How WIDE the cylinder is. It's basically the difference of shooting a bullet vs shooting a cannonball.
  * Pitch: What direction to shoot it in, relative to player pitch
  * Yaw: Same thing as Pitch but with yaw
  * leftRightShift:
    * -5 = the hitscan STARTS from 5 blocks to the left.
    * 0 = Hitscan is centered where the player is.
    * 5 = hitscan STARTS from 5 blocks to the right of the player.&#x20;
  * yShift: Same as left,right, except with a different axis.&#x20;
  * throughEntities: Boolean: Whether or not the HITSCAN can go through entities.
  * throughBlocks: Boolean: Whether or not the HITSCAN can go through blocks.&#x20;
  * Commands: The same than AROUND commands, you can type command1 <+> command2 ... and use the placeholder %around\_target%
* Image to understand:
  *

      <figure><img src="../../.gitbook/assets/image (443).png" alt=""><figcaption></figcaption></figure>

### HITSCAN\_ENTITIES

* Info: It allows to run a command at certain direction to entities
* Command: HITSCAN\_ENTITIES range:5 radius:0 pitch:0 yaw:0 leftRightShift:0 yShift:0 throughBlocks:true throughEntities:true COMMANDS HERE
  * Range: how far an entity can be to be targetted by the HITSCAN command
  * RadiusOfHitscan: How WIDE the cylinder is. It's basically the difference of shooting a bullet vs shooting a cannonball.
  * Pitch: What direction to shoot it in, relative to player pitch
  * Yaw: Same thing as Pitch but with yaw
  * leftRightShift:
    * -5 = the hitscan STARTS from 5 blocks to the left.
    * 0 = Hitscan is centered where the player is.
    * 5 = hitscan STARTS from 5 blocks to the right of the player.&#x20;
  * yShift: Same as left,right, except with a different axis.&#x20;
  * throughEntities: Boolean: Whether or not the HITSCAN can go through entities.
  * throughBlocks: Boolean: Whether or not the HITSCAN can go through blocks.&#x20;
  * Commands: The same than AROUND commands, you can type command1 <+> command2 ... and use the placeholder %around\_target%
* Image to understand:
  *

      <figure><img src="../../.gitbook/assets/image (444).png" alt=""><figcaption></figcaption></figure>



### INVULNERABILITY

* Info: Sets the player invulnerable for a certain amount of time
* Command: INVULNERABILITY {ticks}
  * It supports negative values to decrease the invulnerability time, such as the one after being hit.
* Example:

```
- INVULNERABILITY 60
```



### JUMP

* Info: Launches the player in the air
* Command: JUMP {number} \[fall damage]
  * {number}: To how strong the launch will be
  * \[fall damage]: Select if want the command to have fall damage. Default -> false
* Example:

```
- JUMP 20
```



### LAUNCHENTITY

* Info: Launches an entity to your direction

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html" %}

* Command: LAUNCHENTITY {entityType} {speed} \[angle rotation y]
  * {entityType}: Mob ID of the launched entity (ALL CAPS)
  * {speed}: (number, Double) Define the speed of the entity
  * \[angle rotation y]: (only for 1.14 and +) (not necessary) (default = 0) (in degrees) Define the direction where the entity will be launched
* Example:

```
- LAUNCHENTITY PIG 2
```

* Example to make tri-shoot:

```
- LAUNCHENTITY PIG 2
- LAUNCHENTITY PIG 2 15
- LAUNCHENTITY PIG 2 -15
```



### MLIB\_DAMAGE

* Info: Deals damage to target but the damage type is mainly from MythicLib plugin
* Command: MLIB\_DAMAGE {number} {damageType} {knockback} \[element]
  * {number}: Damage dealt to targets
  * {damage\_type}: Damage type inflicted
    * Example: MAGIC, PHYSICAL, WEAPON, SKILL, PROJECTILE, UNARMED, ON\_HIT, MINION, DOT;
  * {knockback}: true/false whether it knocks back the target
  * \[element]: Specified what kind of element the attack is
    * Reference: [https://gitlab.com/phoenix-dvpmt/mythiclib/-/blob/master/mythiclib-plugin/src/main/resources/default/elements.yml?ref\_type=heads](https://gitlab.com/phoenix-dvpmt/mythiclib/-/blob/master/mythiclib-plugin/src/main/resources/default/elements.yml?ref_type=heads)
* Example:

```
- MLIB_DAMAGE 10 PHYSICAL false FIRE
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

### OPMESSAGE

* Info: It sends a message to OP online players and the console
* Command: OPMESSAGE {text}&#x20;
  * {text}: Text to send
* Example:

```
- OPMESSAGE This is my debug message
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



### REGAIN HEALTH

* Info: Gives you a specific amount of HP
* Command: REGAIN HEALTH {amount}
  * {amount}: The amount of HP you want to gain
* Example:

```
- REGAIN HEALTH 10
```

{% hint style="info" %}
It suports negative values in case of you want to do "true damage".
{% endhint %}



### REMOVEBURN

* Info: Extinguishes you from burning
* Command: REMOVEBURN
* Example:

```
- REMOVEBURN
```



### REMOVEGLOW

* Info: Add the glowing effect with a specific color to the player | target.
* Command: REMOVEGLOW \[color]
* Example:

```
- REMOVEGLOW BLACK
```



### SETGLOW

* Info: Add the glowing effect with a specific color to the player | target.
* Command: SETGLOW \[color]
* Example:

```
- SETGLOW BLACK
```

{% hint style="info" %}
Compatible with the plugin TAB using -> %score\_cmd-glow%
{% endhint %}

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/ChatColor.html" %}



### SETHEALTH

* Info: Sets your health into a specific amount
* Command: SETHEALTH {amount}
  * {amount}: The amount of health you want it to set to
* Example:

```
SETHEALTH 10
```



### SETPITCH

* Info: Forces the player to look in a certain pitch position (-90/90 degrees, up down direction)
* Command: SETPITCH {pitch\_number} \[keepVelocity]
  * {pitch\_number}: The number that you want to input. Placeholders work too
  * \[keepVelocity]: It allows to keep the velocity of the player
* Example:

```
- SETPITCH 0 false
- SETPITCH %target_pitch% false
```



### SETYAW

* Info: Forces the player to look in a certain yaw position (360 degrees, left right direction)
* Command: SETYAW {yaw\_number} \[keepVelocity]
  * {yaw\_number}: The number that you want to input. Placeholders work too
  * \[keepVelocity]: It allows to keep the velocity of the player
* Example:

```
- SETYAW 10 false
```

### SPIN

* Info: Spin the target
* Command: SPIN {duration ticks} {velocity}
  * {duration ticks}: The duration of the spin
  * {velocity}: The velocity of the spin
* Example:

```
- SPIN 20 1
```



{% hint style="info" %}
Q: How to freeze targets/players/mobs ?

A: run <mark style="color:orange;">`SPIN {duration} 0`</mark> for example
{% endhint %}

### STEAL

* Info: Steal an item from the target inventory
* Command: STEAL \[slot] {remove item default true}
  * \[slot] => -1 to mainhand
* Example:

```
- STEAL 10
```



### STRIKELIGHTNING

* Info: Strikes a lightning bolt with no damage to the one that runs the command
* Command: STRIKELIGHTNING
* Example:

```
- STRIKELIGHTNING
```

{% hint style="info" %}
This is not the same as essential's smite command. If you want to smite your targets, put it on target commands or entity commands along with the proper activators like `PLAYER_CLICK_ON_PLAYER` for exampl&#x65;**.**
{% endhint %}



### STUN ENABLE/DISABLE

* Info: It will enable or disable the stun for the player (it lays you down and blocks you from moving your camera
* Commands:
  * STUN\_ENABLE
  * STUN\_DISABLE
* Example:

```
- STUN_ENABLE
- DELAY 5
- STUN_DISABLE
```



### TELEPORT

* Info: Teleports the player/entity to the location
* Command: TELEPORT {world} {x} {y} {z} \[pitch] \[yaw] \[keepVelocity]
  * {world}: The world of the location to teleport
  * {x}: The coordinate x of the location to teleport.
  * {y}: The coordinate y of the location to teleport.
  * {z}: The coordinate z of the location to teleport.
  * \[pitch]: Optional pitch of the teleport location
  * \[yaw]: Optional yaw of the teleport location
  * \[keepVelocity]: Allows to not stop the player velocity.
* Example:

```
- TELEPORT ApocalypseWorld 70 70 70
```



### TELEPORTONCURSOR

* Info: Teleports you on your cursor
* Command: TELEPORTONCURSOR {range} {acceptAir}
  * {range}: To how far you want to teleport
  * {acceptAir}: To be able to teleport even in air, you need to set this to true
* Example:

```
- TELEPORTONCURSOR 8 true
```



### TRANSFER\_ITEM

* Info: It transfer an item on the inventory
* Command: TRANSFER\_ITEM {slot of launcher} {slot of receiver}
  * {slot of launcher}: Slot of the item who is going to move
  * {slot of receiver}: Slot where the item will land
* Example:

```
- TRANSFER_ITEM 38 40
```

{% hint style="info" %}
-1 to mainhand
{% endhint %}



### UNSAFE\_TELEPORTONCURSOR

* Info: Teleports you on your cursor without considering that you will end up on in impossible places
* Command: UNSAFE\_TELEPORTONCURSOR {maxRange}
  * {maxRange}: To how far you want to teleport
* Example:

```
UNSAFE_TELEPORTONCURSOR 20
```



### WORLDTELEPORT

* Info: Teleport to a world
* Command: WORLDTELEPORT {world}
* Example:

```
- WORLDTELEPORT spawn_end
```



## Animation Commands

* BREAK\_BOOTS\_ANIMATION
* BREAK\_CHESTPLATE\_ANIMATION
* BREAK\_HELMET\_ANIMATION
* BREAK\_LEGGINGS\_ANIMATION
* BREAK\_MAIN\_HAND\_ANIMATION
* BREAK\_OFF\_HAND\_ANIMATION
* HURT\_ANIMATION
* SWING\_MAIN\_HAND
* SWING\_OFF\_HAND
* TELEPORT\_ENDER\_ANIMATION
* TOTEM\_ANIMATION
