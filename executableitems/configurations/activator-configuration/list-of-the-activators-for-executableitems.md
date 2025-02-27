# List of the Activators for ExecutableItems

{% hint style="info" %}
Hi ! Its planned for each activator to record video of explanation of it and how to create the examples mentioned. if want to insist ping vayk
{% endhint %}

## Activators of ExecutableItems

Here you have the list of activators available with their description and some examples. Remember as previous knowledge activators are different ways you have to trigger features on your ExecutableItem, it can have conditions, run commands, have cooldown, etc.

The activators that have "⭐" are available only on **premium** version and "🔹" for **free** versions.\
Premium version also have the free version activators just in case.

Activator features are features that are exclusive to that activator.

### 🔹PLAYER\_ALL\_CLICK

* Info: Activator that gets triggered when the player either left or right click with the item.&#x20;
  * You can't differentiate the clicks, for that use different activators such as PLAYER\_RIGHT\_CLICK or PLAYER\_LEFT\_CLICK.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-typetarget](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-typetarget)
  * If typeTarget: ONLY\_BLOCK this features will be available.
    * [ttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands      ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
    * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
* Examples:&#x20;
  * Warping Stone – Instantly teleports the player 5 blocks in the direction they are facing. Cooldown: 10 seconds.
  * Healing Totem – When clicked, heals the player for 4 hearts and grants Regeneration I for 5 seconds.
  * Thunder Rod – Strikes a lightning bolt at the nearest enemy within 10 blocks.
  * Gravity Boots – Launches the player 3 blocks into the air and negates fall damage for 5 seconds.
  * Explosive Rune – Creates a small explosion at the player's location that knocks back nearby mobs but does not damage terrain.

<details>

<summary>Configuration example</summary>

```
// Some code
```

</details>



### ⭐PLAYER\_BED\_ENTER

* Info: Activator that gets triggered when the player right clicks a bed and enters to it. If the player doesn't enter then this activator won't get triggered. This doesn't get triggered when the player sleeps, only by the action of entering the bed.
* Examples:
  * Void Sleep – Upon entering the bed, the player is teleported to a custom-built dream dimension for exploration.
  * Lunar Shield – Grants Absorption IV for 5 minutes when sleeping on the bed, providing temporary bonus health.
  * Nightmare Curse – Spawns a hostile phantom above the bed when the player enters the bed, forcing them to fight before sleeping peacefully.
  * Dreamwalker’s Blessing – When entering the bed, the player gains Regeneration II until they wake up (Wake up action would be PLAYER\_BED\_LEAVE activator).

### ⭐PLAYER\_BED\_LEAVE

* Info: Activator that gets triggered when the player leaves the bed. Be careful ! This activator does get triggered when the player sleeps and its day so they leave the bed, but it also triggers when the player leaves the bed in middle of the sleep, its just the action of leaving the bed.
  * If you would like to activate only when the player sleeps you can use this activator + worldCondition -> ifWorldTime to check if its actually day.
* Examples:
  * Morning Boost – Upon leaving the bed, the player gains Speed II and Haste II for 60 seconds to start the day energized.
  * Phantom's Warning – If the player leaves the bed before fully sleeping, a phantom spawns nearby as a consequence.
  * Dream Collector – Upon waking up, the player receives a random enchanted book as a "dream memory."
  * Energy Surge – When leaving the bed, the player's hunger bar is fully restored, simulating a well-rested night.

### 🔹PLAYER\_BEFORE\_DEATH

* Info: Activator that gets triggered when the player deaths, now, the difference between this activator and PLAYER\_DEATH activator is that this activator gets triggered first in order offering the feature of being able to save the player before he dies.
  * To understand it better vanilla totems of undying gets triggered by this activator to apply the features it does.
* Examples:
  * Soulbound Amulet – When the player is about to die, they are instead teleported to their spawn point with 2 hearts and temporary Regeneration II.
  * Last Stand Shield – Upon near death, the player gains Resistance III and Absorption for 5 seconds, giving them a chance to fight back.
  * Phoenix Blessing – When death is imminent, the player explodes in flames, dealing fire damage to enemies and reviving with half health.
  * Undead Pact – If the player would die, they are instead revived with 3 hearts, but they won't be able to use weapons for 10 seconds.

### ⭐PLAYER\_BLOCK\_BREAK

* Info: Activator that gets triggered when the player breaks a block.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommands)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
* Examples:
  * Ore Booster Pickaxe – When breaking an ore block, there is a 20% chance to double the drop.
  * Nature’s Wrath Axe – Breaking a log has a 10% chance to summon a hostile tree spirit (custom mob).
  * Cursed Excavation – When breaking stone, there is a 5% chance to spawn silverfish or apply Mining Fatigue for 5 seconds.
  * Explosive Demolition Hammer – When breaking blocks the surrounding blocks will be broken too, being able to break in 3x3.

