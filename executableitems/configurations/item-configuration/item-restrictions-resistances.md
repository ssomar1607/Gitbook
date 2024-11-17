# Item Restrictions/Resistances



{% hint style="info" %}
This page will teach you about item restrictions. All restrictions are set to false by default.
{% endhint %}

* If you want to apply a certain restriction across all items, manually add the restriction in your `config.yml`.

{% code title="config.yml" %}
```yaml
# ----------------------------------
# -
#       ExecutableItems
# -
#         By: Ssomar
# -
# ----------------------------------
# -
# WIKI HERE : https://docs.ssomar.com/executableitems/information-ei
# DISCORD HERE : https://discord.com/invite/TRmSwJaYNv
# -
pickup-limit: -1
disable-world: [ ]
premium-enable-cooldown-for-op: true #Premium only
checkVersionMsg: true
disableTestItems: false # If you have a big server with a lot of players, it's recommended to turn this option on true
silentEIGive: false
silentMessagePreventionErrorHeadDBError: false
disableBackup: false #<- Backup your items config at each start / reload of the server
deleteBackupsAfterDays: 7 #<- It will deletes backups older than this number of days
restrictions:
  cancel-deposit-in-furnace: true
  cancel-item-frame: true
  cancel-rename-anvil: true
  cancel-anvil: true
  cancel-grind-stone: true
  cancel-item-delete-by-lightning: true
  cancel-item-place: true
```
{% endcode %}

* Brute-forcing items with container restrictions such as `cancel-deposit-chest` using hoppers would have the EI item stuck in that container and can only be removed via creative mode or by destroying the container holding the item.

```yaml
restrictions:
  cancel-deposit-in-furnace: true
  cancel-item-frame: true
  cancel-rename-anvil: true
  cancel-anvil: true
  cancel-grind-stone: true
  cancel-item-delete-by-lightning: true
  cancel-item-place: true
  cancel-hopper: true
  cancel-enchant: true
  cancel-merchant: true
  cancel-cartography: true
  cancel-brewing: true
  cancel-item-delete-by-cactus: true
  cancel-lectern: true
  cancel-composter: true
  cancel-consumption: true
  cancel-item-drop: true
  cancel-dropper: true
  cancel-item-craft: true
  cancel-smithing-table: true
  locked-in-inventory: true
  cancel-tool-interactions: true
  cancel-dispenser: true
  cancel-item-burn: true
  cancel-item-craft-no-custom: true
  cancel-enchant-anvil: true
  cancel-swap-hand: true
  cancel-beacon: true
  cancel-loom: true
  cancel-deposit-in-chest: true
  cancel-stone-cutter: true
```

### CANCEL DROP

* Info: Prevents players from dropping the executable item
* Config: `cancel-item-drop: false`
* Default: true

####

### CANCEL PLACE

* Info: Prevents players from placing executable items into the ground
* Config: `cancel-item-place: true`

####

### CANCEL CRAFT

