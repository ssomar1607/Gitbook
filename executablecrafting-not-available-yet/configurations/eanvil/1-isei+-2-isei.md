# (1)IsEI+(2)IsEI

{% hint style="info" %}
For the explanation this information will be used

* ![](<../../../.gitbook/assets/image (1).png>)
* NonEI: An item that is not an ExecutableItem, it doesn't mean its vanilla, it can be whatever item with whatever nbt tag but it <mark style="color:red;">**must not be**</mark> an ExecutableItem
* IsEI: An item that is a ExecutableItem, again, it doesn't matter if it has more nbt tag or less, it can be whatever but <mark style="color:green;">**it must be**</mark> an ExecutableItem.
* (id): It refers to the position of the anvil
* \<item.(id)> It refers the item that is on the id position


{% endhint %}

## (1)IsEI+(2)IsEI

ExecutableItem works with a PublicBukkitValue, that is unique and can't be replaced, so "executableitems-id":"\<ID>" can't have two values, so it is not possible to have 2 EI ID(s) in the same EI, so why is this option ? Well, in this option what you can do is apply changes to \<item.1> using commands in \<item.2>, such as the next commands:



For all the commands explained we will use as **example** of \<item.1> an EI DiamondSword with:

<pre class="language-yaml"><code class="lang-yaml"><strong>usage: 1
</strong><strong>lore:
</strong>- '§eLevel: %var_level_int%'
- '§eUsage: %usage%'
variables:
  var0:
    variableName: level
    type: NUMBER
    default: 1.0
</code></pre>

<figure><img src="../../../.gitbook/assets/image (10).png" alt="" width="556"><figcaption></figcaption></figure>

<details>

<summary>&#x3C;item.1> (Full diamond sword) configuration</summary>

```yaml
name: '&6Test sword :D'
glow: false
disableEnchantGlide: false
lore:
- '§eLevel: %var_level_int%'
- '§eUsage: %usage%'
material: DIAMOND_SWORD
disableStack: false
keepItemOnDeath: false
canBeUsedOnlyByTheOwner: false
cancelEventIfNotOwner: false
onlyOwnerBlackListedActivators: []
storeItemInfo: false
unbreakable: false
usage: 1
usageLimit: -1
isDurabilityBasedOnUsage: false
cancelEventIfNoPermission: false
whitelistedWorlds: []
recognitions: []
keepDefaultAttributes: false
ignoreKeepDefaultAttributesFeature: true
config_5: true
config_update: true
dropOptions:
  glowDrop: false
  glowDropColor: WHITE
  displayNameDrop: false
hiders:
  hideEnchantments: false
  hideUnbreakable: false
  hideAttributes: false
  hideUsage: true
  hideDestroys: false
  hidePlacedOn: false
  hideDye: false
  hideArmorTrim: false
  hideAdditionalTooltip: false
enchantments: {}
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
restrictions: {}
variables:
  var0:
    variableName: level
    type: NUMBER
    default: 1.0
activators: {}
displayConditions:
  playerConditions: {}
  worldConditions: {}
  itemConditions: {}
  placeholdersConditions: {}
  enableFeature: false
food:
  nutrition: 1
  saturation: 1
  isMeat: false
  canAlwaysEat: false
  eatSeconds: 1
itemRarity:
  enableRarity: false
  rarity: COMMON
attributes: {}

```

</details>

## Commands

### Modify the EI Usage

```
- EC EANVIL USAGE <SET/MODIFICATION> <VALUE>
```

* Example:
  *

      <figure><img src="../../../.gitbook/assets/image (9).png" alt="" width="375"><figcaption></figcaption></figure>
  * <pre><code><strong>- EC EANVIL USAGE MODIFICATION 100
    </strong></code></pre>

<details>

<summary>&#x3C;item.2> (Usage increaser) configuration</summary>

```yaml
name: '&6Usage increaser'
glow: false
disableEnchantGlide: false
lore:
- §eAdd this item to increase the usage
- §eof your item by 100.
material: NETHER_STAR
disableStack: false
keepItemOnDeath: false
canBeUsedOnlyByTheOwner: false
cancelEventIfNotOwner: false
onlyOwnerBlackListedActivators: []
storeItemInfo: false
unbreakable: false
usage: 1
usageLimit: -1
isDurabilityBasedOnUsage: false
cancelEventIfNoPermission: false
whitelistedWorlds: []
recognitions: []
keepDefaultAttributes: false
ignoreKeepDefaultAttributesFeature: true
config_5: true
config_update: true
dropOptions:
  glowDrop: false
  glowDropColor: WHITE
  displayNameDrop: false
hiders:
  hideEnchantments: false
  hideUnbreakable: false
  hideAttributes: false
  hideUsage: true
  hideDestroys: false
  hidePlacedOn: false
  hideDye: false
  hideArmorTrim: false
  hideAdditionalTooltip: false
enchantments: {}
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
restrictions: {}
variables: {}
activators:
  ECANVIL:
    name: '&eActivator'
    option: CUSTOM_TRIGGER
    scheduleFeatures:
      startDate: '1700-01-01 00:00:00'
      endDate: '3000-01-01 00:00:00'
      when: []
    usageModification: 0
    cancelEvent: false
    noActivatorRunIfTheEventIsCancelled: false
    silenceOutput: false
    autoUpdateItem: false
    updateName: true
    updateLore: true
    updateDurability: false
    updateAttributes: false
    updateEnchants: false
    updateCustomModelData: false
    updateArmorSettings: false
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
      pauseWhenOffline: false
      pausePlaceholdersConditions: {}
    globalCooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
      pauseWhenOffline: false
      pausePlaceholdersConditions: {}
    otherEICooldowns: {}
    requiredItems: {}
    requiredExecutableItems: {}
    requiredMagics: {}
    detailedSlots:
    - -1
    commands:
    - EC EANVIL USAGE MODIFICATION 100
    playerConditions: {}
    worldConditions: {}
    itemConditions: {}
    customConditions:
      ifNeedPlayerConfirmationCancel: false
    placeholdersConditions: {}
    variablesModification: {}
displayConditions:
  playerConditions: {}
  worldConditions: {}
  itemConditions: {}
  placeholdersConditions: {}
  enableFeature: false
food:
  nutrition: 1
  saturation: 1
  isMeat: false
  canAlwaysEat: false
  eatSeconds: 1
itemRarity:
  enableRarity: false
  rarity: COMMON
attributes: {}

```