### ⭐PLAYER\_BLOCK\_HIT\_OF\_ENTITY

* Info: Activator that gets triggered when the player blocks a hit that comes from an entity with the shield.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommands)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)
* Examples:
  * Thorned Shield – When blocking an attack, the attacker takes 3 hearts of damage.
  * Shockwave Defense – Successfully blocking an attack knocks back all nearby enemies within 5 blocks.
  * Energy Absorption – When blocking an attack, the player regenerates 1 heart and gains Resistance I for 3 seconds.
  * Frozen Guard – If an attack is blocked, the attacker is frozen in place (Slowness IV) for 2 seconds.
  * Blazing Counter – Blocking an attack sets the attacker on fire for 4 seconds.

### ⭐PLAYER\_BLOCK\_HIT\_OF\_PLAYER

* Info: Activator that gets triggered when the player blocks a hit that comes from a player with the shield.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)
* Examples:
  * Retribution Shield – When blocking an attack from a player, the attacker is instantly disarmed, dropping their weapon on the ground.
  * Vampiric Guard – When successfully blocking an attack, the player absorbs a portion of the attacker's health (healing 2 hearts).
  * Dimensional Rift – If a player’s attack is blocked, there is a 20% chance they are teleported 10 blocks away in a random direction.
  * Adrenaline Block – When blocking an attack, the player instantly gains Speed II and Strength I for 5 seconds, allowing for a quick counterattack.

### ⭐PLAYER\_BLOCK\_PLACE

* Info: Activator that gets triggered when the player places a block.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommands)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
* Examples:
  * Living Roots – When placing a sapling, there is a 10% chance for it to instantly grow into a tree.
  * Runic Inscription – Placing a stone block has a 5% chance to turn it into a Runed Stone, emitting particles and providing nearby players Haste I for 10 seconds.
  * When placing TNT, there’s a small chance (5%) for it to immediately ignite, creating an unexpected explosion.

### ⭐PLAYER\_BREAK\_SHIELD\_OF\_PLAYER

* Info: Activator that gets triggered when the player breaks a shield of another player (usually called target).
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)
* Examples:
  * Shatter Strike – When breaking a player’s shield, the attacker gains Strength I for 5 seconds, empowering their next attack.
  * Upon destroying a shield, a small explosion occurs at the target’s location, knocking them back 5 blocks.
  * When a shield is shattered, the target receives **Wither I** for **5 seconds**, slowly draining their health.
  * Dimensional Fracture – When breaking a player’s shield, the target is momentarily teleported 5 blocks upwards, disorienting them before they fall back down.

### ⭐PLAYER\_BRUSH\_BLOCK

* Info: Activator that gets triggered when the player brushes a block.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommands)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
* Examples:
  * Cursed Dust – If the player brushes a suspicious block, there is a 10% chance that they get temporarily blinded as a cloud of cursed dust erupts around them.
  * Buried Riches – Brushing a block has a small chance to reward the player with a gold nugget or emerald, simulating the discovery of lost treasure.
  * Temporal Echoes – When brushing an artifact block, the player hears faint whispers from the past, hinting at lore-based secrets hidden nearby.

### 🔹PLAYER\_BUCKET\_ENTITY

* Info: Activator that gets triggered when the player using a bucket, it buckets an entity.
  * Example is how you store a fish inside a bucket with water.
  * If want to run something when "trying" to bucket an entity that can't be bucketed this activator won't run, you should use PLAYER\_CLICK\_ON\_ENTITY.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
