# 🔘 Custom triggers

## Custom triggers !

Custom trigger is a way to store a list of commands and then either run those commands with a simple command or by a schedule system.

### How to create custom triggers ?

* Custom trigger is a type of activator, so go to the plugin you want (available in ExecutableItems, ExecutableBlocks and ExecutableEvents) and create the activator and select as option: CUSTOM\_TRIGGER.
* Then add on "commands section" the commands you want, but be careful ! on ExecutableItems the commands can be run agaisnt the player, but on ExecutableBlocks and ExecutableEvents the commands are run on the console and they are not attached to a player or block, so you can't run for example:
  * ❌SEND\_MESSAGE \&eMy name is..\
    Because the activator doesn't know whom to run this command against.\
    So what can we do ?\
    Well, this answer is very huge, and it can't be answered just like this, we think its just important to know what we have already said, you'll see some examples of how to deal with this on the tutorial. But as said, its a very huge space of solutions which the one for you will depend on your context.&#x20;
* Well, let's continue, since you have already created the activator and the commands, now you can differentiate the CUSTOM\_TRIGGER into 2 types:
  * Callables: Custom triggers activators which are only callable by the command
    * /\<plugin> custom-trigger \<features>
  * Callables and Scheduleds: Custom triggers activators which are callable by commands but also they are scheduled, that means they work in specific certain times. For example:
    * An activator that runs each day at 22:00 hrs.
    * An activator that runs each sunday.
    * An activator that will run the next \<date>.

- [ ] (Optional) Edit the schedule features

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



### How to run custom triggers manually ?

In this category you will learn how to run the custom triggers we have already created !

* Keep in note that values with {} are obligatory for the command to work, and \[] are optional.
* For better understanding we also marked as blue = obligatory and orange = optional

Before knowing how to make them work, let's talk a bit of how they work.

* We have created a custom trigger activator with a certain activatorID
* The commands are basically a "searcher" if they find an ExecutableItem with the specified activatorID which is a custom trigger then it will run the activator.
* What is the idea of doing this ? you would think, why I would refer to a custom trigger inside my ExecutableItem from my ExecutableItem, since I could have write just the commands on my activator instead of calling a custom trigger?&#x20;
  * Well, the idea is to organize, its useful for complex setup, let's say you repeat 5 command always on 4 activators on your same ExecutableItem then it may (not necessary) be a good idea to pack those 5 commands into 1 activator and just run the custom trigger.

The same idea can be extrapolated to other contexts such as using it in ExecutableItems, ExecutableBlocks and ExecutableEvents.&#x20;

#### Running custom triggers for ExecutableItems

* Command: <mark style="color:blue;">**/ei run-custom-trigger trigger:{activatorID}**</mark> <mark style="color:orange;">**\[player:{playerName}] \[slot:{slot}]**</mark>
  * activatorID: The ID of the activator you created as custom trigger.
  * playerName: The playername of the user
    * If there is no player specified such as `/ei run-custom-trigger trigger:{activatorId}` then it will try to execute the custom trigger for all the players that have an ExecutableItem with the specified activator ID of custom trigger.
    * If there is a player specified then it will try to execute the custom trigger only for that player and will run if he has an ExecutableItem with the specified activator ID of custom trigger.
  * slot: The slot where this custom trigger should run
    * If there is no slot present then the search is on all inventory
    * If there is a slot specified then the search is only on that slot
      * You can use -1 to target the mainhand slot.
* Examples:
  * /ei run-custom-trigger trigger:activator0
  * /ei run-custom-trigger trigger:activator0 player:SsomarPluginsPlayer
  * /ei run-custom-trigger trigger:activator0 player:SsomarPluginsPlayer slot:-1

#### Running custom triggers for ExecutableBlocks

