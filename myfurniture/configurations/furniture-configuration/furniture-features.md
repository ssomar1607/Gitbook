# Furniture Features

## ExecutableItem

* Define the Executableitem ID with which the Furniture is associated
* Then manage all item settings directly in ExecutableItems

```yaml
executableItem: acacia_bed
```

## Title Features

It supports [DecentHolograms](https://www.spigotmc.org/resources/96927/), [HolographicDisplays](https://dev.bukkit.org/projects/holographic-displays) and [CMI](https://www.spigotmc.org/resources/3742/)

### Active Title&#x20;

* Info: Whether the title hologram would be enabled or not
* Example:

```yaml
activeTitle: false
```

* Required: NO

### Title

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

### Title Adjustment&#x20;

* Info: How high or low is the adjustment of the elevation of the title hologram
* Example:

```yaml
titleAdjustment: 0.5
```

* Required: NO
  * Extra Info: Positive number for upwards, Negative number for downwards

### Title Features Example&#x20;

<pre class="language-yaml"><code class="lang-yaml"><strong>titleFeatures:
</strong>  # Active the title
  activeTitle: true
  # The title
  title:
   - Hello
   - &#x26;6It's support color
   - and %placeholder%
  titleAdjustment: 0.5
</code></pre>



## Usage

#### Adjust the Furniture usage in the  ExecutableItem configuration



## Display Features

### Item Model

* The model of the furniture
* Example:

```yaml
itemModel: myfurniture:acacia_bed
```

### Scale

* Scale of the display
* Example:

```yaml
scale: 1
```

### Aligned

* If you want the display to be aligned
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>aligned: false
</strong></code></pre>

### Custom Pitch

* Select the custom pitch
* Example:

```yaml
customPitch: 1
```

### Custom Y

* Select the custom Y
* Example:

```yaml
customY: 1.0
```

### Glow

* Glow or not
* Example:

```yaml
glow: false
```

### Click To Break

* Amount of clicks needed to break the display creation
* Example:

```yaml
clickToBreak: 3
```

### Bounding Box Zones

{% hint style="warning" %}
Auto generated feature, don't edit it
{% endhint %}

### Block Light

* The block lighting component of this brightness. (Between 0-15)
* Example:

```yaml
blockLight: 10
```

### Sky Light

* The sky lighting component of this brightness. (Between 0-15)
* Example:

```yaml
skyLight: 10
```

### View Range

* Configure the view range of the furniture
* Example:

```yaml
viewRange: 20.0
```

### Display Features Example

```yaml
displayFeatures:
  itemModel: myfurniture:acacia_bed
  scale: 1.0
  aligned: false
  customPitch: 90
  glow: false
  clickToBreak: 3
  boundingBoxZones: []
  blockLight: 10
  skyLight: 10
  viewRange: 20.0
```

## Interaction Range

* Configure the interaction range of the furniture
* Example:

```yaml
interactionRange: 6.0
```

## Drop Type

* Info: Select the type of drop the Furniture will have
* Type of drops:
  * IN\_THE\_INVENTORY
  * ON\_THE\_GROUND

```yaml
dropType: IN_THE_INVENTORY
```

## Sit Features

* Define if the players can sit or not on the furniture

```yaml
sitFeatures:
  playerCanSit: false
```

## Storage Features

* Define if the furniture can store items like a chest or not

```yaml
storageFeatures:
  enable: false
```

## Activators

* Very important features that allow you to add abilities on your furniture
* Dedicated Wiki for this feature :&#x20;

{% content-ref url="../activator-configuration/" %}
[activator-configuration](../activator-configuration/)
{% endcontent-ref %}

* Example

```yaml
activators:
  activator0:
    name: '&eActivator'
    option: PLAYER_ALL_CLICK_ON
    usageModification: -1
    cancelEvent: false
    requiredItems: {}
    requiredExecutableItems: {}
    requiredMagics: {}
    displayConditions: {}
    displayCommands: []
    worldConditions: {}
    placeholdersConditions: {}
    variablesModification: {}
    ownerCommands: []
    ownerConditions: {}
    playerCommands:
    - say &eHello
    playerConditions: {}
    playerCooldownFeatures:
      cooldown: 0
      pausePlaceholdersConditions: {}
    globalCooldownFeatures:
      cooldown: 0
    customConditions: {}
```

