# Activator Examples



```yaml
activators:
  activator1:
    activator: PLAYER_LAUNCH_PROJECTILE
    displayName: Activator name
    usageModification: 0
    usePerDay: -1
    cancelEventIfMaxUsePerDay: false
    autoUpdateItem: false
    commands:
    - LAUNCHENTITY CREEPER
    - execute at %player% run data merge entity @e[distance=..2,type=creeper,limit=1] {powered:1b}
    silenceOutput: false
    cancelEventIfInvalidRequiredExecutableItems: false
    cancelEvent: true
```

```yaml
activators:
  activator1:
    activator: PLAYER_RIGHT_CLICK
    displayName: Activator name
    usageModification: 0
    usePerDay: -1
    cancelEventIfMaxUsePerDay: false
    autoUpdateItem: false
    commands:
    - FRONTDASH 2 0.2
    silenceOutput: false
    blockCommands: []
    detailedBlocks: []
    cancelEventIfNotDetailedBlocks: false
    onlyAirClick: false
    onlyBlockClick: false
    cancelEventIfInvalidRequiredExecutableItems: false
    cancelEvent: false
    detailedSlots:
    - 37
    cooldown: 5
    displayCooldownMessage: false
    cancelEventIfInCooldown: false
    isCooldownInTicks: false
    cooldownMsg: ''

```
