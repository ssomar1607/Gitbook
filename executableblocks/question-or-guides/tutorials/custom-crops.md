# Custom crops

## Custom SOLID crops

This type of crops are related to crops that places a block, as PUMPKIN and MELON does.

Let's create a pumpkin seed that instead of placing a pumpkin block, it will place a ORANGE\_WOOL (just because they are both orange, but you can select whatever you want)

* Create the block with /ei create \<id>
* Select the material -> PUMPKIN\_SEEDS
*

    <figure><img src="../../../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>
* Create an activator CROP\_PLACE\_BLOCK
*

    <figure><img src="../../../.gitbook/assets/image (401).png" alt=""><figcaption></figcaption></figure>
* And you will see that we have 3 different zones of commands
* ![](<../../../.gitbook/assets/image (409).png>)
* ![](<../../../.gitbook/assets/image (78).png>)
* ![](<../../../.gitbook/assets/image (84).png>)
  * Block commands is for running the commands from the block itself
  * Target Block commands the same as the last one but from the block PLACED itself (in this case, the pumpkin PLACED)
  * And owner commands the commands of the owner (if you want something to happen to the owner when this crop grows and place a block)
* So, in target block commands we will add the command SETBLOCK ORANGE\_WOOL
*

    <figure><img src="../../../.gitbook/assets/image (293).png" alt=""><figcaption></figcaption></figure>
* And then save and test

<figure><img src="../../../.gitbook/assets/2022-10-30 00-42-42.gif" alt=""><figcaption></figcaption></figure>

## Custom crops on grow tick

If want something to happen each time the crop grows, as the seeds do, carrots, potatoes, etc this is the type of block that you want

Let's create a carrots that each time it grows has a 50% of dropping a golden carrot

* First let's create the block /eb create \<id>
* Let's set the material to CARROT
* ![](<../../../.gitbook/assets/image (118).png>)
* Let's create the activator CROP\_GROW
* ![](<../../../.gitbook/assets/image (330).png>)
* And in the commands using RANDOM RUN (command already explained in utilities commands) let's use the DROPITEM command to drop a golden carrot with 50% of probability.

<figure><img src="../../../.gitbook/assets/image (141).png" alt=""><figcaption></figcaption></figure>

And that's it, let's save and test

<figure><img src="../../../.gitbook/assets/2022-10-30 00-50-32.gif" alt=""><figcaption></figcaption></figure>
