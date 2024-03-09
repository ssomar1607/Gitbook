# 📚 Placeholders

{% hint style="success" %}
All numerical placeholders can be incremented or decremented.

* Example : `%amount%+6` (Increase)
  * %amount% = 15
  * %amount% + 6 =
  * (15) + 6 = 21
* Example : `%amount%-8` (Decrease)
  * %amount% = 14
  * %amount% - 8 =
  * (14) - 8 = 6&#x20;
{% endhint %}

{% hint style="success" %}
But you can also you the [math placeholders](https://github.com/PlaceholderAPI/PlaceholderAPI/wiki/Placeholders#math) of [PlaceholderAP](https://www.spigotmc.org/resources/placeholderapi.6245/)I

* EI placeholders are parsed first before PlaceholderAPI placeholders are parsed.
* Examples of using an EI placeholder inside of a math placeholder
  * `%math_0_(%usage%)*10%`
* EI placeholders are pre-parsed and any placeholders that are not ei are parsed upon command activation so you can use ei placeholders for xyz coordinates and not worry about change in values
{% endhint %}

## Miscellaneous Placeholders

{% hint style="info" %}
%activator\_id% : Returns the id of the activator. \
Can be found at:\
![](<../.gitbook/assets/image (438).png>)\
%activator\_name% : Returns the name of the activator that's listed at the DisplayName field of the activator editor
{% endhint %}

{% hint style="info" %}
%rand:MIN\_VALUE|MAX\_VALUE% : Randomizer value

* Example : `%rand:10|100%` - Generates a number between 10-100
* Supports negative value | MIN\_VALUE must be < than MAX\_VALUE
{% endhint %}

{% hint style="warning" %}
Even if there are multiple %rand:MIN\_VALUE|MAX\_VALUE% placeholders in a command line, it would still give the same number so if you want a rng placeholder that would give different answers for every of its placeholder that exists in the command line, use PlaceholderAPI's RNG Expansion
{% endhint %}

{% hint style="info" %}
%timestamp% -> gets the current time
{% endhint %}

{% hint style="info" %}
%score\_cooldown\_{plugin}:{object\_id}:{activator\_id}% -> gets the cooldown, it works for all plugins.\
\
Example: %score\_cooldown\_EI:Free\_Lotery:activator1%
{% endhint %}

## Item placeholders

<table><thead><tr><th width="150">Placeholder</th><th>Description</th></tr></thead><tbody><tr><td><strong>%name%</strong></td><td>The name of the ExecutableItems</td></tr><tr><td><strong>%id%</strong></td><td>Returns the id of the ExecutableItem used to run the activator</td></tr><tr><td><strong>%usage%</strong></td><td>The max usage that the item has (CAN BE USED IN LORE)</td></tr><tr><td><strong>%usage_limit%</strong></td><td>The max usage that the item can have (CAN BE USED IN LORE)</td></tr><tr><td><strong>%usage_roman%</strong></td><td>Display the usage in roman numerals (11 -> XI)</td></tr><tr><td><strong>%max_use_per_day_item%</strong></td><td>The max use per day that the item has.</td></tr><tr><td><strong>%max_use_per_day_activator%</strong></td><td>The max use per day for the activator.</td></tr><tr><td><strong>%amount%</strong></td><td>The amount of ExecutableItems that the player has in his current selected slot. Also tells the amount of EI you dropped when triggering the <code>PLAYER_DROP_THE_EI</code> activator</td></tr><tr><td><p><strong>%usage_bar(amount:30,color1:&#x26;d,color2:&#x26;5,symbol:|)%</strong><br></p><p><img src="https://i.imgur.com/mT6qKeh.png" alt=""><br><em>(by default: amount = 30 bars, color1 is yellow, color2 is green, symbol is |)</em></p></td><td><strong>amount</strong> = The amount of bars the usage bar will have<br><strong>color1</strong> = The color that represents how much usage the item has (The light purple)<br><strong>color2</strong> = The color that represents the dark purple<br><strong>symbol</strong> = The symbol that will be used on the custom usage bar<br><br><strong>Requirements:</strong><br>- The item must have the usage and the usage limit different than -1</td></tr></tbody></table>

## Player placeholders

<table><thead><tr><th width="150">Placeholder</th><th>Description</th></tr></thead><tbody><tr><td><strong>%player%</strong></td><td>Name of the player. Can be used to display the owner of the item in the item's lore</td></tr><tr><td><strong>%player_uuid%</strong></td><td>UUID of the player (%player_uuid_array% for its 4-array integer form. Ex: <code>[I;-1288600659,-373273272,-1897203511,898446696])</code></td></tr><tr><td><strong>%player_world%</strong></td><td>Name of the world (<strong>%player_world_lower%</strong> for lowercase)</td></tr><tr><td><strong>%player_x%</strong></td><td>X-Coordinates of the player (Decimal) >> For an integer use <strong>%player_x_int%</strong></td></tr><tr><td><strong>%player_y%</strong></td><td>Y-Coordinates of the player (Decimal) >> For an integer use <strong>%player_y_int%</strong></td></tr><tr><td><strong>%player_z%</strong></td><td>Z-Coordinates of the player (Decimal) >> For an integer use <strong>%player_z_int%</strong></td></tr><tr><td><strong>%player_slot%</strong></td><td>The slot used to active the activator</td></tr><tr><td><strong>%player_slot_live%</strong></td><td>The current held slot</td></tr><tr><td><strong>%player_pitch%</strong></td><td>The pitch of the player >> For an integer <strong>%player</strong><em><strong>_</strong></em><strong>pitch</strong><em><strong>_</strong></em><strong>int%</strong></td></tr><tr><td><strong>%player_pitch_positive%</strong></td><td>The pitch of the player but always positive >> For an integer <strong>%player</strong><em><strong>_</strong></em><strong>pitch</strong><em><strong>_</strong></em><strong>positive</strong><em><strong>_</strong></em><strong>int%</strong></td></tr><tr><td><strong>%player_yaw%</strong></td><td>The yaw of the player >> For an integer <strong>%player</strong><em><strong>_</strong></em><strong>yaw</strong><em><strong>_</strong></em><strong>int%</strong></td></tr><tr><td><strong>%player_yaw</strong><em><strong>_</strong></em><strong>positive</strong><em><strong>%</strong></em></td><td>The yaw of the player but always positive >> For an integer <strong>%player</strong><em><strong>_</strong></em><strong>yaw_positive_int%</strong></td></tr><tr><td><strong>%player_direction%</strong></td><td>Direction of where the player is facing (ex: N, SW, NE)</td></tr><tr><td><strong>%last_damage</strong><em><strong>_</strong></em><strong>taken%</strong></td><td>The last damage taken by the player (Decimal) >> For an integer use <strong>%last_damage_taken_int%</strong></td></tr><tr><td><strong>%last_damage</strong><em><strong>_</strong></em><strong>dealt%</strong></td><td>The last damage dealt by the player (Decimal) >> For an integer use <strong>%last_damage_dealt_int%</strong></td></tr><tr><td><strong>%player_team%</strong></td><td>The team of the player if the player has one</td></tr><tr><td><strong>%player_attack</strong><em><strong>_</strong></em><strong>charge%</strong></td><td>Gets the current cooldown for a player's attack. This is used to calculate damage, with 1.0 representing a fully charged attack and 0.0 representing a non-charged attack (1.16+ only)<br><br>This placeholder gets reset after a DAMAGE command, so if you want to debug it, display the value before a DAMAGE command.</td></tr></tbody></table>

## Target player placeholders

(The activator must have a target player)

Its the same placeholders that the **PLAYER PLACEHOLDERS** above**,** just replace "player" by "target".

Example: `%target_x%`



## Entity placeholders

(The activator must have an entity)&#x20;

* in EI / EB it's always these placeholders for entity.
* in EE it's quite different, since we can have an entity as a main actor of the event but also as target. So use these placeholders below when the entity is the main actor of the event. And Look the part **Target entity placeholders** when the entity is the target.

<table><thead><tr><th width="150">Placeholder</th><th>Description</th></tr></thead><tbody><tr><td><strong>%entity%</strong></td><td>Type of the entity</td></tr><tr><td><strong>%entity_lower_case%</strong></td><td>Type of the entity in lower case</td></tr><tr><td><strong>%entity_name%</strong></td><td>Name of the entity (lower case: <strong>%entity_name_lower_case%</strong>)</td></tr><tr><td><strong>%entity_uuid%</strong></td><td>UUID of the entity (%entity_uuid_array% for its 4-array integer form. Ex: <code>[I;-1288600659,-373273272,-1897203511,898446696])</code></td></tr><tr><td><strong>%entity_x%</strong></td><td>X-Coordinates of the entity (Decimal) >> For an integer use <strong>%entity_x_int%</strong></td></tr><tr><td><strong>%entity_y%</strong></td><td>Y-Coordinates of the entity (Decimal) >> For an integer use <strong>%entityt_y_int%</strong></td></tr><tr><td><strong>%entity_z%</strong></td><td>Z-Coordinates of the entityr (Decimal) >> For an integer use <strong>%entity_z_int%</strong></td></tr><tr><td><strong>%entity_direction%</strong></td><td>Direction of where the entity is facing (ex: N, SW, NE)</td></tr><tr><td><strong>%entity_pitch%</strong></td><td>The pitch of the entity>> For an integer <strong>%entity</strong><em><strong>_</strong></em><strong>pitch</strong><em><strong>_</strong></em><strong>int%</strong></td></tr><tr><td><strong>%entity_pitch_positive%</strong></td><td>The pitch of the entity but always positive >> For an integer <strong>%entity</strong><em><strong>_</strong></em><strong>pitch</strong><em><strong>_</strong></em><strong>positive</strong><em><strong>_</strong></em><strong>int%</strong></td></tr><tr><td><strong>%entity_yaw%</strong></td><td>The yaw of the entity >> For an integer <strong>%entity</strong><em><strong>_</strong></em><strong>yaw</strong><em><strong>_</strong></em><strong>int%</strong></td></tr><tr><td><strong>%entity_yaw_positive%</strong></td><td>The yaw of the entity but always positive >> For an integer <strong>%entity</strong><em><strong>_</strong></em><strong>yaw_positive%</strong></td></tr><tr><td><strong>%entity_health%</strong></td><td>The health of the entity (Decimal)</td></tr><tr><td><strong>%entity_max</strong><em><strong>_</strong></em><strong>health%</strong></td><td>The max health of the entity (Decimal)</td></tr><tr><td><strong>%entity_world%</strong></td><td>Name of the world (<strong>%entity_world_lower%</strong> for lowercase)</td></tr><tr><td><strong>%entity_team%</strong></td><td>The team of the entity if the entity has one</td></tr><tr><td><strong>%entity_item%</strong></td><td>Returns the material of this item. (items not entities)</td></tr></tbody></table>

## Target entity placeholders

(The activator must have a target entity)

Its the same placeholders that the **ENTITY PLACEHOLDERS** above**,** just replace "entity" by "target".

Example: `%target_x%`

## Block placeholders

(The activator must have a block)

* in EI / EB it's always these placeholders for entity.
* in EE it's quite different, since we can have a block as a main actor of the event but also as target. So use these placeholders below when the block is the main actor of the event. And Look the part **Target block placeholders** when the block is the target.

<table><thead><tr><th width="150">Placeholder</th><th>Description</th></tr></thead><tbody><tr><td><strong>%block%</strong></td><td>Type of the block when the activator has been activated (In caps)</td></tr><tr><td><strong>%block_lower%</strong></td><td>Type of the block when the activator has been activated (In lower case)</td></tr><tr><td><strong>%block_live%</strong></td><td>Current type of the block (In caps)</td></tr><tr><td><strong>%block_item_material%</strong></td><td>Return the item material of the block for example the block CARROTS return CARROT, for lower cases use <strong>%block_item_material_lower%</strong></td></tr><tr><td><strong>%block_live_lower%</strong></td><td>Current type of the block (In lower case)</td></tr><tr><td><strong>%block_x%</strong></td><td>X-Coordinates of the block (USE <strong>%block_x_int%</strong> to get the block coordinates without decimals)</td></tr><tr><td><strong>%block_y%</strong></td><td>Y-Coordinates of the block (USE <strong>%block_y_int%</strong> to get the block coordinates without decimals)</td></tr><tr><td><strong>%block_z%</strong></td><td>Z-Coordinates of the block (USE <strong>%block_z_int%</strong> to get the block coordinates without decimals)</td></tr><tr><td><strong>%blockface%</strong></td><td>Returns the face of the selected block.</td></tr><tr><td><strong>%block_data%</strong></td><td>Returns the data of the block</td></tr><tr><td><strong>%block_world%</strong></td><td>The name of the world where the block is located (<strong>%block_world_lower%</strong> for lower)</td></tr><tr><td>%block_biome%</td><td><p>The name of the biome where the block is located</p><p>List of all biomes <a href="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/Biome.html">here</a></p><p>(<strong>%block_biome_lower%</strong> for lower)</p></td></tr><tr><td><strong>%block_dimension%</strong></td><td>The type of world (nether, custom, normal, end)</td></tr><tr><td><strong>%block_spawnertype%</strong></td><td>Returns the type of mob in spawner or "null"</td></tr><tr><td><strong>%block_is_ageable%</strong></td><td>Returns if the block is ageable or not</td></tr></tbody></table>

## Target block placeholders

(The activator must have a target block)

Its the same placeholders that the **BLOCK PLACEHOLDERS** above**,** just replace "block" by "target\_block".

Example: `%target_block_x%`

## Projectile placeholders

(The activator must have a projectile)

<table><thead><tr><th width="150">Placeholder</th><th>Description</th></tr></thead><tbody><tr><td><strong>%projectile_x%</strong></td><td>X-Coordinates of the projectile (Decimal) (<strong>%projectile_x_int%</strong> for no decimals)</td></tr><tr><td><strong>%projectile_y%</strong></td><td>Y-Coordinates of the projectile (Decimal) (<strong>%projectile_y_int%</strong> for no decimals)</td></tr><tr><td><strong>%projectile_z%</strong></td><td>Z-Coordinates of the projectile (Decimal) (<strong>%projectile_z_int%</strong> for no decimals)</td></tr><tr><td><strong>%projectile%</strong></td><td>The type of projectile but at all caps</td></tr><tr><td><strong>%projectile_lower_case%</strong></td><td>The type of projectile but at all lowercase</td></tr><tr><td><strong>%projectile_name%</strong></td><td>Name of the projectile (More specifically, it will display what's written in your custom projectile's <code>customName</code> option)</td></tr><tr><td><strong>%projectile_name_lower_case%</strong></td><td>Name of the projectile but at all lowercase (More specifically, it will display what's written in your custom projectile's <code>customName</code> option)</td></tr><tr><td><strong>%projectile_uuid%</strong></td><td>UUID of the projectile (%projectile_uuid_array% for its 4-array integer form. Ex: <code>[I;-1288600659,-373273272,-1897203511,898446696])</code></td></tr><tr><td><strong>%projectile_world%</strong></td><td>World name of the projectile (<strong>%projectile_world_lower%</strong> for lower)</td></tr><tr><td><strong>%bow_force%</strong></td><td>If the projectile has been launched with a bow, you can use this placeholder to obtain the force that the player used to shot his projectile. (Between 0 and 1)</td></tr></tbody></table>

## Owner Placeholders

(Will work only if an owner is set for the block / item)

Its the same placeholders that the **PLAYER PLACEHOLDERS** above**,** just replace "player" by "owner".

Example: `%owner_health%`

## AROUND & NEAREST placeholders

(Placeholders to use in the custom commands AROUND)

Its the same placeholders that the **PLAYER PLACEHOLDERS** above**,** just replace "player" by "around\_target".

Example: `%around_target_direction%`

## MOB\_AROUND & MOB\_NEAREST placeholders

(Placeholders to use in the custom commands MOB\_AROUND)

Its the same placeholders that the **ENTITY PLACEHOLDERS** above**,** just replace "entity" by "around\_target".

Example: `%around_target_health%`

Example: `%around_target_uuid%`

Example: `%around_target_x%`



## Variable Placeholders

(Placeholders that you can use if you have a variable)

**Example if your variable is named: X**

| Placeholder         | Description                                |
| ------------------- | ------------------------------------------ |
| **%var\_X%**        | Value of the variable X                    |
| **%var\_X\_int%**   | Value of the variable X cast in an Integer |
| **%var\_X\_roman%** | Value of the variable X in roman numbers   |

## List Variable Placeholders

| Placeholder                  | Description                                                      | Usage                                                                                                                                                           |
| ---------------------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| %var\_MYVAR%                 | Returns the list with the brackets and commas                    | %var\_testVar%                                                                                                                                                  |
| %var\_MYVAR\_size%           | Returns how many elements/values that list variable contains     | %var\_testVar\_size%                                                                                                                                            |
| %var\_MYVAR\_contains\_WHAT% | Returns true/false if the mentioned value is present in the list | <p>%var_testVar_contains_Maximo%<br>%var_testVar_contains_%player%%<br>%var_testVar_contains_%checkitem_mat:stone%%<br>%var_testVar_contains_%var_bomberZ%%</p> |

## Circumstantial

### PLAYER\_WRITE\_COMMAND | PLAYER\_SEND\_MESSAGE

* For this activator you will be able to use the arguments provided by the user in your EI Command or as placeholders conditions, for example:

**`Command: modify`**

* Input by player:&#x20;
  * **`/modify 5`**
* We can take that "5" using the **%arg1%** argument



* If the player would write `/modify diamond_sword 10 true`
* The inputs would be the next
  * <mark style="color:orange;">%arg0%</mark> = <mark style="color:blue;">modify</mark>
  * <mark style="color:orange;">%arg1%</mark> = <mark style="color:blue;">diamond\_sword</mark>
  * <mark style="color:orange;">%arg2%</mark> = <mark style="color:blue;">10</mark>
  * <mark style="color:orange;">%arg3%</mark> = <mark style="color:blue;">true</mark>

### DAMAGE\_BOOST

* For this command you can get the boost given by the custom player command `DAMAGE_BOOST {modification in percentage example 100} {timeinticks}`
  * %score\_cmd-damage-boost%

### DAMAGE\_RESISTANCE

* For this command you can get the boost given by the custom player command `DAMAGE_RESISTANCE {modification in percentage example 100} {timeinticks}`
  * %score\_cmd-damage-resistance%

### **COOLDOWN**

* You can get the cooldown in seconds like that with `%score_cooldown_{plugin}:{object_id}:{activator_id}%`&#x20;

Example: `%score_cooldown_EI:Free_Lotery:activator1%`

It returns the cooldown of the activator1 of the EI Free\_Lotery. It works with EE, EB, EI, EL cooldowns.

### SETGLOW

* You can get the glow color with %score\_cmd-glow% using it on the plugin TAB

### RECEIVE\_EFFECT

placeholders for activators RECEIVE\_EFFECT (in EI and EE)

```
%effect_received%
%effect_received_lower%
%effect_received_level%
%effect_received_duration%
```