* Examples:
  * Instant Fillet – Instead of capturing a fish in a bucket, the player instantly receives raw fish in their inventory, as if they expertly filleted it on the spot.
  * Essence Extraction – When using a bucket on an axolotl, instead of capturing it, the player receives an "Axolotl Mucus" potion, which grants Regeneration I for 10 seconds.

### 🔹PLAYER\_CHANGE\_WORLD

* Info: Activator that gets triggered when the player changes to a different world.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.

### ⭐PLAYER\_CLICK\_ON\_ENTITY

* Info: Activator that gets triggered when the player click on an entity and Citizen NPC(s).
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detailedclick](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detailedclick)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### 🔹PLAYER\_CLICK\_ON\_PLAYER

* Info: Activator that gets triggered when the player click on a player (usually called target).
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detailedclick](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detailedclick)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)

### ⭐PLAYER\_CONNECTION

* Info: Activator that gets triggered when the player log into the server.

### 🔹PLAYER\_CONSUME

* Info: Activator that gets triggered when the player successfully eat / consume an item.

### 🔹PLAYER\_CONSUME\_THE\_EI

* Info: Activator that gets triggered when the player successfully eat/consume the ExecutableItem itself.

### 🔹PLAYER\_CUSTOM\_LAUNCH

* Info: Activator that gets triggered when the player launch a projectile with an SCore command such as:
  * [https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/player-and-target-commands#launch](https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/player-and-target-commands#launch)
  * [https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/player-and-target-commands#located\_launch](https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/player-and-target-commands#located_launch)
  * [https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/mixed-commands-player-and-entity#launchentity](https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/mixed-commands-player-and-entity#launchentity)
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### 🔹PLAYER\_DEATH

* Info: Activator that gets triggered when the player dies.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.&#x20;
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)

### ⭐PLAYER\_DESELECT\_THE\_EI

* Info: Activator that gets triggered when the player deselects the ExecutableItem.
  * This happens when the ExecutableItem is on the mainhand, and then you change the item that you are holding, so you are "deselecting it".&#x20;

### 🔹PLAYER\_DISABLE\_FLY

* Info: Activator that gets triggered when the player stops flying.&#x20;
  * Flying action means literally fly, its not gliding or being in the air due to a fall.

### 🔹PLAYER\_DISABLE\_GLIDE

* Info: Activator that gets triggered when the player stops gliding.&#x20;

### ⭐PLAYER\_DISABLE\_SNEAK

* Info: Activator that gets triggered when the player stops from sneaking.&#x20;

### ⭐PLAYER\_DISABLE\_SPRINT

* Info: Activator that gets triggered when the player stops from sprinting&#x20;

### 🔹PLAYER\_DISCONNECT

* Info: Activator that gets triggered when the player logs out from the server.

### 🔹PLAYER\_DISMOUNT

* Info: Activator that gets triggered when the player dismounts / steps out from riding an entity.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### 🔹PLAYER\_DROP\_ITEM

* Info: Activator that gets triggered when the player drops an item.&#x20;

### ⭐PLAYER\_DROP\_THE\_EI

* Info: Activator that gets triggered when the player drops the ExecutableItem.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### ⭐PLAYER\_EDIT\_BOOK

* Info: Activator that gets triggered when the player made changes to the book and quill and pressed done or sign the book.&#x20;

### ⭐PLAYER\_EI\_BREAK

* Info: Activator that gets triggered when the player breaks the ExecutableItem due to vanilla durability break.

### ⭐PLAYER\_ENABLE\_FLY

* Info: Activator that gets triggered when the player **starts** flying. This activator gets triggered by the action of "double space-bar press while having the permission of flying".
  * This means it doesn't get triggered if you are already flying, its triggered by the action of changing flying state by "double space-bar press".
* Examples:
  * Lightning Takeoff – When flight is activated, a small lightning bolt with no damage strikes the player’s position for dramatic effect.
  * Aerial Boost – Upon starting flight, the player gets a temporary Speed III effect for 5 seconds to simulate a powerful lift-off.
  * Gale Force Wings – When starts flying, a strong wind effect pushes all entities around the player.

### 🔹PLAYER\_ENABLE\_GLIDE

* Info: Activator that gets triggered when the player starts gliding.&#x20;

### ⭐PLAYER\_ENABLE\_SNEAK

* Info: Activator that gets triggered when the player starts sneaking.&#x20;

### ⭐PLAYER\_ENABLE\_SPRINT

* Info: Activator that gets triggered when the player starts sprinting.

### ⭐PLAYER\_ENTER\_IN\_THEIR\_LAND

* Info: Activator that gets triggered if you enter in your land or a land where you are trusted&#x20;
  * Supported plugins:
    * Lands

### ⭐PLAYER\_ENTER\_IN\_THEIR\_PLOT

* Info: Activator that gets triggered if you enter a plot.
  * Supported plugins:
    * PlotSquared&#x20;

### ⭐PLAYER\_EQUIP\_THE\_EI

* Info: Activator that gets triggered if you wear/put the armorpiece into the armor slot.
  * Be careful ! The plugin CMI can make this activator not work due to cmi.inventoryhat permission to true. If you want this activator to work set it the permission to false.&#x20;
  * Fabric addons can bypass this activator.

### 🔹PLAYER\_EXPERIENCE\_CHANGE

* Info: Activator that gets triggered when the player experience changes naturally.&#x20;
  * This means this activator is not triggered due to experience changes by commands. Except if those commands are the summon of an experience orb, will would make the experience change "naturally".

### ⭐PLAYER\_FERTILIZE\_BLOCK

* Info: Activator that gets triggered if the player fertilizes a block with bone meal.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)

### 🔹PLAYER\_FILL\_BUCKET

* Info: Activator that gets triggered when the player fills the bucket with eitherwater or lava.&#x20;
  * Be careful ! When an ExecutableItem fills a bucket and it turns to either "water\_bucket" or "lava\_bucket" its not longer an ExecutableItem, it turns into a vanilla item and cant be reverted.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)

