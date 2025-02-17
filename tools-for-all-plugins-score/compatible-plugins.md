---
description: >-
  Here is a non-exhaustive list of plugin that you can combine with
  ExecutableItems
---

# ✔️ Compatible Plugins

{% hint style="info" %}
Take note that this list is strict related compatible plugins, almost every plugin is compatible with Ssomar plugins, if you want to run a command from another plugin, just replace the name of the target with the placeholders. \
\
For example essentials fly\
essentials:fly %player%\
\
For example vanish\
vanish %player%



For example essentials economy

economy give %player% 100\
\
Etcetera, **every command that supports the name of a player is "compatible" with EI |EB | EE.**
{% endhint %}

This section is for compatible plugins that works with Ssomar plugins, there are some features that we have that its compatible with the other plugins.

* Before starting you must know that compatible ≠ usable, allmost all plugins are usable for Ssomar Plugins, this is because all commands are run by the console, that means you can use your custom plugin's commands using the correct arguments. For example
  * Want to apply fly command from essentials to the player ?
    * essentials:fly %player%
  * Want to apply vanish command from essenntials to the player ?
    * vanish %player%
  * Want to give money from essentials economy to the player?
    * economy give %player% 100
  * And a big list, every command outside Ssomar plugin's world that supports a target where you can fill with %player% then it can be used.

### MythicMobs

#### You can make your MythicMobs mobs drop Ssomar Plugins Items in these ways:

*   ExecutableItems:

    1. Hold the ExecutableItem and do `/mm i import` , this will make the item to get imported into the items.yml file of MythicMobs, from there, you can add it to the LootTable of MythicMobs.
    2. Executing a skill \~onDeath from the mob, casting a command skill adding the next line:

    ```yaml
    Skills:
    - command{c="ei drop <item> 1 <caster.l.w> <caster.l.x> <caster.l.y> <caster.l.z>"} @self ~onDeath
    ```
* ExecutableBlocks:
  * The same idea but instead of using ExecutableItem use the ExecutableBlock, and on the command from skill use "eb" instead of "ei".

#### You can specify the activators from SsomarPlugins to only work with specific MythicMobs using this feature [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p\_e-detailedentities](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#p_e-detailedentities)

* Example : Creating an ExecutableItem that makes more damage to a list of MythicMobs
* Example: Creating an ExecutableBlock  that damages a specific MythicMob when it walks above the block
* Example: Creating an ExecutableEvent that only works for a list of MythicMobs.

#### You can summon MM Mobs using this command inside your activator:

* Depending on the activator you are using you may need to change the placeholders.
  * Example: Instead of %world% it may be needed to use %player\_world%,%target\_world% or %block\_world%

```yaml
activators:  
  activator1: # Activator ID, you can create as many activator on the activators list    
    commands:
    - mm m spawn {mob_id} 1 %world%,%x%,%y%,%z%
```

* ⭐You can use this idea with ExecutableBlocks and LOOP activator to create custom MythicMobs spawner.

#### Run MythicMobs skill from Ssomar Plugins features

* You can use on commands section  `SUDOOP mm test cast <skill>` to run a skill from MythicMobs.

#### Custom SCore commands

