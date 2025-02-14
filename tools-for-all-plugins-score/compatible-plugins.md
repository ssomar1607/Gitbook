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

### MythicMobs

*   You can make your mm mobs drop EI Items in two ways:

    1. First one holding the EI Item and typing /mm i import , this will make the item to get imported into the items.yml file of mm, from there, you can add it to the LootTable of MythicMobs.
    2. Second one is executing a skill \~onDeath from the mob, casting a command skill adding the next line:

    ```yaml
    Skills:
    - command{c="ei drop <item> 1 <caster.l.w> <caster.l.x> <caster.l.y> <caster.l.z>"} @self ~onDeath
    ```

{% hint style="info" %}
To make drop EB is the same idea
{% endhint %}



* You can make your Items/blocks/events to damage/run skills to specific MM mobs using the detailedEntities, so, for example, in EI you could make a sword that makes 60% more damage to a list of MM mobs (like a ender sword -> it makes more damage to all your mm from end), or in EB damage a specific mob that walks above it, or in EE create a specific event that only works for that mob.



* You can summon MM Mobs using this command inside your activator:

```yaml
mm m spawn (mob_id) 1 %world%,%x%,%y%,%z%
```

{% hint style="info" %}
**It is probably that some placeholder don't work depending on the activator you are using, you may need to change %world% to %player\_world% in some cases, or select the ones that will work depending on your config**
{% endhint %}

{% hint style="info" %}
This brings you the idea that MM spawners are possible, but would need premium version.
{% endhint %}



* You can make item system where you can only use "x" item after a MM mobs does something, using the condition of tag, and using the mechanic add tag from MM.



*   <mark style="color:orange;">**\[PREMIUM]**</mark> You can make a fishing system related with MythicMobs like the one in Hypixel.&#x20;

    * For example having tier list of fishing rods, from low probability to higher probability to catch more epic mobs from your lakes, adding restrictions to only fish MM mobs from the lakes in "x" cordinates (or a WorldGuard region), etc.


* Also using the skills from MythicMobs, you could either combine the ExecutableItem with MythicCrucible or just add the command `SUDOOP mm test cast <skill>` (it isn't a good way, but here is explained just in case you want this 100%)
* #### detailedEntities

### **LevelledMobs**

* You can make your LevelledMobs drop EI items thanks to this following resource:

{% embed url="https://www.spigotmc.org/resources/lm-items.102081/" %}
Lm-Items is a bridge resource between LevelledMobs and ExecutableItems
{% endembed %}

### AureliumSkills

* You can make a system of mana related with skills inside EI | EB | EE, so, some abilities would need mana to be run, or some others give you mana, give mana around you (like supporter idk), etc etc.
  * To make an ExecutableItem that increases the cap of mana with aurelium skills, you first need NBTApi, then use their methods (sk modifier) to add cap to an item, hold it and type /ei create, now the EI has its methods, so the EI increases the cap.
* RequiredMana

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