### ⭐PLAYER\_FISH\_BLOCK

* Info: Activator that gets triggered when the player right-click the fishing rod when the fishing rod bobber is on a block.&#x20;
  * It doesn't get triggered when is not on a block, if you want to trigger it on the air then use the activator [https://docs.ssomar.com/executableitems/configurations/activator-configuration/list-of-the-activators-for-executableitems#player\_fish\_nothing](https://docs.ssomar.com/executableitems/configurations/activator-configuration/list-of-the-activators-for-executableitems#player_fish_nothing)
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)

### ⭐PLAYER\_FISH\_ENTITY

* Activates when the player right-click the fishing rod when the fishing rod bobber catches an entity or Citizens NPC.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.&#x20;
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### ⭐PLAYER\_FISH\_FISH

* Info: Activator that gets triggered when the player right-click the fishing rod when the fishing rod bobber catches an item in the water due to fish loot system.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-desactivedrops](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-desactivedrops)
  * [ttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### ⭐PLAYER\_FISH\_NOTHING

* Info: Activator that gets triggered when the player fishes nothing, that means, the bobber wasn't on neither block nor entity nor player.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### ⭐PLAYER\_FISH\_PLAYER

* Info: Activator that gets triggered when the player right-click the fishing rod when the fishing rod bobber catches another player (usually called target).
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)

### 🔹PLAYER\_HARVEST\_BLOCK

* Info: Activator that gets triggered when the player harvests a block
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.&#x20;
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
* Examples:
  * When right-clicking a sweet berry bush to harvest, there is a 10% chance that the bush bites back, dealing half a heart of damage but giving the player Strength I for 5 seconds as a "taste for blood" effect.
  * Bountiful Touch – When harvesting crops, there is a 15% chance to instantly replant them at full growth, allowing for continuous farming.
  * Mystic Bloom – When harvesting a flower, there is a 5% chance for it to drop a random enchanted item infused with nature’s energy.

### ⭐PLAYER\_HIT\_ENTITY

* Info: Activator that gets triggered when the player hits an entity.
  * This activator only works when there is damage involved, that means, the player actually hit the entity. If you would like it to work when clicking the entity then use [https://docs.ssomar.com/executableitems/configurations/activator-configuration/list-of-the-activators-for-executableitems#player\_click\_on\_entity](https://docs.ssomar.com/executableitems/configurations/activator-configuration/list-of-the-activators-for-executableitems#player_click_on_entity)
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    \
    https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)

### 🔹PLAYER\_HIT\_PLAYER

