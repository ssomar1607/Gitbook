# Item Features

{% hint style="info" %}
**Usage of HEX Colors in 1.16**

* Instructions:
  * Go to a site where it can help you choose a color of your choice for the hex color code. I recommend [this.](https://htmlcolorcodes.com/)
  * Pick a color of your choice and note down the hex color of it. [Reference](https://imgur.com/a/tNWtA0a)
  * Add # on the beginning of the hex code and this is what you will type in-game (`#DB6725`)
  * **`#DB6725&lPractice`** [ingame](https://imgur.com/a/7umxduF) look
{% endhint %}

## Basic Settings

#### MATERIAL

* Info: The base Minecraft item of the executable item
* Example:&#x20;

```yaml
material: DIAMOND
```

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html" %}

* For the head settings [**Refer to here**](item-features.md#head-settings).
* Required: YES

#### NAME

* Info: The name of the item
* Example:&#x20;

```yaml
name: '&cEpic Sword'
```

* For 1.16 HEX, refer to the information at the top of this page.
* Required: YES

#### LORE

* Info: The lore of the item
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
* Placeholders that you can use in the lore, %player%, [%usage%](item-features.md#hide-usage-1.14+), and the placeholders of your custom variables.\
  (EXCEPTION) If you allow your player to add some new contents to the lore like custom enchants, custom text. If I refresh it will delete it. So to not delete it, I will not refresh the lore. But, If I don't refresh the lore, it means that the custom placeholders in lore (%usage% and variables placeholders) will not be updated.\
  To conclude: EXTRA THINGS IN THE LORE = NO REFRESH = NO custom placeholders of EI in the lore please.

{% hint style="info" %}
As a pro tip you can leave an empty space using the GUI tiping "\&f" without the "".
{% endhint %}

#### GLOW

* Info: Gives the executable item a glow/enchanted look.
* Example:&#x20;

```yaml
glow: true
```

* Required: NO (Default: false)

#### GLOW DROP / GLOW DROP COLOR

* Info: When the item is dropped, it has a glow effect
* Possible colours:

{% embed url="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/ChatColor.html" %}

* Example:&#x20;

```yaml
glowEffect: true
glowDropColor: DARK_BLUE
```

* Required: NO (Default: false)

#### DISPLAY NAME ON DROP

* Info: Displays the custom name of the item when it is dropped.

![](https://media.discordapp.net/attachments/922829586427957298/976411048498307072/unknown.png)

* Example:&#x20;

```yaml
displayNameOnDrop: true
```

* Required: NO (Default: false)



#### DISPLAY CONDITIONS

* Info: Allows you to display conditions on the lore.
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

#### DURABILITY

* Info: Allows you to customize the durability of the EI item equal or below it's maximum vanilla durability
* Example:&#x20;

```yaml
durability: 150
```

* Required: NO (Default: Max Durability of the Material

#### ENCHANTMENTS

* Info: Sets the enchantments the executable item will have
* Example:

```yaml
enchantments:
  enchantment1:
    enchantment: sharpness
    level: 1
```

* Required: NO

#### UNBREAKABLE

* Info: Whether the executable item will be unbreakable or not
* Example:&#x20;

```yaml
unbreakable: true
```

* Required: NO (Default: false)

#### ATTRIBUTES (1.12+)

{% hint style="info" %}
**(For 1.12 ONLY)** (Other versions : check below :smile:)

**Attributes** are now available in **1.12** ! (<mark style="color:orange;">**It requires the premium version**</mark>)

Generate your item with attributes on a website like that **https://mapmaking.fr/give1.12/** then give you the item to you, take it in your hand and do **/ei create** it will import them automatically.
{% endhint %}

* Info: Sets the item's vanilla attributes
  * Attribute: To what kind of vanilla attribute it will be. [Reference](https://minecraft.fandom.com/wiki/Attribute#Vanilla\_modifiers)

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/attribute/Attribute.html" %}

* UUID: "Code" For the Attribute Modifiers (IGNORE THIS)
* Name: Name of the modifier (Doesn't do anything new)
* Operation:&#x20;

{% embed url="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/AttributeModifier.Operation.html" %}

* Amount: The value for the attribute. Negative value can be used.
* Slot: To which slot the attribute will work
* Example:

```yaml
attributes:
  attribute1:
    attribute: GENERIC_ARMOR
    name: '&eDefault name'
    uuid: 8d6b9b6a-c84d-4c76-9b4d-81a1f44a04a0
    amount: 1.0
    operation: ADD_NUMBER
    slot: HAND
```

* Required: NO

#### CUSTOM MODEL DATA <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> (1.14+)

* Info: Sets the Custom Model Data of the item
* Example:&#x20;

```yaml
customModelData: 2232
```

* Required: NO
* Tutorial:

{% content-ref url="../../questions-or-guides/premium-custom-textures/" %}
[premium-custom-textures](../../questions-or-guides/premium-custom-textures/)
{% endcontent-ref %}

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

<!---->

* [ ] Set the `material: PLAYER_HEAD`
* [ ] Visit a custom heads site similar this one

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

#### DISABLED WORLDS

* Info: Prevents players from using the executable item and its activators completely.
* Example:

```yaml
disable-world:
- world
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

#### DISABLE STACK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Info: Prevents EI items from stacking
* Example:&#x20;

```yaml
disableStack: true
```

* Required: NO (Default: false)

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
