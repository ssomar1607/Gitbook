# Utilities

Here we will leave some stuff that may be useful when developing anything.



### config.yml of ExecutableItems

```
# ----------------------------------
# -
#       ExecutableItems
# -
#         By: Ssomar
# -
# ----------------------------------
# -
# WIKI HERE : https://docs.ssomar.com/executableitems/information-ei
# DISCORD HERE : https://discord.com/invite/TRmSwJaYNv
# -
pickupLimit: -1
disabledWorlds: []
whitelistedWorlds: []
whitelistItemsPerWorld:
  myWorld:
  - myEI1
  - myEI2
  myWorld2:
  - myEI3
  - myEI4
premiumEnableCooldownForOp: true # Premium only
checkVersionMsg: true
disableTestItems: false # If you have a big server with a lot of players, it's recommended to turn this option on true
silentMessagePreventionErrorHeadDBError: false
disableBackup: false # <- Backup your items config at each start / reload of the server
deleteBackupsAfterDays: 7 # <- It will deletes backups older than this number of days
enableGarbageCollectorAfterReload: false # <- It will enable the garbage collector after a reload of the server
giveLimit: 100
# enableTexturesPack: true #Only for 1.20.5+ servers
texturesPackUrl: https://github.com/Ssomar-Developement/items/raw/main/__textures__/ExecutableItems_Pack.zip # Only for 1.20.5+ servers
logs:
  dropped: true
  spawned: true
debugOnlyRun: false # /ei debug will only display the run debug message
config_12_04_2024: true
silentGive: false

```

### Colors

<figure><img src="../../.gitbook/assets/image (231).png" alt=""><figcaption></figcaption></figure>

### Slots

* This is a photo of the slots ID of the latest versions

![](<../../.gitbook/assets/image (215).png>)

### More placeholders

*   There are some placeholders from EI, but if want to really hook into placeholders, you should take a look at PlaceholderAPI and its wiki

    * [https://github.com/PlaceholderAPI/PlaceholderAPI/wiki/Placeholders](https://github.com/PlaceholderAPI/PlaceholderAPI/wiki/Placeholders)


* Here you have an api of all expansions
  *   [https://api.extendedclip.com/all/](https://api.extendedclip.com/all/)



### Effect cmd

* If have no idea how the effect cmd works, take a look at this page:
  * [https://www.digminecraft.com/game\_commands/effect\_command.php](https://www.digminecraft.com/game\_commands/effect\_command.php)

### Playsound cmd

* If have no idea how the playsound cmd works you should take a look here:
  * [https://www.digminecraft.com/game\_commands/playsound\_command.php](https://www.digminecraft.com/game\_commands/playsound\_command.php)

### (General) Particle cmd

* If have no idea how the particle cmd works you should take a look at this links:
  * [https://imgur.com/gallery/tVfks](https://imgur.com/gallery/tVfks)
  * [https://www.digminecraft.com/game\_commands/particle\_command.php](https://www.digminecraft.com/game\_commands/particle\_command.php)

### (Dust) particle cmd



{% embed url="https://www.youtube.com/watch?ab_channel=Vayk&v=fm6nuGEpMh8" %}

* When applying the particle cmd it needs 4 options more than the normal particles
  * \<R> \<G> \<B> \<Size>
  * Size is simple to know, is just the size of the particle, set it to 1 if don't know what to write
  * But R G B are sometimes hard to understand, since in the normal world the amount of each one is a number between 0 and 255, but in minecraft it is between 0 and 1, so you should make some conversions using math, calculator, etc.
* This link will help you to select the correct values to \<R> \<G> \<B>:
  * [https://rgbcolorcode.com](https://rgbcolorcode.com)

### Tellraw cmd

* Normally you would use the SENDMESSAGE command, but sometimes, old commands as tellraw is useful, if don't know how to use it take a look here:
  * [https://www.digminecraft.com/game\_commands/tellraw\_command.php](https://www.digminecraft.com/game\_commands/tellraw\_command.php)

### NBT Tags

*   When developing items, specially in the premium version, you maybe would like to edit some nbt tags to take control of every aspect of minecraft, to know them read this:

    * [https://minecraft.fandom.com/wiki/Tutorials/Command\_NBT\_tags](https://minecraft.fandom.com/wiki/Tutorials/Command\_NBT\_tags)



{% hint style="info" %}
To get the NBT Tag of the item in your hand, you can have a plugin that allows that, downloading a mod, or just run the vanilla command: /data get entity @s SelectedItem
{% endhint %}
