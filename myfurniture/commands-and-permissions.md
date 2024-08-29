# ⌨️ Commands & Permissions



## Permissions

**TIP for beginners:**

{% hint style="info" %}
To give the permissions of all furniture, I advice you to download a permission plugin like [**Luckperms**](https://www.spigotmc.org/resources/luckperms.28140/), Once you have a perm plugin you just need to give the permission **`mf.furniture.*`**, for Luckperm the command is  <mark style="color:blue;">`/lp group default permission set mf.furniture.* true`</mark>
{% endhint %}

#### Block permission

* Permission: `mf.furniture.{id}`
* Negative permission: `-mf.furniture.{id}`&#x20;
* Example: `mf.furniture.Test`
* Give all furniture permission: `mf.furniture.*`&#x20;

#### Give all permissions of MF

* Permission: `mf.*`

#### Give all commands permissions of MF

* Permission: `mf.cmds`

#### Bypass cooldown permission

* Permission: `mf.nocd.{id}` `mf.nocd.*`
* Description: Give this custom permission to disable the cooldown for your vip players
* (Be sure to test without being op)

## Commands

#### Download the default furniture

* Command: <mark style="color:blue;">**/mf download-defaukt-pack**</mark>
* Permission: `eb.cmd.download-default-pack`

#### Load the furniture from the textures pack that you placed in \_\_textures\_\_

* Command: <mark style="color:blue;">**/mf pack**</mark>
* Permission: `eb.cmd.pack`

#### Open the editor / menu

* Command: <mark style="color:blue;">**/mf editor**</mark> or <mark style="color:blue;">**/mf show**</mark>
* Permission: `mf.cmd.editor` or `mf.cmd.show`

#### Open the editor to edit a specific MF

* Command: <mark style="color:blue;">**/mf edit {FurnitureID}**</mark>
* Permission: mf`.cmd.edit`

#### Open the a gui with the MF(s) placed

* command: /mf show-placed filter/sort:

<figure><img src="../.gitbook/assets/image.png" alt="" width="338"><figcaption></figcaption></figure>

#### Reload the plugin

* Command: <mark style="color:blue;">**/mf reload**</mark>
* Permission: `mf.cmd.reload`

#### Reload the plugin (only 1 furniture)

* Command: <mark style="color:blue;">**/mf reload {Furnitureid}**</mark>
* Permission: `mf.cmd.reload`

**Reload a folder**

* Command: <mark style="color:blue;">**/mf reload folder:Name\_Of\_My\_Folder**</mark>
* Permission: `mf.cmd.reload`

#### Delete a Furniture

* Command: <mark style="color:blue;">**/mf delete {id}**</mark>
* Permission: `mf.cmd.delete`

#### Clear all cooldowns and delayed commands of MF

* Command: <mark style="color:blue;">**/mf clear**</mark>** **<mark style="color:purple;">**\[playerName]**</mark>
* Permission: `mf.cmd.clear`

{% hint style="info" %}
It supports entities too just use the entity UUID instead of player name
{% endhint %}

#### Enable / Disable actionbar of MF

* Command: <mark style="color:blue;">**/mf actionbar**</mark>** **<mark style="color:orange;">**{on or off}**</mark>
* Permission: `mf.cmd.actionbar`

#### Place an MF at a specific position

* Command: <mark style="color:blue;">**/mf place {id} {x} {y} {z} {world}**</mark>
* Permission: `mf.cmd.place`

#### Remove an MF at a specific position

* Command: <mark style="color:blue;">**/mf remove {x} {y} {z} {world}**</mark> \[replaceWithAir default true]
* Permission: `mf.cmd.remove`

#### Fill a region selection with a MF

* Requirement: This command require to have the plugin [**worldEdit**](https://dev.bukkit.org/projects/worldedit)
* Command: <mark style="color:blue;">**/mf we-place {id}**</mark>
* Permission: `mf.cmd.we-place`

#### Fill a WorldGuard region with a MF

* Requirement: This command require to have the plugin WorldGuard
* Command: <mark style="color:blue;">/mf wg-fill-region {world} {region\_name} stone:70,MyMF:30</mark>
* Permission: `mf.cmd.wg-fill-region`



#### Remove all MF present in a blocks selection

* equirement: This command require to have the plugin [**worldEdit**](https://dev.bukkit.org/projects/worldedit)
* Command: <mark style="color:blue;">**/mf we-remove {replaceTheEBByAir true or false}**</mark>
* Permission: `mf.cmd.we-remove`

#### MF variable modification

* Command: /mf modification {set/modification} variable {world} {x} {y} {z} {variableName} {value}&#x20;

#### MF usage modification

* /mf modification {set/modification} usage {world} {x} {y} {z} {value}

### Give & Take commands

#### Give command

* (Works for offline players)
* Command:&#x20;
  * <mark style="color:blue;">**/mf give {playername} {id}**</mark><mark style="color:purple;">{Variables:{var\_id:val},Usage:val}</mark> <mark style="color:blue;">**{quantity}**</mark> \[giveOfflinePlayer default true]
* Permission: `mf.cmd.give`
* Examples:
  * Examples:&#x20;
    * <mark style="color:blue;">**/mf give %player% Genesis\_Crystal{Variables:{vibraniun:10,proton:30},Usage:10} 3**</mark>&#x20;
    * <mark style="color:blue;">**/mf give %player% SurgeBlade{Variables:{charge:%var\_charge%+1},Usage:%usage%-1} 1**</mark>
    * <mark style="color:blue;">**/mf give %player% BoneBlade 1**</mark>

#### Take command

* Command:&#x20;
  * <mark style="color:blue;">**/mf take {playername} {id} {quantity}**</mark>
* Permission: `mf.cmd.take`

#### GiveAll command

* Command:&#x20;
  * <mark style="color:blue;">**/mf giveall {id} {quantity}**</mark>** **<mark style="color:purple;">**\[world]**</mark>
* Permission: `mf.cmd.giveall`

#### Give an EB in a specific slot of a player&#x20;

* Command:&#x20;
  * <mark style="color:blue;">**/mf giveslot {playername} {id}**</mark><mark style="color:purple;">{Variables:{var\_id:val},Usage:val}</mark> <mark style="color:blue;">**{quantity} {slot}**</mark>**  **<mark style="color:purple;">**\[override true or false]**</mark>
  * Examples:&#x20;
    * <mark style="color:blue;">**/mf giveslot Ssomar test{Variables:{x:"Hey",world:"Island"},Usage:50} 1 0**</mark> &#x20;
    * <mark style="color:blue;">**/mf giveslot Special70 rum{Usage:69420,Variables:{tell\_me:"why",aint\_nothing:"BUT A HEARTBREAK"\}} 1 %slot%**</mark>
    * <mark style="color:blue;">**/mf giveslot Ssomar xyz{Variables:{test:"Hello boss!"},Usage:5} 1 5**</mark>
  * _Default usage : The usage that is in the config of your Furniture_
  * _Override allow the Furniture to take that slot, and if there was an item there, it is going to move to another slot or get dropped to the ground._
* Permission: `mf.cmd.giveslot`

**Give every EB in a specific folder to a player**

* Command:
  * <mark style="color:blue;">**/mf givefolder {playername} {folder} {quantity}**</mark>

### Drop commands

#### Drop a furniture at a specific location / position

* Command:&#x20;
  * <mark style="color:blue;">**/mf drop {id}**</mark>** **<mark style="color:purple;">**\[quantity] \[world] \[x] \[y] \[z]**</mark>
  * _Default quantity : 1_
  * _Default location : The location of the player who has executed this command_
* Permission: `mf.cmd.drop`
