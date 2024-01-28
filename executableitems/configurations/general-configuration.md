# General Configuration

{% code title="config.yml" %}
```yaml
pickup-limit: -1
disable-world: []
premium-enable-cooldown-for-op: true #Premium only
checkVersionMsg: true
disableTestItems: false # If you have a big server with a lot of players, it's recommended to turn this option on true
silentEIGive: false
silentMessagePreventionErrorHeadDBError: false
disableBackup: false #<- Backup your items config at each start / reload of the server
deleteBackupsAfterDays: 7 #<- It will deletes backups older than this number of days
whitelisted-worlds: [] #iTS A WITHELIST, ExecutableItems plugin will only work in these worlds.
giveLimit: 100 #Limit the maximum items you can give with the give command
jetMinionsGenerateBreakActivator : true #false/true If it is turned to true, when a minion breaks a block, an event will be created to simulate that the owner of the minion has broken the block.
exceptions: #This disable the action of activators with specific DamageCauses
  PLAYER_HIT_ENTITY:
    -THORNS
logs: #This is a log that appears on console for utility.
  dropped: true
  spawned: true

#optional config related to whitelist item per world (you can add a feature similar
#in the config of an item specific, you can do the same here, its just different way
#to do the same)
whitelistItemsPerWorld:
  myWorld:
    - "myEI1"
    - "myEI2"
  myWorld2:
    - "myEI3"
    - "myEI4"
```
{% endcode %}



**Pickup-limit:**

* example: `pickup-limit: 5`
* description: Amount maximum that a player can have on his inventory.
* required: NO, (Default -1)



**Disable-world:**

* description: Blacklisted world, where all ExecutableItems are disabled.
* required: NO, (Default no blacklist world)

```yaml
disable-world:
- Thename
- ofthedisableworld
```

#### Premium-enable-cooldown-for-op**:** <img src="../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* description: For EI premium, Enable or disable cool-down for Oped player.
* required: NO, (Default true)

#### CheckVersionMsg:

* description: If true display you a message when there is a new update of EI.
* required: NO, (Default true)

#### DisableTestItems:

* description: If true default/test items offer by EI will not be loaded, that can improve a bit your performances.
* required: NO, (Default false)

```yaml
disableTestItems: true
```

#### silentEIGive:

* description: If true the output of the command /ei give will will be hidden in the console.
* required: NO, (Default false)

```yaml
silentEIGive: true
```
