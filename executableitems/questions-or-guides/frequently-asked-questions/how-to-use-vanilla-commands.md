# How to use vanilla commands



{% embed url="https://www.youtube.com/watch?ab_channel=Vayk&v=cYtk6Z8O2-c" %}

It is possible that inside your ExecutableItem you will use vanilla commands that **needs a position**, such as:

* playsound..
* summon..
* particle..
* effect..
* etc

If its the case, let's explain you something, all commands in the commands section are run by the console, so when you type "summon zombie \~ \~ \~" that command will be run from "0,0,0" in the default world.&#x20;

To avoid this you have to add <mark style="color:orange;">"</mark><mark style="color:orange;">**execute at %player% run**</mark><mark style="color:orange;">"</mark> before the command, that will force the command to be run from the coordinates where the player is.

For example:

<pre><code>❌run summon tnt ~ ~ ~ 
✅execute at %player% run summon tnt ~ ~ ~

❌playsound minecraft:ambient.cave master %player% ~ ~ ~ 1 1
✅execute at %player% run playsound minecraft:ambient.cave master %player% ~ ~ ~ 1 1

<strong>❌particle minecraft:flame ~ ~ ~ 1 1 1 0 10
</strong>✅execute at %player% run particle minecraft:flame ~ ~ ~ 1 1 1 0 10

✅effect give %player% speed 15 1

✅execute at %player% run setblock ~ ~ ~ stone

✅execute at %player% run fill ~1 ~1 ~1 ~-1 ~-1 ~-1 stone replace air

✅execute at %player% run tellraw %player% {"text":"hi"}
✅execute at %player% run tellraw @a {"text":"hi"}
</code></pre>



These are special exceptions, that means, placeholders or general stuff that only works by certain conditions.

{% tabs %}
{% tab title="Block placeholders" %}
If its the case that the activator you are using is **related with a block** (if don't know what we are talking explore the gui or check the basic tutorial), you can use the [**block placeholders**](../../../tools-for-all-plugins-score/placeholders.md#block-placeholders) on commands, such as:

```
execute at %player% run setblock %block_x% %block_y% %block_z% stone

execute at %player% run fill %block_x% %block_y% %block_z% %block_x% 255 %block_z% stone

execute in <<%block_world%>> positioned %block_x% %block_y% %block_z% run summon tnt ~ ~ ~
```
{% endtab %}

{% tab title="Entity placeholders" %}
If its the case that the activator is **related with an entity** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> (if don't know what we are talking explore the gui or check the basic tutorial), you can use the [entity placeholders](../../../tools-for-all-plugins-score/placeholders.md#target-entity-placeholders) on commands, such as:

```
execute at %entity_uuid% run particle flame ~ ~ ~ 1 1 1 50 0
execute at %player% run setblock %entity_x% %entity_y% %entity_z% stone
execute run effect give %entity_uuid% strength 10 10
```
{% endtab %}

{% tab title="Projectile placeholders" %}
If its the case that the activator is **related with a projectile** (if don't know what we are talking explore the gui or check the basic tutorial), you can use the [projectile placeholders](../../../tools-for-all-plugins-score/placeholders.md#projectile-placeholders) on commands, such as:

```
execute at %projectile_uuid% run particle flame ~ ~ ~ 1 1 1 50 0
execute at %player% run setblock %projectile_x% %projectile_y% %projectile_z% stone
```
{% endtab %}
{% endtabs %}

{% hint style="success" %}
"Multi-world" compatibility for the vanilla commands.

* `execute in <<NAME`_`OF`_`YOUR_WORLD>> run ...`

Example, you want summon a Zombie in the world SsomarWorld:

* `execute in <<SsomarWorld>> run summon zombie 100 50 100`

Example with a placeholder`:`

* `execute in <<%player_world%>> run summon zombie 100 50 100`
* `execute in <<%block_world%>> run particle firework %block_x% %block_y% %block_z% 1 1 1 0.2 20`
{% endhint %}

## Discord

In case this didn't help you to achieve what you wanted or doesn't work for you, feel free to ask in the Discord of Ssomar plugins your question.
