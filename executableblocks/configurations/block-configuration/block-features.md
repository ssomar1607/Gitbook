# Block Features

## Basic Settings

### CreationType

* The way to create the EB
  * BASIC\_CREATION
  * DISPLAY\_CREATION
  * IMPORT FROM EI
  * IMPORT FROM ITEMSADDER
  * IMPORT FROM ORAXEN

### MATERIAL

* Info: The base minecraft item of the executable block.
  * Extra Info: The item has to be a placeable block.

```yaml
material: DIRT
```

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html" %}

* Required: YES

{% hint style="info" %}
It support spawners ! so if you want define a type for your spawner add:

`spawnerType: CHICKEN`
{% endhint %}

{% embed url="https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html" %}

### DISPLAYNAME

* Info: The name of the block
* Example:&#x20;

```yaml
name: '&cEpic Sword'
```

* Required: YES
  * **(IT IS A MUST IN 1.12 AS YOU CANNOT HAVE A NULL NAME)**

### LORE

* Info: The lore of the block
* Example:

```yaml
lore:
- §6>> §e----------- §6<<
- §aClick on this block
- §awhen it is placed !
- §aand see the custom structures !
- §6>> §e----------- §6<<
```

* Required: YES
  * **(IT IS A MUST IN 1.12 AS YOU CANNOT HAVE A NULL LORE)**
