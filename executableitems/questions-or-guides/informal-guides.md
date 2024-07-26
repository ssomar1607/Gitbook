---
description: >-
  Page dedicated for quickly writing guides on how to do something. (Mostly me,
  Special70 being lazy to make a dedicated page)
---

# Informal Guides



## METHODS:

### Check conditions on randomly picked target

{% code overflow="wrap" fullWidth="true" %}
```
1) create a SCore projectile 
  - for this guide, we'll give it an id of "tracker"
  - give it a name for it to be used in placeholder conditions to make PLAYER_CUSTOM_LAUNCH not activate in unwanted manners. for this guide, we'll give it a display name of "tracker"
  - set gravity to false and enable invisibility (requires protocol lib plugin) and set velocity to 0
  
2) create the ei item
3) create any activator of your choice to run the ability
  - run "LOCATED_LAUNCH tracker 0 0 0 0 0 0"
4) create a PLAYER_CUSTOM_LAUNCH activator
  - create a placeholder condition
    - type: PLAYER_STRING
    - part1: %projectile_name%
    - comparator: EQUALS
    - part2: tracker
  - add the commands: 
  
  [!] ITEM CONFIG FORM
  
  entityCommands:
  - execute at %player% run execute at @r[distance=..10,limit=1] run tp %projectile_uuid% ~ ~ ~
  - DELAYTICK 1
  - AROUND 1 CONDITIONS(%::player_name::%!=%player%&&%::worldguard_region_name::%!=spawn) execute at %around_target% as %player% run tp %player% ~ ~ ~

  observe the conditions written in the CONDITIONS() part. It contains criterias of
  - if the around target is not the user to prevent the user being selected just in case no player is detected in radius
  - if the target is not in the "spawn" region
```
{% endcode %}
