# 🔘 Custom triggers

Custom trigger is a way to store commands and then run those commands with a simple command or schedule them.

It's available in ExecutableItems, ExecutableBlocks and ExecutableEvents.

To create a new CUSTOM\_TRIGGER:&#x20;

* [ ] Open the in-game editor
* [ ] Go on the object you want to edit.
* [ ] Add a new activator with the option CUSTOM\_TRIGGER
* [ ] (Optional) Edit the schedule features

<pre class="language-json"><code class="lang-json"><strong># Here are the Schedule formats
</strong><strong>scheduleFeatures:
</strong>    startDate: '1700-01-01 00:00:00' // Begin of the schedule
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
</code></pre>

If you want to trigger your custom trigger using a command it's very easy !

{% hint style="info" %}
The trigger ID is equals to the activator ID, you can customize your activator ID by manually editing your config file.
{% endhint %}

{% hint style="warning" %}
**Be sure your activator id is unique**, if they are all named activator0 they will be triggered at the same time when one will be triggered.
{% endhint %}

For EI&#x20;

<pre><code><strong># For all holder of the EI that has the trigger
</strong>/ei run-custom-trigger trigger:my_activator_trigger

# Only for a specific player
/ei run-custom-trigger trigger:my_activator_trigger player:Ssomar
</code></pre>

For EB

```
# For all ExecutableBlock that has the trigger
/eb run-custom-trigger trigger:my_activator_trigger

# Only for a specific block at specific location
/eb run-custom-trigger trigger:my_activator_trigger block:world,50,65,125
```

For EE

```
# For all EE that has the trigger
/ee run-custom-trigger trigger:my_activator_trigger
```



### Examples

#### EE example

Schedule a message for your next Event, for example for the new year

```
enabled: true
editorIcon: LEVER
name: '&eDefault name'
disabledWorlds: []
activators:
  my_happy_new_year_trigger:
    name: '&eActivator'
    option: CUSTOM_TRIGGER
    scheduleFeatures:
      when:
       - '2025:::XX:::XX:::XX:::XX:::XX:::XX' // It runs the 1 January 2025 at 00:00:00
    consoleCommands:
    - say &eHappy new year Everyone !
    - ei giveall new_year_gift 10
```

#### EI Example

You want to create an item that does some actions at 10h, 14h and 18h, for example rewards your player that are connected and holding their epic stick

```
name: '&eMy epic stick'
lore:
- '&b&oBe connected at 10h , 14h and 18h'
- '&b&oand hold this stick to gain &6500$'
material: STICK
activators:
  my_money_give_trigger:
    name: '&eActivator'
    option: CUSTOM_TRIGGER
    scheduleFeatures:
      startDate: '1700-01-01 00:00:00'
      endDate: '3000-01-01 00:00:00'
      when:
      - '''%%%%:!:%%:!:XX:!:[10,14,18]:!:XX:!:XX'
    detailedSlots:
    - -1
    commands:
    - money give %player% 500
    playerConditions: {}
```

#### EB example

You want to make execute some actions where your ExecutableBlocks are placed by executing a simple command manually. For example reward all your players that have placed an ExecutableBlock in their base.

```
creationType: BASIC_CREATION
name: '&eMy epic block'
lore:
- '&b&oDefault lore'
material: STONE
dropType: IN_THE_INVENTORY
activators:
  my_drop_ei_trigger:
    name: '&eActivator'
    option: CUSTOM_TRIGGER
    commands:
    - DROPEXECUTABLEITEM the_reward_ei 100
    - AROUND 15 false SENDMESSAGE &7&oCheck your epic block, there is a &ebig reward
      &7for you !
```

Now you can type `/eb run-custom-trigger trigger:activator0` to make all the EB placed drop 100 ExecutableItems