</details>

*   Result:

    <figure><img src="../../../.gitbook/assets/image (11).png" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="info" %}
With this you could create for example

* An item that increases the usage so it can repair EI Items
* An item that sets the usage to certain value
{% endhint %}

***

### Modify an EI Variable (CONDITIONS WILL BE ADDED SOON)

```
EC EANVIL VARIABLE:<Name of variable> <SET/MODIFICATION> <VALUE>
```

* Example:
  *

      <figure><img src="../../../.gitbook/assets/image (12).png" alt="" width="370"><figcaption></figcaption></figure>

      * ```
        - 'EC EANVIL VARIABLE:level MODIFICATION 1'
        ```

<details>

<summary>&#x3C;item.2> (Level up) configuration</summary>

```yaml
name: '&eLevel up'
glow: false
disableEnchantGlide: false
lore:
- §fAdd this to your item to
- §fincrease the level
material: STRING
disableStack: false
keepItemOnDeath: false
canBeUsedOnlyByTheOwner: false
cancelEventIfNotOwner: false
onlyOwnerBlackListedActivators: []
storeItemInfo: false
unbreakable: false
usage: 0
usageLimit: -1
isDurabilityBasedOnUsage: false
cancelEventIfNoPermission: false
whitelistedWorlds: []
recognitions: []
keepDefaultAttributes: false
ignoreKeepDefaultAttributesFeature: true
config_5: true
config_update: true
dropOptions:
  glowDrop: false
  glowDropColor: WHITE
  displayNameDrop: false
hiders:
  hideEnchantments: false
  hideUnbreakable: false
  hideAttributes: false
  hideUsage: false
  hideDestroys: false
  hidePlacedOn: false
  hideDye: false
  hideArmorTrim: false
  hideAdditionalTooltip: false
enchantments: {}
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
restrictions: {}
variables: {}
activators:
  ECANVIL:
    name: '&eActivator'
    option: CUSTOM_TRIGGER
    scheduleFeatures:
      startDate: '1700-01-01 00:00:00'
      endDate: '3000-01-01 00:00:00'
      when: []
    usageModification: 0
    cancelEvent: false
    noActivatorRunIfTheEventIsCancelled: false
    silenceOutput: false
    autoUpdateItem: false
    updateName: true
    updateLore: true
    updateDurability: false
    updateAttributes: false
    updateEnchants: false
    updateCustomModelData: false
    updateArmorSettings: false
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
      pauseWhenOffline: false
      pausePlaceholdersConditions: {}
    globalCooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
      pauseWhenOffline: false
      pausePlaceholdersConditions: {}
    otherEICooldowns: {}
    requiredItems: {}
    requiredExecutableItems: {}
    requiredMagics: {}
    detailedSlots:
    - -1
    commands:
    - 'EC EANVIL VARIABLE:level MODIFICATION 1'
    playerConditions: {}
    worldConditions: {}
    itemConditions: {}
    customConditions:
      ifNeedPlayerConfirmationCancel: false
    placeholdersConditions: {}
    variablesModification: {}
displayConditions:
  playerConditions: {}
  worldConditions: {}
  itemConditions: {}
  placeholdersConditions: {}
  enableFeature: false
food:
  nutrition: 1
  saturation: 1
  isMeat: false
  canAlwaysEat: false
  eatSeconds: 1
itemRarity:
  enableRarity: false
  rarity: COMMON
attributes: {}

```

</details>

*   Result:

    <figure><img src="../../../.gitbook/assets/image (14).png" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="info" %}
With this you could create for example:

* Item that levels up your items
* Items that increases the damage of your item
  * let's say you have a variable called damagevalue and player hit activators with the command DAMAGE %var\_damagevalue%
* Item that triggers an ability
  * You can hide activators in your items, and you can toggle them using this method, for example "certain ability" that only works if "x" variable is 1, and by default is 0, you can then create an item called "Explosion arrows" that when its added to your bows their variables "x" set to 1 so now that activator works.
{% endhint %}

***

### Modify the customModelData

* ```
  EC EANVIL CUSTOMMODELDATA <SET/MODIFICATION> <VALUE>
  ```

**Explanation in todo list, but its the same idea than the previous commands, I will try to add the explanation with photos in the next days**

&#x20;
