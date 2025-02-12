# Item Features

## Basic Settings

Here you will learn about the basic features of the item.

### Material of the item

* Info: The material of the Minecraft item of the Executable Item
* Example: If I want the ExecutableItem to have a base item as DIAMOND then it would be

```yaml
material: DIAMOND
```

* You can check the material list information on this link: [https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html)
* If you want to setup as material of the item a custom head check this link [https://docs.ssomar.com/executableitems/configurations/item-configuration/item-features#head-settings](https://docs.ssomar.com/executableitems/configurations/item-configuration/item-features#head-settings).
* Required for the item to work: YES

### Name or DisplayName of the item

* Info: The display name of the item. Its the visible name.
* Example: If I would like my item to have as display name a red title "Epic Sword" then it would be

```yaml
name: '&cEpic Sword'
```

* If you want to use on your display name HEX Colors you can do this:
  * You have to go to a site where it can help you to choose a color of your choice to get the hex color code. We recommend [https://htmlcolorcodes.com/](https://htmlcolorcodes.com/)
  * Then pick the color of your choice and note down / copy the hex color of it. [Reference](https://imgur.com/a/tNWtA0a)
  * With that hex color code you have to add "#" at the beginning and that is what will be before what you want to color. #\<HEX\_COLOR\_CODE>\<What you want to color>
  * Finally you will have something like **`#DB6725&lPractice`** and it will look with the color you selected [in game](https://imgur.com/a/7umxduF).
* Required for the item to work: YES

### Lore or description of the item

* Info: The lore or description of the item
* Example:

```yaml
lore:
- '&7Insta-Boom Bomb'
- ''
- '&f&lABILITIES:'
- '&f&l - &a&lInsta-Boom &f&l(&3&lRIGHT-CLICK&f&l)'
- '&fRight-Click on a block to use. Can only'
- '&fharvest blocks mined using your bare hands.'
- '&fBlows up a 5x5x5 area from where you used'
- '&fthe bomb. Will mostly blow up the type of block'
- '&fthat you clicked and sometimes the blocks around it.'
```

* Required: YES
* You can use placeholders in the lore. Just keep in mind if you use placeholders outside the plugin and then you add some new contents to the lore like custom enchants, custom text. If one of the placeholders refreshes then everything added outside Ssomar plugins will be deleted. To avoid this you will need not to refresh the lore, but that means that the placeholders will not be updated. You have to choose the one you prefer. To conclude: EXTRA THINGS IN THE LORE means NO REFRESH means NO custom placeholders of EI in the lore please.

{% hint style="info" %}
To leave an empty space between lore lines you can add '' in the config file. If you are editing the lore inside Minecraft using the custom GUI you would need to use '\&f' then.
{% endhint %}

### Glowing effect (enchanted glowing)

* Info: Boolean value that selects if gives the executable item a glow/enchanted effect look.
* Example:&#x20;

```yaml
glow: true
```

* Required: NO (Default: false)

### Disable the enchant glowing

* Info: Its only available in 1.20.5 and above. Boolean value that forces the item to not have the glow effect even if it is enchanted.&#x20;
* Example:&#x20;

```yaml
disableEnchantGlow : true
```

{% hint style="info" %}
TIP: You can also remove the glowing effect from some vanilla items such as the nether star for example.
{% endhint %}



### Display conditions on the lore of the item

* Info: It allows you to display conditions on the lore of the item.
* Example:&#x20;

<figure><img src="../../../.gitbook/assets/Minecraft__1.19.4_-_Multiplayer_3rd-party_Server_2023-07-01_16-33-17.gif" alt=""><figcaption></figcaption></figure>

```yaml
displayConditions:
  playerConditions:
    ifSneaking: true
  worldConditions: {}
  itemConditions: {}
  placeholdersConditions: {}
  enableFeature: true
```

* Required: NO&#x20;

### Durability of the item

* Info: Select the durability value of the item.
  * For versions 1.20.5— The durability value must be  equal or below the maximum vanilla durability for the item selected.
  * Example:&#x20;
    * <pre class="language-yaml"><code class="lang-yaml"><strong>durability: 150   
      </strong></code></pre>
  * For versions 1.20.5++ The durability option can be customized, enabling new features such as the sync of usage and the durability value. And allow to select custom max durability.
  * Example:
    * ```yaml
      isDurabilityBasedOnUsage: true
      maxDurability: 20 
      durability: 19
      ```
* Required: NO (Default: Max Durability of the Material

### Enchantments of the item

* Info: Sets the initial enchantments the executable item will have when given.
* Example:

```yaml
enchantments:
  enchantment1: #ID Of this enchantment, you can add as many as you want
    enchantment: sharpness
    level: 1
```

* Required: NO

### Unbreakable

* Info: Boolean value that selects if the executable item will be unbreakable or not
* Example:&#x20;

```yaml
unbreakable: true
```

* Required: NO (Default: false)

### Atributtes of the item feature (1.12++)

* Info: You can select the attributes of the ExecutableItem.
  * Attribute: The type of attribute. List here [https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/attribute/Attribute.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/attribute/Attribute.html)
  * UUID: Its a code that minecraft needs to assign the attribute modifiers. You can ignore it.
  * Name: Its the display name of the Attribute Modifier. Its useful for you to write what it does. It doesn't affect in anything more than visualizing it in the GUI.
  * Operation: Type of operation that the AttributeModifier will do. List here [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/AttributeModifier.Operation.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/AttributeModifier.Operation.html)
  * Amount: The value for the AttributeModifier, it will be applied to the attribute using the operation selected.
  * Slot: The slot that the AttributeModifier will work on.
  * Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>attributes:
</strong>  attribute1: #Id of this attribute, you can add as many as you want
    attribute: GENERIC_ARMOR
    name: '&#x26;eDefault name'
    uuid: 8d6b9b6a-c84d-4c76-9b4d-81a1f44a04a0
    amount: 1.0
    operation: ADD_NUMBER
    slot: HAND
</code></pre>

{% hint style="info" %}
**If you are using 1.12 version you will need to follow these steps:**

* This process requires the premium version of EI.
* Generate your item with attributes on a website. We suggest [https://mapmaking.fr/give1.12/](https://mapmaking.fr/give1.12/)
* Then give the item to yourself inside Minecraft
* While holding it on your hand run the /ei create \<id> command
* And that's it ! Now your EI has the attributes imported automatically.
{% endhint %}

* Required: NO

### **Keep default attributes**

* Info: Boolean value for keeping or not the default attribute of the item.
* Example:

```yaml
keepDefaultAttributes: false
```

* On this link there is a tutorial for attributes, and its features.

{% embed url="https://youtu.be/HqyF0QBYIY4" %}

### **ignoreKeepDefaultAttributesFeature:**&#x20;

* **In**fo: It ignores the setting of keep default attributes. Its useful for the third case in this table explanation:

<table><thead><tr><th width="355">Before 1.21</th><th width="347">After 1.21</th></tr></thead><tbody><tr><td><p>EI STONE_PICKAXE </p><ul><li>keepDefaultAttributes YES </li><li>No other attributes </li><li><p>When in Main Hand:</p><ul><li>3 attack damage (green)</li><li>1.2 attack speed (green)</li></ul></li></ul></td><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes YES</li><li>No other attributes </li><li><p>When in Main Hand:</p><ul><li>3 attack damage (green)</li><li>1.2 attack speed (green)</li></ul></li></ul></td></tr><tr><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes NO </li><li>No other attributes </li><li>When in Main Hand</li></ul></td><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes NO</li><li>No other attributes</li><li>NOTHING</li></ul></td></tr><tr><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes YES </li><li>1 armor attribute </li><li><p>When in Main Hand:</p><ul><li>+ 2 attack damage (blue)</li><li>-2.8 attack speed (red)</li><li>1 armor (blue)</li></ul></li></ul></td><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes YES </li><li>1 armor attribute </li><li><p>When in Main Hand:</p><ul><li>3 attack damage (green)</li><li>1.2 attack speed (green)</li><li>1 armor (blue)</li></ul></li></ul></td></tr><tr><td><p>EI STONE_PICKAXE </p><ul><li>keepDefaultAttributes NO</li><li>1 armor attribute</li><li><p>When in Main Hand:</p><ul><li>1 armor (blue)</li></ul></li></ul></td><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes NO </li><li>1 armor attribute </li><li><p>When in Main Hand:</p><ul><li>1 armor (blue)</li></ul></li></ul></td></tr></tbody></table>

* Example:

```yaml
ignoreKeepDefaultAttributesFeature: true
```

### <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> Custom model data (1.14++)

* Info: Integer to set the value of the customModelData feature of the item. Useful to create different textures for an item.
* Example:&#x20;

```yaml
customModelData: 2232
```

* Required: NO
* Tutorial: [https://docs.ssomar.com/executableitems/questions-or-guides/premium-custom-textures](https://docs.ssomar.com/executableitems/questions-or-guides/premium-custom-textures)

### Item Rarity features (1.20.5+)

* Info: Rarity is a vanilla statistic applied to items and blocks to signify their value and ease in obtaining. It has no effect on gameplay whatsoever. There are four rarity tiers: Common, Uncommon, Rare, and Epic.
  * enableRarity: Boolean that represents if the feature is enabled or not
  * rarity: Type of rarity
* Example:

```yaml
itemRarity:
  enableRarity: false
  rarity: COMMON
```

### Equippable features

* Info: This section configures the behavior of an equippable item. When enabled, the item can be equipped into a designated slot, optionally triggering a sound effect. You can also specify a custom model for the equipped item, define whether it takes damage when the wearer is hurt, and set flags to allow or restrict swapping and disposal. Additionally, you can restrict which entities are allowed to equip the item.
  * enable: Set to true to enable equipping for this item
  * slot: The equipment slot (e.g., BODY, HEAD) where the item is equipped
  * enableSound: Boolean to play a sound when the item is equipped
  * sound: Sound effect to play when equipped
  * equipModel: Optional custom model for the equipped item (e.g., "mynamespace:mymodel")
  * cameraOverlay: Optional custom camera overlay when the item is equipped
  * isDamageableOnHurt: Boolean that selects if the item loses durability when the wearer is hurt
  * isDispensable: Boolean that selects if the item can be disposed of (removed/dropped)
  * isSwappable: Boolean that selects if the item can be swapped with another item
  * allowedEntities: List of entities permitted to equip this item
* Example:

```yaml
equippableFeatures:
    enable: false
    slot: BODY
    enableSound: false
    sound: ITEM_ARMOR_EQUIP_DIAMOND

    equipModel: "" # Example: "mynamespace:mymodel"
    cameraOverlay: "" # Example: "mynamespace:mymodel"

    isDamageableOnHurt: false
    isDispensable: true
    isSwappable: true

    allowedEntities:
     - PLAYER
```

### Repairable features

* Info: Features related to when the ExecutableItem is reppaired.
  * enable: Boolean value that selects if the feature is enabled or not
  * repairCost: Integer value that represents the cost of repairing it on the Anvil
* Example:

```yaml
repairableFeatures:
    enable: false
    repairCost: 2 
```

### Glider

* Info: Feature to allow gliding with the item as you would normally do with the vanilla item "elytra".
* Example:

```yaml
glider: false
```

#### itemModel&#x20;

* Info: To customize the item model

```yaml
itemModel: "" # "mynamespace:mymodel"
```

#### tooltipModel

* Info: To customize the item tooltip model

```yaml
tootipModel: "" # "mynamespace:mymodel"
```

### Tool Rules (1.20.5++)

Info: Here you can select the rules of the tools.

#### Enable

* Info: Boolean value to select if the Tool Rules are enabled or not.
* Example:

```yaml
toolRules:
  enable: true
```

#### Default mining speed

* Info: Float value to set the default mining speed of the ExecutableItem.
* Example:

```yaml
toolRules:
  enable: true
  defaultMiningSpeed: 1.0
```

#### Damage per block break

* Info: Integer value to set as the durability value which will be taken after the ExecutableItem breaks a block.&#x20;
* Example:

```yaml
toolRules:
  enable: false
  damagePerBlock: 1
```

#### Specific tool rules

* Info: You can select the mining speed, droppable for certain blocks with the ExecutableItem, in order of tool customization.
  * miningSpeed: Float value to set the minig speed of the ExecutableItem for the selected blocks on the tool rule.
  * correctForDrops: Boolean value that represents if the block will be dropped or not using the ExecutableItems.
  * blocks: List of BLOCKS to apply the tool rules to.
* Example:

```yaml
toolRules:
  toolRule0: #ID Of this tool rule, you can add as many as you want
    miningSpeed: 1.0
    correctForDrops: true
    blocks:
    - STONE
  enable: true
```

### Features related to the item dropped

Here you will learn about features that are only visible when the item is dropped on the ground.

#### Glowing on drop

* Info: When the item is dropped, it has a glow effect
* Example:&#x20;

```yaml
dropOptions:
  glowDrop: false
```

* Required: NO (Default: false)

#### Glowing color when dropped

* Info: If the item has glowEffect enabled then its possible to select the color of the glowing effect when dropped.
* Possible colours: [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/ChatColor.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/ChatColor.html)
* Example:

```yaml
dropOptions:
  glowDrop: false
  glowDropColor: WHITE
```

#### Display name when the item is dropped

* Info: Select if the item will show the display name displayed as a floating text when it is dropped.
* Example:&#x20;

```yaml
dropOptions:
  displayNameDrop: true
```

* Required: NO (Default: false)



## NBT Tags

#### NBT TAGS SUPPORT <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

Require this plugin [**NBTAPI**](https://www.spigotmc.org/resources/nbt-api.7939/)

* Info: Insert your custom nbt tags in your ExecutableItem
* Example:

```yaml
nbt:
 '1':
    type: INT
    key: 'MyKeyTag'
    value: 3
 '2':
    type: STRING
    key: 'MyOtherKey'
    value: 'myValue'
 '3':
    type: BOOLEAN
    key: 'KeyKeyKeykey'
    value: true
 '4':
    type: DOUBLE
    key: 'KeyKeyKeykeykeykey'
    value: 0.5
 '5':
    type: BYTE
    key: 'IsCustom'
    value: 1
 '6':
    key: ExtraAttributes
    type: COMPOUND
    value:
      nbt:
        '0':
          key: id
          type: STRING
          value: TRIAL_OF_THE_SUN_GOD
 '7':
    key: CanDestroy
    type: STRING_LIST
    value:
    - minecraft:stone
```

* Different Type: `BOOLEAN`, `BOOL` | `STRING`, `STR` | `INTEGER`, `INT` | `DOUBLE |` `COUMPOUND`
* Example value: `true`, `false` | `blabblabla`, `mystringhere` | `4`, `2000` | `0.25`, `0.6`
* Required: NO (Default: false)



#### BUKKIT TAGS

* This is what it will look like in the item's config

```yaml
tags:
 - mytag:blabla1
 - myothertag:blabla2
```

In game it will be represented in PublicBukkitValues, like that

```yaml
executableitems:mytag:blabla1
executableitems:myothertag:blabla2
```

## Hiders Settings

```yaml
hiders:
  hideEnchantments: false
  hideUnbreakable: false
  hideAttributes: false
  hidePotionEffects: false
  hideUsage: false
  hideDye: false
  hideArmorTrim: false
  hidePlacedOn: false
  hideDestroys: false
```

#### HIDE ENCHANTMENTS

* Info: Hides the enchantments on the executable item in the lore while still being functional
* Required: NO (Default: false)

#### HIDE ATTRIBUTES

* Info: Hides the attributes on the executable item in the lore while still being functional
* Required: NO (Default: false)

#### HIDE UNBREAKABLE

* Info: Hides the unbreakable attribute on the lore of the Executable Item
* Required: NO (Default: false)

#### HIDE POTION/BANNER TAGS

* Info: Hides potion and banner descriptions in their lore
* Required: NO (Default: false)

#### HIDE USAGE

* Info: Hides the usage of the item
* Required: NO

{% hint style="success" %}
It will hide the text "Remaining usage: ..." from the lore, but if you want you can set the usage again in the lore with the placeholder **%usage%**
{% endhint %}

## Custom usage Settings



#### USAGE

* Info: The value of how many times you can use it. Mostly used for the usage modification function of activators.
* Example:&#x20;

```yaml
usage: 1
```

For infinite items use:

```yaml
usage: -1
```

* Required: NO (Default: 0)

{% hint style="info" %}
usage: 0 -> equals usage: 1 + the option hideUsage turn on true
{% endhint %}

{% hint style="success" %}
You are able to hide the usage text : "Remaining use: ..." from the lore, check the setting [hideUsage](item-features.md#hide-usage-1.14+).
{% endhint %}

#### USAGE LIMIT <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Info: The value to how large the usage can only be. (Value cannot be 0)
* Example:&#x20;

```yaml
usageLimit: 600
```

* Required: NO (Default: -1)

#### USE PER DAY

* Info: The limit to how many times you can use the item each day (In real life)
* Example:&#x20;

```yaml
usePerDay: 200
```

* Required: NO (Default: -1)



## Food Settings (1.20.5++)

```
food:
  nutrition: 1
  saturation: 1
  isMeat: false
  canAlwaysEat: false
  eatSeconds: 
```

#### Nutrition

* Info: Set the nutriniotal value of the item

#### Saturation

* Info: The saturation level that the item gives

#### isMeat

* Info: If you can eat the item

#### canAlwaysEat

* Info: If you can always eat the item or only when hunger

#### eatSeconds

* Info: The amount of seconds it takes to eat the item





## Potion Settings

#### POTION SETTINGS

*   Info: Options for the potion effects

    * color: Pick a color on the website below and copy/paste the **MapInfo Color**&#x20;



{% embed url="https://www.tydac.ch/color" %}

* potionType:

{% embed url="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionType.html" %}

* potionEffectType:&#x20;

{% embed url="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffectType.html" %}

* potionExtended: Boost of time (generally from 3m to 8m on vanilla potions)
* potionUpgrade: Boost of level (generally from level I to level II on vanilla potions)
* duration: Duration of the effect in seconds.
* Example:

```yaml
potionSettings:
  potionColor: 56575
  potionType: WATER
  potionExtended: false
  potionUpgraded: false
  potionEffects:
    pEffect1:
      isAmbient: false
      duration: 200
      potionEffectType: REGENERATION
      amplifier: 2
      hasParticles: false
      hasIcon: false
    pEffect0:
      isAmbient: true
      duration: 30
      potionEffectType: HEAL
      amplifier: 1
      hasParticles: true
      hasIcon: true
```

* **NOTE: IF YOU ARE TRYING TO CREATE AN ITEM THAT GIVES EFFECTS TO THE USER OF THE ITEM, DON'T USE THIS.** [**USE THE LOOP ACTIVATOR INSTEAD.**](https://github.com/ssomar1607/ExecutableItems/wiki/%E2%9E%A4-Activators#loop--premium-)

## Armor Settings

#### ARMOR SETTINGS

*   Info: Options for the color of the leather armor executable items.

    * color: Pick a color on the website below and copy/paste the **MapInfo Color**&#x20;



{% embed url="https://www.tydac.ch/color" %}

* Example:

```yaml
armorColor: 56575
```

* Then put this at the bottom of the item config, save and reload the plugin

## Head Settings

{% hint style="success" %}
If you want use Head material for your ExecutableItem, you are in the good part !
{% endhint %}

### Without plugin ?

{% hint style="danger" %}
The without plugin method requires to edit direclty your item FILE, it's not possible IN-GAME !
{% endhint %}

#### Custom Head Texture (Only at version 1.13+)

* Instructions:

- [ ] Set the `material: PLAYER_HEAD`
- [ ] Visit a custom heads site similar this one

{% embed url="https://minecraft-heads.com/custom-heads" %}

* [ ] Select an HEAD
* [ ] Get the "Value" of the head. [Reference](https://imgur.com/a/VJuFzpv)
* [ ] Put the value like that :  `headValue: VALUE`
* [ ] Then you can save (CTRL + S) your file and reload the plugin

Example:

```yaml
headValue: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvMTk4ZGY0MmY0NzdmMjEzZmY1ZTlkN2ZhNWE0Y2M0YTY5ZjIwZDljZWYyYjkwYzRhZTRmMjliZDE3Mjg3YjUifX19
```

### With a Head plugin ? <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

#### HEAD DATABASE  (1.12+)

* Info: Option to use head database custom heads (No need to modify the material with this method)
  * `headDBID:` The id of the head. [Reference](https://imgur.com/a/FhywTlS)
* Example:

```yaml
headDBID: 44328
```

{% hint style="info" %}
**You need to have one of theses plugins below**
{% endhint %}

* **Premium** [**Head Database**](https://www.spigotmc.org/resources/head-database.14280/) **plugin**
* **Free** [**Head database**](https://www.spigotmc.org/resources/headdb-head-menu-auto-update-free.84967/) **plugin**





## Custom Settings

#### whitelistedWorlds

* Info: Prevents or allow the players from using the EI in certain worlds
* Example:

```yaml
whitelistedWorlds:
- ZombieSurvivalWorld_the_end
- '!ApocalypseWorld'
```

#### STORE ITEM INFO

* Info: Stores information in the item itself like Owner of the item and many more in the future. Also needed for the ifOwnerOfTheEI condition to work properly.
* Example:

```yaml
storeItemInfo: false
```

* Required: NO (Default: true)

#### CAN BE USED ONLY BY THE OWNER

* Info: The player who first got the item is the only one who can use it
* Example:&#x20;

```yaml
canBeUsedOnlyByTheOwner: false
```

* Required: NO (Default: false)

#### KEEP ITEM ON DEATH

* Info: Keeps the item on the player's inventory even after death
* Example:&#x20;

```yaml
keepItemOnDeath: true
```

* Required: NO (Default: false)

{% hint style="info" %}
Its compatible with worldguard keepInventory and vanilla keepInventory gamerule
{% endhint %}

#### DISABLE STACK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Info: Prevents EI items from stacking
* Example:&#x20;

```yaml
disableStack: true
```

* Required: NO (Default: false)



#### customStackSize<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> (1.20.5 ++)

* Info: Set the max of stacking of an item
* Example:&#x20;

```yaml
customStackSize: 32
```

* Required: NO (Default: 0)



## Variables Settings

{% hint style="danger" %}
<mark style="color:red;background-color:red;">**NEVER TYPE "id" or "usage" IN THE ID OF A VARIABLE AS IT MAY CAUSE ISSUES AND BREAK THE EI ITEM**</mark>
{% endhint %}

#### ITEM VARIABLES&#x20;

* Info: Defines what variables are inside your item. (Number or String)
* [Link to how to setup variables in-game](https://github.com/ssomar1607/ExecutableItems/wiki/Variables#how-to-setup-variables-ingame)
* Example:

```yaml
variables:
  var0:
    variableName: x
    type: NUMBER
    default: 0.0
  var1:
    variableName: myVar
    default: hello
    type: STRING
```

* Required: NO
* [Link to how to create an example item that uses variables](https://docs.ssomar.com/executableitems/tutorials/items/delayed-teleport-towards-saved-location)

## Custom give first join Settings

```yaml
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
```

#### GIVE FIRST JOIN

* Info: Gives the players that has joined the server for the first time the executable item
* Required: NO (Default: false)

#### GIVE SLOT

* Info: (GIVE FIRST JOIN MUST BE SET TO TRUE) Sets the slot number of where the ei item will be given when a new player joins.&#x20;
* Required: NO (Default: 0)

## Item Recognition Settings



#### ITEM RECOGNITION <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> (1.14+)

* Info: Considers anything that isn't EI as EI
* Example:

```yaml
recognitions:
- NAME
- MATERIAL
- LORE
```

* `HIDE_ATTRIBUTE` : (By default), The items are recognize with an hide attribute (injected on the item when you give it)
* `NAME`: Checks if the item's name is exactly the same as the EI item's name
* `MATERIAL`: Checks if the item's material type is exactly the same as the EI's material
* `LORE`: Check if the item's lore is exactly the same as the EI's lore
* Example Scenarios:
  * If an EI item only has the item recognition of `MATERIAL` and is a DIAMOND, all the diamonds that exist in the server will be an EI item
  * If an EI item only has the item recognition of `NAME` and is named "\&dAngle", if you attempt to use any item with the name, "\&dAngle", it will be considered as an EI item. BUT if the name was "\&eAngle", it will not work.
  * If an EI item only has the item recognition of `LORE`, an item will only be considered as an EI if the item EXACTLY has the same color codes on lore lines and every bit of capitalizing and lowercasing of letters and characters.
  * If an EI item only has the item recognition of `MATERIAL` and `NAME`, the items must have the EXACT NAME and MATERIAL of the EI item for the item to be considered as an EI item.

{% hint style="warning" %}
**KEEP IN MIND:**

* If the item recognition's option is set to **material only**, **only use it on one EI item.**
* Because for example, if there are 2 EI items with the material of a diamond block and the item recognition is both material only, the first one in the alphabetic order will be the one who will have the most priority.
{% endhint %}

## Container Features

### isLocked <a href="#islocked" id="islocked"></a>

* If the container is locked or not
