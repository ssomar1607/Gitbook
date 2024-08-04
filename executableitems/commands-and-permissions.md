# ⌨️ Commands & Permissions

## Permissions

**TIP for beginners:**

{% hint style="info" %}
To give the permissions of all items, I advice you to download a permission plugin like [**Luckperms**](https://www.spigotmc.org/resources/luckperms.28140/), Once you have a perm plugin you just need to give the permission **`ei.item.*`**, for Luckperm the command is  <mark style="color:blue;">`/lp group default permission set ei.item.* true`</mark>
{% endhint %}

#### Item permission

* Permission: `ei.item.{id}`
* Negative permission: `-ei.item.{id}` <img src="../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">
* Example: `ei.item.Test`
* Give all items permission: `ei.item.*`&#x20;

#### Bypass cooldown permission

* Permission: `ei.nocd.{id}` `ei.nocd.*`
* Description: Give this custom permission to disable the cooldown for your vip players
* (Be sure to test without being op)

#### Give all permissions of EI

* Permission: `ei.*`

#### Give all commands permissions of EI

* Permission: `ei.cmds`

## Commands

#### Create a new ExecutableItem

* Command: <mark style="color:blue;">**/ei create {id}**</mark>
* Tip:&#x20;
  * If you want **copy the item of another plugin**, or a custom vanilla item (Banner, Shield, ...), it's simple ! Take it in your main hand and execute the create command.
* Permission: `ei.cmd.create`

#### Open the editor / menu

* Command: <mark style="color:blue;">**/ei editor**</mark> or <mark style="color:blue;">**/ei show**</mark>
* Permission: `ei.cmd.editor` or `ei.cmd.show`

#### Reload the plugin

* Command: <mark style="color:blue;">**/ei reload**</mark>
* Permission: `ei.cmd.reload`

**Reload only 1 item**

* Command: <mark style="color:blue;">**/ei reload \<Id of the item>**</mark>
* Permission: `ei.cmd.reload`

**Reload a folder**

* Command: <mark style="color:blue;">**/ei reload folder:Name\_Of\_My\_Folder**</mark>
* Permission: `ei.cmd.reload`

#### Regenerates the default items configs

* Command: <mark style="color:blue;">**/ei default\_items**</mark>
* Permission: `ei.cmd.default_items`

#### Delete an ExecutableItem

* Command: <mark style="color:blue;">**/ei delete {id}**</mark>
* Permission: `ei.cmd.create`

#### Edit an ExecutableItem with a command

* Command: <mark style="color:blue;">**/ei edit {id}**</mark>
* Permission: `ei.cmd.edit`

#### Clear all cooldowns and delayed commands of EI

* Command: <mark style="color:blue;">**/ei clear**</mark>** **<mark style="color:purple;">**\[playerName] \[ALL/DELAYED\_COMMANDS/COOLDOWNS/ACTIONBARS]**</mark>
  * ALL - Resets the player's delayed commands, cooldowns and actionbars
  * DELAYED\_COMMANDS - Resets all delayed commands caused by DELAY and DELAYTICK
  * COOLDOWNS - Resets all player's cooldowns across all items
  * ACTIONBARS - Resets all player's actionbars from the ACTIONBAR custom command
* Permission: `ei.cmd.clear`

{% hint style="info" %}
It supports entities too just use the entity UUID instead of player name
{% endhint %}

#### Enable / Disable actionbar of EI

* Command: <mark style="color:blue;">**/ei actionbar**</mark>** **<mark style="color:orange;">**{on or off}**</mark>
* Permission: `ei.cmd.actionbar`

#### Inspect the ExecutableItem that is in your main hand

* Command: <mark style="color:blue;">**/ei inspect**</mark>
* Requirement: The item must have the option `storeItemInfos: true`
* \+ : it shows the owner of the item, id, usage, and more !&#x20;
* Permission: `ei.cmd.inspect`

#### Remove the owner of the EI that is in your hand

* Command: <mark style="color:blue;">**/ei unowned**</mark>
* \+ : After that the next player who click on this item will become the new owner (the player must be not op)
* Permission: `ei.cmd.unowned`

#### Take EI from player inventory

* Command: <mark style="color:blue;">**/ei take {playername} {id} {quantity}**</mark>
* Permission: `ei.cmd.take`

#### Refresh the ExecutableItems of your players with the last version of the lore , name, attributes... (The players must have the EIs in their inventory)

* command: <mark style="color:blue;">**/ei refresh**</mark>** **<mark style="color:orange;">**{playername or all} {ExecutableItemID or all}**</mark>** **<mark style="color:blue;">**{resetUsage} {resetDurability}**</mark>
* Permission: `ei.cmd.refresh`

#### **Modify the owner of the EI that is in your hand**

* command: <mark style="color:blue;">/ei set\_owner</mark> <mark style="color:orange;">\<playerName></mark>

{% hint style="info" %}
It works even with offline players
{% endhint %}

#### Open the debug mode

* It is useful to check when an activator is being activated
* command: <mark style="color:blue;">/ei debug</mark>



### Give commands

#### Give command

* Command: (The variables and usage part besides the id is optional)
  * <mark style="color:blue;">**/ei give {playername} {id}**</mark><mark style="color:purple;">{Variables:{var\_id:val},Usage:val}</mark> <mark style="color:blue;">**{quantity}**</mark> \[giveOfflinePlayer default true]
  * Examples:&#x20;
    * <mark style="color:blue;">**/ei give %player% Genesis\_Crystal{Variables:{vibraniun:10,proton:30},Usage:10} 3**</mark>&#x20;
    * <mark style="color:blue;">**/ei give %player% SurgeBlade{Variables:{charge:%var\_charge%+1},Usage:%usage%-1} 1**</mark>
    * <mark style="color:blue;">**/ei give %player% BoneBlade 1**</mark>
* Permission: `ei.cmd.give`
* Works for offline players

#### GiveAll command

* Command:&#x20;
  * <mark style="color:blue;">**/ei giveall {id} {quantity}**</mark>** **<mark style="color:purple;">**\[world]**</mark> \[giveOfflinePlayer default false]
* Permission: `ei.cmd.giveall`
* Does not work for offline players

#### Give an EI in a specific slot of a player  <img src="../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Command: (The variables and usage part besides the id is optional)
  * <mark style="color:blue;">**/ei giveslot {playername} {id}**</mark><mark style="color:purple;">{Variables:{var\_id:val},Usage:val}</mark> <mark style="color:blue;">**{quantity} {slot}**</mark>**  **<mark style="color:purple;">**\[override true or false]**</mark>
  * Examples:&#x20;
    * <mark style="color:blue;">**/ei giveslot Ssomar test{Variables:{x:"Hey",world:"Island"},Usage:50} 1 0**</mark> &#x20;
    * <mark style="color:blue;">**/ei giveslot Special70 rum{Usage:69420,Variables:{tell\_me:"why",aint\_nothing:"BUT A HEARTBREAK"\}} 1 %slot%**</mark>
  * _Default usage : The usage that is in the config of your EI_
  * _Override allow the EI to take that slot, and if there was an item there, it is going to move to another slot or get dropped to the ground._
* Permission: `ei.cmd.giveslot`

**Give every EI in a specific folder to a player**

* Command:
  * <mark style="color:blue;">**/ei givefolder {playername} {folder} {quantity}**</mark>

### Drop commands

#### Drop an EI at a specific location / position <img src="../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Command:&#x20;
  * <mark style="color:blue;">**/ei drop {id}**</mark>** **<mark style="color:purple;">**\[quantity] \[world] \[x] \[y] \[z]**</mark>
    * <mark style="color:blue;">**Example:**</mark>
      * <mark style="color:blue;">**ei drop totemshatter 1 %world% %x% %y% %z%**</mark>
      * <mark style="color:blue;">**ei drop nuclearWar{Usage:3,Variables:{niconico:"nii"\}} 25 %block\_world% %block\_x% %block\_y% %block\_z%**</mark>
      * <mark style="color:blue;">**ei drop cybert1\_5{Variables:{eh:5},Usage:5} 1 world 535 74 1329**</mark>
  * _Default quantity : 1_
  * _Default location : The location of the player who has executed this command_
* Permission: `ei.cmd.drop`

### Modification commands

#### Modify the usage of a created ExecutableItem

*   Command:&#x20;

    * <mark style="color:blue;">**In-game > /ei modification set|modification usage {slot} {value}**</mark>
    * <mark style="color:blue;">**In console > /ei console-modification set|modification usage {player} {slot} {value}**</mark>
    * set: Set a new value
    * modification: if the value set is positive it will increase the actual value of the usage otherwise it will decrease the usage
    * For the slot check the image below:



    <img src="https://i.imgur.com/KAwW8N0.png" alt="" data-size="original">
* Permission: `ei.cmd.modification`

#### Modify a variable

* VIA CONSOLE
  * Command:&#x20;
    * `/ei console-modification {set/modification} variable {player} {slot} {variableName} {value}`
* VIA on game
  * Command:
    * `/ei modification {set/modification} variable {slot} {variableName} {value}`



#### Search EI in the server

* Command:
  * `/ei search [Item ID] [search mode]`
  *   Search modes:

      * players: Search an EI in all **online** player inventories
      * containers: Search an EI in all **loaded** containers
      * all: both last.


  * Example: /ei search EternalSword all

