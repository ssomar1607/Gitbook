# Transform Vanilla Items into ExecutableItems

{% hint style="info" %}
First of all you have to know that this method is only available to PREMIUM VERSION
{% endhint %}

![](<../../../.gitbook/assets/Executable Items Color3.png>)

### Let's create it, first decide what vanilla item you want to transform.

* For this tutorial it will be the **diamond\_sword**

![](<../../../.gitbook/assets/image (96).png>)

### **Then, we have to create the item that it will be replaced for**

* To create an item type `/ei create <id>` command

![](<../../../.gitbook/assets/image (194).png>)

* Change the Material of the Item to the vanilla-item you are going to change (In this case diamond\_sword)

![](<../../../.gitbook/assets/image (168).png>)

* Let's create an activator

![](<../../../.gitbook/assets/image (92).png>)

* For this example it will be `PLAYER_CLICK_ON_ENTITY`

![](<../../../.gitbook/assets/image (213).png>)

* Detailed click to left, to only work when hitting

![](<../../../.gitbook/assets/image (272).png>)

* And on commands I'll put these commands:

```yaml
commands:
- SENDMESSAGE §6This is not a normal sword..
- PARTICLE FLAME 50 0.5 0
entityCommands:
- BURN 4
```

* So when hitting the swords will say _<mark style="color:orange;">This is not a normal sword</mark>_ and the entity will burn for 4 seconds
* OK ! We have the item ready, you can test it if you want (to be sure the EI Item works fine). Now we have to make the.. transformation 😈😈

### Transforming the vanilla item into the EI Created

* To do this, you first have to go to edit the yml of your item.

{% hint style="info" %}
It is in plugins/ExecutableItems/items/\<itemID>.yml
{% endhint %}

![](<../../../.gitbook/assets/image (195).png>)

* Open it and add these lines. (they must be without ident/spaces on the left side)

```yaml
recognitions:
- MATERIAL
```

* Now ExecutableItems <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line"> will think that any item that has the same material as the EI Item (that we just created) will be the EI Item.
* Save the \<item>.yml , go inside the game and type `/ei reload`

### Let's test it

* If we did every step fine, now we have to take a diamond\_sword from vanilla, get close to a cow, and hit it -> It should burn for 4 seconds, some particle will show up and you will recieve a message.

![](<../../../.gitbook/assets/image (245).png>)

![](<../../../.gitbook/assets/image (105).png>)

![](<../../../.gitbook/assets/image (73).png>)![](<../../../.gitbook/assets/image (181).png>)

* Tested and works ! Yup !!

{% hint style="info" %}
Any question you can ask on discord ^^

Method by Special70
{% endhint %}

