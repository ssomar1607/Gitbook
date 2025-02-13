---
description: >-
  These options are utilized to accomplish specific things to create simple to
  complex items
---

# Activators features

All this features are inside the activator, as reminder activators are different ways you have to trigger features on your ExecutableItem, it can have conditions, run commands, have cooldown,&#x20;

## General features of an activator

### Display name of the activator

* Info: String value of the display name of the activator, it doesn't have much use, its used for the developer to recognize one activator from another. It also appears on the default message "timeLeft" inside the locale.yml file.
* Example:&#x20;

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activators on the activators list
    name: '&#x26;eThor activator'
</code></pre>

### Usage modification of the activator<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Info: Very important feature, the value of the usage of the item will be modified by this integer value. That means, if this value is positive then usage will increase and if this value is negative then the usage will decrease.
* Example: (Increasing the value of the usage by 1 each time this activator is triggered)

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    usageModification: 1
```

### Variables modification

* Info: Its a list of variables modification to apply to the variables inside your item. Its useful for example, for increase the value of a variable, for overriding an old value of a variable to another value, etc.
  * variableName: Name of the variable the variableModification is targetting
  * type: Type of variableModification you are using
    * SET: Override the old value of the variable and sets the modification value.
    * ADD: Apply math to the current value of the variable using the modification value. It needs the variable to be type of NUMBER. If the modification value is positive then it will increase, if its negative then it will decrease.
    * LIST\_ADD: Applied to variable type LIST, it appens the modification value to the variable list.
    * LIST\_CLEAR: Applied to variable type LIST, it clears the variable list.
    * LIST\_REMOVE: Applied to variable type LIST, it removes the modification value from the variable list.
  * modification: Value of modification. Its applied to the variable using the types of modifications.
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    variablesModification:
      varUpdt0: # Variable modification ID, you can create as many variable modifications on the activator as you want  
        # This variable modification updates the value of targethp to 20
        variableName: targethp 
        type: SET
        modification: 20
      varUpdt1: # Variable modification ID, you can create as many variable modifications on the activator as you want 
        # This variable modification updates the value of hit by increasing it on 1
        variableName: hit
        type: MODIFICATION
        modification: 1
      varUpdt1: # Variable modification ID, you can create as many variable modifications on the activator as you want 
        # This variable modification updates the value of hit by decreasing it on 1
        variableName: durability
        type: MODIFICATION
        modification: -1
```

* Be careful when using placeholders here ! There is no problem with that, just make sure the returning output is a NUMBER, otherwise you will need to use STRING features. For example, let's update a variableModification by another variable that we know it returns a NUMBER.

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    variablesModification:
      varUpdt0: # Variable modification ID, you can create as many variable modifications on the activator as you want  
        # This variable modification updates the value of the bullets to the value of the variable max bullets, as if I was reloading a gun
        variableName: currentBullets
        type: SET
        modification: '%var_maxbullets_int%'
```

```yaml
activators:
  activator1: # Activator ID, you can create as many activators on the activators list
    variablesModification:
      varUpdt0: # Variable modification ID, you can create as many variable modifications on the activator as you want  
        # This variable modification updates the value of the current bullets by the variable bullets per shot, so its decreasing our bullets depending on the amount of bullets we are firing
        variableName: currentBullets
        type: MODIFICATION
        modification: '-%var_bulletspershot%'
```

### Detailed slots

* Info: List of integer values that represents slots of the inventory where the activator will be able to work. This means, if the event occurs in one slot that is not from here then the activator won't be triggered.
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    detailedSlots:
  - -1 # Slot for mainhand, this is not a static slot but having it on mainhand
  - 40 # This is a static slot, it represents the offhand slot.
```

### Auto update item

