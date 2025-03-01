# Utility Commands

If you edit the commands in-game don't add the **-** that is before all examples.

### DELAY

* Info: Delays a command line for seconds
* Command: DELAY {amount}
  * {amount}: To how long you want commands to be delayed (In seconds)
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    commands: #There will be a delay of 10 seconds between the command1 and the command2.
<strong>    - command1
</strong>    - DELAY 10
    - command2
</code></pre>



### DELAYTICK

* Info: Delays a command line for game ticks (20 ticks = 1 second)
* Command: DELAYTICK {amount}
  * {amount}: To how long you want commands to be delayed (In ticks)
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - command1
    - DELAYTICK 5 # (0.25 seconds)
    - command2
```

## **IF**

{% hint style="info" %}
CURRENTLY ONLY WORKS IN PLAYER RELATED AND ENTITY RELATED COMMANDS
{% endhint %}

* Info: Executes commands if condition is met
* Command: IF {condition\_without\_spaces} {command1} <+> {command2} <+> ...
  * {condition\_without\_spaces}: The condition for the IF to decide whether it runs or not.
    * Symbols: =, !=, >=, <=, >, <
    * It supports () for priority , && for AND and || for OR
  * {command1},{command2}: The commands that will be executed
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - IF %player_health%>20 say cool
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - IF %entity%=PIG say I'm a pig <+> SETBABY <+> say I'm now a baby pig
```

