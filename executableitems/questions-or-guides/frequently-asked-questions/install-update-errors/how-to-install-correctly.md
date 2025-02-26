# How to install correctly

### Introduction

Here you can see a resume of specs you need to know when downloading the plugin and what you have to do, if you already knew and did all the things here and still having an error, please contact us on Discord and we'll help you.

### Type of server

* First of all keep in mind that the plugin is a spigot coded plugin, so it needs a server based on it, such as:
  * Spigot
  * Paper
  * Purpur
  * Etc (Any fork of spigot)

{% hint style="danger" %}
For example, Bukkit isn't compatible, it has to be BukkitSpigot.
{% endhint %}

### Type of hosting

* The hosting must allow the owner to import files, if the host doesn't allow that, such as using only the plugins available in a list of the hosting, ExecutableItems can't be used.

{% hint style="danger" %}
There are Hostings that allows you to install quickly some plugins that are downloaded in their clouds, in the case of ExecutableItems don't use them, most of them don't work properly, its better to install it with the normal method of importing files.
{% endhint %}

### Versions of Minecraft

* These are the versions supported by ExecutableItems.
  * Free version from 1.12.2 to 1.21.4+
  * Premium version from 1.8 to 1.21.4+
* &#x20;(More information in [<mark style="color:blue;">MC Versions Compatibility</mark>](../../../mc-versions-compatibility.md))

{% hint style="info" %}
In case you are using a version between **1.8** and **1.12.2** you need to have installed NBTAPI.
{% endhint %}

### Correct way of installing

1. Download the plugin (Links are available on the page bellow)

{% content-ref url="../../../information-ei.md" %}
[information-ei.md](../../../information-ei.md)
{% endcontent-ref %}

{% tabs %}
{% tab title="You get .jar" %}
* If you only get ExecutableItems.jar, you will need to download also the SCore jar (our lib plugin). You can find it on [Modrinth ](https://modrinth.com/plugin/score)
* Pick up both **plugins jar** and drag them into plugins folder.
{% endtab %}

{% tab title="You get a .zip" %}
* You get a file .zip (this is like a folder, you have to open it using Winrar)
* You open it and you see that there are 2 files inside, **ExecutableItems.jar** and **Score.jar**, <mark style="color:green;">**both of them are needed**</mark>
* Pick up both **plugins jar** and drag them into plugins folder. (the zip is nothing so don't drag that file into plugins folder, you only need the two plugins inside the jar)

{% hint style="warning" %}
If its the case you are using a webpage host server, it is <mark style="color:green;">**highly recommended**</mark> to <mark style="color:red;">**don't drop it instantly into plugins folder**</mark>, but, drag them first into desktop and once they are in your desktop, drag them into plugins folder.
{% endhint %}
{% endtab %}
{% endtabs %}

Once done, you can start your server.

{% hint style="info" %}
It is highly suggested to install it with a reload of the server (stop+start) and not with plugins managers.
{% endhint %}

### Special cases

* If its the case you have ExecutableItems or ExecutableBlocks in your server, once downloading one you should update the current one.
  * For example, I want to install ExecutableItems, while doing, I should update ExecutableBlocks too.

{% hint style="info" %}
This is just for keep both plugins in the same versions (otherwise it can bring problems)
{% endhint %}

### Still not working

* In case you got all the information said before, doing the right things and the plugin still not working, feel free to ask in the Discord and we will help you.

{% hint style="info" %}
Also what you can do, that is something that have fixed some problems on people's threads related to the plugin not working, is downloading the plugin again and installing it again. It is weird, it is not our fault, but sometimes just doing the steps again fixes it, nobody knows why, its like a law of life, you could give it a try :P
{% endhint %}
