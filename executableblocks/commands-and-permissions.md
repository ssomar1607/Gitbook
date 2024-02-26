# ⌨️ Commands & Permissions



## Permissions

**TIP for beginners:**

{% hint style="info" %}
To give the permissions of all items, I advice you to download a permission plugin like [**Luckperms**](https://www.spigotmc.org/resources/luckperms.28140/), Once you have a perm plugin you just need to give the permission **`eb.block.*`**, for Luckperm the command is  <mark style="color:blue;">`/lp group default permission set eb.block.* true`</mark>
{% endhint %}

#### Block permission

* Permission: `eb.block.{id}`
* Negative permission: `-eb.block.{id}` <img src="../.gitbook/assets/ExecutableBlocks (64x64)px.png" alt="" data-size="line">
* Example: `eb.block.Test`
* Give all items permission: `eb.block.*`&#x20;

#### Give all permissions of EB

* Permission: `eb.*`

#### Give all commands permissions of EB

* Permission: `eb.cmds`

#### Bypass cooldown permission

* Permission: `eb.nocd.{id}` `eb.nocd.*`
* Description: Give this custom permission to disable the cooldown for your vip players
* (Be sure to test without being op)

**Limit of EB**

* Permission: `eb.limit.{amount}`
* Description: Sets the max value a player can place EB(s).

#### Limit a specific EB

* Permission: `eb.block.ID.limit.{amount}`
* Description: Limit the amount of specific EB ID a player can place

## Commands

#### Create a new ExecutableBlock

* Command: <mark style="color:blue;">**/eb create {id}**</mark>
* Tip:&#x20;
  * If you want **copy the item/block of another plugin**, or a custom vanilla block (Banner, Custom block, ...), You need to install my other plugin, ExecutableItems, type **/ei create {id}** and then import your ExecutableItem in ExecutableBlocks.
* Permission: `eb.cmd.create`

####

#### Open the a gui with the EB(s) placed

* command: /eb show-placed filter/sort:

<figure><img src="../.gitbook/assets/image.png" alt="" width="338"><figcaption></figcaption></figure>

#### Open the editor / menu

* Command: <mark style="color:blue;">**/eb editor**</mark> or <mark style="color:blue;">**/eb show**</mark>
* Permission: `eb.cmd.editor` or `eb.cmd.show`

#### Open the editor to edit a specific EB

* Command: <mark style="color:blue;">**/eb edit {BlockID}**</mark>
* Permission: `eb.cmd.edit`

#### Reload the plugin

* Command: <mark style="color:blue;">**/eb reload**</mark>
* Permission: `eb.cmd.reload`

#### Reload the plugin (only 1 block)

* Command: <mark style="color:blue;">**/eb reload {block\_id}**</mark>
* Permission: `eb.cmd.reload`

**Reload a folder**

* Command: <mark style="color:blue;">**/eb reload folder:Name\_Of\_My\_Folder**</mark>
* Permission: `eb.cmd.reload`

#### Delete an ExecutableBlock

* Command: <mark style="color:blue;">**/eb delete {id}**</mark>
* Permission: `eb.cmd.create`

#### Reload the default blocks of ExecutableBlock

* Command: <mark style="color:blue;">**/eb default\_blocks**</mark>
* Permission: `eb.cmd.default_blocks`

#### Clear all cooldowns and delayed commands of EB

* Command: <mark style="color:blue;">**/eb clear**</mark>** **<mark style="color:purple;">**\[playerName]**</mark>
* Permission: `eb.cmd.clear`

#### Enable / Disable actionbar of EB

* Command: <mark style="color:blue;">**/eb actionbar**</mark>** **<mark style="color:orange;">**{on or off}**</mark>
* Permission: `eb.cmd.actionbar`

#### Place an EB at a specific position

* Command: <mark style="color:blue;">**/eb place {id} {x} {y} {y} {world}**</mark>
* Permission: `eb.cmd.place`

#### Remove an EB at a specific position

* Command: <mark style="color:blue;">**/eb remove {id} {x} {y} {y} {world}**</mark> \[replaceWithAir default true]
* Permission: `eb.cmd.remove`

#### Fill a region selection with an EB

* Requirement: This command require to have the plugin [**worldEdit**](https://dev.bukkit.org/projects/worldedit)
* Command: <mark style="color:blue;">**/eb we-place {id}**</mark>
* Permission: `eb.cmd.we-place`

#### Fill a WorldGuard region with an EB

* Requirement: This command require to have the plugin WorldGuard
* Command: <mark style="color:blue;">/eb wg-fill-region {world} {region\_name} stone:70,MyEb:30</mark>
* Permission: `eb.cmd.wg-fill-region`



#### Remove all EB present in a blocks selection

* equirement: This command require to have the plugin [**worldEdit**](https://dev.bukkit.org/projects/worldedit)
* Command: <mark style="color:blue;">**/eb we-remove {replaceTheEBByAir true or false}**</mark>
* Permission: `eb.cmd.we-remove`

#### EB variable modification

* Command: /eb modification {set/modification} variable {world} {x} {y} {z} {variableName} {value}&#x20;

#### EB usage modification

* /eb modification {set/modification} usage {world} {x} {y} {z} {value}

### Give & Take commands

#### Give command

* Command:&#x20;
  * <mark style="color:blue;">**/eb give {playername} {id} {quantity}**</mark>
* Permission: `eb.cmd.give`

#### Take command

* Command:&#x20;
  * <mark style="color:blue;">**/eb take {playername} {id} {quantity}**</mark>
* Permission: `eb.cmd.take`

#### GiveAll command

* Command:&#x20;
  * <mark style="color:blue;">**/eb giveall {id} {quantity}**</mark>** **<mark style="color:purple;">**\[world]**</mark>
* Permission: `eb.cmd.giveall`

#### Give an EB in a specific slot of a player&#x20;

* Command:&#x20;
  * <mark style="color:blue;">**/eb giveslot {playername} {id} {quantity} {slot}**</mark>**  **<mark style="color:purple;">**\[override true or false] USAGE(\<usage>) VAR(\<var>)**</mark>
  * Examples:&#x20;
    * <mark style="color:blue;">**/eb giveslot Ssomar test 1 0 USAGE(50) VAR(x:Hey,world:Island)**</mark>
    * <mark style="color:blue;">**/eb giveslot Special70 rum 1 %slot% USAGE(69420) VAR(tell\_me:WHY,aint\_nothing:BUT\_A\_HEARTBREAK)**</mark>
  * _Default usage : The usage that is in the config of your EB_
  * _Override allow the EB to take that slot, and if there was an item there, it is going to move to another slot or get dropped to the ground._
* Permission: `eb.cmd.giveslot`

**Give every EB in a specific folder to a player**

* Command:
  * <mark style="color:blue;">**/eb givefolder {playername} {folder} {quantity}**</mark>

### Drop commands

#### Drop an EB at aspecific location / position <img src="../.gitbook/assets/ExecutableBlocks (64x64)px.png" alt="" data-size="line">

* Command:&#x20;
  * <mark style="color:blue;">**/eb drop {id}**</mark>** **<mark style="color:purple;">**\[quantity] \[world] \[x] \[y] \[z]**</mark>
  * _Default quantity : 1_
  * _Default location : The location of the player who has executed this command_
* Permission: `eb.cmd.drop`
