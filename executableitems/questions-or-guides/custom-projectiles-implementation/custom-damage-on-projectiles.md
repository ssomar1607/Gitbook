# Custom damage on projectiles

This tutorial requires the premium version of the plugin.

## Custom damage for 1 projectile in your item

*   If want to select a specific amount of damage in your projectiles (any type of projectile) you have to first create this 2 steps (They are already explained in the other tutorials so it won't be explained here.)

    * [x] Create an ExecutableItem
    * [x] Create a Score projectile
    * [x] Make the EI to launch the projectile


*   Ok so we have the EI that launches the projectile, now to customize it you could check the options of Score (related to velocity of the arrow, explosion radius in fireball, etc) but this isn't the best way, snowball damage couldn't be customized, so, the best way to add damage is:

    * Create an activator PROJECTILE\_HIT\_PLAYER
    * Add on targetCommands -> DAMAGE \<AMOUNT> (Example: DAMAGE 5)


* And that's it, if want to the same with entities instead of PROJECTILE\_HIT\_PLAYER create an activator PROJECTILE\_HIT\_ENTITY and add the commands in entityCommands.

{% hint style="info" %}
Instead of only adding DAMAGE command you could add lot of things more, use AROUND command, or summon a lightning bolt, or use BURN command, give the target an effect, etc
{% endhint %}

## Custom damage per projectile in the same item

If you have an ExecutableItem that launches 2 different projectiles and want to customize the damage for each one, this is the correct place to learn about, its the same technic before explained but with 1 thing added.

* [x] Create the ExecutableItem
* [x] Create 2 Score projectiles
* [x] Make the EI to launch each projectile (for example one with left click and the other one with right click)

<!---->

* Now following the tutorial above, you create an activator PROJECTILE\_HIT\_PLAYER | PROJECTILE\_HIT\_ENTITY and add the command DAMAGE \<AMOUNT>, well, since in this case we have 2 projectiles, you have to create 2 activators like this
* After having the 2 activators, add a placeholder condition STRING for each one with `%projectile_name%  = <thenameofyourprojectile>`
* So you will have 2 activators related to projectile hit, that each one will work depending on the projectile name that is triggering the activator

If don't understand yet I will create a little summarize right here

<pre class="language-yaml"><code class="lang-yaml">- Activator RIGHT CLICK:
    Command: LAUNCH SNIPERBULLET #the customName of this projectile is "SniperBullet"
<strong>
</strong><strong>- Activator LEFT CLICK:
</strong>    Command: LAUNCH ROCKETBULLET #the customName of this projectile is "RocketBullet"

- Activator PROJECTILE_HIT_PLAYER:
    targetCommand: DAMAGE 1000
    Placeholder String condition: %projectile_name% = "SniperBullet"

- Activator PROJECTILE_HIT_PLAYER:
    targetCommand: AROUND 5 DAMAGE 10 +++ PARTICLE FIREWORKS_SPARK 10 0.1 0.5
    Placeholder String condition: %projectile_name% = "RocketBullet"
</code></pre>



