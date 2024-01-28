# Creating a basic projectile

### Create the EI Item.

* Every projectile from Score is launched by an ExecutableItem item, so you need that first
* /ei create \<id>

<figure><img src="../../../.gitbook/assets/image (418).png" alt=""><figcaption></figcaption></figure>

* Edit everything you want, as the material, item name, lore, etc.

<figure><img src="../../../.gitbook/assets/image (255).png" alt=""><figcaption></figcaption></figure>

* Now, let's create the way we are going to launch the projectile, in this case I want it to be when right clicking, that means, Activator: PLAYER\_RIGHT\_CLICK

<figure><img src="../../../.gitbook/assets/image (300).png" alt=""><figcaption></figcaption></figure>

* Now, let's save the activator and item for a while, because we need to launch the projectile we want

{% hint style="info" %}
The order explained here isn't the best, you can do it in the order you want, it is just done in a way you can understand how everything works step by step
{% endhint %}

### Create the projectile

* Remember, we have the EI Item ready, it is just waiting for our projectile, to create it use the command /score projectiles-create

<figure><img src="../../../.gitbook/assets/image (252).png" alt=""><figcaption></figcaption></figure>

* You can select there the type of projectile, edit the particles, edit a lot of features, just do it as you want, edit everything you want, until your projectile is done, in this case I did:
  * Projectile: SNOWBALL
  * Invisible: true
  * Silent: true
  * Gravity: false
  * Added some particles in the particle editor inside the gui.
* Once the projectile is done, save it, and let's go back into our EI Item.

### Link the projectile created into our EI Item

*   Let's go back to the activator PLAYER\_RIGHT\_CLICK of our item, and in commands we are going to use the LAUNCH command, the format is

    * LAUNCH \<ID>

    In this case, the ID is the id of the projectile, I set it to "ThisIsTheIdOfMyProjectile" so the command part would look like:

<figure><img src="../../../.gitbook/assets/image (344).png" alt=""><figcaption></figcaption></figure>

* Then press FINISH, save the activator, and save the item and.. TEST !

<figure><img src="../../../.gitbook/assets/2022-10-23 14-10-15.gif" alt=""><figcaption></figcaption></figure>