* Info: This feature of the activator makes that the item is updated in one of the features of the list. Be careful ! This may not be necessary depending on what you want. There are things that are updated automatically, for example, commands on the activator, conditions, cooldown, etc are updated automatically without this feature.&#x20;
* This feature targets most the visual aspects of the item, so if you created once a ExecutableItem with id:ex\_sword with a display name of "\&dExcalibur" and you distributed this item to all players and now you would like all the ExecutableItems "ex\_sword" to have the new display name of "\&eEpic Sword" then you would need to enable this feature on one of the activators of the item. Enabling the feature (autoUpdateItem) + the feature of update name (updateName).
* To make sure its correctly explained, this feature will override the current value depending on the options you enabled with the current option of the config file, and its only used for visual features. Its not necessary for common changes that don't involve the options of this feature.
  * autoUpdateItem: Boolean value that represents if this feature is enabled or not for the activator.
  * updateName: Boolean value to update the display name of the ExecutableItem. If its true, it will override the current display name of the item with the current/updated item name set on the config file of the ExecutableItem.
  * updateLore: Boolean value to update the lore of the ExecutableItem. If its true, it will override the current lore of the item with the current/updated lore set on the config file of the ExecutableItem.
  * updateDurability: Boolean value to update the current durability of the ExecutableItem. If its true, it will override the current durability of the item with the current/updated durability set on the config file of the ExecutableItem.
  * updateAttributes: Boolean value to update all the attributes of the ExecutableItem. If its true, it will override the current attributes of the item with the current/updated attributes set on the config file of the ExecutableItem.
  * updateEnchants: Boolean value to update the enchantments of the ExecutableItem. If its true, it will override the current enchantments of the item with the current/updated enchantments set on the config file of the ExecutableItem.
  * updateCustomModelData: Boolean value to update the custom model data value of the ExecutableItem. If its true, it will override the current custom model data of the item with the current/updated customModelData value set on the config file of the ExecutableItem.
  * updateArmorSettings: Boolean value to update the armor settings of the ExecutableItem. If its true, it will override the current armor settings of the item with the current/updated armor settings set on the config file of the ExecutableItem. e.g. (Armor color)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    autoUpdateItem: false
    updateName: false
    updateLore: false
    updateDurability: false
    updateAttributes: false
    updateEnchants: false
    updateCustomModelData: false
    updateArmorSettings: false
```

## Cooldown

### Player cooldown

* Info: Cooldown options its the cooldown applied to the player who triggered this activator for this activator.
* If the activator is PLAYER\_RIGHT\_CLICK, it has some commands \[] and the cooldown is 30 seconds, if the player triggers this activator he will need to wait 30 seconds in order to make it trigger again. This doesn't prevent other player from running it between those 30 seconds as long as that player is not on cooldown too. This is a feature per player
  * cooldown: Integer value that represents the amount of time the cooldown will last for this activator.
  * isCooldownInTicks: Boolean value that sets the cooldown time to be in ticks (20 ticks = 1 second)
  * cooldownMsg: String value to be displayed when the player try to trigger the activator when its on cooldown
  * displayCooldownMessage: Boolean value to allow or prevent the message of cooldownMsg displayed if the player try to trigger the activator while he is on cooldown.
    * Placeholders that can be used:
      * %time% -> the entire cooldown in seconds
      * %time\_H% -> the hours part of the cooldown
      * %time\_M% -> the minutes part of the cooldown
      * %time\_S% -> the seconds part of the cooldown&#x20;
  * cancelEventIfInCooldown: Boolean value that cancels the event of the activator if the player is on cooldown. This means, if the activator is PLAYER\_HIT\_ENTITY, while he is on cooldown all the player event's of PLAYER\_HIT\_ENTITY will be cancelled and so they will be ignored, disabling the ability of the player to attack entities (reminder: that activator targets all entities except players)
  * pauseWhenOffline: Boolean value that pauses the cooldown if the player is offline. To better understanding, if its false, the cooldown time doesn't stop so he can leave the server, wait the cooldown and join again and he will be able to trigger the activator again. But if this feature is enabled and he left the server while on cooldown, when he joins again he will have the same remaining cooldown time that he had when he left.
  * pausePlaceholdersConditions: Its similar to pauseWhenOffline but it only pauses depending on certain placeholdersConditions. Example of usages would be pausing the cooldown if the player is VIP rank. So VIP rank has access to that feature.
  * enableVisualCooldown: Enables a visual cooldown for the item.
* Example:&#x20;

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
      pauseWhenOffline: false
      pausePlaceholdersConditions: {}
      enableVisualCooldown: false
```

### Global cooldown

