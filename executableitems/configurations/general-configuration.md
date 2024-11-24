# General Configuration

{% code title="config.yml" %}
```yaml
pickupLimit: -1
disabledWorlds: [] #Its a blacklist, EI will be disabled in these worlds
whitelistedWorlds: [] #Its a whitelist, EI will be enabled only in these worlds
whitelistItemsPerWorld:
  myWorld:
    - "myEI1"
    - "myEI2"
  myWorld2:
    - "myEI3"
    - "myEI4"
premiumEnableCooldownForOp: true #Premium only
checkVersionMsg: true
disableTestItems: false # If you have a big server with a lot of players, it's recommended to turn this option on true
silentEIGive: false
silentMessagePreventionErrorHeadDBError: false
disableBackup: false #<- Backup your items config at each start / reload of the server
deleteBackupsAfterDays: 7 #<- It will deletes backups older than this number of days
enableGarbageCollectorAfterReload: false #<- It will enable the garbage collector after a reload of the server
giveLimit: 100
enableTexturesPack: true #Only for 1.20.5+ servers
texturesPackUrl: "https://github.com/Ssomar-Developement/items/raw/main/__textures__/ExecutableItems_Pack.zip" #Only for 1.20.5+ servers
logs:
  dropped: true
  spawned: true
debugOnlyRun: false # /ei debug will only display the run debug message
itemCheckWithNBTAPI: false #Enabling this setting should result better performance when ExecutableItems checks if the item is an EI or not.
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

#### Premium-enable-cooldown-for-o&#x70;**:** <img src="../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

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
