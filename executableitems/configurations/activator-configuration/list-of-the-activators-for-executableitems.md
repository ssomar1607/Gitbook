# List of the Activators for ExecutableItems

## Activators of ExecutableItems

Here you have the list of activators available with their description and some examples. Remember as previous knowledge activators are different ways you have to trigger features on your ExecutableItem, it can have conditions, run commands, have cooldown, etc.

The activators that have "⭐" are available only on premium version and "🔹" for free versions.\
Premium version also have the free version activators just in case.

Activator features are features that are exclusive to that activator.

### 🔹PLAYER\_ALL\_CLICK

* Info: Activator that gets triggered when the player either left or right click with the item.&#x20;
  * You can't differentiate the clicks, for that use different activators such as PLAYER\_RIGHT\_CLICK or PLAYER\_LEFT\_CLICK.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-typetarget](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-typetarget)
* Examples:&#x20;
  * Warping Stone – Instantly teleports the player 5 blocks in the direction they are facing. Cooldown: 10 seconds.
  * Healing Totem – When clicked, heals the player for 4 hearts and grants Regeneration I for 5 seconds.
  * Thunder Rod – Strikes a lightning bolt at the nearest enemy within 10 blocks.
  * Gravity Boots – Launches the player 3 blocks into the air and negates fall damage for 5 seconds.
  * Explosive Rune – Creates a small explosion at the player's location that knocks back nearby mobs but does not damage terrain.

### ⭐PLAYER\_BED\_ANTER

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
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
* Examples:
  * Ore Booster Pickaxe – When breaking an ore block, there is a 20% chance to double the drop.
  * Nature’s Wrath Axe – Breaking a log has a 10% chance to summon a hostile tree spirit (custom mob).
  * Cursed Excavation – When breaking stone, there is a 5% chance to spawn silverfish or apply Mining Fatigue for 5 seconds.
  * Explosive Demolition Hammer – When breaking blocks the surrounding blocks will be broken too, being able to break in 3x3.

### ⭐PLAYER\_BLOCK\_HIT\_OF\_ENTITY

