---
description: >-
  These options are utilized to accomplish specific things to create simple to
  complex items
---

# Activators features

## General features

### displayName

* Example:&#x20;

```yaml
displayName: "&eThor activator"
```

* Description: It appears on the default `timeLeft:` message in the locale and on the default condition message.
* Required: NO, (Default "an activator")



### usageModification<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Example:

```yaml
usageModification: 1
```

* Description: Increase or Decrease the current amount of usage of the item.
* Required: NO, (Default -1)



### variablesModification

* Description: This is where you can modify the variables into your item.
* [Link to how to setup the variables modification to your activator](https://github.com/ssomar1607/ExecutableItems/wiki/Variables#how-to-setup-variables-in-the-activator-editor)
* Example:

```yaml
    variablesModification:
      varUpdt0:
        variableName: targethp
        type: SET
        modification: 20
```

* Required: NO (Default: no modification)



{% hint style="danger" %}
IF YOU'RE USING PLACEHOLDERS LIKE `%parseother_{%target%}_{player_health}%` AND THE TYPE OF THE SAID VARIABLE IS A NUMBER, USE STRING INSTEAD OR ISSUES WILL OCCUR
{% endhint %}

### detailedSlots

* Description: This makes it so the EI item will only work on specific slots.
* Example:

```yaml
detailedSlots:
- -1
- 40
# THIS MEANS THAT IT WILL ONLY WORK IF THE ITEM IS AT THE OFFHAND OR AT YOUR MAIN HAND.
# BEST TO AVOID ENABLING ALL SLOTS FOR BETTER PERFORMANCE
```

* More Information:
  * Choose slot 0-41 for the slots
  * If you select -1, it will only activate if you are holding it at your main hand.
* Required: NO (Default: -1)

### autoUpdateItem

* Description: Update specific things on the item when that activator gets triggered.

{% hint style="info" %}
Keep in mind that normally, if you change a feature in an activator of "x" item it will change on every "x" Item in your server, but, if the change is a visual related change, as a display name change, or lore change, it won't get updated, in the case you want it to get updated too this feature will be useful for you.
{% endhint %}

* Example:

```yaml
    autoUpdateItem: true
    updateName: true
    updateLore: false
    updateDurability: true
    updateAttributes: false
    updateEnchants: true
    updateCustomModelData: true
```

## Specifics features

These features doesn't work for all activators

### desactiveDrops

* Description: This makes it so vanilla loot will not be obtained from breaking blocks or killing mobs.
  * **NOTE: CUSTOM DROPS FROM CUSTOM MOBS PLUGIN LIKE MYTHIC MOBS WILL NOT GET AFFECTED BY THIS.**
* Options: true or false
* Example:&#x20;

```yaml
desactiveDrops: false
```

* Required: NO (Default: false)

<details>

<summary>Only for those activators</summary>

* **PLAYER\_BLOCK\_BREAK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_FISH** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_KILL\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_KILL\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>



### onlyAirClick

* Description: This attribute makes it so it will only activate if you only clicked air.
* Options: true or false
* Example:&#x20;

```yaml
onlyAirClick: false
```

* Required: NO (Default: false)

<details>

<summary>Only for those activators</summary>

* PLAYER\_ALL\_CLICK

<!---->

* PLAYER\_LEFT\_CLICK

<!---->

* PLAYER\_RIGHT\_CLICK

</details>

### onlyBlockClick

* Description: This attribute makes it so it will only activate if you click blocks.
* Options: true or false
* Example:&#x20;

```yaml
onlyBlockClick: false
```

* Required: NO (Default: false)

<details>

<summary>Only for those activators</summary>

* PLAYER\_ALL\_CLICK

<!---->

* PLAYER\_LEFT\_CLICK

<!---->

* PLAYER\_RIGHT\_CLICK

</details>

### detailedClick

* Description: This makes it so it will only activate if you are right-clicking, left-clicking or both.
* Options: RIGHT, LEFT, RIGHTORLEFT
* Example:&#x20;

```yaml
detailedClick: LEFT
```

* Required: YES (Default: RIGHT)

<details>

<summary><strong>Only for those activators</strong></summary>

* PLAYER\_ALL\_CLICK

<!---->

* **PLAYER\_CLICK\_ON\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* PLAYER\_CLICK\_ON\_PLAYER

</details>

### delay

* Description: This delays the repetition of the LOOP activator.
* Example:&#x20;

```yaml
delay: 30 #IN SECONDS
```

* Required: YES (Default: 30)

{% hint style="danger" %}
Only for the premium activator LOOP
{% endhint %}

### delayTick

* Description: This makes it so the value under the delay attribute will be counted in game ticks instead of seconds.
* Example: `delayTick: true`
* Required: NO (Default: false)

{% hint style="danger" %}
Only for the premium activator LOOP
{% endhint %}

## Cooldown

### cooldown

* Example:&#x20;

```yaml
cooldown: 30
```

* Description: Cooldown for activating an activator (in seconds)
* Required: NO, (Default 30)



{% hint style="info" %}
Custom cooldown features:

* pauseWhenOffline : It pauses the cooldown when the player disconnect
* pausePlaceholdersConditions : It pauses the cooldown when the placeholderConditions set is valid
{% endhint %}

### isCooldownInTicks

* Example:&#x20;

```yaml
isCooldownInTicks: true
```

* Description: If the cooldown value will be counted by ticks
* Required: NO, (Default false)

### cooldownMsg

* Example:&#x20;

```yaml
cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
```

* Placeholders available in this message:
  * %time% -> the entire cooldown in seconds
  * %time\_H% -> the hours part of the cooldown
  * %time\_M% -> the minutes part of the cooldown
  * %time\_S% -> the seconds part of the cooldown&#x20;
* Description: Cooldown message
* Required: NO

### displayCooldownMessage

* Example:&#x20;

```yaml
displayCooldownMessage: true
```

* Options: true or false
* Description: Enable/disable the display of the cooldown message.
* Required: NO, (Default false)

### cancelEventIfInCooldown

* Description: This attribute prevents vanilla events from happening on the EI item if you are in cooldown.
* Options: true or false
* Example:&#x20;

```yaml
cancelEventIfInCooldown: true
```

* Required: NO (Default: false)

### otherEICooldowns

* Example:

```yaml
otherEICooldowns:
      cd1:
        executableItem: Free_Fly
        activators:
        - activator1
        cooldown: 10
        isCooldownInTicks: false
      cd0:
        executableItem: Free_Custom_Crate
        activators: []
        cooldown: 10
        isCooldownInTicks: false
```

* Description: Add cooldown for another Executable item (in seconds)
  * It can add cooldown to a specific activator of an EI Item
* Required: NO

### Global Cooldown

* Description: Add cooldown to the activator in a global way, so if one player use the activator, all players will be in cooldown for this same activator.
* Example:

```yaml
    globalCooldownOptions:
      cooldown: 100
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
```

## Required Things

### requiredExecutableItems<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Example:

```yaml
requiredExecutableItems: 
  requiredEI1:
   id: EXECUTABLEITEMS_ID_HERE
   amount: 3
   consume: true/false
   validUsages: #OPTIONAL DELETE THIS OPTION IF YOU DONT WANT A VERIFICATION OF USAGE
   - 1
   - 3
   - 4
requiredExecutableItemsMsg: '&e'  #<- Here is where you will add the custom message.
```

* Description: This attribute searches for the required executable items in the player's inventory in order to activate.
* Required: NO, (Default: No EI is required)
* More Info: You can edit the message in locale or directly by adding this in the file:&#x20;

```yaml
requiredExecutableItemsMsg: "&4&lError you need...."
```

* If you don't want any messages to appear, add this in the file:&#x20;

```yaml
requiredExecutableItemsMsg: '&e'
```

### requiredItems<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Example:

```yaml
requiredItems: 
  - DIAMOND:5
  - EMERALD:3
requiredItemsMsg: '&e'  #<- Here is where you will add the custom message.
```

* Description: This attribute searches for the required vanilla items in the player's inventory in order to activate. This does not consume Executable Items.
* Required: NO, (Default: No item is required)
* More info: You can edit the message in locale or directly by adding this in the file:&#x20;

```yaml
requiredItemsMsg: "&4&lError you need...."
```

* If you don't want any messages to appear, add this in the file:&#x20;

```yaml
requiredItemsMsg: '&e'
```

### requiredMoney<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">&#x20;

* (Requires Vault)
* Example:

```yaml
requiredMoney: 500
requiredMoneyMsg: '&e'  #<- Here is where you will add the custom message.
```

* Description: This attribute checks if you have the required amount of money or more in order to activate. If the player has enough money, the value under requiredMoney will take away that amount from your current money.
  * Example:
    * `If you have 150k money and the amount is 'requiredMoney: 100000', the attribute will take away 100k from your 150k leaving 50k money left in you and the activator will run.`
    * `If you have 70k money and the amount is 'requiredMoney: 200000', the attribute will reject the player and the activator will not run.`
* Required: NO, (Default: No money is required)
* More Info: You can edit the message in locale or directly by adding this in the file:&#x20;

```yaml
requiredMoneyMsg: "&4&lError you need...."
```

* If you don't want any messages to appear, add this in the file:&#x20;

```yaml
requiredMoneyMsg: '&e'
```

### requiredLevel<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Example:

```yaml
requiredLevel: 1
requiredLevelMsg: '&e'  #<- Here is where you will add the custom message.
```

* Description: This attribute checks if the player has the required amount of Experience Levels or more in order to activate. If the player has the right amount of Experience Levels or more, this activator will take away the required amount of Experience Levels.
  * Example:
    * `If you have 216 Levels and the amount is 'requiredLevel: 99', the attribute will take away 99 levels from your 216 levels leaving 117 levels left in you and the activator will run.`
    * `If you have 60 levels and the amount is 'requiredLevel: 400', the attribute will reject the player and the activator will not run.`
* Required: NO, (Default: No level is required)
* More Info: You can edit the message in locale or directly by adding this in the file:&#x20;

```yaml
requiredLevelMsg: "&4&lError you need...."
```

* If you don't want any messages to appear, add this in the file:&#x20;

```yaml
requiredLevelMsg: '&e'
```

### requiredExperience

* Description: This attribute checks if the player has the required amount of Experience or more in order to activate. If the player has the right amount of Experience or more, this activator will take away the required amount of Experience.

### RequiredMana

* Description: Checks if the player has the required amount of mana or more in order to activate.
  * If this condition match, the mana will be consumed, if you don't want this to happen use a condition placeholder.

```yaml
    requiredMana:
      requiredMana: 10
```

{% hint style="info" %}
Compatible with AureliumSkills and MMOCore
{% endhint %}

### RequiredMagic (EcoSkills)

* Description: Checks if the player has the required amount of magic or more in order to activate.

```yaml
   requiredMagics:
      requiredMagic_0:
        magicID: mana
        amount: 70
```

## Commands&#x20;

### commands

* More information: **➤** [**Player commands**](../../../tools-for-all-plugins-score/custom-commands/player-and-target-commands.md)
* Example:

```yaml
commands:
- "COMMAND1"
- "COMMAND2"
```

* Required: NO

### blockCommands

* More information: **➤**[ **Block commands**](../../../tools-for-all-plugins-score/custom-commands/block-commands.md)
* Example:

```yaml
blockCommands:
- "EXPLODE"
- "SETBLOCK STONE"
```

* Required: NO

<details>

<summary>Only for those activators</summary>

* PLAYER\_ALL\_CLICK

<!---->

* **PLAYER\_BLOCK\_BREAK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* PLAYER\_LEFT\_CLICK

<!---->

* PLAYER\_RIGHT\_CLICK

<!---->

* **PROJECTILE\_HIT\_BLOCK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>

### entityCommands

* More information: **➤** [**Entity commands**](../../../tools-for-all-plugins-score/custom-commands/entity-commands.md)
* Example:

```yaml
entityCommands:
- "BURN"
- "HEAL"
```

* Required: NO

<details>

<summary>Only for those activators</summary>

* **PLAYER\_HIT\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">\

* **PLAYER\_CLICK\_ON\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_KILL\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_RECEIVE\_HIT\_BY\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PROJECTILE\_HIT\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>

### targetCommands

* More information: **➤** [**Target commands**](../../../tools-for-all-plugins-score/custom-commands/player-and-target-commands.md)
* Example:

```yaml
targetCommands:
- "SUDOOP effect give %player% slowness 10 10"
- "BURN 10"
```

* Required: NO

<details>

<summary>Only for those activators</summary>

* PLAYER\_HIT\_PLAYER\

* PLAYER\_CLICK\_ON\_PLAYER

<!---->

* **PLAYER\_KILL\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_RECEIVE\_HIT\_BY\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PROJECTILE\_HIT\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>

### silenceOutput

* Description: This makes it so any commands done by EI will not relay anything on the console panel.
* Options: true or false
* Example:&#x20;

```yaml
silenceOutput: true
```

* Required: NO (Default: false)

{% hint style="info" %}
This command will hide only the outputs of the vanilla commands of Minecraft, like /effect

/give, ...
{% endhint %}

{% hint style="info" %}
You can add custom messages to silence on the Score config&#x20;
{% endhint %}

## Select only certain types

### detailedBlocks

* Description: This attribute serves as a whitelisting to what blocks would trigger the activator
* Example:

```yaml
detailedBlocks:
- STONE
- COBBLESTONE
- ANDESITE
- FURNACE{lit:true} (🎇 **BLOCK STATE FEATURE IS PREMIUM EXCLUSIVE ONLY AND FOR 1.13+** 🎇)
- ITEMSADDER:turquoise_block
- EXECUTABLEBLOCKS:CUSTOMDIRT
- !DIRT
- ALL_ORES
```

* Required: NO (Default: false)

{% hint style="info" %}
It supports ItemsAdder blocks, example:

detailedBlocks:

* ITEMSADDER:turquoise\_block

It supports ExecutableBlocks blocks example:

* EXECUTABLEBLOCKS:MYBLOCK

And you can blacklist all things by adding a ! before, example:

* !DIRT
* !ALL\_ORES
{% endhint %}

{% embed url="https://minecraft.fandom.com/wiki/Block_states" %}

<details>

<summary>Only for those activators</summary>

* PLAYER\_ALL\_CLICK

<!---->

* **PLAYER\_BLOCK\_BREAK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* PLAYER\_LEFT\_CLICK

<!---->

* PLAYER\_RIGHT\_CLICK

<!---->

* **PROJECTILE\_HIT\_BLOCK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>

<details>

<summary>You can add a group of blocks, these are the groups:</summary>

```
    ALL_CHESTS,
    ALL_FURNACES,
    ALL_PLANKS,
    ALL_LOGS,
    ALL_WOODS,
    ALL_ORES,
    ALL_WOOLS,
    ALL_SLABS,
    ALL_STAIRS,
    ALL_FENCES,
    ALL_SAPLINGS,
    ALL_CROPS,
    ALL_DOORS,
    ALL_TRAPDOORS,
    ALL_BEDS,
    ALL_TERRACOTTA,
    ALL_NORMAL_TERRACOTTA,
    ALL_GLAZED_TERRACOTTA,
    ALL_CONCRETE,
    ALL_GLASS,
    ALL_STAINED_GLASS,
    ALL_SHULKER_BOXES
    ALL_CARPETS;
```

</details>

### detailedEntities

* Description: This attribute serves as a whitelisting to what entities would trigger the activator
* It supports NBT Tags so you can add for example something like: `ZOMBIE{IsBaby:1}`
* To blacklist mobs, add a "!" symbol beside the entity type.
  * Ex: `!CREEPER`
* It supports MythicMobs adding like this:

```yaml
detailedEntities:
 - MM-Giant
 - MM-MyMob
 - '!SKELETON' #this blacklist
 - ZOMBIE{CustomName:"*"}
```

{% embed url="https://minecraft.fandom.com/wiki/Tutorials/Command_NBT_tags#Entities" %}

NBT Tags require the plugin:

{% embed url="https://www.spigotmc.org/resources/nbt-api.7939/" %}

* Example:

```yaml
detailedEntities:
- ZOMBIE{IsBaby:1}
- ZOMBIE{IsBaby:0}
- CREEPER
- PIGLIN
```

* Required: NO (Default: false)
* Mob Type List:&#x20;

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html" %}

<details>

<summary>Only for those activators</summary>

* **PLAYER\_KILL\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_RECEIVE\_HIT\_BY\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PROJECTILE\_HIT\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>

### detailedItems

* Description: Checks the item related to the activator
* Example:

```yaml
detailedItems:
      items:
      - DIRT{CUSTOMMODELDATA:5}
      - !TORCH
      cancelEventIfNotValid: false
      messageIfNotValid: '&4&l[Error] &cthe item is not correct !'
```



<details>

<summary>Only for these activators (For now it only works with EE)</summary>

PLAYER\_PICKUP\_ITEM

PLAYER\_DROP\_ITEM

PLAYER\_CONSUME

</details>

### detailedDamageCauses

* Description: Checks the damage cause that you recieved
* Example:

```yaml
detailedDamageCauses:
- ENTITY_EXPLOSION
```

* Required: NO
* More Info:&#x20;

{% embed url="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html" %}

<details>

<summary>Only for those activators</summary>

* **PLAYER\_RECEIVE\_HIT\_BY\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_RECEIVE\_HIT\_BY\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_RECEIVE\_HIT\_GLOBAL** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* PLAYER\_DEATH

</details>

### detailedEffects

* Description: Checks if the effect received matches the ones in the list
* Example:

```yaml
    detailedEffects:
      effects:
      - SPEED
      cancelEventIfNotValid: false

```

<details>

<summary>Only for those activators</summary>

**PLAYER\_RECEIVE\_EFFECT** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>

### detailedCommands

* Description: Checks if the executed command matches the ones in the list
* Example:

```yaml
detailedCommands:
- test
- about
```

* Required: YES

<details>

<summary>Only for those activators</summary>

**PLAYER\_WRITE\_COMMAND** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>



## CancelEvent

### cancelEvent

* Description: This attribute prevents vanilla events from happening on the ei item.
* Options: true or false
* Example:&#x20;

```yaml
cancelEvent: false
```

* Required: NO (Default: false)

### cancelEventIfInvalidRequiredExecutableItems

* Description: This attribute prevents vanilla events from happening on the ei item if you don't have the required executable items.
* Options: true or false
* Example:&#x20;

```yaml
cancelEventIfInvalidRequiredExecutableItems: false
```

* Required: NO (Default: false)
* **NOTE: YOU NEED TO HAVE A REQUIRED EXECUTABLE ITEM ATTRIBUTE FIRST IN ORDER TO USE THIS ATTRIBUTE.**

### cancelEventIfInvalidRequiredLevel

* Description: This attribute prevents vanilla events from happening on the ei item if you don't have the required experience levels.
* Options: true or false
* Example:&#x20;

```yaml
cancelEventIfInvalidRequiredLevel: false
```

* Required: NO (Default: false)
* **NOTE: YOU NEED TO HAVE A REQUIRED LEVEL ATTRIBUTE FIRST IN ORDER TO USE THIS ATTRIBUTE.**

### cancelEventIfInvalidRequiredItems

* Description: This attribute prevents vanilla events from happening on the ei item if you don't have the required items.
* Options: true or false
* Example:&#x20;

```yaml
cancelEventIfInvalidRequiredItems: false
```

* Required: NO (Default: false)
* **NOTE: YOU NEED TO HAVE A REQUIRED ITEMS ATTRIBUTE FIRST IN ORDER TO USE THIS ATTRIBUTE.**

### cancelEventIfInvalidRequiredMoney

* Description: This attribute prevents vanilla events from happening on the ei item if you don't have the required money.
* Options: true or false
* Example:&#x20;

```yaml
cancelEventIfInvalidRequiredMoney: false
```

* Required: NO (Default: false)
* **NOTE: YOU NEED TO HAVE A REQUIRED MONEY ATTRIBUTE FIRST IN ORDER TO USE THIS ATTRIBUTE.**

### cancelEventIfMaxUsePerDay

* Description: This attribute prevents vanilla events from happening on the ei item if the player reaches the max usage per day of the item
* Options: true or false
* Example:&#x20;

```yaml
cancelEventIfMaxUsePerDay: true
```

* Required: NO (Default: false)

### cancelEventIfInCooldown

* Description: This attribute prevents vanilla events from happening on the ei item if the activator is in cooldown.
* Options: true or false
* Example:&#x20;

```yaml
cancelEventIfInCooldown: false
```

* Required: NO (Default: false)



### cancelEventIfNotDetailedBlocks

* Description: Cancels the event if the target block is not in the list of detailed blocks
* Example:

```yaml
cancelEventIfNotDetailedBlocks: true
```

* Required: NO

<details>

<summary>Only for those activators</summary>

* PLAYER\_ALL\_CLICK

<!---->

* **PLAYER\_BLOCK\_BREAK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* **PLAYER\_BLOCK\_PLACE** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

<!---->

* PLAYER\_LEFT\_CLICK

<!---->

* PLAYER\_RIGHT\_CLICK

<!---->

* **PROJECTILE\_HIT\_BLOCK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>
