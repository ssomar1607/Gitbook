# List of the Activators for ExecutableItems

## Activators of ExecutableItems

Here you have the list of activators available with their description and some examples. Remember as previous knowledge activators are different ways you have to trigger features on your ExecutableItem, it can have conditions, run commands, have cooldown, etc.

The activators that have "⭐" are available only on premium version and "🔹" for free versions.\
Premium version also have the free version activators just in case.

Activator features are features that are exclusive to that activator.

### 🔹PLAYER\_ALL\_CLICK

* Info: Activator that gets triggered when the player either left or right click with the item.&#x20;
  * You can't differentiate the clicks, for that use different activators such as PLAYER\_RIGHT\_CLICK or PLAYER\_LEFT\_CLICK.
* activatarFeatures
  * \<IF I FORGOT PLS PING VAYK>
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
* Example:
  * Soulbound Amulet – When the player is about to die, they are instead teleported to their spawn point with 2 hearts and temporary Regeneration II.
  * Last Stand Shield – Upon near death, the player gains Resistance III and Absorption for 5 seconds, giving them a chance to fight back.
  * Phoenix Blessing – When death is imminent, the player explodes in flames, dealing fire damage to enemies and reviving with half health.
  * Undead Pact – If the player would die, they are instead revived with 3 hearts, but they won't be able to use weapons for 10 seconds.

### ⭐PLAYER\_BLOCK\_BREAK

* Info: Activator that gets triggered when the player breaks a block.