* Placeholders that you can use in the lore, %player%, [%usage%](block-features.md#hide-usage-1.14+), etc.

### DROP BLOCK IF IT IS BROKEN

* Info: Whether if you want to make your Executable Block to be obtainable by breaking or not
* Example:&#x20;

```yaml
dropBlockIfItIsBroken: true
```

* Required: NO (Default: true)

### DROP BLOCK IF IT IS BURNS

* Info: Whether if you want to make your Executable Block to be obtainable by breaking or not
* Example:&#x20;

```yaml
dropBlockIfItIsBurns: true
```

* Required: NO (Default: false)

### DROP BLOCK WHEN IT EXPLODES

* Info: Whether if you want to make your Executable Block to be obtainable by getting destroyed from any explosion
* Example:

```yaml
dropBlockWhenItExplodes: true
```

* Required: NO (Default: true)

### DROP TYPE

* Info: Select the type of drop the EB block will have
* Type of drops:
  * IN\_THE\_INVENTORY
  * ON\_THE\_GROUND

### ONLY BREAKABLE WITH EI

* Info: Requirements to at least have the required Executable Item into your main hand or offhand to break the executable block
* Example:

```yaml
onlyBreakableWithEI:
- firework
```

* Required: NO (Default: empty)

### CANBEMOVED

* Info: Whether if the block can be moved used a piston or not.
* Example:

```yaml
canBeMoved: false
```

### EXECUTABLE ITEMS ID

* Info: It's basically an option that allows you to sync your executable block into an executable item.
  * Extra Info: The executable block copies the name, material and lore of the executable item so when you attempt to edit the name, material or lore of the eb, nothing will change. You have to edit the name, material and lore of the ei for the changes in eb to take place
* Example:&#x20;

```yaml
executableItem: hack
```

* Required: NO

## Title <img src="../../../.gitbook/assets/ExecutableBlocks (64x64)px.png" alt="" data-size="line">

It supports [DecentHolograms](https://www.spigotmc.org/resources/96927/), [HolographicDisplays](https://dev.bukkit.org/projects/holographic-displays) and [CMI](https://www.spigotmc.org/resources/3742/)

### ACTIVE TITLE <img src="../../../.gitbook/assets/ExecutableBlocks (64x64)px.png" alt="" data-size="line">

* Info: Whether the title hologram would be enabled or not
* Example:

```yaml
activeTitle: false
```

* Required: NO

### TITLE NAME <img src="../../../.gitbook/assets/ExecutableBlocks (64x64)px.png" alt="" data-size="line">

* Info: The displayed text of the hologram
* Example:&#x20;

```yaml
title: '&7&oDefault title'
```

* (With HolographicDisplay) You can display item in the title type ITEM::MATERIAL

```yaml
title: 
- '&7&oDefault title'
- 'ITEM::DIAMOND'
```

* Required: NO

### TITLE ADJUSTMENT <img src="../../../.gitbook/assets/ExecutableBlocks (64x64)px.png" alt="" data-size="line">

* Info: How high or low is the adjustment of the elevation of the title hologram
* Example:

```yaml
titleAdjustement: 0.5
```

* Required: NO
  * Extra Info: Positive number for upwards, Negative number for downwards

## Custom usage Settings

#### USAGE

* Info: The value of how many times you can use it. Mostly used for the usage modification function of activators.
* Example:&#x20;

```yaml
usage: 0
```

For infinite block use:

```yaml
usage: -1
```

* Required: NO (Default: 0)

{% hint style="info" %}
usage: 0 equals to usage:1 , but it will not display the text "Remaining use:..." in the lore.
{% endhint %}

## Container features

{% hint style="info" %}
Items filters support correctly the tag {CUSTOMODELDATA:X} So for example you can create an hopper that takes only an item with a specific textures
{% endhint %}

### whitelistMaterials

* Here you can add a list of materials that can be placed inside your block

```
containerFeatures:
  whitelistMaterials:
  - DIRT
```

### blacklistMaterials

* Here you can add a list of materials that can't be placed inside your block

```
containerFeatures:
  blacklistMaterials:
  - STONE
```

{% hint style="info" %}
In case of HOPPERS whitelist and blacklist restrict the items that the hopper can suck.
{% endhint %}

### isLocked

* If the container is locked or not

### lockedName

* In case it is locked you have to select the name of the key

```
containerFeatures:
  isLocked: true
  lockedName: ThisIsMyKey
```

### inventoryTitle

* The inventory title of the container&#x20;

```
containerFeatures:
  inventoryTitle: INVENTORY TITLE
```



## Furnace features

### furnaceSpeed

* It allows to customize the speed of your furnace.
* Example:

```
furnaceFeatures:
  furnaceSpeed: 2.0
```

{% hint style="info" %}
Default -> 1

2 times default velocity -> 2

Half speed of default -> 0.5
{% endhint %}

### infiniteFuel

* Makes the block not require fuel to run

```
furnaceFeatures:
  infiniteFuel: true
```

### infiniteVisualLit

* Makes the block look like it's lit

```
furnaceFeatures:
  infiniteVisualLit: true
```

## Brewing stand features

### brewingStandSpeed

* It allows to customize the speed of your brewingStand
* Example:

```
brewingStandFeatures:
  brewingStandSpeed: 1.0
```

{% hint style="info" %}
Default -> 1

2 times default velocity -> 2

Half speed of default -> 0.5
{% endhint %}

## Hopper features

### amountItemsTransferred

* It allows you to customize the amount of items is transferred each tick of hopper.
* Example:

```yaml
hopperFeatures:
  amountItemsTransferred: 5
```

### Display features

#### Material

* Material of the item that will be displayed
* Example:

```
DisplayFeatures:
  material: PAPER
```

#### Custom model data

* Custom model data of the material that will be displayed
* Example:

```
DisplayFeatures:
  customModelData: 3
```

#### Scale

* Scale of the display
* Example:

```
DisplayFeatures:
  scale: 1
```

#### aligned

* If you want the display to be aligned
* Example:

<pre><code><strong>DisplayFeatures:
</strong>  aligned: false
</code></pre>

#### customPitch

* Select the custom pitch
* Example:

```
DisplayFeatures:
  customPitch: 1
```

#### customY

* Select the custom Y
* Example:

```
DisplayFeatures:
  customY: 1.0
```

#### Glow

* Glow or not
* Example:

```
DisplayFeatures:
  glow: false
```

#### Interaction zone features

* Width of the display
* Height of the display
* Collidable or not
* Example:

```
DisplayFeatures:
  InteractionZoneFeatures:
    width: 1.0
    height: 1.0
    isCollidable: false
```

## Chiseled Bookshelf

### occupiedSlots

* Sets which slots (Index 0-5) would have a book in it

```
chiseledBookshelfFeatures:
  occupiedSlots:
  - '2'
  - '5'
```

## Cancel

### cancelLiquidDestroy

* Info: It will cancel the destruction of seeds, player heads by water/lava
* Example:&#x20;

```
cancelLiquidDestroy: true
```
