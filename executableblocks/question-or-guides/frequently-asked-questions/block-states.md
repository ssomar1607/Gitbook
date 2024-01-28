# Block states

## <mark style="color:orange;">**This is not the best way, but for now its an option if you REALLY need it.**</mark>



If you'd like your EB to have a specific state, for example:

* A Lit lamp
* A Trapdoor in a specific position or looking into a specific direction
* A custom note block
* A lit furnace
* etc

You have to create your EB, set the things you want, etc and then create an activator PLAYER\_PLACE

![](<../../../.gitbook/assets/image (289).png>)

After that, go to commands and add a setblock command, in my case I want to setblock a **lit furnace**, so the setblock command will refeer to that block.

```
execute at %player% run setblock %block_x_int% %block_y_int% %block_z_int% furnace[lit=true]
```

{% hint style="info" %}
Its a normal setblock command, if don't know how it works you should take a look at "how to use vanilla commands"
{% endhint %}

{% hint style="info" %}
The example is placing a lit furnace, to place another stuff the block will have different nbt, you can check them in [https://minecraft.fandom.com/wiki/Tutorials/Command\_NBT\_tags](https://minecraft.fandom.com/wiki/Tutorials/Command\_NBT\_tags)
{% endhint %}

So once I place it, even though in my inventory it looks like a normal furnace

![](<../../../.gitbook/assets/image (277).png>)

Once I place it, it looks like:

![](<../../../.gitbook/assets/image (347).png>)

And that's it, the idea is ready, now there are some problems that we will tell you below.



<mark style="color:red;">**Now, actually it only has one problem, the direction, right now it doesn't keep the direction, so you'll need to create 4 activators using direction conditions to place it correctly.**</mark>

