# Action Counter

Well ! This method is about to get a counter of how many "x" action has been being activated, for example, how many kills with the sword, how many times an ability has been activated, how many blocks the item has broke, etc.&#x20;

To achieve any of the examples before its the same, just changing the activator and a couple of instinct things.&#x20;

This example will be with the "how many blocks the item has broke", so, let's do it !

## Let's create the item

* Using the /ei create command, we will create the item.

![](<../../../.gitbook/assets/image (290).png>)

* Once the item is created you can change the name, lore, item, etc. In this case my item looks like this:

![Item display](<../../../.gitbook/assets/image (148).png>)

* So, the idea is to trigger something when the pickaxe has broken 15 blocks, this "something" could be whatever you want, in this case I'll give another EI item to the player (The pickaxe level 2).

### Where are we going to store the information? 🤔

* Well, we're going to store it in variables

<figure><img src="../../../.gitbook/assets/image (431).png" alt=""><figcaption></figcaption></figure>

* Let's create one.

<figure><img src="../../../.gitbook/assets/image (433).png" alt=""><figcaption></figcaption></figure>

* id: blockbreaks
* type: number
* default value: 0

<figure><img src="../../../.gitbook/assets/image (434).png" alt=""><figcaption></figcaption></figure>

### Let's create the activator

* So, just because the trigger is "breaking blocks" the activator will be `PLAYER_BLOCK_BREAK`

![](<../../../.gitbook/assets/image (413).png>)

* And the idea is that each time you break a block store "1" in the variable we just created, so, let's go to variablesModification.

<figure><img src="../../../.gitbook/assets/image (435).png" alt=""><figcaption></figcaption></figure>

* The one created will have this settings:
  * variable id: **blockbreaks** (that is the one where we want to store)
  * type of modification: **modification**
  * modification: **1**

<figure><img src="../../../.gitbook/assets/image (436).png" alt=""><figcaption></figcaption></figure>

* Ok, the "saving" part is ready, we're going to setup something just to check it is working fine. We're going to add the "blocks broken" in the lore.

![](<../../../.gitbook/assets/image (108).png>)

* This is how it looks in my inventory

![](<../../../.gitbook/assets/image (235).png>)

* And.. ¿What if I break a block?

![](<../../../.gitbook/assets/image (276).png>)

* Boom ! Now the blocks broken is 1, the store is readdyy

### Reward of achieving the objective

* Well the reward part will be another activator, since I want it to be triggered when breaking block it will be also a break block activator (2nd, the 1st stores the information)

![](<../../../.gitbook/assets/image (350).png>)

* Let's add in the commands the reward

![](<../../../.gitbook/assets/image (326).png>)

* I have an item called "breakblockcounter2" its the same pickaxe but level 2
* Now let's add the CONDITION to only work when the pickaxe has broken 15 blocks.

![](<../../../.gitbook/assets/image (379).png>)

![](<../../../.gitbook/assets/image (64).png>)

* The type will be PLAYER\_NUMBER

![](<../../../.gitbook/assets/image (262).png>)

* We're going to compare the variable

![](<../../../.gitbook/assets/image (79).png>)

* To be EQUALS

![](<../../../.gitbook/assets/image (336).png>)

* To 15

![](<../../../.gitbook/assets/image (80).png>)

* And that's all, let's test it.

### Final words

I setup a ei take command to delete the pickaxe, and the 2nd pickaxe was created outside this tutorial.

![gg](<../../../.gitbook/assets/2022-05-14 18-31-01.gif>)

* If have any question feel free to ask in the Discord !! ^^

{% hint style="info" %}
If would like to be the same but with another trigger, for example storing how many time a item has hit a player, just change the activator, in the case I said you'd need PLAYER\_HIT\_PLAYER, but if you want another thing just search the activator you need.
{% endhint %}