* [<mark style="color:orange;">**PLAYER\_BLOCK\_BREAK**</mark>](list-of-the-activators-for-executableitems.md#player_block_break) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player mines / breaks a block.**
* <mark style="color:orange;">**PLAYER\_BLOCK\_HIT\_OF\_ENTITY**</mark><img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">: Activates when the player blocks a hit that comes from an entity with the shield.
* <mark style="color:orange;">**PLAYER\_BLOCK\_HIT\_OF\_PLAYER**</mark><img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">: Activates when the player blocks a hit that comes from a player with the shield.
* [<mark style="color:orange;">**PLAYER\_BLOCK\_PLACE**</mark>](list-of-the-activators-for-executableitems.md#player_block_place) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player places a block.**
* <mark style="color:orange;">**PLAYER\_BREAK\_SHIELD\_OF\_PLAYER**</mark><img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">: Activates when the player breaks a shield of a player
* <mark style="color:orange;">**PLAYER\_BRUSH\_BLOCK**</mark> <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player brushes a block.**
* <mark style="color:blue;">**PLAYER\_BUCKET\_ENTITY**</mark>: Activates when the player buckets an entity
* [<mark style="color:blue;">**PLAYER\_CHANGE\_WORLD**</mark>](list-of-the-activators-for-executableitems.md#player_change_world) : Activates when the player moves to a different world.
* [<mark style="color:orange;">**PLAYER\_CLICK\_ON\_ENTITY**</mark>](list-of-the-activators-for-executableitems.md#player_click_on_entity) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player click on an entity.**
* [<mark style="color:blue;">**PLAYER\_CLICK\_ON\_PLAYER**</mark>](list-of-the-activators-for-executableitems.md#player_click_on_player) : Activates when the player click on a player.
* [<mark style="color:orange;">**PLAYER\_CONNECTION**</mark>](list-of-the-activators-for-executableitems.md#player_connection) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player log into the server. (Does not activate when you log out)**
* [<mark style="color:blue;">**PLAYER\_CONSUME**</mark>](list-of-the-activators-for-executableitems.md#player_consume) : Activates when the player successfully eat / consume the item.
* <mark style="color:blue;">**PLAYER\_CONSUME\_THE\_EI**</mark>  : Activates when the player successfully eat/consume the EI itself
* <mark style="color:blue;">**PLAYER\_CUSTOM\_LAUNCH**</mark> : Activates when the player launch a projectile with the commands: LAUNCH, LOCATEDLAUNCH and LAUNCHENTITY.
* [<mark style="color:blue;">**PLAYER\_DEATH**</mark>](list-of-the-activators-for-executableitems.md#player_death) : Activates when the player dies.
* [<mark style="color:orange;">**PLAYER\_DESELECT\_THE\_EI**</mark>](list-of-the-activators-for-executableitems.md#player_deselect_the_ei) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates if you deselect the EI item in the hotbar.**
* <mark style="color:blue;">**PLAYER\_DISABLE\_FLY**</mark>**&#x20; : Activates when the player stops flying.**
* <mark style="color:blue;">**PLAYER\_DISABLE\_GLIDE**</mark>**&#x20; : Activates when the player stops gliding.**
* [<mark style="color:orange;">**PLAYER\_DISABLE\_SNEAK**</mark>](list-of-the-activators-for-executableitems.md#player_desactive_sneak) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player stops from sneaking.**&#x20;
* [<mark style="color:orange;">**PLAYER\_DISABLE\_SPRINT**</mark>](list-of-the-activators-for-executableitems.md#player_desactive_sprint)<img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player stops from sprinting**
* [<mark style="color:blue;">**PLAYER\_DISCONNECTION**</mark>](list-of-the-activators-for-executableitems.md#player_deconnection) **: Activates when the player logs out from the server.**&#x20;
* [<mark style="color:blue;">**PLAYER\_DISMOUNT**</mark>](list-of-the-activators-for-executableitems.md#player_dismount) **: Activates when the player steps out from riding an entity.**&#x20;
* [<mark style="color:blue;">**PLAYER\_DROP\_ITEM**</mark>](list-of-the-activators-for-executableitems.md#player_drop_item) : Activates when the player drops an item.
* [<mark style="color:orange;">**PLAYER\_DROP\_THE\_EI**</mark>](list-of-the-activators-for-executableitems.md#player_drop_the_ei) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player drops the EI item.**
* [<mark style="color:orange;">**PLAYER\_EDIT\_BOOK**</mark>](list-of-the-activators-for-executableitems.md#player_edit_book) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player made changes to the book and quill and pressed done or sign the book.**
* [<mark style="color:orange;">**PLAYER\_EI\_BREAK**</mark>](list-of-the-activators-for-executableitems.md#player_item_break) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player breaks the ExecutableItem.**

### ⭐PLAYER\_ENABLE\_FLY

* Info: Activator that gets triggered when the player **starts** flying. This activator gets triggered by the action of "double space-bar press while having the permission of flying".
  * This means it doesn't get triggered if you are already flying, its triggered by the action of changing flying state by "double space-bar press".
* Examples:
  * Lightning Takeoff – When flight is activated, a small lightning bolt with no damage strikes the player’s position for dramatic effect.
  * Aerial Boost – Upon starting flight, the player gets a temporary Speed III effect for 5 seconds to simulate a powerful lift-off.
  * Gale Force Wings – When starts flying, a strong wind effect pushes all entities around the player.
* <mark style="color:blue;">**PLAYER\_ENABLE\_GLIDE**</mark>**: Activates when the player starts gliding.**
* [<mark style="color:orange;">**PLAYER\_ENABLE\_SNEAK**</mark>](list-of-the-activators-for-executableitems.md#player_active_sneak) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player starts sneaking.**
* [<mark style="color:orange;">**PLAYER\_ENABLE\_SPRINT**</mark>](list-of-the-activators-for-executableitems.md#player_active_sprint) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player starts sprinting**
* <mark style="color:orange;">**PLAYER\_ENTER\_IN\_THEIR\_LAND**</mark> <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">**: Activates if you enter in your land or a land where you are trusted**
* [<mark style="color:orange;">**PLAYER\_ENTER\_IN\_THEIR\_PLOT**</mark>](list-of-the-activators-for-executableitems.md#player_enter_in_his_plot) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates if you enter a plot from the PlotSquared plugin.**
* [<mark style="color:orange;">**PLAYER\_EQUIP\_THE\_EI**</mark>](list-of-the-activators-for-executableitems.md#player_equip_the_ei) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates if you put the armorpiece in the armor slot.**
  * **The plugin CMI can break** this activator be sure you have the `cmi.inventoryhat` permission set to **false**&#x20;
* <mark style="color:blue;">**PLAYER\_EXPERIENCE\_CHANGE**</mark>**: Activates when the player experience changes naturally.**
* [<mark style="color:orange;">**PLAYER\_FERTILIZE\_BLOCK**</mark>](list-of-the-activators-for-executableitems.md#player_fertilize_block) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates if the player fertilizes blocks with bone meal.**
* [<mark style="color:blue;">**PLAYER\_FILL\_BUCKET**</mark>](list-of-the-activators-for-executableitems.md#player_fill_bucket) : Activates when the player attempts to pickup water or lava with a bucket.
* [<mark style="color:orange;">**PLAYER\_FISH\_BLOCK**</mark>](list-of-the-activators-for-executableitems.md#player_fish_block) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player right-click the fishing rod when the fishing rod bobber is on a block.**
* [<mark style="color:orange;">**PLAYER\_FISH\_ENTITY**</mark>](list-of-the-activators-for-executableitems.md#player_fish_entity) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player right-click the fishing rod when the fishing rod bobber catches an entity.**
* [<mark style="color:orange;">**PLAYER\_FISH\_FISH**</mark>](list-of-the-activators-for-executableitems.md#player_fish_fish) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player right-click the fishing rod when the fishing rod bobber catches something.**
* [<mark style="color:orange;">**PLAYER\_FISH\_NOTHING**</mark>](list-of-the-activators-for-executableitems.md#player_fish_nothing) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player fishes nothing.**
* [<mark style="color:orange;">**PLAYER\_FISH\_PLAYER**</mark>](list-of-the-activators-for-executableitems.md#player_fish_player) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player right-click the fishing rod when the fishing rod bobber catches a player.**
* <mark style="color:blue;">**PLAYER\_HARVEST\_BLOCK**</mark>: Activates when the player harvests a block (Example: Activator runs if the player right clicks a sweet berry bush that contains berries that can be harvested upon right-click)
* [<mark style="color:orange;">**PLAYER\_HIT\_ENTITY**</mark>](list-of-the-activators-for-executableitems.md#player_hit_entity) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">: **Activates when the player hits an entity**&#x20;
* [<mark style="color:blue;">**PLAYER\_HIT\_PLAYER**</mark>](list-of-the-activators-for-executableitems.md#player_hit_player) **:** Activates when the player hits a player
* [<mark style="color:orange;">**PLAYER\_ITEM\_BREAK**</mark>](list-of-the-activators-for-executableitems.md#player_item_break) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player breaks the item by making it loose all its durability.**
* [<mark style="color:orange;">**PLAYER\_JUMP**</mark>](list-of-the-activators-for-executableitems.md#player_jump) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player jumps. (In 1.21.2+, it can trigger even if the player is in the air)**
* <mark style="color:blue;">**PLAYER\_KICK**</mark>: Activates when the player gets kicked
* [<mark style="color:orange;">**PLAYER\_KILL\_ENTITY**</mark>](list-of-the-activators-for-executableitems.md#player_kill_entity) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player kills an entity.**
* [<mark style="color:orange;">**PLAYER\_KILL\_PLAYER**</mark>](list-of-the-activators-for-executableitems.md#player_kill_player) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player kills a player.**
* [<mark style="color:blue;">**PLAYER\_LAUNCH\_PROJECTILE**</mark>](list-of-the-activators-for-executableitems.md#player_launch_projectile): Activates when the player shoots a projectile.
* <mark style="color:blue;">**PLAYER\_LEAVE\_THEIR\_LAND**</mark>**&#x20;: Activates if you leave your land or a land where you are trusted**
* [<mark style="color:orange;">**PLAYER\_LEAVE\_THEIR\_PLOT**</mark>](list-of-the-activators-for-executableitems.md#player_leave_his_plot) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates if you leave a plot from the PlotSquared plugin.**
* [<mark style="color:blue;">**PLAYER\_LEFT\_CLICK**</mark>](list-of-the-activators-for-executableitems.md#player_left_click) : Activates when the player left-clicks the item.
* <mark style="color:blue;">**PLAYER\_MEND\_THE\_EI**</mark>: Activates when the player mends the EI
* <mark style="color:blue;">**PLAYER\_OPEN\_INVENTORY**</mark>: Activates when the player opens inventory
* <mark style="color:orange;">**PLAYER\_PICKUP\_THE\_EI**</mark> <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> : Activates when the player pick ups the ExecutableItem.
* <mark style="color:blue;">**PLAYER\_PORTAL**</mark>: Activates when the player uses a portal
* <mark style="color:orange;">**PLAYER\_RECEIVE\_EFFECT**</mark><img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">: Activates when the player receives an effect
* [<mark style="color:orange;">**PLAYER\_RECEIVE\_HIT\_BY\_ENTITY**</mark>](list-of-the-activators-for-executableitems.md#player_receive_hit_by_entity) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when you get hit by anything from an entity.**
* [<mark style="color:orange;">**PLAYER\_RECEIVE\_HIT\_BY\_PLAYER**</mark>](list-of-the-activators-for-executableitems.md#player_receive_hit_by_player) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when you get hit by anything from a player.**
* [<mark style="color:orange;">**PLAYER\_RECEIVE\_HIT\_GLOBAL**</mark>](list-of-the-activators-for-executableitems.md#player_receive_hit_global) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when you get hit by anything.**
* <mark style="color:blue;">**PLAYER\_REGAIN\_HEALTH**</mark>: Activates when the player regains health
* [<mark style="color:orange;">**PLAYER\_RESPAWN**</mark>](list-of-the-activators-for-executableitems.md#player_respawn) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player re-spawns.**
* [<mark style="color:blue;">**PLAYER\_RIGHT\_CLICK**</mark>](list-of-the-activators-for-executableitems.md#player_right_click) : Activates when the player right-clicks the item. (IT REQUIRES EITHER HAVE AN ITEM IN THE HAND OR TARGET AT A BLOCK TO BE TRIGGERED, THIS IS A SPIGOT LIMITATION)
* <mark style="color:blue;">**PLAYER\_RIPTIDE**</mark>: Activates when the player riptides
* [<mark style="color:orange;">**PLAYER\_SELECT\_THE\_EI**</mark>](list-of-the-activators-for-executableitems.md#player_select_the_ei) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player selects the EI item in the hotbar.**
* [<mark style="color:orange;">**PLAYER\_SHEAR\_ENTITY**</mark>](list-of-the-activators-for-executableitems.md#player_shear_entity) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player shears an entity.**
* <mark style="color:orange;">**PLAYER\_SHIELD\_BREAK\_BY\_PLAYER**</mark><img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">: Activates when the shield of the player gets broken by someone else.
* <mark style="color:blue;">**PLAYER\_SPAWN\_CHANGE**</mark>: Activates when the player changes their spawn
* <mark style="color:blue;">PLAYER\_SWAPHAND\_THE\_EI</mark>: Activates when the player swaphand the EI.
* [<mark style="color:orange;">**PLAYER\_TARGETED\_BY\_AN\_ENTITY**</mark>](list-of-the-activators-for-executableitems.md#player_targeted_by_an_entity) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">: Activates when an entity targets the player.
* <mark style="color:blue;">**PLAYER\_TRAMPLE\_CROP**</mark> : Activates when the player tramples a crop.
* [<mark style="color:orange;">**PLAYER\_UNEQUIP\_THE\_EI**</mark>](list-of-the-activators-for-executableitems.md#player_unequip_the_ei) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates if you unequip the EI.**
  * **The plugin CMI can break** this activator be sure you have the `cmi.inventoryhat` permission set to **false**&#x20;
* [<mark style="color:orange;">**PLAYER\_WALK**</mark>](list-of-the-activators-for-executableitems.md#player_walk) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player walks.**
* [<mark style="color:orange;">**PLAYER\_WRITE\_COMMAND**</mark>](list-of-the-activators-for-executableitems.md#player_write_command) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player enters commands.**
* [<mark style="color:orange;">**PROJECTILE\_ENTER\_LIQUID**</mark>](list-of-the-activators-for-executableitems.md#projectile_enter_liquid) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">**: Activates if the launched projectile enters and stays long enough in water**
* [<mark style="color:orange;">**PROJECTILE\_HIT\_BLOCK**</mark>](list-of-the-activators-for-executableitems.md#projectile_hit_block) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the projectile of the player hits a block.**
* [<mark style="color:orange;">**PROJECTILE\_HIT\_ENTITY**</mark>](list-of-the-activators-for-executableitems.md#projectile_hit_entity) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the projectile of the player hits an entity.**
* [<mark style="color:blue;">**PROJECTILE\_HIT\_PLAYER**</mark>](list-of-the-activators-for-executableitems.md#projectile_hit_player) : Activates when the projectile of the player hits a player.
* <mark style="color:blue;">**CUSTOM\_TRIGGER**</mark>: It can be executed by running a command, or it can be scheduled.
* <mark style="color:orange;">**EI\_ENTER\_IN\_THE\_PLAYER\_INVENTORY**</mark><img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the item enters to the player's inventory. (**&#x49;f when a plugin gives an ExecutableItem to a player it doesn't trigger this activator, you should go on their support and ask them to call this method: [CLICK HERE](https://docs.ssomar.com/executableitems/developer-api#event-to-call-when-you-add-an-executableitem-in-a-player-inventory))
* <mark style="color:orange;">**EI\_LEAVE\_THE\_PLAYER\_INVENTORY**</mark><img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the item leaves the player's inventory. (** Require ProtocolLib to make this activator works properly **)**
* [<mark style="color:orange;">**INVENTORY\_CLICK**</mark>](list-of-the-activators-for-executableitems.md#inventory_click) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates when the player clicks the item in its inventory.**&#x20;
* [<mark style="color:orange;">**LOOP**</mark>](list-of-the-activators-for-executableitems.md#loop) <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> **: Activates in repeat as long as the item is in the player's inventor**
