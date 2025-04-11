# 🏹 Custom Projectiles

### This page will help you to learn about creating Executable Items's custom projectiles 😎

* We created for you an in-game editor to make the edition simple. **Use it.**

{% hint style="info" %}
THIS PROJECTILES ARE USED WITH <mark style="color:blue;">**LAUNCH**</mark> AND <mark style="color:blue;">**LOCATED\_LAUNCH**</mark> COMMAND, THEY CAN'T BE "GIVEN" TO A PLAYER.
{% endhint %}

### Commands:

| Command                         | Function                                                    |
| ------------------------------- | ----------------------------------------------------------- |
| /score projectiles              | Shows you all projectiles and let you edit them             |
| /score projectiles-create \<id> | Open the editor to create a new projectile                  |
| /score projectiles-delete \<id> | Action to delete a projectile (need confirmation)           |
| /score reload                   | Reload the plugin (useful if you edit a projectile in .yml) |

## <mark style="color:purple;">Basic Information</mark>

### Type

This is the first thing you have to set, the type of projectile you want to create, Score supports:

* ARROW
* SPECTRAL\_ARROW
* EGG
* ENDER\_PEARL
* FIREBALL
* SPLASH\_POTION
* SHULKER\_BULLET
* SNOWBALL
* TRIDENT
* WITHER\_SKULL
* DRAGON\_FIREBALL
* THROWNEXPBOTTLE
* WIND\_CHARGE
* LLAMASPIT
* FISHHOOK
* FIREWORK

Example:

```yaml
type: ARROW
```

### Custom name visible

* It allow you to show the custom name above the projectile
* Options:
  * true
  * false
* Example:

```yaml
customNameVisible: true
```

### Custom Name

* This is the NAME of the projectile, useful for customNameVisible and placeholder stuff.
* Example:

```yaml
customName: '&eBullet'
```

### visualFire

* Option to allow visual fire on the projectile
* Example:

```yaml
visualFire: true
```

### Invisible

* Whether the projectile will be invisible or not

{% hint style="warning" %}
**It requires PROTOCOLIB plugin !!**
{% endhint %}

### Pickup status

* Option to configure if the projectile can be picked up
* Options:
  * ALLOWED
  * DISALLOWED
  * CREATIVE\_ONLY
* Example:

```yaml
pickupStatus: CREATIVE_ONLY
```

### Glowing

* Whether the projectile will have the glowing effect or not
* Options:
  * true
  * false
* Example:

```yaml
glowing: true
```

### Bounce

* Whether the projectile will bounce from the entity during it's invulnerable state.
* Options:
  * true
  * false
* Example:

```yaml
bounce: true
```

### Gravity

* Whether the projectile will affected by gravity or not
* Options:
  * true
  * false
* Example:

```yaml
gravity: true
```

### Velocity

* How fast the projectile will be
* Example:

```yaml
velocity: 2.0
```

{% hint style="danger" %}
THE DAMAGE OF THE **ARROW** WILL BE AFFECTED BY THIS OPTION

Equation: `velocity x 1 = Arrow Damage`
{% endhint %}

### Particles

* This can edit what particles will display the projectile around it.

| config                                                          | explanation                                                                                                                        |
| --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| particlesType                                                   | Type of particle                                                                                                                   |
| particlesAmount                                                 | How many particles will it emit each time                                                                                          |
| particlesOffSet                                                 | How close to the projectile will the particles spawn                                                                               |
| particlesSpeed                                                  | How fast the particles will move                                                                                                   |
| redstoneColor (ONLY TYPE: REDSTONE)                             | <p>Change the color of redstone particle <br>LIST: <a href="https://helpch.at/docs/1.12.2/org/bukkit/Color.html">Particles</a></p> |
| blockType (ONLY TYPE: BLOCK\_CRACK, BLOCK\_DUST, BLOCK\_MARKER) | What block the particle displays                                                                                                   |
| particleDensity                                                 | Density of the particles, useful when want a clean trail of your projectile                                                        |

* Example:

