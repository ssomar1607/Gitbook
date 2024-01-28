# Item Examples

{% hint style="info" %}
Here are some examples without activators, to focus only on the item features !
{% endhint %}

### Potion example

{% code title="Free_Epic_Potion.yml" %}
```yaml
name: '&d֎ &5&lEpic potion &d֎'
lore:
- '&d&l---&7&l>>&d&l-----&7&l<<&d&l---'
- '&7Tier: &dRare'
- '&7Effects:'
- ' &5• &dSpeed 3 (30 secs)'
- ' &5• &dStrength 5 (10 secs)'
- '&7Epic:'
- ' &5• &dEpic particles ❁'
- '&d&l---&7&l>>&d&l-----&7&l<<&d&l---'
- '&8Signed by: &5%player%'
material: POTION
glow: true
disableStack: false
keepItemOnDeath: false
canBeUsedOnlyByTheOwner: false
storeItemInfo: false
unbreakable: false
usage: 0
usageLimit: -1
dropOptions:
  glowDrop: false
  glowDropColor: WHITE
  displayNameDrop: false
hiders:
  hideEnchantments: false
  hideUnbreakable: false
  hideAttributes: false
  hidePotionEffects: true
  hideUsage: false
enchantments: {}
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
restrictions:
  cancel-item-drop: true
  cancel-anvil: true
  cancel-item-place: true
  cancel-item-craft: true
cancelEventIfNoPerm: false
cancelEventIfNotOwner: false
disabledWorlds: []
variables: {}
activators:
  activator1:
    name: '&eActivator'
    option: PLAYER_CONSUME
    usageModification: -1
    cancelEvent: false
    silenceOutput: false
    autoUpdateItem: false
    cooldownOptions:
      cooldown: 0
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: false
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
    - 40
    commands:
    - PARTICLE DRAGON_BREATH 200 1.5 0.12
    playerConditions: {}
    worldConditions: {}
    itemConditions: {}
    customConditions: {}
    placeholdersConditions: {}
    variablesModification: {}
recognitions: []
potionSettings:
  potionColor: 16776960
  potionType: WATER
  potionExtended: false
  potionUpgraded: false
  potionEffects:
    '1':
      isAmbient: false
      duration: 400
      potionEffectType: SPEED
      amplifier: 2
      hasParticles: false
      hasIcon: false
    '2':
      isAmbient: false
      duration: 200
      potionEffectType: INCREASE_DAMAGE
      amplifier: 4
      hasParticles: false
      hasIcon: false
attributes: {}
config_5: truep
```
{% endcode %}

### Head example

{% code title="Free_Money.yml" %}
```yaml
name: '&6$ &e&l5000 &6$'
lore:
- '&8&m-----------------------'
- '&7'
- '&6➤ &e&oClick + sneak to execute me !'
- '&7'
- '&7&oInfo:'
- '&6» &eReceive 5000$'
- '&7'
- '&8&m-----------------------'
material: PLAYER_HEAD
glow: true
disableStack: false
keepItemOnDeath: false
canBeUsedOnlyByTheOwner: false
storeItemInfo: false
unbreakable: false
usage: 0
usageLimit: -1
dropOptions:
  glowDrop: false
  glowDropColor: WHITE
  displayNameDrop: false
hiders:
  hideEnchantments: false
  hideUnbreakable: false
  hideAttributes: false
  hidePotionEffects: false
  hideUsage: false
enchantments: {}
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
restrictions:
  cancel-item-drop: true
  cancel-item-place: true
  cancel-item-craft: true
cancelEventIfNoPerm: false
cancelEventIfNotOwner: false
disabledWorlds: []
variables: {}
activators:
  activator1:
    name: '&eActivator'
    option: PLAYER_ALL_CLICK
    typeTarget: NO_TYPE_TARGET
    usageModification: -1
    cancelEvent: false
    silenceOutput: false
    autoUpdateItem: false
    cooldownOptions:
      cooldown: 5
      isCooldownInTicks: false
      cooldownMsg: '&cYou are in cooldown ! &7(&e%time_H%&6H &e%time_M%&6M &e%time_S%&6S&7)'
      displayCooldownMessage: false
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
    - 40
    commands:
    - /eco give %player% 5000
    - SENDMESSAGE §a§l[ExecutableItems] §e%player% you have receive §a5000$
    playerConditions:
      ifSneaking: true
    worldConditions: {}
    itemConditions: {}
    customConditions: {}
    placeholdersConditions: {}
    variablesModification: {}
recognitions: []
headValue: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvMTk4ZGY0MmY0NzdmMjEzZmY1ZTlkN2ZhNWE0Y2M0YTY5ZjIwZDljZWYyYjkwYzRhZTRmMjliZDE3Mjg3YjUifX19
headDBID: ''
attributes: {}
config_5: true

```
{% endcode %}