* Info: Its the same idea as cooldown but instead of being the cooldown applied to the player its a global cooldown that is applied to all players. That means, if someone triggers the activator and it has 30 seconds of global cooldown, then no one will be able to use it after those 30 seconds  has gone. It has the same features as cooldown.
  * cooldown: Integer value that represents the amount of time the cooldown will last for this activator.
  * isCooldownInTicks: Boolean value that sets the cooldown time to be in ticks (20 ticks = 1 second)
  * cooldownMsg: String value to be displayed when a player try to trigger this activator when its on cooldown
  * displayCooldownMessage: Boolean value to allow or prevent the message of cooldownMsg displayed if the player try to trigger the activator while he is on cooldown.
    * Placeholders that can be used:
      * %time% -> the entire cooldown in seconds
      * %time\_H% -> the hours part of the cooldown
      * %time\_M% -> the minutes part of the cooldown
      * %time\_S% -> the seconds part of the cooldown&#x20;
  * cancelEventIfInCooldown: Boolean value that cancels the event of the activator if the player is on cooldown. This means, if the activator is PLAYER\_HIT\_ENTITY, while he is on cooldown all the player event's of PLAYER\_HIT\_ENTITY will be cancelled and so they will be ignored, disabling the ability of the player to attack entities (reminder: that activator targets all entities except players)
  * pauseWhenOffline: \<TODO IF I FORGOT PLS PING VAYK>
  * pausePlaceholdersConditions: \<TODO IF I FORGOT PLS PING VAYK>
  * enableVisualCooldown: Enables a visual cooldown for the item.
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    globalCooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
      pauseWhenOffline: false
      pausePlaceholdersConditions: {}
      enableVisualCooldown: false
```

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

## Required features

### requiredExecutableItems<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Example:

```yaml
   requiredExecutableItems: 
     requiredEI1:
      executableItem: EXECUTABLEITEMS_ID_HERE
      amount: 3
      usageConditions: CONDITION>2
     errorMsg: '' #<- Here is where you will add the custom message.
```

* Description: This attribute searches for the required executable items in the player's inventory in order to activate.
* Required: NO, (Default: No EI is required)

### requiredItems<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Example:

```yaml
    requiredItems:
      requiredItem0:
        material: STONECUTTER
        amount: 1
        notExecutableItem: false
      errorMessage: kamehameha
```

* Description: This attribute searches for the required vanilla items in the player's inventory in order to activate. This does not consume Executable Items.
* Required: NO, (Default: No item is required)

### requiredMoney<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">&#x20;

* (Requires Vault)
* Example:

```yaml
    requiredMoney:
      requiredMoney: 1200.0
      errorMessage: apt
      cancelEventIfError: true
```

* Description: This attribute checks if you have the required amount of money or more in order to activate. If the player has enough money, the value under requiredMoney will take away that amount from your current money.
  * Example:
    * `If you have 150k money and the amount is 'requiredMoney: 100000', the attribute will take away 100k from your 150k leaving 50k money left in you and the activator will run.`
    * `If you have 70k money and the amount is 'requiredMoney: 200000', the attribute will reject the player and the activator will not run.`
* Required: NO, (Default: No money is required)

### requiredLevel<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Example:

```yaml
    requiredLevel:
      requiredLevel: 10
```

* Description: This attribute checks if the player has the required amount of Experience Levels or more in order to activate. If the player has the right amount of Experience Levels or more, this activator will take away the required amount of Experience Levels.
  * Example:
    * `If you have 216 Levels and the amount is 'requiredLevel: 99', the attribute will take away 99 levels from your 216 levels leaving 117 levels left in you and the activator will run.`
    * `If you have 60 levels and the amount is 'requiredLevel: 400', the attribute will reject the player and the activator will not run.`
* Required: NO, (Default: No level is required)

### requiredExperience

* Description: This attribute checks if the player has the required amount of Experience or more in order to activate. If the player has the right amount of Experience or more, this activator will take away the required amount of Experience.

```yaml
    requiredExperience:
      requiredExperience: 20
      errorMessage: wawa
```

### RequiredMana

* Description: Checks if the player has the required amount of mana or more in order to activate.
  * If this condition match, the mana will be consumed, if you don't want this to happen use a condition placeholder.

```yaml
    requiredMana:
      requiredMana: 10
      errorMessage: ''
```

{% hint style="info" %}
Compatible with AureliumSkills, MMOCore and AuraSkills
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

- **PLAYER\_BLOCK\_BREAK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* PLAYER\_LEFT\_CLICK

- PLAYER\_RIGHT\_CLICK

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

- **PLAYER\_KILL\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* **PLAYER\_RECEIVE\_HIT\_BY\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

- **PROJECTILE\_HIT\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

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

- **PLAYER\_KILL\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* **PLAYER\_RECEIVE\_HIT\_BY\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

- **PROJECTILE\_HIT\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

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
- '#MINECRAFT:MINEABLE/PICKAXE'
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

- **PLAYER\_BLOCK\_BREAK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* PLAYER\_LEFT\_CLICK

- PLAYER\_RIGHT\_CLICK

* **PROJECTILE\_HIT\_BLOCK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>

<details>

<summary>You can add a group of blocks, these are the groups:</summary>

```
    ALL_CHESTS,
    ALL_FURNACES,
    ALL_PLANKS,
    ALL_LOGS,
    ALL_STRIPPED_LOGS,
    ALL_STRIPPED_WOODS,
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
    ALL_CONCRETE_POWDERS,
    ALL_GLASS,
    ALL_STAINED_GLASS,
    ALL_SHULKER_BOXES,
    ALL_LEAVES,
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

