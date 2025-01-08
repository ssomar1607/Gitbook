---
description: >-
  Mostly used as a place to visit just in case we forget how a command is
  written in a specific way
---

# Code Bin/Stock



## Command that drops the target's head in 1.21.4+

{% code overflow="wrap" %}
```
execute at %player% run summon item %target_x% %target_y% %target_z% {Item:{id:"minecraft:player_head",count:1,components:{"minecraft:profile":{id:%target_uuid_array%}}}}
```
{% endcode %}