* Info: Activator that gets triggered when the player hits another player (usually called target).
  * This activator only works when there is damage involved, that means, the player actually hit the other player. If you would like it to work when clicking the player then use [https://docs.ssomar.com/executableitems/configurations/activator-configuration/list-of-the-activators-for-executableitems#player\_click\_on\_player](https://docs.ssomar.com/executableitems/configurations/activator-configuration/list-of-the-activators-for-executableitems#player_click_on_player)
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)

### ⭐PLAYER\_ITEM\_BREAK

* Info: Activator that gets triggered when the player breaks the ExecutableItem by making it lose all its durability.&#x20;

### ⭐PLAYER\_JUMP

* Info: Activator that gets triggered when the player jumps.
  * In 1.21.2+, it can trigger even if the player attempted to jump mid-air.

### 🔹PLAYER\_KICK

* Info: Activator that gets triggered when the player gets kicked&#x20;

### ⭐PLAYER\_KILL\_ENTITY

* Info: Activator that gets triggered when the player kills an entity or a Citizens NPC.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-desactivedrops](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-desactivedrops)

### ⭐PLAYER\_KILL\_PLAYER

* Info: Activator that gets triggered when the player kills a player (usually called target).
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-desactivedrops](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-desactivedrops)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)

### 🔹PLAYER\_LAUNCH\_PROJECTILE

* Info: Activator that gets triggered when the player shoots a projectile.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### 🔹PLAYER\_LEAVE\_THEIR\_LAND

* Info: Activator that gets triggered if you leave your land or a land where you are trusted&#x20;
  * Supported plugins:
    * Lands

### ⭐PLAYER\_LEAVE\_THEIR\_PLOT

* Info: Activator that gets triggered if you leave a plot.
  * Support plugins:
    * PlotSquared&#x20;

### 🔹PLAYER\_LEFT\_CLICK

* Info: Activator that gets triggered when the player left-clicks the item.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-typetarget](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-typetarget)
  * If typeTarget: ONLY\_BLOCK this features will be available.
    * [ttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands      ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
    * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)

### 🔹PLAYER\_MEND\_THE\_EI

* Info: Activator that gets triggered when the player mends the ExecutableItem by the mending enchantment.&#x20;

### 🔹PLAYER\_OPEN\_INVENTORY

* Info: Activator that gets triggered when the player opens his inventory.&#x20;

### ⭐PLAYER\_PICKUP\_THE\_EI

* Info: Activator that gets triggered when the player pick ups the ExecutableItem.&#x20;

### 🔹PLAYER\_PORTAL

* Info: Activator that gets triggered when the player uses a portal.

### ⭐PLAYER\_RECEIVE\_EFFECT

* Info: Activator that gets triggered when the player receives a potion effect.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detailedeffects](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detailedeffects)

### ⭐PLAYER\_RECEIVE\_HIT\_BY\_ENTITY

* Info: Activator that gets triggered when the player gets hit by an entity.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)

### ⭐PLAYER\_RECEIVE\_HIT\_BY\_PLAYER

* Info: Activator that gets triggered when the player gets hit by another player (usually called target).
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)

### ⭐PLAYER\_RECEIVE\_HIT\_GLOBAL

* Info: Activator that gets triggered when the player gets hit.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)

### 🔹PLAYER\_REGAIN\_HEALTH

* Info: Activator that gets triggered when the player regains health naturally.

### ⭐PLAYER\_RESPAWN

* Info: Activator that gets triggered when the player re-spawns.
  * As normal, all ExecutableItem activator works when the player has it on the inventory, so if the player respawns without the item on the inventory this activator won't trigger.

### 🔹PLAYER\_RIGHT\_CLICK

* Info: Activator that gets triggered when the player right-clicks the item.&#x20;
  * Due to spigot limitations this activator will only trigger if you have an item(any) in your hand.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-typetarget](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-typetarget)
  * If typeTarget: ONLY\_BLOCK this features will be available.
    * [ttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands      ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
    * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)

### 🔹PLAYER\_RIPTIDE

* Info: Activator that gets triggered when the player riptides.

### ⭐PLAYER\_SELECT\_THE\_EI