* Command: <mark style="color:blue;">**/eb run-custom-trigger trigger:my\_activator\_trigger:{activatorID}**</mark> <mark style="color:orange;">**\[block:{location}]**</mark>
  * activatorID: The ID of the activator you created as custom trigger.
  * location: Location of the ExecutableBlock
    * If no location is provided then it will try to run for all ExecutableBlocks placed, and it will run for the ones who has the custom trigger activator with the ID selected.
    * If a location is provided it will do the same idea but only at that location.
* Examples:
  * /eb run-custom-trigger trigger:MyEpicTrigger
  * /eb run-custom-trigger trigger:MyEpicTrigger block:world,50,65,125

#### Running custom triggers for ExecutableEvents

* Info: This trigger is quite different, because on EI we have as condition the player and slot, on EB the location, but on ExecutableEvents we don't have conditions, that means, if you call for this trigger, if it exists it will always run.
* Command: <mark style="color:blue;">**/ee run-custom-trigger trigger:{activatorID}**</mark>
  * activatorID: The ID of the activator you created as custom trigger.
* Examples:
  * /ee run-custom-trigger trigger:MyEpicTrigger



### How to run our custom triggers ?

We have already explained the basics of how to create a custom trigger, but it may be not very clear how schedule works or how to run them, that's why, since we already know the content, let's check a couple of examples

#### \[ExecutableEvents] Schedule activator with message for your next Event, for example for the new year

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
       - '2026:::XX:::XX:::XX:::XX:::XX:::XX' // It runs the 1 January 2025 at 00:00:00
    consoleCommands:
    - say &eHappy new year Everyone !
    - ei giveall new_year_gift 10
```

* This activator will run automatically at 1 January 2026 at 00:00:00 and it will run the consoleCommands, so we will start the year with good messages and 10 gifts ^^

#### \[ExecutableItem] Scheduled activator, such as rewards for having the ExecutableItem in their inentory

* "In their inventory" statement is on the title because remember an ExecutableItem only work if its inside a player inventory !
* With that said let's create an activator inside our item that runs the commands at 10h, 14h and 18h each day, and we give him for having the item some money in game with the command money.

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

* Be careful ! The detailedSlots of this activator is -1, so it will trigger on the hours scheduled but if the player doesn't have it on mainhand it will fail due to conditions, so the player won't receive money. You can adjust the features depending on what you want.

#### \[ExecutableBlock] Custom trigger as reward

* Here you will see a basic example of an ExecutableBlock with a CUSTOM\_TRIGGER activator, which when it runs it will drop some rewards at the block location.

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
    - score run-player-command player:%owner% SEND_MESSAGE &7&oCheck your epic block, there is a &ebig reward
      &7for you !
    - DROPEXECUTABLEITEM the_reward_ei 8
```

* The idea would be, for example after an event, killing a boss, something epic run the commands:
  * \[command to display a message to the server about the event]
  * `/eb run-custom-trigger trigger:my_drop_ei_trigger` then what would happen is o make all the EB placed drop 100 ExecutableItems
* But how could we do this ? where ? Well ! let's use what we learn, let's create an ExecutableEvent custom trigger:

```yaml
activators:
  activator0: # ID OF THE ACTIVATOR OF CUSTOM_TRIGGER
    name: '&eActivator'
    option: CUSTOM_TRIGGER
    cancelEvent: false
    silenceOutput: false
    requiredItems: {}
    requiredExecutableItems: {}
    requiredMagics: {}
    worldConditions: {}
    placeholdersConditions: {}
    consoleCommands:
    - say &eCheck your bases mate, there are some rewards !
    - eb run-custom-trigger trigger:my_drop_ei_trigger
```

* So basically now we just need to do `/ee run-custom-trigger trigger:activator0` and thats it, it would send the broadcast message and all EB will run the custom trigger activator (if they have it, I am asumming they have it) which will send a message to the owner about a reward and it will drop the reward, very cool !
* What each player would look, would be like this:
  * ```yaml
    - Check your bases mate, there are some rewards ! # Message sent by EE CUSTOM_TRIGGER
    - &7&oCheck your epic block, there is a &ebig reward&7for you ! # Message sent by EB CUSTOM_TRIGGER
    ```
