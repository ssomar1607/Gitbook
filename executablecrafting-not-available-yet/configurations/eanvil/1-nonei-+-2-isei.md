# (1)NonEI + (2)IsEI

{% hint style="info" %}
For the explanation this information will be used

* ![](<../../../.gitbook/assets/image (1).png>)
* NonEI: An item that is not an ExecutableItem, it doesn't mean its vanilla, it can be whatever item with whatever nbt tag but it <mark style="color:red;">**must not be**</mark> an ExecutableItem
* IsEI: An item that is a ExecutableItem, again, it doesn't matter if it has more nbt tag or less, it can be whatever but <mark style="color:green;">**it must be**</mark> an ExecutableItem.
* (id): It refers to the position of the anvil
* \<item.(id)> It refers the item that is on the id position


{% endhint %}

### (1)NonEI + (2)IsEI

* This anvil placement will return on (3) the \<item.1> but with the ExecutableItem <mark style="color:orange;">**ID**</mark> of \<item.2>.
* Example:
  * There is an EI item - Material:FEATHER- ID:speedUpgrade - Loop activator that gives the player an effect of speed all the time its on the mainhand (slot:-1)
    *

        <figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

        <figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
  * And we have a NonEI Diamond Sword
    *

        <figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
  * We can mix them on the Anvil placing the Diamond Sword on slot (1) and our custom EI Feather on slot (2) and it will return us the same \<item.1> but with the <mark style="color:orange;">**ID**</mark> of \<item.2>
    *

        <figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
    *

        <figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

        asd