* Info: Activator that gets triggered when the player selects the ExecutableItem in the hotbar, this means starts holding it on mainhand.&#x20;

### ⭐PLAYER\_SHEAR\_ENTITY

* Info: Activator that gets triggered when the player shears an entity.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### ⭐PLAYER\_SHIELD\_BREAK\_BY\_PLAYER

* Info: Activator that gets triggered when the shield of the player gets broken by another player (usually called target).
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)

### 🔹PLAYER\_SPAWN\_CHANGE

* Info: Activator that gets triggered when the spawnpoint of the player is changed.&#x20;

### 🔹PLAYER\_SWAPHAND\_THE\_EI

* Info: Activator that gets triggered when the player swaphand the ExecutableItem. This means the shortcut of mainhand to offhand and vice versa.&#x20;

### ⭐PLAYER\_TARGETED\_BY\_AN\_ENTITY

* Info: Activator that gets triggered when an entity targets the player.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

### 🔹PLAYER\_TRAMPLE\_CROP

* Info: Activator that gets triggered when the player tramples a crop.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)

### ⭐PLAYER\_UNEQUIP\_THE\_EI

* Info: Activator that gets triggered when the player unequips the ExecutableItem.&#x20;
  * Be careful ! The plugin CMI can make this activator not work due to cmi.inventoryhat permission to true. If you want this activator to work set it the permission to false.
  * Fabric addons can bypass this activator.

### ⭐PLAYER\_WALK

* Info: Activator that gets triggered when the player walks.&#x20;
  * This activator gets triggered each tick the player walks, so its very expensive in performances, use it carefully. You can add use cooldown feature to decrease the impact.

### ⭐PLAYER\_WRITE\_COMMAND

* Info: Activator that gets triggered when the player enters/inputs a command.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detailedcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detailedcommands)

### ⭐PROJECTILE\_ENTER\_IN\_LIQUID

* Info: Activator that gets triggered when a launched projectile of the player enters to water.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-mustbeaprojectilelaunchwiththesameei](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-mustbeaprojectilelaunchwiththesameei)

### ⭐PROJECTILE\_HIT\_BLOCK

* Info: Activator that gets triggered when a launched projectile of the player hits a block.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-blockcommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-blockcommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-mustbeaprojectilelaunchwiththesameei](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-mustbeaprojectilelaunchwiththesameei)

### ⭐PROJECTILE\_HIT\_ENTITY

* Info: Activator that gets triggered when a launched projectile of the player hits an entity.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-entitycommands    ](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-entitycommandshttps://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-mustbeaprojectilelaunchwiththesameei](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-mustbeaprojectilelaunchwiththesameei)

### 🔹PROJECTILE\_HIT\_PLAYER

* Info: Activator that gets triggered when a launched projectile of the player hits another player (usually called target).
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_t-targetcommands](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_t-targetcommands)
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-mustbeaprojectilelaunchwiththesameei](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-mustbeaprojectilelaunchwiththesameei)

### 🔹CUSTOM\_TRIGGER

* Info: Activator that can be executed by running a command, or it can be scheduled.&#x20;
  * This activator is for all plugins, because of that its explained on [https://docs.ssomar.com/tools-for-all-plugins-score/custom-triggers](https://docs.ssomar.com/tools-for-all-plugins-score/custom-triggers)

### ⭐EI\_ENTER\_IN\_THE\_PLAYER\_INVENTORY

* Info: Activator that gets triggered when the ExecutableItem enters to the player's inventory.
  * If you are using another plugin that manages give items and an ExecutableItem is given and this activator doesn't run then go onto their support and ask them to call this method.

### ⭐EI\_LEAVE\_THE\_PLAYER\_INVENTORY

* Info: Activator that gets triggered when the item leaves the player's inventory.
  * Requires ProtocolLib to make this activator works properly.&#x20;

### ⭐INVENTORY\_CLICK

* Info: Activator that gets triggered when the player clicks the item in its inventory.&#x20;
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detailedclick](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detailedclick)

### ⭐LOOP

* Info: Activator that gets triggered in repeat as long as the item is in the player's inventory. Its basically a cycle, it runs the commands each \<delay> \<seconds/ticks> depending on the configuration of this activator.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-delay-and-delaytick](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-delay-and-delaytick)
