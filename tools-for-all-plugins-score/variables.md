# 🧮    Variables

{% hint style="info" %}
Since SCore variable placeholders are supported by PlaceholderAPI, you can use the SCore variables like this:

`%math_{score_variables_userLevel}*10%`
{% endhint %}

## Score (Global variables)

Score has a integration of variables where you can store strings/numbers in variables in a global way or per player, they aren't integrated in EI or EB, but they are integrated as commands (so they can be used in combination with EI / EB)

They are stored in `plugins/Score/variables`

### Types of Score variables

| Type       | Explanation                                                                                                                                                             |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **GLOBAL** | Variable stored in a global way, that means, if this variable is parsed with one player it will get the same value as it would be parsed with another player.           |
| **PLAYER** | Variable stored for each player, that means, the value is different per player, so parsing this variable with one player can have a different value with another player |

### Variables modification

| Type             | Explanation                                                                                                          |
| ---------------- | -------------------------------------------------------------------------------------------------------------------- |
| **SET**          | You set a static value to the variable                                                                               |
| **MODIFICATION** | You modify the variable (useful for INT variables, to add value to a integer value, or to substract a certain value) |







### Variables tools

* /score variables list
* /score variables info {var\_name} \[player]
* /score variables-create {var\_name}
* /score variables-delete {var\_name}
* /score variables
* /score variables clear {typeofvariable} {nameofvariable} \[player]



**/score variables \<typeofmodification> \<typeofvariable> \<nameofvariable> \<value> \[player]**

* Examples:
  *   **GLOBAL Variables**:

      * /score variables SET GLOBAL thisisthenameofthevariable 100
        * /score variables MODIFICATION GLOBAL thisisthenameofthevariable 100


  * **PLAYER Variables**
    * /score variables SET PLAYER myvariable -50 Ssomar
      * /score variables MODIFICATION PLAYER myvariable -50 Ssomar

### Variables placeholders

This requires PlaceholderAPI.

* %score\_variables\_\<var\_name>%
* %score\_variables\_\<var\_name>\_int%

{% hint style="danger" %}
Name of the variables can't have underscores -> "
{% endhint %}

{% hint style="info" %}
If you want to set a variable a value with spaces, such as value: "This is my variable", we suggest you to:

1\) Don't use spaces, just write "\_" instead of " " so the variable name would be "This\_is\_my\_variable"

2\) If you really need the spaces you can use the Formatter extension of PlaceholderAPI to remove certain letters, for example:&#x20;

%formatter\_text\_replace\_\*\_ \_{score\_variables\_ThisIsTheNameOfMyVariable}%

Normally %score\_variables\_ThisIsTheNameOfMyVariable% would return HELLO\_THERE, but with the Formatter placeholder the result is HELLO THERE .
{% endhint %}







### Variable-List

This is a type of variable that is quite complex and have its own features, that's why it is separated, let's explain it

* Create a variable
  * /score variables-create ThisIsTheNameOfMyVariable
* Add values into the list
  * /score variables list-add PLAYER ThisIsTheNameOfMyVariable TEXT1 Ssomar
  * /score variables list-add PLAYER ThisIsTheNameOfMyVariable TEXT2 Ssomar
*   To specify a place to add the value into the list use index feature

    * /score variables list-add PLAYER ThisIsTheNameOfMyVariable TEXT3 Ssomar index:0


*   To see the modification

    * /score variables info ThisIsTheNameOfMyVariable


* Removing values:
  * Remove the last value
    * /score variables list-remove PLAYER ThisIsTheNameOfMyVariable Ssomar
  * Remove a specific index
    * /score variables list-remove PLAYER ThisIsTheNameOfMyVariable Ssomar index:0
  * Remove a specific value
    * /score variables list-remove PLAYER ThisIsTheNameOfMyVariable Ssomar value:Test

{% hint style="info" %}
Variable-list also work with GLOBAL variables, but you would need to change instead of PLAYER -> GLOBAL and remove the player in the command
{% endhint %}

### Variable-List Placeholders