```yaml
particles:
  1:
    particlesType: FLAME
    particlesAmount: 10
    particlesOffSet: 1
    particlesSpeed: 2
  2:
    particlesType: REDSTONE
    particlesAmount: 10
    particlesOffSet: 0.2
    particlesSpeed: 0.5
    redstoneColor: GRAY
  3:
    particlesType: BLOCK_DUST
    particlesAmount: 10
    particlesOffSet: 1.0
    particlesSpeed: 1.0
    particlesDelay: 1
    blockType: SPONGE
```

{% hint style="info" %}
[**Potion types**](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffectType.html)
{% endhint %}

### Despawn delay

* How long will be the projectile's life in seconds
* Example:

```yaml
despawnDelay: 10
```

{% hint style="info" %}
It supports decimals
{% endhint %}

### Knockback strength

* How strong the knockback of the projectile will inflict to its targets
* Equation:

`Knockback strength x 3` = Amount of blocks the target gets knocked back

### Remove when hit block

* Whether the projectile disappears when it hits a block
* Options:
  * true
  * false
* Example:

```yaml
removeWhenHitBlock: true
```

## <mark style="color:purple;">Custom information</mark>

* All of the next information is restricted with the type of projectile.

### Visual item:

* This brings you the ability to disguise a projectile with a item
* Projectiles available:
* <mark style="color:yellow;">**EGG**</mark>
* <mark style="color:yellow;">**ENDER\_PEARL**</mark>
* <mark style="color:yellow;">**SNOWBALL**</mark>

Example:

```yaml
visualItem: diamond_sword
```

{% hint style="info" %}
visualItem is compatible with custom head and adding textures to that head
{% endhint %}

<figure><img src="../.gitbook/assets/image (133).png" alt=""><figcaption></figcaption></figure>

#### Custom model data

* Also visual item supports custom model data of the item.

```yaml
customModelData: 37
```

#### Item Model

* Since the 1.21.2 you can edit the item Model of the projectile.

```yaml
itemModel: mypack:mymodel
```

### Arrow

#### Critical

* Whether the **ARROW** projectile will leave a trial of critical particles
* Options:
  * true
  * false
* Example:

```yaml
critical: true
```

{% hint style="info" %}
Only for the ARROW projectile
{% endhint %}

#### Damage

* How much damage will the arrow make
* Equation:

`<Damage> x 3` = Arrow damage&#x20;

* Default: -1
* Example:

```yaml
damage: 10.0
```

{% hint style="info" %}
Don't use negative value, nothing will change.
{% endhint %}

#### Pierce level

* How many mobs will get hit in a single projectile before it dissapears
* Equation:

`<PierceLevel> + 1` = Amount of mobs that will get hit

* If value is set to -1, it will disappear after hitting 1 mob.
* Example:

```yaml
pierceLevel: 4
```

#### Active color | Color

* **Active color** in -> **true** allows the edition of Color

```yaml
activeColor: true
```

* It is the color that the arrow will emit

```yaml
color: AQUA
```

{% hint style="info" %}
[Click to check all the available colors](https://helpch.at/docs/1.12.2/org/bukkit/Color.html)
{% endhint %}

#### Silent

* Whether the arrow will emit noise
* Options:
  * true
  * false
* Example:

```yaml
silent: true
```

### Wither skull

#### Charged

* Whether the wither\_skull is charged or not
* Options:
  * true
  * false
* Example:

```yaml
charged: true
```

### Fireball

#### Radius

* Radius of explosion
* Example

```yaml
radius: 3
```

#### Incendiary

* Whether the fireball projectile will cause fire or not upon hitting something
* Options:
  * true
  * false
* Example:

```yaml
incendiary: true
```



## YML Config

* There are some features that are not editable in game-yet

### Enchantments (TRIDENT)

* Allow to enchant tridents.

```yaml
enchantments:
 enchantment1:
   enchantment: unbreaking
   level: 1
 enchantment3:
   enchantment: mending
   level: 1
```

### Potion effects (Splash potion)

* Allow to edit the effects of the splash potion

```yaml
potionEffects:
 1:
  potionEffectType: SPEED
  duration: 20
  amplifier: 2
 2:
  potionEffectType: INCREASE_DAMAGE
  duration: 10
  amplifier: 4
```

{% hint style="info" %}
Here are all the potion effect type -> [<mark style="color:blue;">**POTION TYPES**</mark>](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/potion/PotionEffectType.html)
{% endhint %}