* [https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/entity-commands#changetomythicmob](https://docs.ssomar.com/tools-for-all-plugins-score/custom-commands/entity-commands#changetomythicmob)
  * ⭐Its possible to make a fishing system using MythicMobs like the one that is on the Hypixel Minecraft Server. For example having tier list of different fishing rods (All handled by ExecutableItems), that each tier will have from low probability to higher probability to catch more epic mobs from your lakes, adding restrictions to only fish MM mobs from the lakes in "x" cordinates (or a WorldGuard region), etc.

### **LevelledMobs**

* You can make your LevelledMobs drop ExecutableItems using this resource:
  * [https://www.spigotmc.org/resources/lm-items.102081/](https://www.spigotmc.org/resources/lm-items.102081/)

### AureliumSkills

* Ssomar Plugins have this feature [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#requiredmana](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#requiredmana) in order to have as requirement for the activator to work Mana.
* Aurelium Skills commands
  * Also you can use AureliumSkills commands on your plugin, such as giving mana to the player, giving mana to the players around (Like a supporter), etc.
* Aurelium Skills NBT
  * You can create an ExecutableItem that while holding it increases your maximum mana, this can be done by creating an item, running the `/sk modifier` command and then while holding the item running `/ei create <id>` now the ExecutableItem has the NBTTag of the command and so it has the modifications that you made.

### ExecutableBlocks & ExecutableItems

* You can link an ExecutableItems and ExecutableBlocks so the item will have activators as an item and same as a block, the usage will keep the same in both even if the EB is placed and then broke.

### ItemsAdder

* You can link an item/block from ItemsAdder and ExecutableItems (also the item texture & block texture is supported, etc). The method for items can be done with 2 ways:
  * Item:
    * By their side adding this in their .yml
      *

          ```
          executableitem:
            id: ZEUSCROWN
          ```
      * You can search more info in their wiki.
    * Having NBTAPI plugin, taking the ItemsAdder item on your hand and doing /ei create
  * Block:
    * And for block texture import the EB as ItemsAdder (from EB gui).



* detailedBlocks of specific activators supports ItemsAdder blocks
  * Example:

<pre><code>detailedBlocks:
<strong>- STONE
</strong><strong>- ANDESITE
</strong>- FURNACE{lit:true}
- ITEMSADDER:turquoise_block
</code></pre>

### Oraxen

* The Oraxen retexturing blocks is supported by EI as item retexturing
* The oragen retexturing blocks and furnitures is supported by EB.&#x20;

### PlaceholderAPI

* You can use any placeholder as a condition, as a variable, as a value to print, as a value to damage, as a value of almost anything you want.

### ShopGui+

* This plugin supports EI | EB from being sell in its shop.
* Also it has a command that allow you to sell all the items inside a chest

### ShopKeepers

* This plugin supports EI | EB from being sell in its shop.

### Tradesplus

* This plugin supports EI | EB from being sell in its shop.

### WorldGuard

* Inside conditions of EI |EB | EE you can select the condition if you want an activator to run if IN or OUTSIDE a region of WorldGuard
* Most of the commands are detected by WorldGuard first, so you can chill out thinking, "oh, the players will grief the server if I use a break command from EI", because that will not happen (unless you don't use a EI Command, for example setblock vanilla command, that is not protected with griefing.)
* Also on EB you can fill a WorldGuard region with specific percentages of eb, and normal blocks, useful for mines.

### HeadDB

* You can make your EI items to have the displayItem a head from HeadDB
* #### silentMessagePreventionErrorHeadDBError

{% hint style="info" %}
And then you can link it to an EB if want the EB to be a head, more info in EB FAQ.
{% endhint %}

### IridiumSkyblock

* Inside conditions of EI | EB | EE you can select the condition if you want an activator to run if is IN his island.

### SuperiorSkyblock

* Inside conditions of EI | EB | EE you can select the condition if you want an activator to run if is IN his island.
* Coop feature from the plugin SuperiorSkyblock. For example the commands like MINEINCUBE will not anymore be canceled for the coop players.

### GriefPrevention

* Inside conditions of EI | EB | EE you can select the condition if you want an activator to run if is IN his claim.

### Lands

* Inside conditions of EI | EB | EE you can select the condition if you want an activator to run if is IN his claim.
*   Two activators specific for the plugin Lands: &#x20;

    ```
    PLAYER_ENTER_IN_HIS_LAND
    PLAYER_LEAVE_HIS_LAND
    ```

### GriefDefender

* Inside conditions of EI | EB | EE you can select the condition if you want an activator to run if is IN his claim.

### Residence

* Inside conditions of EI | EB | EE you can select the condition if you want an activator to run if is IN his claim.

### PlotSquared

* Inside conditions of EI | EB | EE you can select the condition if you want an activator to run if is IN his Plot.

### Towny

* Inside conditions of EI | EB | EE you can select the condition if you want an activator to run if is IN his "town"

### Advanced Enchantments

* Due to how it works, their enchants are not present in the enchantments list. So it can't be added with the enchants feature:
* ![](<../.gitbook/assets/image (256).png>)
* But it's possible to add their enchants on your ExecutableItems:

- [ ] Require ExecutableItems premium to have access to the NBT tags modifications
- [ ] Require the plugin [NBT- API ](https://www.spigotmc.org/resources/nbt-api.7939/)
- [ ] Then you have two choices:
  * [ ] Create a vanilla item , add the AE on it and then do /ei create, the new EI will automatically have the Advanced enchantments.
  * [ ] Or modify manually the config of your existing ExecutableItem, open the config and add the good NBT tag. Look the example below:

```yaml
nbt:
  '0':
    key: ae_enchantment;haste
    type: INT
    value: 1
```

_It will add the Advanced enchantment **Haste** with a level of **1** on your ExecutableItem_

* [ ] Then you should edit the lore of your EI, to let your player know that their is an Advanced enchant on it.

### RoseLoots

* Most of the commands related to break supports the custom block loots from this plugin. Such as: MINEINCUBE-FARMINCUBE-BREAK-etc.

### MMOInventory

* The activator EI\_ENTER\_IN\_THE\_PLAYER\_INVENTORY is triggered by their methods.

### EnchantsSquared

* Items from ExecutableItems can have their enchantments.

### ExcellentEnchants

* Items from ExecutableItems can have their enchantments (it could be that the enchantments aren't displayed in the lore, this is problem of ExcellentEnchants, not our problem. Written in 12/28/2022)

### MMOCore

* requiredMana feature for activators can use mana from this plugin.

### TAB

* The custom command SETGLOW is compatible with TAB, just use the placeholder %score\_cmd-glow%

### BlocksToCommand

* This allows you to import structures that can be placed with EI | EB | EE.

### Terra

* Their biomes are supported by biome conditions

### EcoSkills

* You can use conditions to checks if the player has specific magic values.
* You can use commands to get or remove magic values.
* RequiredMagic

### FACTIONS UUID

* It supports
  * Block protections
  * Custom claim conditions

### CMI

* SELL\_CONTENT command supports CMI prices

### JOBS REBORN

* JOBS\_MONEY\_BOOST command work for this plugin.

### AURA SKILLS

* requiredMana features inside the activator supports the mana from this plugin.

### VAULT

* requiredMoney feature works with Vault.



### Citizen NPC

* PLAYER\_CLICK\_ON\_ENTITY
* ### PLAYER\_FISH\_ENTITY
* ### PLAYER\_KILL\_ENTITY





NBT API

* #### itemCheckWithNBTAPI

