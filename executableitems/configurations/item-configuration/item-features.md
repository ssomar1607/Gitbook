# Item Features

List of item features, these are the first thing you should set up on your item.

* Starred features ⭐ are for premium version.

### Material of the item

* Info: The material of the Minecraft item of the Executable Item
* Example: If I want the ExecutableItem to have a base item as DIAMOND then it would be

```yaml
material: DIAMOND
```

* You can check the material list information on this link: [https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html)
* If you want to setup as material of the item a custom head check this link [https://docs.ssomar.com/executableitems/configurations/item-configuration/item-features#head-settings](https://docs.ssomar.com/executableitems/configurations/item-configuration/item-features#head-settings).

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

* You can use placeholders in the lore. Just keep in mind if you use placeholders outside the plugin and then you add some new contents to the lore like custom enchants, custom text. If one of the placeholders refreshes then everything added outside Ssomar plugins will be deleted. To avoid this you will need not to refresh the lore, but that means that the placeholders will not be updated. You have to choose the one you prefer. To conclude: EXTRA THINGS IN THE LORE means NO REFRESH means NO custom placeholders of EI in the lore please.

{% hint style="info" %}
To leave an empty space between lore lines you can add '' in the config file. If you are editing the lore inside Minecraft using the custom GUI you would need to use '\&f' then.
{% endhint %}

{% hint style="info" %}
For ExecutableItems free there is a line with "Made with ExecutableItems": It cant be removed, its the counterpart of the update of increasing the amount of items from 25 to 500.
{% endhint %}

### Glowing effect (enchanted glowing)

* Info: Boolean value that selects if gives the executable item a glow/enchanted effect look.
* Example:&#x20;

```yaml
glow: true
```

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

### Durability of the item

* Info: Select the durability value of the item.
  * For versions 1.20.5— The durability value must be  equal or below the maximum vanilla durability for the item selected.
  * Example:&#x20;
    * <pre class="language-yaml"><code class="lang-yaml"><strong>durability: 150   
      </strong></code></pre>
  * For versions 1.20.5++ The durability option can be customized, enabling new features such as the sync of the usage of the ExecutableItem and the durability value. And allow to select custom max durability.
  * Example:
    * ```yaml
      isDurabilityBasedOnUsage: true
      maxDurability: 20 
      durability: 19
      ```

### Enchantments of the item

* Info: Sets the initial enchantments the executable item will have when given.
* Example:

```yaml
enchantments:
  enchantment1: #ID Of this enchantment, you can add as many as you want
    enchantment: sharpness
    level: 1
```

### Unbreakable

* Info: Boolean value that selects if the executable item will be unbreakable or not
* Example:&#x20;

```yaml
unbreakable: true
```

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

* This process requires the premium version of EI ⭐
* Generate your item with attributes on a website. We suggest [https://mapmaking.fr/give1.12/](https://mapmaking.fr/give1.12/)
* Then give the item to yourself inside Minecraft
* While holding it on your hand run the /ei create \<id> command
* And that's it ! Now your EI has the attributes imported automatically.
{% endhint %}

#### **Keep default attributes**

* Info: Boolean value for keeping or not the default attribute of the item.
* Example:

```yaml
keepDefaultAttributes: false
```

* On this link there is a tutorial for attributes, and its features.

{% embed url="https://youtu.be/HqyF0QBYIY4" %}

#### **ignoreKeepDefaultAttributesFeature:**&#x20;

* **In**fo: It ignores the setting of keep default attributes. Its useful for the third case in this table explanation:

<table><thead><tr><th width="355">Before 1.21</th><th width="347">After 1.21</th></tr></thead><tbody><tr><td><p>EI STONE_PICKAXE </p><ul><li>keepDefaultAttributes YES </li><li>No other attributes </li><li><p>When in Main Hand:</p><ul><li>3 attack damage (green)</li><li>1.2 attack speed (green)</li></ul></li></ul></td><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes YES</li><li>No other attributes </li><li><p>When in Main Hand:</p><ul><li>3 attack damage (green)</li><li>1.2 attack speed (green)</li></ul></li></ul></td></tr><tr><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes NO </li><li>No other attributes </li><li>When in Main Hand</li></ul></td><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes NO</li><li>No other attributes</li><li>NOTHING</li></ul></td></tr><tr><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes YES </li><li>1 armor attribute </li><li><p>When in Main Hand:</p><ul><li>+ 2 attack damage (blue)</li><li>-2.8 attack speed (red)</li><li>1 armor (blue)</li></ul></li></ul></td><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes YES </li><li>1 armor attribute </li><li><p>When in Main Hand:</p><ul><li>3 attack damage (green)</li><li>1.2 attack speed (green)</li><li>1 armor (blue)</li></ul></li></ul></td></tr><tr><td><p>EI STONE_PICKAXE </p><ul><li>keepDefaultAttributes NO</li><li>1 armor attribute</li><li><p>When in Main Hand:</p><ul><li>1 armor (blue)</li></ul></li></ul></td><td><p>EI STONE_PICKAXE</p><ul><li>keepDefaultAttributes NO </li><li>1 armor attribute </li><li><p>When in Main Hand:</p><ul><li>1 armor (blue)</li></ul></li></ul></td></tr></tbody></table>

* Example:

```yaml
ignoreKeepDefaultAttributesFeature: true
```

### Custom model data (1.14++)

* Info:&#x20;
  * For the Minecraft version before 1.21.4: Integer to set the value of the customModelData feature of the item. Useful to create different textures for an item.
  * Since the Minecraft version 1.21.4 you can now add text and boolean.
* Example:&#x20;

```yaml
# For the Minecraft version before 1.21.4
customModelData: 2232

# Since the 1.21.4
# Use ; to separate your data
customModelData: 1.0;true;hello;5.0;false;true;my text 2

# A vanilla item like this : /give @p brick[custom_model_data={floats:[1.0],flags:[true],strings:["hello"]}] 1
# Will look like this in EI : 
customModelData: 1.0;true;hello
```

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

### itemModel&#x20;

* Info: Path of a custom item model on texture pack in the format of \<mynamespace:model\_id> that will target inside assets/\<mynamespace>/models/item/\<model\_id>.
* Example:

```yaml
itemModel: "" # "mynamespace:mymodel"
```

### ⭐tooltipModel

* Info: Path of a custom tooltip model on texture pack in the format of \<mynamespace:model\_id> that will target inside assets/\<mynamespace>/models/item/\<model\_id>.
* Example:

```yaml
tootipModel: "" # "mynamespace:mymodel"
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

### &#x20;NBT Tags

* Info: Requires the plugin [**NBTAPI**](https://www.spigotmc.org/resources/nbt-api.7939/) available on Spigo&#x74;**.** This features allows you to add your custom nbt tags inside your ExecutableItem.
  * type: The type of value you are storing e.g:
    * BOOLEAN: true | false
    * STRING: car
    * INTEGER: 6
    * DOUBLE: 17.6
    * COMPOUND: Example below, it will depend on your needs and what you want to add.
  * key: The string key that represents that nbt storage
  * value: Value of the NBT Tag you are adding
* Example:

```yaml
nbt:
 '1': #Id of this nbt, you can add as many as you want
    type: INT
    key: 'MyKeyTag'
    value: 3
 '2': #Id of this nbt, you can add as many as you want
    type: STRING
    key: 'MyOtherKey'
    value: 'myValue'
 '3': #Id of this nbt, you can add as many as you want
    type: BOOLEAN
    key: 'KeyKeyKeykey'
    value: true
 '4': #Id of this nbt, you can add as many as you want
    type: DOUBLE
    key: 'KeyKeyKeykeykeykey'
    value: 0.5
 '5': #Id of this nbt, you can add as many as you want
    type: BYTE
    key: 'IsCustom'
    value: 1
 '6': #Id of this nbt, you can add as many as you want
    key: ExtraAttributes
    type: COMPOUND
    value:
      nbt:
        '0':
          key: id
          type: STRING
          value: TRIAL_OF_THE_SUN_GOD
 '7': #Id of this nbt, you can add as many as you want
    key: CanDestroy
    type: STRING_LIST
    value:
    - minecraft:stone
```

### Bukkit tags

* Info: You can add bukkit tag values to your ExecutableItem.
* Example:

```yaml
tags:
 - mytag:blabla1
 - myothertag:blabla2
```

In game it will be represented in PublicBukkitValues, like this

<pre class="language-yaml"><code class="lang-yaml"><strong>executableitems:mytag:blabla1
</strong>executableitems:myothertag:blabla2
</code></pre>

### Hiders Settings

* Info: Settings related to hiding features that are normally shown on your ExecutableItem. All features even though they are hide will still be functional.
  * hideEnchantments: Boolean value that represents if the enchantments on the ExecutableItem will be displayed in the lore or not.
  * hideUnbreakable: Boolean value that represents if the unbreakable description will be shown in the lore or not.
  * hideAttributes: Boolean value that represents if the attributes of the ExecutableItem will be displayed in the lore or not.
  * hidePotionEffects: Boolean value that represents if the potion effects of the ExecutableItem will be displayed in the lore or not.
  * hideUsage: Boolean value that represents if the Usage custom feature from ExecutableItem plugin of the item itself will be displayed in the lore or not.
    * You can display manually the usage using %usage% placeholder adding it when editing your lore.
  * hideDye: Boolean value that represents if the dye color (#\<color>) of the ExecutableItem will be displayed in the lore or not.
  * hideArmorTrim: Boolean value that represents if the armor trim of the ExecutableItem will be displayed in the lore or not.
  * hidePlacedOn: Boolean value that represents if the NBT Tag of "Can be placed on: \[...]" of the ExecutableItem will be displayed in the lore or not.
  * hideDestroys: Boolean value that represents if the NBT Tag of "Can destroy: \[...]" of the ExecutableItem will be displayed in the lore or not.
  * hideToolTip: Boolean value that represents if the tooltip is hide or not. (Only available in 1.20.5++)
* Example:

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
  hideToolTip: false
```

### Usage Settings

This section will explain what usage is and its features.

#### Usage

* Info: Usage is a integer value stored inside your ExecutableItem, it can be modified through usageModification inside an activator or commands. But its not just a value stored, this was made to represent the "custom durability system" of your ExecutableItem, that means if somehow the usage gets to 0, your item is deleted.
* Example:&#x20;
  * An usage of 1 doesn't mean the item has one of durability, as we explained previously, its a custom system of durability. It will last as long as the usage doesn't reach 0. For example, if you add an activator to your item that has usageModification feature with value "-1" once the activator triggers one time, your item is gone.
  * Following up the same idea, we have usage 1, if we don't have activators that changes the usage of the item, our item will last infinitely, until again.. somehow either a command or a new activator added to the item, modifies the usage to a value equal or less than 0, then the item will be deleted.
    * ```yaml
      usage: 1
      ```
  * Usage as we said, don't think like its just a durability system, because it can go up too ! .  For example if we have an activator that instead of having a negative value on usageModification it has a positive value, then our usage will increase once the activator is triggered ^^
  * Now, if you want your item neither increase nor decrease, basically don't use this custom value storage. You can set the usage to -1.
    * ```yaml
      usage: -1
      ```

#### ⭐Usage limit

* Info: Integer value that limits the upper amount the usage can reach. (Value cannot be 0)
* Example:&#x20;

```yaml
usageLimit: 600 #Usage will not be able to go up more than this value, -1 to don't take it into account
```

#### Uses per day

* Info: Integer value that limits how many times you can use the item each day In real life
* Example:&#x20;

```yaml
usePerDay: 200 # -1 to ignore it
```



### Food Settings (1.20.5++)

* Info: This feature allows you to customize food settings related to your ExecutableItem
  * nutrition: Integer value that represent amount of "half-food" it will fill the player once the item is eaten
    * For better understanding the player has 20 of nutrition max, and it is shown in-game as 10 hunger icons wich each icon able to split in 2.
  * saturation: Integer value that represents the saturation that the player will receive once the item is eaten.
  * isMeat: Boolean value that will make the item to be considered as food. This will be forced applied, that means, if you set this value to true, any item even the ones that can't be eaten will be considered as food, and so they will be consumable.
  * canAlwaysEat: Boolean value that represents if the item can always be eaten even when the player has his food bar full filled.
* &#x20;Example:

```yaml
food:
  nutrition: 1
  saturation: 1
  isMeat: false
  canAlwaysEat: true
```

### Consumable features

* Info: Features related to consumable, it allows you to customize the consumable options, is closer to the food feature.
  * enable: Boolean that represents enabling or disabling the consumable features
  * animation: ANIMATION\_TYPE that will be reproduced when eating/consuming the ExecutableItem
  * sound: SOUND that will be played when the item is being eaten/consumed
  * hasConsumeParticles: Boolean value that represents if the item will drop particles of being eaten
  * consumeSeconds: Amount of seconds the item gets to be eaten/consumed.
* Example:

```yaml
consumableFeatures:
  enable: true
  animation: SPYGLASS
  sound: ITEM.ARMOR.EQUIP_DIAMOND
  hasConsumeParticles: false
  consumeSeconds: 3
```

### Potion Settings

Here you can customize the potion settings of your ExecutableItem if the material of the item is a potion.

#### Potion color

* Info: Integer of MapInfo Color that represents a color. Use a page like [https://www.tydac.ch/color/](https://www.tydac.ch/color/) to get the value of MapInfo from a color.
* Example:

```yaml
potionSettings:
  potionColor: 10265481
```

#### Potion type

* Info: Potion Type  you want the potion item to be. Its only visibility feature, it doesn't affect the real behavior of the potion. The list is available here [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionType.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionType.html)
* Example:

```yaml
potionSettings:
  potionType: WIND_CHARGED
```

#### Potion effects

* Info: Here you can create the potion effects your option will have
  * potionEffectType: PotionEffectType selected, list available here [https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/potion/PotionEffectType.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/potion/PotionEffectType.html)
  * isAmbient: Boolean value that makes the potion to be ambient, that makes potion effect produce more, translucent, particles.
  * duration: Integer value of ticks (20 ticks = 1 second) which represents the duration of the potion effect.
  * amplifier: Integer value that represents the level/grade/strength of the potion effect. Amplifier 0 means level 1, amplifier 1 means level 2 and so on.
  * hasParticles: Boolean value that enables or disables showing effect particles around the player.
  * hasIcon: Boolean value that enables or disables showing the icon effect on the top right of the player screen.
* Example:

```yaml
potionSettings:
  potionColor: 10265481
  potionType: FIRE_RESISTANCE
  potionEffects:
    pEffect0:
      isAmbient: false
      duration: 30
      potionEffectType: HEALTH_BOOST
      amplifier: 0
      hasParticles: false
      hasIcon: false
```

### Leather armor color

* Info: If your ExecutableItem its an instance of leathers armors then here you can select a value of MapInfo Color that you can get from this website [https://www.tydac.ch/color/](https://www.tydac.ch/color/) to change the color.
* Example:

```yaml
armorColor: 7702341
```

### Head Settings

Here you can select configuration for the head settings, that means the custom head from a player head value or from a database.

#### If you don't have a plugin for head database (1.13++)

* If you want to add a custom head for 1.13++ without having a plugin data base you can follow the next steps:
  * Set the material of the ExecutableItem to PLAYER\_HEAD
  * Visit a custom head page, like this one [https://minecraft-heads.com/custom-heads](https://minecraft-heads.com/custom-heads)
  *   Then get the Value of the head\


      <figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
  * Now copy that value and paste it inside the headValue feature of ExecutableItems
  * Example:
  * ```yaml
    headValue: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvMTk4ZGY0MmY0NzdmMjEzZmY1ZTlkN2ZhNWE0Y2M0YTY5ZjIwZDljZWYyYjkwYzRhZTRmMjliZDE3Mjg3YjUifX19
    ```

#### If you have the plugin Head Database (1.12++)

* If you want to add a custom head for 1.12++ and you have the plugin head databases you can follow the next steps:
  * Open the GUI of your plugin and get the ID of the head you want
  * Then paste it inside the head features on headDBID
  * Example:
  * ```yaml
    headDBID: 44328
    ```
* Here you have the links in case you don't have it and you want it.
  * Premium version: [https://www.spigotmc.org/resources/head-database.14280/](https://www.spigotmc.org/resources/head-database.14280/)
  * Free version: [https://www.spigotmc.org/resources/headdb-head-menu-auto-update-free.84967/](https://www.spigotmc.org/resources/headdb-head-menu-auto-update-free.84967/)

### whitelistedWorlds

* Info: List of String of the names of the worlds you want to prevent or allow the players from using the ExecutableItem.
* Example:

```yaml
whitelistedWorlds:
- ZombieSurvivalWorld_the_end # This allows the use of the EI in that world
- '!ApocalypseWorld' # Using ! Disables the use of the EI in that world
```

### Store item info

* Info: Boolean value that represents if it stores or not the information in the item itself. Currently it stores the feature of "owner". So if you want to use the placeholder of %owner% or the conditions related to owner you must have it enabled.
* Example:

```yaml
storeItemInfo: false
```

### Owner features

#### canBeUsedOnlyByTheOwner

* Info: Boolean value that represents if the item can only be used by the owner or not.
  * This only works if the store item info is turned on in order for the item to have an owner.
* Example:&#x20;

```yaml
canBeUsedOnlyByTheOwner: false
```

#### cancelEventIfNotOwner

* Info: Boolean value that represents if the item is not used by the owner then all events are cancelled. This means, if the activator is, for example, PLAYER\_BREAK\_BLOCK if someone that is not the owner tries to use this item, he won't be able to break any block due all events will be cancelled.
  * This only works if the store item info is turned on in order for the item to have an owner.
* Example:&#x20;

```yaml
cancelEventIfNotOwner: false
```

#### onlyOwnerBlackListedActivators

* Info: List of activators ID of your ExecutableItem, this is a blacklist list which disables the features enabled of canBeUsedOnlyByTheOwner, this means, all activators ID here that targets an activator of the ExecutableItem will be able to be used by everyone even if canBeUsedOnlyByTheOwner is on true.
  * This only works if the store item info is turned on in order for the item to have an owner.
* Example:&#x20;

```yaml
onlyOwnerBlackListedActivators:
- activator0
- activator1
```

### cancelEventIfNoPermission

* Info: Boolean value that represents if the player doesn't have the permission (ei.item.\<id>) to use the item then all events are cancelled. This means, if the activator is, for example, PLAYER\_BREAK\_BLOCK if someone that doesn't have the permission to use this item to use this item, he won't be able to break any block due all events will be cancelled.

```yaml
cancelEventIfNoPermission: true
```

### Keep item on death

* Info: Boolean value that represents if the player will keep the item after the death or not.
* Example:&#x20;

```yaml
keepItemOnDeath: true
```

{% hint style="info" %}
Its compatible with WorldGuard keepInventory feature and Vanilla keepInventory gamerule
{% endhint %}

### &#x20;⭐Disable stack

* Info: Boolean value that represents preventing or not for the ExecutableItem to be stacked. Setting this feature to true will make the customStackSize of this item to be 1.
* Example:&#x20;

```yaml
disableStack: true
```

### ⭐customStackSize (1.20.5 ++)

* Info: Integer value to set the size of the stack of this item. It will override the current stack amount.
* To understand it better, the vanilla diamond\_sword has a stack size of 1, since it can't be stacked, with this feature you can increase this value. On other side, dirt has a stack size of 64, but with this you can decrease it, to for example, stack size of 20.
* Example:&#x20;

```yaml
customStackSize: 32
```

### Variables Settings

* Info: Variables are a way to store information inside your ExecutableItem. This allows to track amount, store positions, actually, you can store whatever you want. They help to create dynamic and customizable item behaviors, by that we mean that variables allow you to create unique behaviors for each item by storing and tracking data specific to that item. For example, you can track how many times a player has used a particular item or how many players they have killed with it.
  * variableName: Name of the variable, it will be used as reference with %var\_\<name>% to use it in the lore, inside commands, etc. This name can't be "id" or "usage" or have spaces.
  * type: VariableType of the variable, it can be the next types within examples of uses:
    * STRING: With this variable type you can store STRING values, such as words, numbers, letters, characters, etc. For example you can store the name of the last player hit. This type of variable doesn't support variableModification(type:MODIFICATION) increasing or decreasing the value. Its static unless its replaced with a variableModification(type:SET) which will override the old value.
    * NUMBER: With this variable type you can store FLOAT values, such as numbers. For example if you want to store the amount of blocks broken, the amount of kills, track the seconds before something happens, etc. This type of variable support variableModification(type:MODIFICATION) and variableModification(type:SET).
    * LIST: This variable is a list type variable that stores STRING values. Its useful to store a list of things, for example, have track of the clicked blocks and append them to this list, or append the killed players here, etc.
  * isRefreshableClean: Boolean value that enables the refresh clean. This allows to add custom lore lines and not being removed when the variable updates. Its recommended to have it on true.
* Example
  * ```yaml
    variables:
      var2:
        variableName: ThisVariableIsTypeIntegerAndICanDoModifications
        type: NUMBER
        default: 10.0
      var1:
        variableName: anotherVariable # This variable is type string
        type: STRING
        default: '' #It starts with no value, we can then change it from an activator or using commands
      var0:
        variableName: nameOfVariable
        type: LIST
        default:
        - value1
        - value2
        - '1'
        - '2'
    ```
* You can check more information on the next page about other type of variables:
  * [https://docs.ssomar.com/tools-for-all-plugins-score/score-variables](https://docs.ssomar.com/tools-for-all-plugins-score/score-variables)

### Custom give first join Settings

* Info: Here you can customize the feature of giving the item when the player join for the first time on the server.
  * giveFirstJoin: Boolean value that represents if the feature is enabled or not
  * giveFirstJoinAmount: Integer value that represents how many items will be given to the player of this ExecutableItem.
  * giveFirstJoinSlot: Slot where the ExecutableItem will be given to the player.
* Example:

```yaml
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
```

### ⭐Item Recognition Settings

* Info: This features allows to make other items that are not the ExecutableItem as they were the ExecutableItem you are editing. Basically the idea is to work with recognitions, its a list of type of recognitions that if one of them matches between your ExecutableItem and another item (even if its not ExecutableItem) the features that the ExecutableItem has will be on the another item too. This works as long as its recognized following the recognitions requirements.
  * Available recognitions options:
    * NAME:  This enable the recognition for all items that matches the custom name of the ExecutableItem
    * MATERIAL: This enable the recognition for all items that matches the material of the ExecutableItem
    * LORE: This enable the recognition for all items that matches the lore of the ExecutableItem
* For example, if you create a diamond pickaxe ExecutableItem, that has an activator PLAYER\_RIGHT\_CLICK and on commands "SEND\_MESSAGE I am a pickaxe" every time you right click it will send that message to the minecraft chat. Now, if you enable item recognition, let's say, for the material, now ALL diamond pickaxes on the server will trigger that activator and so the message will be displayed.
* Example:&#x20;

```yaml
recognitions:
- NAME
- MATERIAL  
- LORE 
```

* Example Scenarios:
  * If an EI item only has the item recognition of `MATERIAL` and is a DIAMOND, all the diamonds that exist in the server will behave as that EI item
  * If an EI item only has the item recognition of `NAME` and is named "\&dAngle", if you attempt to use any item with the name, "\&dAngle", it will behave as the original EI item. BUT if the name was "\&eAngle" or another name it will not work.
  * If an EI item only has the item recognition of `LORE`, an item will only behave as the EI if the item EXACTLY has the same color codes on lore lines and every bit of capitalizing and lowercasing of letters and characters.
  * If an EI item only has the item recognition of `MATERIAL` and `NAME`, the items must have the EXACT NAME and MATERIAL of the EI item for the item to be considered as an EI item.
* Keep in mind that if one of your ExecutableItems has item recognitions enabled on MATERIAL, then you shouldn't use more item recognitions based on MATERIAL for another ExecutableItem with the same MATERIAL. The reason is because if there are 2 ExecutableItems items with the recognition of MATERIAL enabled and both are DIAMOND\_BLOCK, only the first one in the alphabetic order will be the one who will have the most priority in case someone triggers a DIAMOND\_BLOCK.



## Depending on the type of block

### Container Features

* Info: Here you can customize the container features if the block is an instance of container such as the chest and the barrel.
  * isLocked: Boolean value that represents if the container is locked or not
  * lockedName: String value that represents the key name if the container is locked. Its a feature of minecraft, if you have an item with the same name as the lockedName then you will be able to open the chest, otherwise not.
  * containerContent: List of materials inside the container when placed using the format of slot:\<slot>;\<material>
* Example:

```yaml
containerFeatures:
  isLocked: true
  lockedName: thisIsTheKey
  containerContent:
  - slot:0;minecraft:loom
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

### chargedProjectiles

* Info: Feature that allows to have already charged projectiles when the ExecutableItem is a crossbow item and its given to the player.
  * The format of the material must be as `minecraft:<id>`. It supports vanilla items for now.
* Example:

```yaml
material: CROSSBOW
chargedProjectiles:
- minecraft:arrow
```

### bundleContent

* Info: Feature that allows to have already content items if the ExecutableItems is a bundle item and its given to the player.
  * The format of the material must be as `minecraft:<id>`. It supports vanilla items for now.
* Example:

```yaml
material: BUNDLE
bundleContent:
- minecraft:stone
- minecraft:dirt
```

### fireworkFeatures

* Info: Feature that allows to have a customized firework features if the ExecutableItems is a firework item.
* Example:

```yaml
fireworkFeatures:

  lifeTime: 1
  fireworkExplosions:
    explosion_0:
      colors:
      - BLUE
      fadeColors:
      - RED
      type: BALL_LARGE
      hasTrail: true
      hasTwinkle: true
    explosion_1:
      colors:
      - GREEN
      fadeColors: []
      type: CREEPER
      hasTrail: true
      hasTwinkle: true
```