### Crate example

{% code title="Free_Custom_Crate.yml" %}
```yaml
name: '&7&l(&e&l❖&7&l)>> &7&oEpic box'
lore:
- '&f'
- '&8&l»&7&l&m----------------&8&l«'
- '&e     Click to open !'
- '&f'
- '&7&oLoots:'
- '&a   20% &e20 gold ingots'
- '&a   15% &215 emeralds'
- '&a   40% &810 coal'
- '&a   25% &b5 diamonds'
- '&8&l»&7&l&m----------------&8&l«'
- '&f'
material: CHEST
glow: true
disableStack: false
keepItemOnDeath: false
canBeUsedOnlyByTheOwner: false
storeItemInfo: false
unbreakable: false
usage: 1
usageLimit: -1
dropOptions:
  glowDrop: false
  glowDropColor: WHITE
  displayNameDrop: false
hiders:
  hideEnchantments: false
  hideUnbreakable: false
  hideAttributes: false
  hidePotionEffects: false
  hideUsage: false
enchantments: {}
giveFirstJoin:
  giveFirstJoin: false
  giveFirstJoinAmount: 1
  giveFirstJoinSlot: 0
restrictions: {}
cancelEventIfNoPerm: false
cancelEventIfNotOwner: false
disabledWorlds: []
variables: {}
activators:
  activator1:
    name: '&eActivator'
    option: PLAYER_ALL_CLICK
    typeTarget: NO_TYPE_TARGET
    usageModification: -1
    cancelEvent: false
    silenceOutput: true
    autoUpdateItem: false
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
    - SENDMESSAGE You have executed %item%
    - execute at %player% run playsound minecraft:entity.firework_rocket.launch voice
      %player%
    - title %player% title {"text":"You have executed","color":"yellow","bold":"true"}
    - title %player% subtitle {"text":"Money Pouch - Tier I","color":"yellow","bold":"true"}
    - DELAY 2
    - title %player% title {"text":"Rolling","color":"red","bold":"true"}
    - title %player% subtitle [{"text":"$  ","color":"green","bold":"true"},{"text":"2
      3 4 5 6 7","color":"green","obfuscated":"true","bold":"true"}]
    - execute at %player% run playsound minecraft:entity.experience_orb.pickup voice
      %player%
    - 'LOOP START: 30'
    - DELAYTICK 2
    - execute at %player% run playsound minecraft:block.note_block.bass ambient %player%
    - LOOP END
    - 'RANDOM RUN: 1'
    - 'LOOP START: 20'
    - title %player% times 0 60 0 +++ title %player% title {"text":"20 GOLD INGOTS
      ","color":"gold"}+++ title %player% subtitle {"text":""} +++ execute at %player%
      run playsound minecraft:entity.villager.yes voice %player% +++ give %player%
      gold_ingot 20
    - LOOP END
    - 'LOOP START: 15'
    - title %player% times 0 60 0 +++ title %player% title {"text":"15 EMERALDS ","color":"green"}+++
      title %player% subtitle {"text":""} +++ execute at %player% run playsound minecraft:entity.villager.yes
      voice %player% +++ give %player% emerald 15
    - LOOP END
    - 'LOOP START: 40'
    - title %player% times 0 60 0 +++ title %player% title {"text":"10 COAL ","color":"gray"}+++
      title %player% subtitle {"text":""} +++ execute at %player% run playsound minecraft:entity.villager.no
      voice %player% +++ give %player% coal 10
    - LOOP END
    - 'LOOP START: 25'
    - title %player% times 0 60 0 +++ title %player% title {"text":"5 DIAMONDS ","color":"blue"}+++
      title %player% subtitle {"text":""} +++ execute at %player% run playsound minecraft:entity.villager.yes
      voice %player% +++ give %player% diamond 5
    - LOOP END
    - RANDOM END
    playerConditions: {}
    worldConditions: {}
    itemConditions: {}
    customConditions: {}
    placeholdersConditions: {}
    variablesModification: {}
recognitions: []
attributes: {}
config_5: trueyaml
```
{% endcode %}
