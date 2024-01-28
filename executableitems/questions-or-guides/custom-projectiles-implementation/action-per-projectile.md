# Action per projectile

To create different action per projectile, for example, having 4 types of projectiles in your item:

* projectile1: It is launched by RIGHT\_CLICK activator NOT SHIFTING
* projectile2: It is launched by RIGHT\_CLICK activator SHIFTING
* projectile3: It is launched by LEFT\_CLICK activator NOT SHIFTING
* projectile4: It is launched by LEFT\_CLICK activator SHIFTING

And having 4 different actions on each projectile, you have to create

* 4 different activator PROJECTILE\_HIT\_ENTITY and 4 different activator PROJECTILE\_HIT\_PLAYER
  * And for each activator create a placeholder condition
    * PLAYER\_STRING
    * %projectile\_name%
    * EQUALS
    * \<theprojectilename>

\======================================================================

For example

* ACTIVATOR1 PROJECTILE\_HIT\_ENTITY
  * Placeholder condition
    * PLAYER\_STRING
    * %projectile\_name%
    * EQUALS
    * projectile1
  *   entityCommands:

      * DAMAGE 20


* ACTIVATOR2 PROJECTILE\_HIT\_ENTITY
  * Placeholder condition
    * PLAYER\_STRING
    * %projectile\_name%
    * EQUALS
    * projectile2
  *   entityCommands:

      * BURN 10


* ACTIVATOR3 PROJECTILE\_HIT\_ENTITY
  * Placeholder condition
    * PLAYER\_STRING
    * %projectile\_name%
    * EQUALS
    * projectile3
  *   entityCommands:

      * execute at %entity\_uuid% run summon lightning\_bolt


* ACTIVATOR4 PROJECTILE\_HIT\_ENTITY
  * Placeholder condition
    * PLAYER\_STRING
    * %projectile\_name%
    * EQUALS
    * projectile4
  * entityCommands:
    * execute at %entity\_uuid% run setblock \~ \~ \~ cobweb replace air



And that's it, the weapon will make stuff different depending on the projectile launched. If have any question feel free to ask it in the discord ^^