* Info: Activator that gets triggered when the player blocks a hit that comes from an entity with the shield.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.ve.
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
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s\_a\_l-detaileddamagecauses](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#s_a_l-detaileddamagecauses)
* Examples:
  * Retribution Shield – When blocking an attack from a player, the attacker is instantly disarmed, dropping their weapon on the ground.
  * Vampiric Guard – When successfully blocking an attack, the player absorbs a portion of the attacker's health (healing 2 hearts).
  * Dimensional Rift – If a player’s attack is blocked, there is a 20% chance they are teleported 10 blocks away in a random direction.
  * Adrenaline Block – When blocking an attack, the player instantly gains Speed II and Strength I for 5 seconds, allowing for a quick counterattack.

### ⭐PLAYER\_BLOCK\_PLACE

* Info: Activator that gets triggered when the player places a block.
* activatorFeatures: Normally all activators shares features, but there are some that are exclusive for some activators, if its the case, the feature(s) will be listed here.
  * [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_b-detailedblocks](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_b-detailedblocks)
* Examples:
  * Living Roots – When placing a sapling, there is a 10% chance for it to instantly grow into a tree.
  * Runic Inscription – Placing a stone block has a 5% chance to turn it into a Runed Stone, emitting particles and providing nearby players Haste I for 10 seconds.
  * When placing TNT, there’s a small chance (5%) for it to immediately ignite, creating an unexpected explosion.

### ⭐PLAYER\_BREAK\_SHIELD\_OF\_PLAYER

* Info: Activator that gets triggered when the player breaks a shield of another player (usually called target).



<figure><img src="../../../.gitbook/assets/image (446).png" alt=""><figcaption></figcaption></figure>



### ⭐PLAYER\_BRUSH\_BLOCK

* Info: Activator that gets triggered when the player brushes a block.

### 🔹PLAYER\_BUCKET\_ENTITY

* Info: Activator that gets triggered when the player buckets an entity

### 🔹PLAYER\_CHANGE\_WORLD

* Info: Activator that gets triggered when the player moves to a different world.

### ⭐PLAYER\_CLICK\_ON\_ENTITY

* Info: Activator that gets triggered when the player click on an entity

### 🔹PLAYER\_CLICK\_ON\_PLAYER

* Info: Activator that gets triggered when the player click on a player

### ⭐PLAYER\_CONNECTION

* Info: Activator that gets triggered  when the player log into the server. (Does not activate when you log out)

### 🔹PLAYER\_CONSUME

* Info: Activator that gets triggered when the player successfully eat / consume the item.

### 🔹PLAYER\_CONSUME\_THE\_EI

* Info: Activator that gets triggered when the player successfully eat/consume the EI itself

### 🔹PLAYER\_CUSTOM\_LAUNCH

* Info: Activator that gets triggered when the player launch a projectile with the commands: LAUNCH, LOCATEDLAUNCH and LAUNCHENTITY.

### 🔹PLAYER\_DEATH

* Info: Activator that gets triggered when the player dies.&#x20;

### ⭐PLAYER\_DESELECT\_THE\_EI

* Info: Activator that gets triggered if you deselect the EI item in the hotbar.&#x20;

### 🔹PLAYER\_DISABLE\_FLY

* Info: Activator that gets triggered when the player stops flying.&#x20;

### 🔹PLAYER\_DISABLE\_GLIDE

* Info: Activator that gets triggered when the player stops gliding.&#x20;

### ⭐PLAYER\_DISABLE\_SNEAK

* Info: Activator that gets triggered when the player stops from sneaking.&#x20;

### ⭐PLAYER\_DISABLE\_SPRINT

* Info: Activator that gets triggered when the player stops from sprinting&#x20;

### 🔹PLAYER\_DISCONNECTION

* Info: Activator that gets triggered when the player logs out from the server.

### 🔹PLAYER\_DISMOUNT

* Info: Activator that gets triggered when the player steps out from riding an entity.&#x20;

### 🔹PLAYER\_DROP\_ITEM

* Info: Activator that gets triggered when the player drops an item.&#x20;

### ⭐PLAYER\_DROP\_THE\_EI

* Info: Activator that gets triggered when the player drops the EI item.&#x20;

### ⭐PLAYER\_EDIT\_BOOK

* Info: Activator that gets triggered when the player made changes to the book and quill and pressed done or sign the book.&#x20;

### ⭐PLAYER\_EI\_BREAK

* Info: Activator that gets triggered when the player breaks the ExecutableItem.

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

* Info: Activator that gets triggered when the player starts sprinting&#x20;

### ⭐PLAYER\_ENTER\_IN\_THEIR\_LAND

* Info: Activator that gets triggered if you enter in your land or a land where you are trusted&#x20;

### ⭐PLAYER\_ENTER\_IN\_THEIR\_PLOT

* Info: Activator that gets triggered if you enter a plot from the PlotSquared plugin.&#x20;

### ⭐PLAYER\_EQUIP\_THE\_EI

* Info: Activator that gets triggered if you put the armorpiece in the armor slot. The plugin CMI can break this activator be sure you have the cmi.inventoryhat permission set to false&#x20;

### 🔹PLAYER\_EXPERIENCE\_CHANGE

* Info: Activator that gets triggered when the player experience changes naturally.&#x20;

### ⭐PLAYER\_FERTILIZE\_BLOCK

* Info: Activator that gets triggered if the player fertilizes blocks with bone meal.&#x20;

### 🔹PLAYER\_FILL\_BUCKET

* Info: Activator that gets triggered when the player attempts to pickup water or lava with a bucket.&#x20;

### ⭐PLAYER\_FISH\_BLOCK

* Info: Activator that gets triggered when the player right-click the fishing rod when the fishing rod bobber is on a block.&#x20;

### ⭐PLAYER\_FISH\_ENTITY

* Activates when the player right-click the fishing rod when the fishing rod bobber catches an entity.&#x20;

### ⭐PLAYER\_FISH\_FISH

* Info: Activator that gets triggered when the player right-click the fishing rod when the fishing rod bobber catches something.&#x20;

### ⭐PLAYER\_FISH\_NOTHING

* Info: Activator that gets triggered when the player fishes nothing.&#x20;

### ⭐PLAYER\_FISH\_PLAYER

* Info: Activator that gets triggered when the player right-click the fishing rod when the fishing rod bobber catches a player.&#x20;

### 🔹PLAYER\_HARVEST\_BLOCK

* Info: Activator that gets triggered when the player harvests a block (Example: Activator runs if the player right clicks a sweet berry bush that contains berries that can be harvested upon right-click)&#x20;

### ⭐PLAYER\_HIT\_ENTITY

* Info: Activator that gets triggered when the player hits an entity&#x20;

### 🔹PLAYER\_HIT\_PLAYER

* Info: Activator that gets triggered when the player hits a player&#x20;

### ⭐PLAYER\_ITEM\_BREAK

* Info: Activator that gets triggered when the player breaks the item by making it loose all its durability.&#x20;

### ⭐PLAYER\_JUMP

* Info: Activator that gets triggered when the player jumps. (In 1.21.2+, it can trigger even if the player is in the air)&#x20;

### 🔹PLAYER\_KICK

* Info: Activator that gets triggered when the player gets kicked&#x20;

### ⭐PLAYER\_KILL\_ENTITY

* Info: Activator that gets triggered when the player kills an entity.&#x20;

### ⭐PLAYER\_KILL\_PLAYER

* Info: Activator that gets triggered when the player kills a player.&#x20;

### 🔹PLAYER\_LAUNCH\_PROJECTILE

* Info: Activator that gets triggered when the player shoots a projectile.&#x20;

### 🔹PLAYER\_LEAVE\_THEIR\_LAND

* Info: Activator that gets triggered if you leave your land or a land where you are trusted&#x20;

### ⭐PLAYER\_LEAVE\_THEIR\_PLOT

* Info: Activator that gets triggered if you leave a plot from the PlotSquared plugin.&#x20;

### 🔹PLAYER\_LEFT\_CLICK

* Info: Activator that gets triggered when the player left-clicks the item.&#x20;

### 🔹PLAYER\_MEND\_THE\_EI

* Info: Activator that gets triggered  when the player mends the EI&#x20;

### 🔹PLAYER\_OPEN\_INVENTORY

* Info: Activator that gets triggered when the player opens inventory&#x20;

### ⭐PLAYER\_PICKUP\_THE\_EI

* Info: Activator that gets triggered when the player pick ups the ExecutableItem.&#x20;

### 🔹PLAYER\_PORTAL

* Info: Activator that gets triggered when the player uses a portal&#x20;

### ⭐PLAYER\_RECEIVE\_EFFECT

* Info: Activator that gets triggered when the player receives an effect&#x20;

### ⭐PLAYER\_RECEIVE\_HIT\_BY\_ENTITY

* Info: Activator that gets triggered when you get hit by anything from an entity.&#x20;

### ⭐PLAYER\_RECEIVE\_HIT\_BY\_PLAYER

* Info: Activator that gets triggered when you get hit by anything from a player.&#x20;

### ⭐PLAYER\_RECEIVE\_HIT\_GLOBAL

* Info: Activator that gets triggered when you get hit by anything.&#x20;

### 🔹PLAYER\_REGAIN\_HEALTH

* Info: Activator that gets triggered when the player regains health

### ⭐PLAYER\_RESPAWN

* Info: Activator that gets triggered when the player re-spawns.&#x20;

### 🔹PLAYER\_RIGHT\_CLICK

* Info: Activator that gets triggered when the player right-clicks the item. (IT REQUIRES EITHER HAVE AN ITEM IN THE HAND OR TARGET AT A BLOCK TO BE TRIGGERED, THIS IS A SPIGOT LIMITATION)&#x20;

### 🔹PLAYER\_RIPTIDE

* Info: Activator that gets triggered when the player riptides&#x20;

### ⭐PLAYER\_SELECT\_THE\_EI

* Info: Activator that gets triggered when the player selects the EI item in the hotbar.&#x20;

### ⭐PLAYER\_SHEAR\_ENTITY

* Info: Activator that gets triggered when the player shears an entity.&#x20;

### ⭐PLAYER\_SHIELD\_BREAK\_BY\_PLAYER

* Info: Activator that gets triggered when the shield of the player gets broken by someone else.&#x20;

### 🔹PLAYER\_SPAWN\_CHANGE

* Info: Activator that gets triggered when the player changes their spawn&#x20;

### 🔹PLAYER\_SWAPHAND\_THE\_EI

* Info: Activator that gets triggered when the player swaphand the EI.&#x20;

### ⭐PLAYER\_TARGETED\_BY\_AN\_ENTITY

* Info: Activator that gets triggered when an entity targets the player.&#x20;

### 🔹PLAYER\_TRAMPLE\_CROP

* Info: Activator that gets triggered when the player tramples a crop.&#x20;

### ⭐PLAYER\_UNEQUIP\_THE\_EI

* Info: Activator that gets triggered if you unequip the EI. The plugin CMI can break this activator be sure you have the cmi.inventoryhat permission set to false&#x20;

### ⭐PLAYER\_WALK

* Info: Activator that gets triggered when the player walks.&#x20;

### ⭐PLAYER\_WRITE\_COMMAND

* Info: Activator that gets triggered when the player enters commands.&#x20;

### ⭐PROJECTILE\_ENTER\_LIQUID

* Info: Activator that gets triggered if the launched projectile enters and stays long enough in water&#x20;

### ⭐PROJECTILE\_HIT\_BLOCK

* Info: Activator that gets triggered when the projectile of the player hits a block.&#x20;

### ⭐PROJECTILE\_HIT\_ENTITY

* Info: Activator that gets triggered when the projectile of the player hits an entity.&#x20;

### 🔹PROJECTILE\_HIT\_PLAYER

* Info: Activator that gets triggered when the projectile of the player hits a player.&#x20;

### 🔹CUSTOM\_TRIGGER

* Info: Activator that can be executed by running a command, or it can be scheduled.&#x20;

### ⭐EI\_ENTER\_IN\_THE\_PLAYER\_INVENTORY

* Info: Activator that gets triggered when the item enters to the player's inventory. (If when a plugin gives an ExecutableItem to a player it doesn't trigger this activator, you should go on their support and ask them to call this method: CLICK HERE)&#x20;

### ⭐EI\_LEAVE\_THE\_PLAYER\_INVENTORY

* Info: Activator that gets triggered  when the item leaves the player's inventory. ( Require ProtocolLib to make this activator works properly )&#x20;

### ⭐INVENTORY\_CLICK

* Info: Activator that gets triggered when the player clicks the item in its inventory.&#x20;

### ⭐LOOP

* Info: Activator that gets triggered in repeat as long as the item is in the player's inventor
