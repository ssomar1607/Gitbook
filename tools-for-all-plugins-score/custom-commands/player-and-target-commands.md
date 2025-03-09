# Player & Target Commands

{% hint style="warning" %}
You need to know that by default all commands are run by the console, so if you want that the player run the command add [**SUDO**](player-and-target-commands.md#sudo) or [**SUDO\_OP**](player-and-target-commands.md#sudo_op) before.&#x20;

_(Click on SUDO or SUDO\_OP for more infos)_

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

In addition of the following list of commands you can also use

* [https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/mixed-commands-player-and-entity](https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/mixed-commands-player-and-entity)

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
* Command settings:
  * amount: amount of absorption half hearts. Supports negative values to remove.
  * time: time of the effect in ticks. Set it empty or "0" if want to be infinite.
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - ABSORPTION amount:5 time:200 # Gives the player absorption
  activator1: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - ABSORPTION amount:5 time:200 # Gives the target absorption
```

{% hint style="warning" %}
Your MAX\_ABSORPTION attribute value must be above 0 !

Check the value by typing : /attribute PLAYER\_NAME minecraft:max\_absorption base get

And you can increase it by typing: /attribute PLAYER\_NAME minecraft:max\_absorption base set 20
{% endhint %}

<pre class="language-yaml"><code class="lang-yaml">activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    # You can do that to temporary up the max_absorption value of the player
<strong>    - attribute %player% minecraft:max_absorption base set 5
</strong>    - ABSORPTION amount:5 time:200
    - DELAYTICK 200
    - attribute PLAYER_NAME minecraft:max_absorption base set 0
  activator1: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    # You can do that to temporary up the max_absorption value of the target
    - attribute %player% minecraft:max_absorption base set 5
    - ABSORPTION amount:5 time:200
    - DELAYTICK 200
    - attribute PLAYER_NAME minecraft:max_absorption base set 0
</code></pre>

### ACTIONBAR

* Info: Display the action bar with your text + the time remaining (59, 58, 57...).
* Command:&#x20;
  * `ACTIONBAR {Your text} {delay}`
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - `ACTIONBAR &6Hey &e%player% ! 10` # Sends an ACTIONBAR to the player
  activator1: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - `ACTIONBAR &6Hey &e%player% ! 10`# Sends an ACTIONBAR to the target
```



### ADD\_ITEM\_ATTRIBUTE

* Info: It adds an attribute to an item as sum or rest operation.
* Command: settings
  * slot: The slot where it will be applied. -1 for mainhand
  * attribute: The attribute you want to add
  * value: The value for the operation
  * equipmentSlot: The slot where the attribute will be enabled
  * mode: select the mode of addition
    * mode:ADD # Add the attribute to the item&#x20;
    * mode:OVERRIDE # Remove the current attributes of the same type of the item + Add the attribute to the item&#x20;
    * mode:STACK # Stack with the attribute present on the item, if no one exist it adds it
  * affectDefaultAttributes: true or false # When it's true the mode OVERRIDE will also override the default attributes, and for the MODE stack it allows to stack with the default attributes (green)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - ADD_ITEM_ATTRIBUTE slot:%slot% attribute:GENERIC_ATTACK_DAMAGE value:1.0 equipmentSlot:HAND mode:ADD # Add this attribute to the player
  activator1: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - ADD_ITEM_ATTRIBUTE slot:%slot% attribute:GENERIC_ATTACK_DAMAGE value:1.0 equipmentSlot:HAND mode:STACK affectDefaultAttributes: true # Add this attribute to the target
```

{% hint style="info" %}
You can find the attributes here [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html)

And the slots here

[https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/EquipmentSlot.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/EquipmentSlot.html)
{% endhint %}



### ADD\_ITEM\_ENCHANTMENT

* Info: It adds an enchantment on an item on a specific slot with certain level
* Command: settings
  * slot: The slot where it will be applied. -1 for mainhand
  * enchantment: The enchantment that you want to be applied, don't use spaces, use the minecraft enchantments not the display ones.
  * level: The level for the enchantment
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - ADD_ITEM_ENCHANTMENT slot:-1 enchantment:unbreaking level:1 
  activator1: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of target
    targetCommands:
    - ADD_ITEM_ENCHANTMENT slot:-1 enchantment:unbreaking level:1
```

{% hint style="info" %}
You can find the enchantments here

[https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/enchantments/Enchantment.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/enchantments/Enchantment.html)
{% endhint %}

### ADD\_ITEM\_LORE

* Info: Adds a line of lore
* Command settings
  * slot: The slot where it will be applied. -1 for mainhand
  * text: The text for the new lore line
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - ADD_ITEM_LORE slot:%slot% text:&7Item of %player%
  activator1: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of target
    commands:
    - ADD_ITEM_LORE slot:%slot% text:&7Item of %target% added by %player%
```

### AROUND

* Info: Targets players in a specific radius and makes them run commands
* Command settings:
  * distance: To how far in radius the command will select players (Default 3)
  * displayMsgIfNoPlayer: (true or false) To notify the user of the item if it managed to target players or not (Default true)
  * throughBlocks: it will affect or not the players that are behind blocks (Default true)
  * safeDistance: If the distance between the target and the launcher are below or equals to the safeDistance value then the target will not be affected. (Default 0)
  * commands: The commands that will be executed for the target players, separate them with <+>
* Example:

This summons lightning at players in a 20 block radius

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:20 displayMsgIfNoPlayer:false execute at %around_target% run summon lightning_bolt
```

This gives players slowness in a 10 block radius

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:10 effect give %around_target% slowness 50 5
</code></pre>

Damages nearby visible players by 20 player damage in a 7 block radius

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:7 throughBlocks:false DAMAGE 20
```

Send a message to players between 5 and 10 blocks

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:10 displayMsgIfNoPlayer:true throughBlocks:true safeDistance:5 SENDMESSAGE &eIt is a test !
```

Many around in the same command

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:5 displayMsgIfNoPlayer:false say &a(0)&e%around_target% <+> DELAY 3 <+> AROUND distance:5 displayMsgIfNoPlayer:false say &a(1)&e%around_target::step1% <+::step1> DELAY 3 <+::step1> AROUND distance:5 displayMsgIfNoPlayer:false say &a(2)&e%around_target::step2%
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND say &a(0)&e%around_target% <+> DELAY 3 <+> NEAREST 10 say &a(1)&e%around_target::step1%
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:10 throughBlocks:false displayMsgIfNoPlayer:false say &a(0)&e%around_target% <+> DELAY 3 <+> AROUND distance:5 displayMsgIfNoPlayer:false say &a(1)&e%around_target::step1% and x &c%around_target_x::step1% <+::step1> IF %around_target_x::step1%>10 say &aThe target &e%around_target_x::step2% <+::step2> effect give %around_target::step2% slowness 20
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:10 displayMsgIfNoPlayer:false CONDITIONS(%::parseother_{% raw %}
{%player%}
{% endraw %}_{betterteams_name}::%!=%::betterteams_name::%) effect give %around_target% weakness 10 10 true
```

#### You can add conditions to AROUND command

* The condition looks like AROUND \<settings> CONDITIONS(\<conditions>) \<command>
* Conditions works with placeholders but need to be %::\_::% instead of %\_%
  * For example %::player\_health::%
* To add MORE than 1 condition use "&&" between the conditions
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:10 CONDITIONS(%::player_health::%>10&#x26;&#x26;%::player_name::%=2Ssomar) SENDMESSAGE &#x26;eclick
</code></pre>

(Mainly in blockCommands/entityCommands) where you want the owner of the block/projectile won't harm the user of the item (Requires PlaceholderAPI's Player Expansion)

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - AROUND distance:2 CONDITIONS(%::player_name::%!=%player%) DAMAGE 15
```

{% hint style="info" %}
Keep in mind that the CONDITIONS() part parses the placeholders in it with the player selected by the AROUND command. So what actually happened in the placeholders above is that it checks if the target's health is greater than 10 and if that player who got selected by the AROUND command is named "2Ssomar"
{% endhint %}

{% hint style="info" %}
Placeholders that came from plugins like ExecutableItems, ExecutableBlocks will be parsed not by the player affected by the AROUND command.

For example, with ExecutableBlocks, CONDITIONS(%var\_faction%=%::factionsuuid\_faction\_name::%) works through checking if the block's factions variable value is equal to the targetted player's faction\
Placeholder Source: ([https://factions.support/placeholderapi/](https://factions.support/placeholderapi/))
{% endhint %}



### BOOTS

* Info: Puts the item in your main hand to your boots slot. (Will not work if the item has "Curse of Binding")
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - BOOTS
```



### BOSSBAR

* Info: Creates a bossbar text for a certain duration time.
* Command: settings
  * time: The duration of the bossbar in ticks
  * color: Color of bossbar text
  * text: text on the bossbar
  * count: how many times you want it to count&#x20;
    * if this option is present, the time argument will not matter anymore
  * countTicks: true/false whether you want it to count in ticks or in seconds instead
  * countOrder:&#x20;
    * ascending: makes the timer count from 0
    * descending: makes the timer count from the given
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - BOSSBAR time:200 color:RED text:This is a bossbar text
    - BOSSBAR time:20 color:BLUE text:Hello_world count:50 countTicks:true countOrder:ascending
```



### CANCEL\_PICKUP

* Info: Disables pickup on a player for a set amount of time
* Command: settings
  * time: The duration in ticks of how long till the player can pickup items again
  * material: If set the player cant pickup only the material specified, if null he can't pickup everything
* Example:

<pre class="language-yaml"><code class="lang-yaml">activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CANCEL_PICKUP time:600
<strong>    - CANCEL_PICKUP time:600 material:stone
</strong></code></pre>

{% hint style="info" %}
The only way to RESET this command after setting a time in ticks is reloading or restarting the server. If would like a way to reset this suggest it in the #suggestions channel on Discord.
{% endhint %}



### CHAT

* Info: Send a message from the player to the chat
* Command settings
  * text: Text to send
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CHAT &6Hello !!
```



### CHESTPLATE

* Info: Puts the item in your main hand to your chestplate slot. (Will not work if the item has "Curse of Binding")
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CHESTPLATE
```



### CLOSE\_INVENTORY

* Info: It closes the inventory to the player
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CLOSE_INVENTORY
```



### CROPS\_GROWTH\_BOOST

* Info: It boost the growth of the crops around you
* Command settings:
  * radius: The radius of the boost (Default 5)
  * delay: The delay in ticks between each growth boost
  * duration: The duration in ticks of the total boost
  * chance: The chance of growth the blocks have when the boost is applied
* Example:

The following command will generate 20 growth boost every 10 ticks.\
All blocks within the radius will have 50% chance to growth when a boost is applied.

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - CROPS_GROWTH_BOOST radius:5 delay:10 durations:200 chance:50
```



### DISABLE\_FLY\_ACTIVATION

* Info: Deny the usage of the fly for a player (Gliding in Elytra is not considered as flying)
* Command settings
  * time: The duration in seconds of the effect
* Example: (The command below disable the activation of the fly during 1 minute)

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - DISABLE_FLY_ACTIVATION time:60
```



### DISABLE\_GLIDE\_ACTIVATION

* Info: Deny the use of elytra for a period of time
* Command settings:
  * time: The duration in seconds of the effect
* Example: (the command below disable the use of elytra for 20 secs)

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - DISABLE_GLIDE_ACTIVATION time:20
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

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - EICOOLDOWN %player% thisismyid 10 true
```



### EBCOOLDOWN

* Info: It applys a cooldown to a specific ExecutableBlocks
* Command: EBCOOLDOWN {PLAYER} {ID} {SECONDS} {boolean TICKS} \[optional activator id]
  * {PLAYER}: The player to target the command
  * {ID}: The id of the ExecutableItem
  * {Seconds}: The amount of time
  * {boolean TICKS}: If you want the time to be in ticks
  * \[optional activator id]: You can apply it to a specific activator id
* Example:&#x20;

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - EBCOOLDOWN %player% thisismyid 10 true
</code></pre>



### EECOOLDOWN

* Info: It applys a cooldown to a specific ExecutableItems
* Command: EECOOLDOWN {PLAYER} {ID} {SECONDS} {boolean TICKS} {optional activator}
  * {PLAYER}: The player to target the command
  * {ID}: The id of the ExecutableItem
  * {Seconds}: The amount of time
  * {boolean TICKS}: If you want the time to be in ticks
  * \[optional activator id]: You can apply it to a specific activator id
* Example:&#x20;

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - EECOOLDOWN %player% thisismyid 10 true
```



### FLY\_ON

* Info: Gives the player creative flight
* No command setting
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - FLY_ON
</code></pre>

### FLY OFF

* Info: Disables creative flight on the player and if the player's flight get's disabled midair, the player will be teleported on the possible block under the player.
* Command settings:
  * teleportOnTheGround: (true or false) Whether the player would get teleported to the ground or not (Default true)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - FLY_OFF teleportOnTheGround:true
```



### FORCE\_DROP

* Info: It drops all the EI in your inventory with the id specified
* Command settings
  * ei\_id: Specify the EI that you want to be force dropped by the player
* Example:&#x20;

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - FORCE_DROP ei_id:excalibursword
```



### FORMAT\_ENCHANTMENTS

* Info: It formats all enchantments in your lore
* Command: FORMAT\_ENCHANTMENTS {slot}
  * It supports -1 as slot to target the mainhand
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - FORMAT_ENCHANTMENTS %slot%
```

![](<../../.gitbook/assets/image (393).png>) -> ![](<../../.gitbook/assets/image (382).png>)



### GRAVITY\_DISABLE

* Info: It stops the gravity for the player, stopping the player to "fall" down or going up.
* No command settings
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - GRAVITY_DISABLE
    - DELAY 5
    - GRAVITY_ENABLE
```

### GRAVITY\_ENABLE

* Info: It enable again the gravity for the player, so the player will fall normally.
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - GRAVITY_DISABLE
    - DELAY 5
    - GRAVITY_ENABLE
```

### HEAD

* Info: Puts the item in your main hand to your head slot. (Will not work if the item has "Curse of Binding")
* No command setting
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - HEAD
</code></pre>

### JOBS\_MONEY\_BOOST

{% hint style="info" %}
It supports "Jobs reborn"
{% endhint %}

* Info: Increases the money gained temporarily
* Command settings
  * multiplier: Multiplier value
  * time: Duration in seconds of the boost in seconds
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - JOBS_MONEY_BOOST multiplier:2.0 time:10
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

* Command settings
  * projectile: the type of the projectile or the custom projectile ID from SCore ( [Reference](https://github.com/ssomar1607/ExecutableItems/wiki/%E2%9E%A4-Custom-Projectiles#type) )
  * angleRotationVertical: (only for 1.14 and +) (not necessary) (default = 0) (in degrees) Define the direction where the entity will be launched
  * angleRotationHorizontal: (only for 1.14 and +) (not necessary) (default = 0) (in degrees) Define the direction where the entity will be launched
  * velocity: To customize the velocity of the projectile
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - LAUNCH projectile:My_Custom_Proj velocity:5
```

* Example multiple shoots:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - LAUNCH projectile:WITHERSKULL
    - LAUNCH projectile:WITHERSKULL angleRotationVertical:20
    - LAUNCH projectile:WITHERSKULL angleRotationVertical:-20
```

{% hint style="info" %}
If you use the LAUNCH COMMAND in the activator PLAYER\_LAUNCH\_PROJECTILE, and the projectile has been launched by a bow, the projectile launch with the custom LAUNCH command will keep the same velocity.
{% endhint %}



### LEGGINGS

* Info: Puts the item in your main hand to your leggings slot. (Will not work if the item has "Curse of Binding")
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - LEGGINGS
```



### LOCATED\_LAUNCH

* Info: Launches a projectile at a specific location
* Command: settings:
  * projectileType: the type of the projectile or the custom projectile ID from SCore ( [Reference](https://github.com/ssomar1607/ExecutableItems/wiki/%E2%9E%A4-Custom-Projectiles#type) )
  * frontValue: positive=front , negative=back - Front/Back Position. For example, if you want to spawn the projectile 5 blocks far from where you're facing, use a higher positive value
  * rightValue: right=positive, negative=left - Right/Left Position. For example, if you want the projectile to spawn to your left, use a higher negative value
  * yValue: To how high up from your Y position will the projectile will spawn.
  * velocity: To how fast will the projectile fly. Set the value to 0 for the projectile to fall downwards upon spawning the projectile.
  * &#x20;angleRotationVertical: (Optional) you can add a vetical rotation for your projectile (in degrees)
  * &#x20;angleRotationHorizontal: (Optional) you can add a horizontal rotation for your projectile (in degrees)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - LOCATED_LAUNCH projectile:ARROW frontValue:0 rightValue:0 yValue:0 velocity:1 angleRotationVertical:0 angleRotationHorizontal:0
```

### MINECART\_BOOST

* Info: It boost you when riding a minecart (Effect close to when you go up of a powered rail)
* Command settings:
  * boost: The boost speed
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - MINECART_BOOST boost:10
```



### MIX\_HOTBAR

* Info: it mixes the hotbar of the player
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - MIX_HOTBAR
```



### MOB\_AROUND

* Info: Targets entities in a specific radius and makes them run commands
  * Available entities -> [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/LivingEntity.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/LivingEntity.html)
* Command settings:
  * distance: To how far in radius the command will select entities
  * displayMsgIfNoEntity: (true or false) To notify the user of the item if it didn't manage to target any mobs.
    * **Set to true to hide the message**
  * throughBlocks: it will affect or not the mobs that are behind blocks
  * safeDistance: If the distance between the target and the launcher are below or equals to the safeDistance value then the target will not be affected.
  * You can BLACKLIST or WHITELIST entities adding one of these ones in anyplace of the command:
    * BLACKLIST(ZOMBIE,ARMOR\_STAND)
    * WHITELIST(CHICKEN)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - MOB_AROUND distance:3 displayMsgIfNoEntity:true throughBlocks:true safeDistance:0 [conditions] COMMAND1 <+> COMMAND2 <+> ...
    - MOB_AROUND distance:3 displayMsgIfNoEntity:false BURN 10
    - MOB_AROUND distance:5 execute at %around_target_uuid% run summon lightning_bolt
    - MOB_AROUND distance:5 BLACKLIST(ZOMBIE,ARMOR_STAND) DAMAGE 20
    - MOB_AROUND distance:5 displayMsgIfNoEntity:false effect give %around_target_uuid% poison 10 10
    - MOB_AROUND distance:10 WHITELIST(ZOMBIE{CustomName:"*"}) say HELLO
```

To use entity nbt on the WHITELIST/BLACKLIST field, you need to install NBT API plugin

{% embed url="https://www.spigotmc.org/resources/nbt-api.7939/" %}

It supports NBT Tags so you can add for example something like: `ZOMBIE{IsBaby:1}`

{% embed url="https://minecraft.fandom.com/wiki/Tutorials/Command_NBT_tags#Entities" %}

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - MOB_AROUND distance:7 BLACKLIST(ZOMBIE{CustomName:"Test Test"},ZOMBIE{CustomName:"Miyamoto"}) false BURN 3
    - MOB_AROUND distance:5 WHITELIST(ZOMBIE{IsBaby:1}) DAMAGE 20
    - MOB_aROUND distance:9 WHITELIST(WOLF{Owner:"%player%"}) HEAL 5
    - MOB_aROUND distance:9 WHITELIST(WOLF{Owner:%player_uuid%}) HEAL 5
```



### MODIFY\_DURABILITY

* Modifies the durability of a specific item in a specific slot
* Command settings:
  * modification: Positive value to increase the durability. Negative value to decrease the durability
  * slot: The slot number of the item (-1 for the held slot)
  * supportUnbreaking: (true or false) If it supports the unbreaking enchantment or not
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - MODIFY_DURABILITY modification:-1 slot:%slot% supportUnbreaking:true
```



### OPEN\_CHEST

* Info: It opens a chest in the selected location
* Command: OPENCHEST {world} {x} {y} {z} \[bypassProtections]
  * {bypassProtections}: If it will open the chest anyways even if its protected
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - OPENCHEST VanillaWorld 100 100 100
```

{% hint style="info" %}
It supports barrels
{% endhint %}

### OPEN\_ENDERCHEST

* Info: It opens the ender chest for the player that runs the activator
* No command setting
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - OPEN_ENDERCHEST
</code></pre>



### OPEN\_WORKBENCH

* Info: It opens a workbench for the player that runs the activator
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - OPEN_WORKBENCH
```

### OXYGEN

* Info: It gives oxygen to the target
* Command settings:
  * time: The duration in ticks of oxygen you want to give
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - OXYGEN time:200
```



### PROJECTILE\_CUSTOMDASH1

* Info: Similar to CUSTOMDASH1 but the xyz will be replaced with the xyz coords of the nearest projectile from you.
* Command settings:
  * fallDamage: Whether you will get fall damage or not (If you forgot to set whether it's true or false, the default will be false. To get fall damage, set this to true)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - PROJECTILE_CUSTOMDASH1 fallDamage:false
```



### REGAIN\_FOOD

* Info: Gives you a specific amount of food/saturation
* Command settings:
  * amount: The amount of saturation points you want to gain. Use negative values to reduce hunger points
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - REGAIN_FOOD amount:5
```



### REGAIN\_MAGIC

* Info: Gives the player specific values of a specific magic&#x20;
* Command settings:
  * ecoSkillsMagicID: The ID of the Ecoskills's magic.
  * amount: The amount to get.
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - REGAIN_MAGIC ecoSkillsMagicID:mana amount:15
```

{% hint style="info" %}
It supports negative values.
{% endhint %}



### REGAIN\_SATURATION

* Info: Gives you a specific amount of saturation
* Command settings:
  * amount: The amount of saturation you can to give
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - REGAIN_SATURATION amount:10
```



### REMOVE\_ENCHANTMENT

* Info: Remove an enchantment from a slot
* Command settings:
  * slot: Slot to remove the enchantment from
  * enchantment: Enchantment to remove (ALL for every enchantment)
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - REMOVE_ENCHANTMENT slot:-1 enchantment:ALL
</code></pre>



### REMOVE\_LORE

* Info: Remove a lore line
* Command settings:
  * {slot}: Slot to remove the lore from
  * {line}: The line that you want to remove
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - REMOVE_LORE slot:1 line:5
```



### REPLACE\_BLOCK

* Info: Replaces the block the player is looking at into a different one
* Command settings
  * {material}: Block ID (Block states are supported)&#x20;
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - REPLACE_BLOCK STONE_BRICKS
    - REPLACE_BLOCK WATER[LEVEL=0]
```



### SEND\_BLANK\_MESSAGE

* Info: Sends you a blank message
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SEND_BLANK_MESSAGE
```



### SEND\_MESSAGE

* Info: Sends you a message
* Command settings:
  * message: the message you want to send
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - SEND_MESSAGE text:&fThis is a somewhat random text.
```

{% hint style="info" %}
You can use minimessages color codes, like using gradient and stuff from this site: [https://docs.adventure.kyori.net/minimessage/format.html](https://docs.adventure.kyori.net/minimessage/format.html)\
\
You can only use one type of formatting at once in the same SENDMESSAGE command, either the classic color codes format or minimessage format.
{% endhint %}

### SEND\_CENTERED\_MESSAGE

* Info: Sends you a message centered in the chat
* Command settings:
  * message: the message you want to send
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SEND_CENTERED_MESSAGE text:&fThis is a somewhat random text.
```

{% hint style="info" %}
You can use minimessages color codes, like using gradient and stuff from this site: [https://docs.adventure.kyori.net/minimessage/format.html](https://docs.adventure.kyori.net/minimessage/format.html)\
\
You can only use one type of formatting at once in the same SENDMESSAGE command, either the classic color codes format or minimessage format.
{% endhint %}



### SET\_ARMOR\_TRIM

* Info: Set the specific armor trim with the specific pattern for the specified slot
* Command settings:
  * slot: The slot to apply the command (slot -1 for main hand)
  * pattern: The pattern of the trim (if 'null' or 'remove' it will remove the current pattern)
  * patternMaterial: The material of the pattern
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ARMOR_TRIM slot:38 pattern:vex patternMaterial:netherite
    - SET_ARMOR_TRIM slot:38 pattern:null #to clear the armor trim
```



{% hint style="info" %}
You can find all trim pattern here:

[https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/meta/trim/TrimPattern.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/meta/trim/TrimPattern.html)

You can find all trim material here:

[https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/meta/trim/TrimMaterial.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/meta/trim/TrimMaterial.html)
{% endhint %}

### SET\_BLOCK

* Info: Place a block on the block targeted by the player
* Command settings:
  * blockface: You can specify or not a blockFace to force the placement above for example
  * material: Block ID (Block states are supported)&#x20;
  * bypassProtection: Whether or not it will place the block even if the player doesnt have the permission
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_BLOCK blockface:UP material:OAK_WOOD
    - SET_BLOCK material:FURNACE[LIT=TRUE]
```

{% hint style="info" %}
You can find all blockface here:

[https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/block/BlockFace.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/block/BlockFace.html)
{% endhint %}

### SET\_BLOCK\_POS

* Info: Set a block in a specific position
* Command: SETBLOCKPOS {x} {y} {z} {material} \[bypassProtection true-false] \[replace true or false]
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SETBLOCKPOS %entity_x% %entity_y% %entity_z% BEDROCK true
</code></pre>



### SET\_EXECUTABLE\_BLOCK

* Info: Setblock but for Executable Blocks. **(EXECUTABLE BLOCKS MUST BE INSTALLED)**
* Command settings:
  * id: ID of the executable block you are trying to place down
  * x: X-Coordinate
  * y: Y-Coordinate
  * z: Z-Coordinate
  * world: Name of the world
  * replace: true or false. Whether it will replace the existing block in the said coordinates or not
  * bypassProtection: if you want bypass the protections like worldguard (default false)
  * ownerUUID: (Optional) The uuid of the supposed owner of the executable block
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_EXECUTABLE_BLOCK id:Mithril_Ore x:%block_x_int% y:%block_y_int% z:%block_z_int% world:%block_world% replace:false bypassProtection:true ownerUUID:%player_uuid%
```



### SET\_ITEM\_NAME

* Info: Sets a custom name for your item in a specific slot
* Command settings:
  * slot: The slot where it will be applied. -1 for mainhand
  * name: the new name of the item
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ITEM_NAME slot:%slot% name:&eThis is the new name of the item
```



### SET\_ITEM\_COLOR

* Info: Sets a specific color for the item (item colorables as leather armor)
* &#x20;Command settings:
  * slot: The slot where it will be applied. -1 for mainhand
  * color: number value of the color
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ITEM_COLOR slot:1 color:0
```

{% hint style="info" %}
Use the website: [https://www.tydac.ch/color/](https://www.tydac.ch/color/) for the leather color
{% endhint %}

{% hint style="info" %}
It supports FIREWORK\_STAR
{% endhint %}



### SET\_ITEM\_ATTRIBUTE

* Info: It sets an attribute to an item.
* Command settings:
  * slot: The slot where it will be applied. -1 for mainhand
  * attribute: The attribute you want to add
  * value: The value for the operation
  * equipmentSlot: The slot for the attribute
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ITEM_ATTRIBUTE slot:%slot% attribute:GENERIC_ARMOR value:10 equipmentSlot:CHEST
```

{% hint style="info" %}
You can find the attributes here [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html)
{% endhint %}



### SET\_ITEM\_CUSTOM\_MODEL\_DATA

* Info: Sets a specific custom model data to the specific item
* Command settings:
  * slot: The slot where it will be applied. -1 for mainhand
  * customModelData: value of the customModelData
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ITEM_CUSTOM_MODEL_DATA slot:10 customModelData:10
```



### SET\_ITEM\_COOLDOWN

* Gives the player/target cooldown on an item
* Command settings:
  * material or group: The type of material or the group
  * cooldown:: cooldown in seconds
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ITEM_COOLDOWN material:ENDER_PEARL cooldown:10
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ITEM_COOLDOWN group:my_cooldown_group cooldown:10
```

more info for the group arg:

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

{% embed url="https://www.minecraft.net/en-us/article/minecraft-java-edition-1-21-2" %}

### SET\_ITEM\_MATERIAL&#x20;

{% hint style="info" %}
Only works at 1.20.5 and above
{% endhint %}

* Replaces the material of the item with a different material while keeping the nbt of the target item
* Commands settings:
  * slot: Slot number (-1 for mainhand)&#x20;
  * material: The material you want the item to become into
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ITEM_MATERIAL slot:10 material:DIAMOND_HOE
```



### SET\_ITEM\_LORE

* Info: Sets a line of lore
* Command settings:
  * slot: Slot number (-1 for mainhand)&#x20;
  * line : If you want to set the lore of the first type 1
  * text: The new line text
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_ITEM_LORE slot:%slot% line:3 text:&6LEGENDARY SWORD
```



### SET\_TEMP\_BLOCK\_POS

* Info : Set a temporary block
* Command settings&#x20;
  * x: X-Coordinate
  * y: Y-Coordinate
  * z: Z-Coordinate
  * world: Name of the world
  * material: Block ID
  * time: Time in ticks
  * bypassProtection: (true or false) Whether to ignore 3rd party intervention or not
  * whitelistCurrentBlock: List of blocks to watch out for
    * Examples:
    * AIR, WATER
    * !STONE, !COBBLESTONE

{% code overflow="wrap" %}
```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SET_TEMP_BLOCK_POS x:%entity_x% y:%entity_y% z:%entity_z% world:%entity_world% material:BEDROCK time:40 bypassProtectiontrue whitelistCurrentBlock:!AIR,!WATER
```
{% endcode %}

{% hint style="warning" %}
It doesn't replace blocks that have extra datas (inventory, rotation, etc)
{% endhint %}

### SPAWN\_ENTITY\_ON\_CURSOR

{% embed url="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html" %}

* Info: Spawn entities on your cursor
* Command settings:
  * entity: Mob ID (ALL CAPS)
  * amount: The amount of mobs that will spawn in that spot
  * maxRange: The max range of the spawn (Default 200)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SPAWN_ENTITY_ON_CURSOR entity:CREEPER amount:1
```



### SUDO

* Info: Forces you to run a command
* Command: SUDO (command)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SUDO sit
    - SUDO say hi
```



### SUDO\_OP

* Info: Gives the player OP, SUDOs the player and DEOPs it
* Extra Info: During the OP, the player can only run the specified command after the SUDOOP, all other commands are blocked when the player is OP, and if the server crashes, no problem. The player will be DEOPed when the player reconnects.
* Command: SUDO\_OP (command)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
    - SUDO_OP summon zombie
    - SUDO_OP fly
    - SUDO_OP god
    - SUDO_OP /replacenear 20 tnt
```

{% hint style="danger" %}
It is not recommended to use this **a lot**. As it is explained on the top of this page, if want to run vanilla commands use the execute command (Explained on the FAQ "How to use vanilla commands").

If have another way to achieve what you want use it.

And if you have no other way but using SUDOOP, then use this command. This shouldn't be your first option.
{% endhint %}

### SWAP\_HAND

* Info: Swaps the current item with your offhand item
* No command setting
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
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
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    option: # Here goes an activator that is at least instance of player
    commands:
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



## Mixed Commands

In addition of the following list of commands you can also use:

{% content-ref url="mixed-commands-player-and-entity.md" %}
[mixed-commands-player-and-entity.md](mixed-commands-player-and-entity.md)
{% endcontent-ref %}

These commands can be used in the Player related commands OR Entity related commands.