| Placeholder                                             |                                                             |
| ------------------------------------------------------- | ----------------------------------------------------------- |
| %score\_variables\_\<variable-name>\_\<index>%          | Return the value at the specific index of the list          |
| %score\_variables\_\<variable-name>%                    | returns all the elements of the list                        |
| %score\_variables-contains\_\<variable-name>\_\<value>% | Boolean to see if the list contains a value (true or false) |
| %score\_variables-size\_\<variable-name>%               | Returns the size of the list                                |

What you can do with this feature -> Item created by Ssomar

<details>

<summary>Terminator<br>RIGHT CLICK to select entities<br>SHIFT+RIGHT CLICK to explode them</summary>

```
name: '&6&l>> &7Terminator stick &6&l<<'
lore:
- '&7Select entites by right'
- '&7clicking on them !'
- '&eLimit: &63 entities'
- '&e'
- '&7Then shift + right click'
- '&7to make them explode !'
material: STICK
glow: false
disableStack: false
keepItemOnDeath: false
canBeUsedOnlyByTheOwner: false
storeItemInfo: false
unbreakable: false
usage: 1
usageLimit: -1
cancelEventIfNoPerm: false
cancelEventIfNotOwner: false
disabledWorlds: []
recognitions: []
config_5: true
config_update: true
dropOptions:
  glowDrop: false
  glowDropColor: WHITE
  displayNameDrop: false
hiders:
  hideEnchantments: false
  hideUnbreakable: false
  hideAttributes: false
  hidePotionEffects: false
  hideUsage: true
  hideDye: false
enchantments: {}
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
restrictions: {}
variables: {}
activators:
  activator0:
    name: '&eActivator'
    option: PLAYER_RIGHT_CLICK
    typeTarget: NO_TYPE_TARGET
    usageModification: 0
    cancelEvent: false
    noActivatorRunIfTheEventIsCancelled: false
    silenceOutput: false
    autoUpdateItem: false
    updateName: true
    updateLore: true
    updateDurability: false
    updateAttributes: false
    updateEnchants: false
    updateCustomModelData: false
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    globalCooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    otherEICooldowns: {}
    requiredItems: {}
    requiredExecutableItems: {}
    detailedSlots:
    - -1
    commands:
    - SWING_MAIN_HAND
    - LAUNCH DEFAULT_INVISIBLE_ARROW_NO_GRAVITY_SPEED
    playerConditions: {}
    worldConditions: {}
    itemConditions: {}
    customConditions: {}
    placeholdersConditions: {}
    variablesModification: {}
  activator5:
    name: '&eActivator'
    option: PROJECTILE_HIT_ENTITY
    usageModification: 0
    cancelEvent: false
    noActivatorRunIfTheEventIsCancelled: false
    silenceOutput: false
    autoUpdateItem: false
    updateName: true
    updateLore: true
    updateDurability: false
    updateAttributes: false
    updateEnchants: false
    updateCustomModelData: false
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    globalCooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    otherEICooldowns: {}
    requiredItems: {}
    requiredExecutableItems: {}
    detailedSlots:
    - -1
    commands:
    - 'SENDMESSAGE &7You &cunselected &7the entity: &e%entity_name%'
    - score variables list-remove player myList %player% value:%entity_uuid%
    playerConditions: {}
    worldConditions: {}
    itemConditions: {}
    customConditions: {}
    placeholdersConditions:
      plchCdt0:
        type: PLAYER_STRING
        comparator: EQUALS
        part1: '%score_variables-contains_myList_%entity_uuid%%'
        part2: 'true'
        cancelEventIfNotValid: false
        messageIfNotValid: ''
        messageIfNotValidForTarget: ''
    detailedEntities: []
    entityCommands: []
    entityConditions: {}
    variablesModification: {}
  activator2:
    name: '&eActivator'
    option: PLAYER_LEFT_CLICK
    typeTarget: NO_TYPE_TARGET
    usageModification: 0
    cancelEvent: false
    noActivatorRunIfTheEventIsCancelled: false
    silenceOutput: false
    autoUpdateItem: false
    updateName: true
    updateLore: true
    updateDurability: false
    updateAttributes: false
    updateEnchants: false
    updateCustomModelData: false
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    globalCooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    otherEICooldowns: {}
    requiredItems: {}
    requiredExecutableItems: {}
    detailedSlots:
    - -1
    commands:
    - execute at %score_variables_myList_0% run summon minecraft:tnt ~ ~ ~
    - execute at %score_variables_myList_1% run summon minecraft:tnt ~ ~ ~
    - execute at %score_variables_myList_2% run summon minecraft:tnt ~ ~ ~
    - score variables clear player myList %player%
    - SENDMESSAGE &7Then it's just a big &eBOOOOOM &7but you can do many other things
      let's talk your imagination
    playerConditions:
      ifSneaking: true
      ifSneakingMsg: ''
    worldConditions: {}
    itemConditions: {}
    customConditions: {}
    placeholdersConditions: {}
    variablesModification: {}
  activator1:
    name: '&eActivator'
    option: PROJECTILE_HIT_ENTITY
    usageModification: 0
    cancelEvent: false
    noActivatorRunIfTheEventIsCancelled: false
    silenceOutput: false
    autoUpdateItem: false
    updateName: true
    updateLore: true
    updateDurability: false
    updateAttributes: false
    updateEnchants: false
    updateCustomModelData: false
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    globalCooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    otherEICooldowns: {}
    requiredItems: {}
    requiredExecutableItems: {}
    detailedSlots:
    - -1
    commands:
    - 'SENDMESSAGE &7You &aselected &7the entity: &e%entity_name%'
    - score variables list-add player myList %entity_uuid% %player%
    playerConditions: {}
    worldConditions: {}
    itemConditions: {}
    customConditions: {}
    placeholdersConditions:
      plchCdt0:
        type: PLAYER_STRING
        comparator: EQUALS
        part1: '%score_variables-contains_myList_%entity_uuid%%'
        part2: 'false'
        cancelEventIfNotValid: false
        messageIfNotValid: ''
        messageIfNotValidForTarget: ''
      plchCdt1:
        type: PLAYER_NUMBER
        comparator: INFERIOR
        part1: '%score_variables-size_myList%'
        part2: '3'
        cancelEventIfNotValid: false
        messageIfNotValid: '&4&l>> &7&oYou can''t select more than 3 entities'
        messageIfNotValidForTarget: ''
    detailedEntities: []
    entityCommands: []
    entityConditions: {}
    variablesModification: {}
  activator3:
    name: cancelProjectileSelection
    option: PROJECTILE_HIT_ENTITY
    usageModification: 0
    cancelEvent: true
    noActivatorRunIfTheEventIsCancelled: false
    silenceOutput: false
    autoUpdateItem: false
    updateName: true
    updateLore: true
    updateDurability: false
    updateAttributes: false
    updateEnchants: false
    updateCustomModelData: false
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    globalCooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: true
      cancelEventIfInCooldown: false
    otherEICooldowns: {}
    requiredItems: {}
    requiredExecutableItems: {}
    detailedSlots:
    - -1
    commands: []
    playerConditions: {}
    worldConditions: {}
    itemConditions: {}
    customConditions: {}
    placeholdersConditions: {}
    detailedEntities: []
    entityCommands: []
    entityConditions: {}
    variablesModification: {}
attributes: {}

```

</details>







## ExecutableItems (Item variables)

ExecutableItems has a integration of variables where you can store strings/numbers/list in variables **inside** the item. With them you can create multiple mechanics in your items.

{% hint style="info" %}
There are ways to change the variable outside the item, using this methods:\
\


#### Modify a variable

* VIA CONSOLE
  * Command:&#x20;
    * /ei console-modification {set/modification} variable {player} {slot} {variableName} {value}
* VIA on game
  * Command:
    * /ei modification {set/modification} variable {slot} {variableName} {value}
{% endhint %}







## ExecutableBlocks (Block variables)

ExecutableBlocks has a integration of variables where you can store strings/numbers/list in variables **inside** the block. With them you can create multiple mechanics in your blocks.