- **PLAYER\_RECEIVE\_HIT\_BY\_ENTITY** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

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

- **PLAYER\_RECEIVE\_HIT\_BY\_PLAYER** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* **PLAYER\_RECEIVE\_HIT\_GLOBAL** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

- PLAYER\_DEATH

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

- **PLAYER\_BLOCK\_BREAK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* **PLAYER\_BLOCK\_PLACE** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

- PLAYER\_LEFT\_CLICK

* PLAYER\_RIGHT\_CLICK

- **PROJECTILE\_HIT\_BLOCK** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

</details>



## Specifics features depending on the type of activator

The next features only works on specific activators, depending on the feature. For example if the feature requires a block then the activator must be involved with a block. e.g. (PLAYER\_HIT\_ENTITY its not involved with a block, but PLAYER\_BLOCK\_BREAK involved with a block). The same idea with different features, such as for blocks, targets (enemy players), entities, etc.

### Desactive the drops when the activator is triggered.

* Type of activators where the feature works: This feature works on activators that have involved drops, for example:
  * PLAYER\_KILL\_ENTITY
  * PLAYER\_BLOCK\_BREAK
  * PLAYER\_KILL\_PLAYER
  * PLAYER\_FISH
* Info: Boolean value that allows or prevents the vanilla loot to be dropped when breaking blocks or killing mobs. Since its vanilla drops, custom drops from custom mobs e.g. (MythicMobs) will not get affected by this.
* Example:&#x20;

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    desactiveDrops: false
```

### onlyAirClick

* Type of activators where the feature works: This feature works on activators that have involved clicks. Not the action of clicking, which could happen when hitting an entity, or breaking a block, but the event of clicking. For example:
  * PLAYER\_ALL\_CLICK
  * PLAYER\_RIGHT\_CLICK
  * PLAYER\_LEFT\_CLICK
* Description: Boolean feature that restricts the activator so it will only get activated/triggered when the event occurred with clicking only on the air. This means if you clicked on a block the activator won't get triggered. Don't get confuse ! You may think, what happens if I click on a player ? well, its not an event instance of PLAYER\_(CLICK) but that event is instance of PLAYER\_CLICK\_ON\_PLAYER.
* Example:&#x20;

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activators on the activators list
    onlyAirClick: false
</code></pre>

### onlyBlockClick

* Type of activators where the feature works: This feature works on activators that have involved clicks. Not the action of clicking, which could happen when hitting an entity, or breaking a block, but the event of clicking. For example:
  * PLAYER\_ALL\_CLICK
  * PLAYER\_RIGHT\_CLICK
  * PLAYER\_LEFT\_CLICK
* Description: Boolean feature that restricts the activator so it will only get activated/triggered when the event occurred with clicking only in a block. This means if you clicked on the air the activator won't get triggered.
* Example:&#x20;

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    onlyBlockClick: false
```

### detailedClick

* Type of activators where the feature works: This feature works on activators that have involved more than one click, this means PLAYER\_LEFT\_CLICK doesn't enter in this category due its restricted only to one click. For example:
  * PLAYER\_ALL\_CLICK
  * PLAYER\_CLICK\_ON\_ENTITY
  * PLAYER\_CLICK\_ON\_PLAYER
* Info: Type of click restriction to make the activator only work/trigger/activate when the correct click is involved.
  * detailedClick
    * RIGHT: Right click
    * LEFT: Left click
    * RIGHTORLEFT: Right or left click.
* Example:&#x20;

```yaml
activators:
  activator0: # Activator ID, you can create as many activators on the activators list
    detailedClick: LEFT
```

### delay and delayTick

* Type of activators where these features works: This features are exclusive for LOOP activator.
* Info: Delay and delayTick manage sthe behavior of the loop repetitions of the activator.
  * delay: Integer value that represents how many seconds will the loop be. This means, each \<delay> \[time] the loop will trigger again. e.g. (If the delay is 30 seconds then each 30 seconds the activator will trigger)
  * delayTick: Boolean value to set the delay time in ticks, otherwise it is in seconds. (20 ticks = 1 second)
* Example:&#x20;

```yaml
activators:
  activator1: # Activator ID, you can create as many activators on the activators list
    option: LOOP
    delay: 30 #IN SECONDS
    delayInTick: false
```
