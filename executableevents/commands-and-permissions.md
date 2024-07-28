# ⌨️ Commands & Permissions

## Permissions

#### Give all permissions of EE

* Permission: `ee.*`

#### Give all commands permissions of EE

* Permission: `ee.cmds`

## Commands

#### Create a new ExecutableEvent

* Command: <mark style="color:blue;">**/ee create {id}**</mark>
* Permission: `ee.cmd.create`

#### Open the editor / menu

* Command: <mark style="color:blue;">**/ee editor**</mark> or <mark style="color:blue;">**/ee show**</mark>
* Permission: `ee.cmd.editor` or `ee.cmd.show`

#### Reload the plugin

* Command: <mark style="color:blue;">**/ee reload**</mark>
* Permission: `ee.cmd.reload`

**Reload a folder**

* Command: <mark style="color:blue;">**/ee reload folder:Name\_Of\_My\_Folder**</mark>
* Permission: `ee.cmd.reload`

#### Delete an ExecutableEvent

* Command: <mark style="color:blue;">**/ee delete {id}**</mark>
* Permission: `ee.cmd.delete`

#### Enables an EE event or a folder of events

* Command: <mark style="color:blue;">**/ee enable {event}**</mark>
* Permission: `ee.cmd.enable`

#### Disables an EE event or a folder of events

* Command: <mark style="color:blue;">**/ee disable {event}**</mark>
* Permission: `ee.cmd.disable`

#### Clear all cooldowns and delayed commands of EE

* Command: <mark style="color:blue;">**/ee clear**</mark>** **<mark style="color:purple;">**\[playerName]**</mark>
* Permission: `ee.cmd.clear`

{% hint style="info" %}
It supports entities too just use the entity UUID instead of player name
{% endhint %}

#### Enable / Disable actionbar of EE

* Command: <mark style="color:blue;">**/ee actionbar**</mark>** **<mark style="color:orange;">**{on or off}**</mark>
* Permission: `ee.cmd.actionbar`