* Info: Prevents players from crafting vanilla recipes with the said executable items (including custom crafting recipes from Wolfy's CustomCrafting plugin)
* Config: `cancel-item-craft: true`

####

### CANCEL CRAFT NO CUSTOM

* Info: Prevents players from crafting vanilla recipes with the said executable items but can still be used for custom crafting recipes from Wolfy's CustomCrafting plugin
* Config: `cancel-item-craft-no-custom: true`



### CANCEL DECORATED POT

* Info: Prevents players from putting executable items in the decorated pots
* Config: `cancel-decorated-pot: false`



### CANCEL DEPOSIT CHEST

* Info: Prevents players from putting executable items in the following,
  * Chest
  * Ender Chest
  * Trapped Chest
  * Barrel
  * Shulker Box
* Config: `cancel-deposit-in-chest: false`
* **NOTE: THIS WILL NOT WORK ON CREATIVE**

####

### CANCEL DEPOSIT FURNACE

* Info: Prevents players from putting executable items in the following,
  * Furnace
  * Blast Furnace
  * Smoker
* Config: `cancel-deposit-in-furnace: false`
* **NOTE: THIS WILL NOT WORK ON CREATIVE**

####

### CANCEL ITEM BURN (IN FIRE/LAVA)

* Info: Prevents the item to get burn in fire or lava
* Config: `cancel-item-burn: true`



### CANCEL ITEM DELETE BY CACTUS

* Info: Prevents the item to get deleted when touching a cactus
* Config: `cancel-item-delete-by-cactus: true`



### CANCEL ITEM DELETE BY LIGHTNING

* Info: Prevents the item to get deleted when a lightning strikes it.
* Config: `cancel-item-delete-by-lightning: true`



### CANCEL ENCHANT

* Info: Prevents players from enchanting this item in any way
* Config: `cancel-enchant: false`

####

### CANCEL ANVIL

* Info: Prevents players from putting executable items in anvils
* Config: `cancel-anvil: true`

####

### CANCEL HORSE

* Info: Prevents the EI placing on horses/mules/llamas
* Config: `cancel-horse: true`



### CANCEL ACTION RENAME IN ANVIL

* Info: Prevents players from renaming EI items in the anvil
* Config: `cancel-rename-anvil: true`

####

### CANCEL ACTION ENCHANT IN ANVIL

* Info: Prevents players from enchanting EI items in the anvil
* Config: `cancel-enchant-anvil: true`

####

### CANCEL CONSUMPTION

* Info: Prevents players from consuming executable items
* Config: `cancel-consumption: false`
*

### CANCEL CRAFTER

* Info: Prevents players from putting the executable items into crafter
* Config: `cancel-crafter: false`



### LOCKED IN INVENTORY

* Info: Makes the executable item stay in that slot number and prevents players from moving it in any way possible
* Config: `locked-in-inventory: false`
* **NOTE: THIS WILL NOT WORK ON CREATIVE**

####

### CANCEL TOOL INTERACTIONS

* Info: Prevents players from using executable items to do tool interactions
* Config: `cancel-tool-interactions: false`

####

### CANCEL ITEM FRAME

* Info: Prevents players from putting executable items in item frames
* Config: `cancel-item-frame: false`

####

### CANCEL SMITHING TABLE

* Info: Prevents players from putting executable items in smithing tables
* Config: `cancel-smithing-table: false`

####

### CANCEL GRIND STONE

* Info: Prevents players from putting executable items in grindstones
* Config: `cancel-grind-stone: true`

####

### CANCEL STONE CUTTER

* Info: Prevents players from putting executable items in stonecutters
* Config: `cancel-grind-stone: true`

####

### CANCEL EVENT IF NO PERM

* Info: Prevents players from using executable items if he hasn't the permission (example if player has a pickaxe executable item, if he hasn't the perm of this executable item, he can't mine with it)
* Config: `cancelEventIfNoPerm: true`

####

### CANCEL EVENT IF NOT OWNER

* Info: Prevents players from using executable items if he isn't the owner of this EI (example if player has a pickaxe EI, if isn't the owner, he can't mien with it)
* Config: `cancelEventIfNotOwner: true`

####

### CANCEL BREWING

* Info: Prevents players from putting EI items into brewing stands
* Config: `cancel-brewing: false`

####

### CANCEL BEACON

* Info: Prevents players from putting EI items into beaconds
* Config: `cancel-beacon: false`

####

### CANCEL CARTOGRAPHY

* Info: Prevents players from putting EI items into cartographies
* Config: `cancel-cartography: false`

####

### CANCEL COMPOSTER

* Info: Prevents players from putting EI items into composters
* Config: `cancel-composter: false`

####

### CANCEL DISPENSER

* Info: Prevents players from putting EI items into dispensers
* Config: `cancel-dispenser: false`

####

### CANCEL DROPPER

* Info: Prevents players from putting EI items into droppers
* Config: `cancel-dropper: false`

####

### CANCEL HOPPER

* Info: Prevents players from putting EI items into dispensers. (Not to be confused with putting items to hoppers via dropping them on top of hoppers
* Config: `cancel-hopper: false`

####

### CANCEL LECTERN

* Info: Prevents players from putting EI items into lecterns
* Config: `cancel-lectern: false`

####

### CANCEL MERCHANT

* Info: Prevents players from putting EI items into villager trades
* Config: `cancel-merchant: false`



### CANCEL SWAP HAND

* Info: Prevents players from swapping hand with the item
* Config: `cancel-swaphand: false`



### CANCEL HORN

* Info: Prevents players from playing the horns
* Config: `cancel-horn: false`



### CANCEL ARMOR STAND

* Info: Prevents players from placing the item on an armor stand
* Config: `cancel-armorstand: true`