<pre class="language-yaml"><code class="lang-yaml"><strong>activators:
</strong>  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - IF 1=1||2=3 BACKDASH 1 # 1=1 OR 2=3 -> YES because 1=1
    - IF 1=1&#x26;&#x26;2=2||2=3 BACKDASH 1 # 1=1 and 2=2 or 2=3 -> YES because 1=1 and 2=2
    - IF (1=1&#x26;&#x26;2=2)||(2=3||3=2) BACKDASH 1 # (1=1 and 2=2) or (2=3 or 3=2) -> YES because 1=1 and 2=2
</code></pre>



## **WHILE**

* Info: Repeats indefinitely as long as the condition is met. It is also running in async
* Command: WHILE {condition\_without\_spaces} {delay\_in\_ticks} {command1} <+> {command2} <+> ...
  * {condition\_without\_spaces}: The condition for the while loop to decide whether it continues or stops
  * {delay\_in\_ticks}: The delay before the next repetition
    * Delay supports decimals value but they are casted to the next integer (20.1 -> 20)
  * {command},{command2}: The commands that will be executed in repeat
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - WHILE %player_health%>10 20 SENDMESSAGE &eHello &6While <+> effect give %player% speed 1 1
```

{% hint style="info" %}
It runs async + Condition support double placeholders, example %player\_x%>%player\_z%
{% endhint %}

{% hint style="info" %}
The command will be stopped if the player is offline
{% endhint %}

## LOOP

* LOOP START
  * Info: First part of the command
  * Command: LOOP START: {amount}
    * {amount}: Number of times a command gets repeated. Placeholders are supported
* LOOP END
  * Info: Last part of the command
  * Command: LOOP END
* Example: (This is what you will see on config)

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - 'LOOP START: 5' # (50%)
    - SENDMESSAGE &cYOU GOT AN APPLE! +++ give %player% apple 1
    - LOOP END
    - 'LOOP START: 3' # (30%)
    - SENDMESSAGE &7YOU GOT IRON! +++ give %player% iron_ingot 1
    - LOOP END
    - 'LOOP START: 2' # (20%)
    - SENDMESSAGE &aYOU GOT DIAMOND! +++ give %player% diamond 1
    - LOOP END
    - RANDOM END
```

This is what the ExecutableItems plugin sees when it runs

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - SENDMESSAGE &cYOU GOT AN APPLE! +++ give %player% apple 1
    - SENDMESSAGE &cYOU GOT AN APPLE! +++ give %player% apple 1
    - SENDMESSAGE &cYOU GOT AN APPLE! +++ give %player% apple 1
    - SENDMESSAGE &cYOU GOT AN APPLE! +++ give %player% apple 1
    - SENDMESSAGE &cYOU GOT AN APPLE! +++ give %player% apple 1
    - SENDMESSAGE &7YOU GOT IRON! +++ give %player% iron_ingot 1
    - SENDMESSAGE &7YOU GOT IRON! +++ give %player% iron_ingot 1
    - SENDMESSAGE &7YOU GOT IRON! +++ give %player% iron_ingot 1
    - SENDMESSAGE &aYOU GOT DIAMOND! +++ give %player% diamond 1
    - SENDMESSAGE &aYOU GOT DIAMOND! +++ give %player% diamond 1
    - RANDOM END
```

Explanation:

When the plugin runs the commands, it duplicates the commands inside the loop commands to reduce the number of command lines in your config to make your config cleaner and since RANDOM RUN gives each command equal rates, the estimated rate will be:

* 50% chance to get an apple
* 30% chance to get iron
* 20% chance to get diamond

{% hint style="info" %}
It supports placeholders
{% endhint %}

## FOR - ENDFOR

* Command that allows you to target multiple elements inside a list

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - FOR [Special70, Ssomar, Vayk] > for1
    - effect give %for1% speed 60 2
    - ENDFOR for1
```

{% hint style="info" %}
What exactly happened here is that the FOR command will run 3 times because inside the bracket symbols, there are 3 values which are `Special70`, `Ssomar` and `Vayk`.

The `for1` word will be used as an "identifier" for that FOR command so we can use the placeholder for it.&#x20;

So when the effect command runs for the first time, %for1% will return "\
Special70" then "Ssomar" for the second and "Vayk" for the third timehinhin

Don't overthink about the `>` symbol.
{% endhint %}

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - FOR [Special70, Ssomar, Vayk] > for2
    - FOR [5,4,3,2,1] > for3
    - SENDMESSAGE >> &e%for2% &a%for3%
    - ENDFOR for3
    - ENDFOR for2
```

{% hint style="info" %}
What exactly happened here is that the FOR loops got stacked so the first FOR command will run the commands in it which is another FOR command that will run 5 times.

If you're gonna focus on the SENDMESSAGE command, the reason it ran 15 times because the first FOR command executed what's inside it by 3 while the second FOR command executed the SENDMESSAGE command 5 times which totals 15 times.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (292).png" alt=""><figcaption><p>Output of the example 2</p></figcaption></figure>

{% hint style="info" %}
**It works with score variable list placeholders**
{% endhint %}

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - FOR %score_variables_myList% > for4
    - effect give %for4% speed 60 2
    - ENDFOR for4
```

## Run commands randomly ?

{% embed url="https://youtu.be/jXTDlqoE8dc" %}

### RANDOM RUN / RANDOM END

* Info: A command mainly used for RNG.
* RANDOM RUN
  * Info: The first part of the command
  * Command: RANDOM RUN: {amount}
    * {amount}: The amount of commands that will be randomly selected inside of the command line. Placeholders are supported
* RANDOM END
  * Info: The other part of the command
  * Command: RANDOM END
* Example:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - give %player% coal 1
    - give %player% iron_ingot 1
    - give %player% gold_ingot 1
    - RANDOM END
```

This means that you have a 1/3 chance of getting coal, iron or gold

{% hint style="success" %}
**To be able to run multiple commands in one command line use `+++`**
{% endhint %}

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 2'
    - give %player% diamond 1 +++ SENDMESSAGE &aYou receive &b1 Diamond
    - give %player% emerald 1 +++ SENDMESSAGE &aYou receive &21 Emerald
    - give %player% diamond_block 1 +++ SENDMESSAGE &aYou receive &b1 Diamond block
    - RANDOM END
```

This means that from the 3 give commands, 2 of the randomly chosen command lines will run.

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - NOTHING*9
    - give %player% diamond_block 1
    - RANDOM END
```

This means that there's a 10% chance to give you a diamond block.



{% hint style="info" %}
NOTHING is just a command to adjust y percentage and if you want a case where the RNG will do nothing.
{% endhint %}

{% hint style="info" %}
It supports placeholders
{% endhint %}

### NOTHING\*

* Info: Mainly used for RANDOM RUN commands as a "dummy" command for RNG adjustments
* Command: NOTHING\*{amount}
* Example of usage:

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - NOTHING*99
    - give %player% diamond 1
    - RANDOM END
```

This command line means that there is a 1/100 chance it will give you a diamond



### More Examples:

1. I want to make it so 99% chance it will give me dirt and 1% chance to give me diamond BUT I don't want to write 99 lines of the give dirt command.

* So here is how to do it.

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'LOOP START: 99' 
    - give %player% dirt 1
    - LOOP END
```

* The 99 represents that any commands inside the loop command will be duplicated 99 times. You will only see the give command and the loop command but the plugin sees 99 give commands.
* Here is what the plugin sees

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - give %player% dirt 1
    - give %player% dirt 1
    - give %player% dirt 1
    - give %player% dirt 1
    - give %player% dirt 1
    - give %player% dirt 1
    - give %player% dirt 1
    - give %player% dirt 1
    - give %player% dirt 1
    - give %player% dirt 1
```

(You get the idea.)

* So let's go back to our main objective. 99% chance to get dirt, 1% chance to get diamond. The RANDOM RUN command evenly gives the same rng rates to all the commands inside the RANDOM RUN command.

{% hint style="warning" %}
The (5%) percentage stuff is not part of the command. It's written here in the wiki for you to acknowledge the chances for that command to be selected from the list of commands
{% endhint %}

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - give %player% dirt #(1/2 = 50%)
    - give %player% diamond #(1/2 = 50%)
    - RANDOM END
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - give %player% dirt #(1/3 = 33%)
    - give %player% diamond #(1/3 = 33%)
    - give %player% diamond #(1/3 = 33%)
    - RANDOM END
```

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - give %player% dirt #(1/4 = 25%)
    - give %player% dirt #(1/4 = 25%)
    - give %player% diamond #(1/4 = 25%)
    - NOTHING*1 #(1/4 = 25%)
    - RANDOM END
```

* After seeing these RANDOM RUN examples, we will acknowledge that it would work like this.

```yaml
activators:
  activator0: # Activator ID, you can create as many activator on the activators list
    commands:
    - 'RANDOM RUN: 1'
    - 'LOOP START: 99' 
    - give %player% dirt 1  #(99/100 = 99%)
    - LOOP END
    - give %player% diamond 1 #(1/100 = 1%)
    - RANDOM END
```

* The total of the supposed lines is 100 so it's going to be (100 command lines / 100% = 1%) rate per command.

{% hint style="info" %}
It supports placeholders
{% endhint %}

### RANDOM RUN | RANDOM END Generator

* Click on **Run**
* **Wait** until the GUIDE message appears
* Use the generator

{% embed url="https://replit.com/@Vayk1/Score-or-RANDOM-RUN-generator?v=1" %}

Or you could visit ([https://special70.github.io/item%20config%20editors/executableitems\_editor.html](https://special70.github.io/item%20config%20editors/executableitems_editor.html)) where you can adjust the rates and have a button that evens out the rates across all of your commands. \
Just click the RANDOM RUN button in that website
