# How to update correctly

This tutorial will be made assuming you already have the plugin on your server following the instructions in How to install correctly and now you want to update it but don't know how.

* Stop the server
* Go to spigot and download the last version. Both links in the link below.

{% content-ref url="../../../information-ei.md" %}
[information-ei.md](../../../information-ei.md)
{% endcontent-ref %}

* Go to your server files / plugins / and delete <mark style="color:orange;">ExecutableItems</mark>.jar and <mark style="color:orange;">Score</mark>.jar (old ones).
* Then, inside the file downloaded from spigot you will have two files <mark style="color:blue;">ExecutableItems</mark>.jar and <mark style="color:blue;">Score</mark>.jar (new ones), drag both of them into the plugins folder.&#x20;
* Start your server.

{% hint style="warning" %}
If its the case you are using a webpage host server, it is <mark style="color:green;">**highly recommended**</mark> to <mark style="color:red;">**don't drop it instantly into plugins folder**</mark>, but, drag them first into desktop and once they are in your desktop, drag them into plugins folder.
{% endhint %}

### Special case

* If its the case you have ExecutableItems or ExecutableBlocks in your server and you want to update one of them, you should update both.
  * For example, I want to update ExecutableItems, while doing, I should update ExecutableBlocks too.

{% hint style="info" %}
This is just for keep both plugins in the same versions (otherwise it can bring problems)
{% endhint %}

