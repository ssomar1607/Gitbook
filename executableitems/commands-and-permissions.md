# ⌨️ Commands & Permissions

On this page you will learn about Commands and Permissions of ExecutableItems plugin.

Starred features ⭐ are for premium version.

## Permissions

**TIP for beginners:**

{% hint style="info" %}
To give the permissions of all items, I advice you to download a permission plugin like [**Luckperms**](https://www.spigotmc.org/resources/luckperms.28140/), Once you have a perm plugin you just need to give the permission **`ei.item.*`**, for Luckperm the command is  <mark style="color:blue;">`/lp group default permission set ei.item.* true`</mark>
{% endhint %}

#### Item permission

* Info: Permission for a player to use an ExecutableItems.
  * Permission for using specific ExecutableItem ID: `ei.item.{id}`
  * Permission for using all ExecutableItems: `ei.item.*`&#x20;
  * ⭐Negative permission to prohibit a specific ExecutableItems ID: `-ei.item.{id}`
* Example: `ei.item.test`

#### Bypass cooldown permission

* Info: Permission for a player to not have cooldown while using an ExecutableItems.&#x20;
  * While testing you must test without op/operator/admin.
  * Permission to bypass specific ExecutableItems ID: `ei.nocd.{id}`
  * Permission to bypass all ExecutableItems: `ei.nocd.*`
* Example: `ei.nocd.test`

#### All permissions

* Info: Permission that grants all permissions for ExecutableItems.
  * Be careful ! This one grants literally every permission, even the administrator ones.
  * Permission: `ei.*`
* If you want to give a specific permission keep reading below, it will be detailed every command with each permission.

#### All commands permissions

* Info: Permission that grants all commands permissions for ExecutableItems.
  * Permission: `ei.cmds`
* If you want to give a specific permission keep reading below, it will be detailed every command with each permission.

## Commands

Here you will learn about commands of ExecutableItems, there will be some words that will be repeaten through the explanation, here they are:

* SsomarPluginsItem: Its the ID of an ExecutableItem that its created, the same way it can be "Excalibur", "SuperPickaxe", "turtle", "12345", we stablished this name.
* SsomarPluginsPlayer: Its the name of a player, the same way there is "Vayk\_", "Ssomar", "Special70", "Tidal\_Flame" there is also this name.

The format of the commands will have different symbols:

* {} : If an argument is surrounded by {} that means its necessary to run the command.
* \[] : If an argument is surrounded by \[] that means its optional to run the command.

Also there will be different colors (but its the same idea as {} and \[] ):

* Blue: Obligatory
* Orange: Optional

### General Commands

#### Create a new ExecutableItem

* Command: <mark style="color:blue;">**/ei create {id}**</mark>
  * id: ID of the ExecutableItem.
  * If you want **copy the item of another plugin**, or a custom vanilla item (Banner, Shield, ...), it's simple ! Take it in your main hand and execute this create command.
* Example: `/ei create SsomarPluginsItem`
* Permission: `ei.cmd.create`

#### Create a new ExecutableItem from a targeted block

* Command: /ei create-from\_block {id}
  * id: ID of the ExecutableItem.
* Example: `/ei create-from_block SsomarPluginsItem`
* Permission: `ei.cmd.create-from-block`

#### Open the editor / menu

* Command: <mark style="color:blue;">**/ei editor**</mark> or <mark style="color:blue;">**/ei show**</mark>
* Permission: `ei.cmd.editor` or `ei.cmd.show`

#### Reload the plugin

* Command: <mark style="color:blue;">**/ei reload**</mark>
* Permission: `ei.cmd.reload`

**Reload only 1 item**

* Command: <mark style="color:blue;">**/ei reload {id}**</mark>
  * id : ID of the ExecutableItem.
* Example: `/ei reload SsomarPluginsItem`
* Permission: `ei.cmd.reload`

**Reload a folder**

* Command: <mark style="color:blue;">**/ei reload folder:Name\_Of\_My\_Folder**</mark>
* Permission: `ei.cmd.reload`

#### Regenerates the default items configs

* Command: <mark style="color:blue;">**/ei default\_items**</mark>
* Permission: `ei.cmd.default_items`

#### Delete an ExecutableItem

* Command: <mark style="color:blue;">**/ei delete {id}**</mark>
  * id: ID of the ExecutableItem.
* Example: `/ei delete SsomarPluginsItem`
* Permission: `ei.cmd.create`

#### Edit an ExecutableItem with a command

* Command: <mark style="color:blue;">**/ei edit {id}**</mark>
  * id : ID of the ExecutableItem.
* Example: `/ei edit SsomarPluginsItem`
* Permission: `ei.cmd.edit`

#### Clear all cooldowns and delayed commands of ExecutableItems

* Command: <mark style="color:blue;">**/ei clear {target} \[optionaltarget]**</mark>
  * target
    * You can use player names to target a player
    * You can use UUID to target an entity.
  * optional\_target
    * ALL: Resets the player's delayed commands, cooldowns and actionbars.
    * DELAYED\_COMMANDS: Resets all delayed commands caused by DELAY and DELAYTICK.
    * COOLDOWNS: Resets all player's cooldowns across all items.
    * ACTIONBARS - Resets all player's actionbars from the ACTIONBAR custom command.
* Example: `/ei clear SsomarPluginsPlayer COOLDOWNS`
* Permission: `ei.cmd.clear`

#### Enable / Disable actionbar of ExecutableItems

* Command: <mark style="color:blue;">**/ei actionbar {on or off}**</mark>
* **Example:** `/ei actionbar off`
* Permission: `ei.cmd.actionbar`

#### Inspect the ExecutableItem that is in your main hand

* Command: <mark style="color:blue;">**/ei inspect**</mark>
  * In order to use this command the ExecutableItem must have the feature of store item info enabled. [https://docs.ssomar.com/executableitems/configurations/item-configuration/item-features#store-item-info](https://docs.ssomar.com/executableitems/configurations/item-configuration/item-features#store-item-info)
  * Output:
    * Usage
    * Owner UUID
    * Owner name
    * ExecutableItems ID
    * Variables&#x20;
* Permission: `ei.cmd.inspect`

#### Remove the owner of the EI that is in your hand

* Command: <mark style="color:blue;">**/ei unowned**</mark>
  * In order to un-own an item it must have an owner before, to do that the feature of [https://docs.ssomar.com/executableitems/configurations/item-configuration/item-features#store-item-info](https://docs.ssomar.com/executableitems/configurations/item-configuration/item-features#store-item-info) must be enabled on that ExecutableItem
  * After running this command, the next player who interact with this item will be the next owner. (He must not be operator/op/admin)
* Permission: `ei.cmd.unowned`

#### Take EI from player inventory

* Command: <mark style="color:blue;">**/ei take {player} {id} {quantity}**</mark>
  * player: Name of the player to take the item from
  * id: Id of the ExecutableItems
  * quantity: Integer value of the amount to remove
* Example: `/ei take SsomarPluginsPlayer SsomarPluginsItem 1`
* Permission: `ei.cmd.take`

#### Refresh the ExecutableItem(s) of your player(s) with their last config version

* Info: This command refresh the ExecutableItemID(s) to their last version on its/their config, that means, if a player has an ExecutableItem on old version for example with attribute of GENERIC\_ARMOR to 10, and then you change the value of the attribute on the config of the ExecutableItem, it will not be update on the player side, to allow this update you can use this command so its refreshed and he will have instead of 10 the new updated value.
  * In order to make this process of refresh the ExecutableItem(s) selected must be on the players inventory, otherwise they won't be refreshed
  * As a tip, another way to make this refresh is using [https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#auto-update-item](https://docs.ssomar.com/executableitems/configurations/activator-configuration/activators-features#auto-update-item)
* Command: <mark style="color:blue;">**/ei refresh {player} {ExecutableItemID}**</mark>**&#x20;**<mark style="color:orange;">**{resetUsage} {resetDurability}**</mark>
  * player: Name of a specific player or "all" to target all players online.
  * ExecutableItemID: Name of a specific ExecutableItem or "all" to target all ExecutableItems created.
  * resetUsage: Boolean value to allow through the refresh process to reset the usage value
  * resetDurability: Boolean value to allow through the refresh process to reset the durability value
* Permission: `ei.cmd.refresh`

#### **Modify the owner of the ExecutableItem that is in your hand**

* Command: <mark style="color:blue;">**/ei set\_owner**</mark> <mark style="color:blue;">**{player}**</mark>
  * player: Name of the player to set as target of this command
    * It works with offline players.
* Permission: `ei.cmd.set_owner`

#### Enable debug mode

* Info: Mode where each activator prints to the user different messages to know the state of the activator and know why it is not working on how it is being activated.
* Command: <mark style="color:blue;">**/ei debug**</mark>
* Permission: `ei.cmd.debug`

### Give commands

#### Give command

* Info: Command to give a player an ExecutableItem in the first slot available.
* Command: <mark style="color:blue;">**/ei give {player} {id}**</mark><mark style="color:orange;">**{Variables:{var\_id:value},Usage:value}**</mark>**&#x20;**<mark style="color:blue;">**{quantity}**</mark>**&#x20;**<mark style="color:orange;">**\[giveOfflinePlayer]**</mark>
  * player: Name of the player who will be the target of this command
  * id: Id of the ExecutableItem to give.
    * Optional values: In order to add this custom setup, there must be no space(s)/white space(s) in the format.&#x20;
      * Variables: You can select a setup of variables for when giving the item.
        * ✅`{Variables:{a:"1",b:"2",c:"3"}}` # Not use of whitespaces
        * ❌`{Variables:{a : "1",b: "2",c :"3"}}` # Use of whitespaces
      * Usage: You can select a value for the usage when giving the item
        * ✅`{Usage:5}` # Not use of white space(s)
        * ❌`{Usage : 5}` # Use of white space(s)
      * **Durability**: You can decide how much durability the item loses upon giving the user the item
        * ✅`{Durability:5}` # Not use of white space(s)
        * ❌`{Durability : 5}` # Use of white space(s)
  * quantity: Amount of items to give
  * giveOfflinePlayer: Boolean value to set if the item will be given to an offline player or not. By default this value is on true.
* Examples: (On all this examples the commands is being run inside an ExecutableItems in order to parse placeholders such as %player%,%var\_name% and %usage%)
  * `/ei give %player% Genesis_Crystal{Variables:{vibraniun:10,proton:30},Usage:10} 3`&#x20;
  * `/ei give %player% SurgeBlade{Variables:{charge:%var_charge%+1},Usage:%usage%-1} 1`
  * `/ei give SsomarPluginsPlayer BoneBlade 1`
  * `/ei give edp445 cupcake{Durability:12} 1`
* Permission: `ei.cmd.give`

#### Give All command

* Command: <mark style="color:blue;">**/ei giveall {id} {quantity}**</mark>**&#x20;**<mark style="color:orange;">**\[world] \[giveOfflinePlayer]**</mark>
  * id: Id of the ExecutableItem to give.
  * quantity: Amount of items to give
  * world: Optional argument of world to run the command in. This would make people that are not on this world won't be given the ExecutableItem.
  * giveOfflinePlayer: Boolean value to set if the item will be given to an offline player or not. By default this value is on true.
* Permission: `ei.cmd.giveall`

#### ⭐Give an EI in a specific slot of a player&#x20;

* Command: <mark style="color:blue;">**/ei giveslot {player} {id}**</mark><mark style="color:orange;">**{Variables:{var\_id:value},Usage:value}**</mark>**&#x20;**<mark style="color:blue;">**{quantity} {slot}**</mark>  <mark style="color:orange;">**\[override true or false]**</mark>
  * player: Name of the player who will be the target of this command
  * id: Id of the ExecutableItem to give.
    * Optional values: In order to add this custom setup, there must be no space(s)/white space(s) in the format.&#x20;
      * Variables: You can select a setup of variables for when giving the item.
        * ✅{Variables:{a:"1",b:"2",c:"3"\}} # Not use of whitespaces
        * ❌{Variables:{a : "1",b: "2",c :"3"\}} # Use of whitespaces
      * Usage: You can select a value for the usage when giving the item
        * ✅{Usage:5} # Not use of white space(s)
        * ❌{Usage : 5} # Use of white space(s)
  * quantity: Amount of items to give
  * slot: Player slot where this item will be given to.
  * override: Boolean value to override the slot if there is already an item in that slot. If its the case it will be moved, and if the player has the inventory full it will be dropped to the ground.
* Examples:&#x20;
  * **`/ei giveslot`**`SsomarPluginsPlayer`**`test{Variables:{x:"Hey",world:"Island"},Usage:50} 1 0`** &#x20;
  * **`/ei giveslot`**`SsomarPluginsPlayer`**`rum{Usage:69420,Variables:{tell_me:"why",aint_nothing:"BUT A HEARTBREAK"}} 1 %slot%`**
* Permission: `ei.cmd.giveslot`

**Give every EI in a specific folder to a player**

* Info: Command to give a folder of the plugin to a player.
* Command: <mark style="color:blue;">**/ei givefolder {player} {folder} {quantity}**</mark>
  * player: Name of the player who will be the target of this command
* Permission: `ei.cmd.givefolder`

### Drop commands

#### Drop an EI at a specific location / position <img src="../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Command: <mark style="color:blue;">**/ei drop {id}**</mark>**&#x20;**<mark style="color:orange;">**{quantity} {\[world] \[x] \[y] \[z]}**</mark>
  * id: Id of the ExecutableItem to give.
  * quantity: Amount of items to drop. By default its 1.
  * location: The whole location is optional, in case you want to add it then you would need to fill the next arguments:
    * world: World where the item will be dropped.
    * x: X's coordinates where the item will be dropped.
    * y: Y's coordinates where the item will be dropped.
    * z: Z's coordinates where the item will be dropped.
* Examples:  (On all this examples the commands is being run inside an ExecutableItems in order to parse placeholders such as %player%,%var\_name% and %usage%)
  * /ei drop totemshatter 1 %world% %x% %y% %z%
  * ei drop nuclearWar{Usage:3,Variables:{niconico:"nii"\}} 25 %block\_world% %block\_x% %block\_y% %block\_z%
  * ei drop cybert1\_5{Variables:{eh:5},Usage:5} 1 world 535 74 1329
* Permission: `ei.cmd.drop`

### Modification commands

#### Modify the value of usage of an ExecutableItem

* Command:&#x20;
  * In-game: <mark style="color:blue;">**/ei modification {set or modification} usage {slot} {value}**</mark>
  * In console: <mark style="color:blue;">**/ei console-modification {set or modification} usage {player} {slot} {value}**</mark>
  * Parameters:
    * set or modification
      * set: It sets the new {value} and replace the old one
      * modification: Useful for add modifications, it increases or decrease by the {value} to the original value
    * player: Name of the player who will be the target of this command
    * slot: Player slot where this item will be given to.
      * More information about slots here [https://docs.ssomar.com/tools-for-all-plugins-score/general-questions-or-guides/utilities#slots](https://docs.ssomar.com/tools-for-all-plugins-score/general-questions-or-guides/utilities#slots)&#x20;
    * value: Value used for the modification.
* Permission: `ei.cmd.modification`

#### Modify the value of a variable of an ExecutableItem

* Command:&#x20;
  * In-game: <mark style="color:blue;">**/ei modification {set or modification} variable {slot} {variableName} {value}**</mark>
  * In console: <mark style="color:blue;">**/ei console-modification {set or modification} variable {player} {slot} {variableName} {value}**</mark>
  * Parameters:
    * set or modification
      * set: It sets the new {value} and replace the old one
      * modification: Useful for add modifications, it increases or decrease by the {value} to the original value
    * player: Name of the player who will be the target of this command
    * slot: Player slot where this item will be given to.
      * More information about slots here [https://docs.ssomar.com/tools-for-all-plugins-score/general-questions-or-guides/utilities#slots](https://docs.ssomar.com/tools-for-all-plugins-score/general-questions-or-guides/utilities#slots)&#x20;
    * variableName: The name of the variable you want to apply the typeOfModication with the selected value to.
    * value: Value used for the modification.
* Permission: `ei.cmd.modification`

#### Search an ExecutableItem in the server

* Info: It gives you information of where are the ExecutableItems with id {id} on your server.
* Command: <mark style="color:blue;">**/ei search {id} {searchMode}**</mark>
  * id: Id of the ExecutableItem you are searching for
  * searchMode: Type of search
    * players: Search the ExecutableItem in all **online** player inventories.
    * containers: Search the ExecutableItem in all **loaded** containers.
    * all: Search using the both methods.
* Example:&#x20;
  * `/ei search EternalSword all`
* Permission: `ei.cmd.search`

### Custom triggers

* Info: ExecutableItems has commands for running custom triggers, if want to know what they are and how to use them check the info here [https://docs.ssomar.com/tools-for-all-plugins-score/custom-triggers](https://docs.ssomar.com/tools-for-all-plugins-score/custom-triggers)&#x20;
