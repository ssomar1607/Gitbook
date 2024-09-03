# 🔘 Custom trigger

Custom trigger is a way to store commands and then run those commands to certain players.

If you are used to programation its like creating a function

```
Programation
public void addDamageToPlayer(Player player, Damage damage){
    player.addDamage(damage);
}

You call it with addDamageToPlayer(pepe,5)

=====================================================================

Inside minecraft:
activator5:
    name: '&eActivator'
    option: CUSTOM_TRIGGER
    commands:
    - DAMAGE 5
    
You call it depending on the plugin you are using, in the case of EI one example is
/ei run-custom-trigger trigger:activator5 player:pepe
```

Custom trigger can be called using the commands in EI, EB and EE that you can check in each page

{% content-ref url="../executableitems/commands-and-permissions.md" %}
[commands-and-permissions.md](../executableitems/commands-and-permissions.md)
{% endcontent-ref %}

{% content-ref url="../executableblocks/commands-and-permissions.md" %}
[commands-and-permissions.md](../executableblocks/commands-and-permissions.md)
{% endcontent-ref %}

{% content-ref url="../executableevents/commands-and-permissions.md" %}
[commands-and-permissions.md](../executableevents/commands-and-permissions.md)
{% endcontent-ref %}

But also you can schedule the custom trigger to be activated. For example:



```json
activator5:
    name: '&eActivator'
    option: CUSTOM_TRIGGER
    scheduleFeatures:
      startDate: '1700-01-01 00:00:00' // Begin of the schedule
      endDate: '3000-01-01 00:00:00' // End of the schedule
      when:
      // Formats
      // Format 1 : {YEAR}:::{MONTH}:::{DAY}:::{HOUR}:::{MIN}:::{SEC}
      // Format 2 : {YEAR}:!:{WEEK}:!:{DAYSTRING}:!:{HOUR}:!:{MIN}:!:{SEC}
      // Examples :
      - '%%%%:::%%:::%%:::%%:::%%:::XX' // It runs every minute
      - '%%%%:::12:::[24,25,26]:::16:::XX:::XX' // It runs only the 24,25,26 December at 16 hours
      - '2024:::XX:::XX:::XX:::XX:::XX:::XX' // It runs the 1 January 2024 at 00:00:00
      - '%%%%:!:%%:!:MONDAY:!:14:!:XX:!:XX' // It runs every Monday at 14 hours
      - '%%%%:!:42:!:XX:!:[10,14,18]:!:XX:!:XX  // It runs at 10,14,18 hours everyday during the week 42
```

