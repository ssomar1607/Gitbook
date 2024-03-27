# Folders on /ei show



{% embed url="https://www.youtube.com/watch?ab_channel=Vayk&v=h-gkzHYPUmg" %}

## Folder management

* The folder management can only be done from the server files, it **can't be done inside game**. It is useful to manage your items in different folders and organize them.

### Create a folder

* If you would like to create folder you have to go to plugins/ExecutableItems/items/\<here> and create a folder with the name you want
* After that, just type /ei reload to reload the plugin inside Minecraft.

{% hint style="info" %}
You can add a custom item as icon folder using the next format

ThisIsTheNameOfMyFolder\[icon-GOLDEN\_SWORD]
{% endhint %}

{% hint style="info" %}
If your server host does not allow you to use special characters such as brackets, the only solution seems to be this, you can try using SFTP to create the folder instead of the file manager, there is help with setting up SFTP here: [https://support.minehut.com/hc/en-us/articles/27126955782291-How-do-I-use-SFTP-on-my-server](https://support.minehut.com/hc/en-us/articles/27126955782291-How-do-I-use-SFTP-on-my-server) assuming the server host allows you to directly access your server files through SFTP\
\
Credits: @stxrblxzer &#x20;
{% endhint %}

### Move items to a folder

* To move items inside a folder you have to create them with /ei create
* Now that we have an item ready, to move it just go to plugins/ExecutableItems/items/\<here> and take and drop an **item yml file inside the folder**
* After that, just type /ei reload to reload the plugin inside Minecraft
