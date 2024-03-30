# 📚 Custom Commands

Here you have information related to all commands !&#x20;

{% content-ref url="tools-for-all-plugins-score/custom-commands/player-and-target-commands.md" %}
[player-and-target-commands.md](tools-for-all-plugins-score/custom-commands/player-and-target-commands.md)
{% endcontent-ref %}

{% content-ref url="tools-for-all-plugins-score/custom-commands/entity-commands.md" %}
[entity-commands.md](tools-for-all-plugins-score/custom-commands/entity-commands.md)
{% endcontent-ref %}

{% content-ref url="tools-for-all-plugins-score/custom-commands/block-commands.md" %}
[block-commands.md](tools-for-all-plugins-score/custom-commands/block-commands.md)
{% endcontent-ref %}

{% content-ref url="tools-for-all-plugins-score/custom-commands/utility-commands.md" %}
[utility-commands.md](tools-for-all-plugins-score/custom-commands/utility-commands.md)
{% endcontent-ref %}

## You can use all commands from the list above in other plugins !!

Score has more than 100 custom commands, that normalyl were able to only run inside your EI/EB/EE, but now, they can be executed from anywhere, let's take a look how this works:

### Player commands

* Run a custom command from SCore for a specific player
  * /score run-player-command player:{playername} {command}

```
Example:
/score run-player-command player:Ssomar SENDMESSAGE &eHello
/score run-player-command player:Ssomar SENDMESSAGE &eHello player:Ssomar +++ DELAY 10 +++ SWING_MAIN_HAND
```

{% hint style="info" %}
It supports PAPI Placeholders
{% endhint %}

### Block commands

* Run a custom command from SCore for a specific block
  * /score run-block-command player:Ssomar block:{world},{x},{y},{z} {command}

### Entity commands

* Run a custom command from SCore for a specific entity
  * /score run-entity-command entity:{entityUUID} {command}



## Command Issues

### Issues related to ' and " symbols

While writing commands like:

{% code overflow="wrap" %}
```
MOB_AROUND 10 true BLACKLIST(ARMOR_STAND) execute at %around_target_uuid% run summon armor_stand ~ ~3 ~ {NoGravity:1b,Silent:1b,Invulnerable:1b,Small:1b,Marker:1b,Invisible:0b,Tags:["mete0"],ArmorItems:[{},{},{},{id:"minecraft:magma_block",Count:1b,tag:{CustomModelData:10002}}]}
```
{% endcode %}

You might encounter console errors such as:

```
[07:41:08 INFO]: Expected '}'
...:minecraft:magma_block,Count:1b,tag:{CustomModelData:10002}}]}<--[HERE]
```

To fix it, change the `"` symbols to `'`
