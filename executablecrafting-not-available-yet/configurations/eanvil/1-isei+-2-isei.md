# (1)IsEI+(2)IsEI

{% hint style="info" %}
For the explanation this information will be used

* ![](<../../../.gitbook/assets/image (1) (1) (1).png>)
* NonEI: An item that is not an ExecutableItem, it doesn't mean its vanilla, it can be whatever item with whatever nbt tag but it <mark style="color:red;">**must not be**</mark> an ExecutableItem
* IsEI: An item that is a ExecutableItem, again, it doesn't matter if it has more nbt tag or less, it can be whatever but <mark style="color:green;">**it must be**</mark> an ExecutableItem.
* (id): It refers to the position of the anvil
* \<item.(id)> It refers the item that is on the id position


{% endhint %}

## (1)IsEI+(2)IsEI

ExecutableItem works with a PublicBukkitValue, that is unique and can't be replaced, so "executableitems-id":"\<ID>" can't have two values, so it is not possible to have 2 EI ID(s) in the same EI, so why is this option ? Well, in this option what you can do is apply changes to \<item.1> using commands in \<item.2>, such as the next commands:

## Commands

{% embed url="https://youtu.be/3t999NklW5Q" %}

### Modify the EI Usage

* Info: It modifies the usage of the EI in (1) slot (\<item.1>)
* Command: EC EANVIL USAGE \<SET/MODIFICATION> \<VALUE>
* Example:

```
- EC EANVIL USAGE MODIFICATION 100
```

{% hint style="info" %}
You can add conditions adding CONDITIONS() at the end, example:

```
EC EANVIL USAGE <SET/MODIFICATION> <VALUE> CONDITIONS(%player_name%==Vayk_)
```
{% endhint %}

{% hint style="info" %}
With this you could create for example:

* An item that increases the usage so it can repair EI Items up to certain limits using on conditions %usage%
* An item that sets the usage to certain value
{% endhint %}

***

### Modify an EI Variable

* Info: It modifies the variable of the EI in (1) slot (\<item.1>)
* Command: EC EANVIL VARIABLE:\<Name of variable> \<SET/MODIFICATION> \<VALUE>
* Example:

```
- 'EC EANVIL VARIABLE:level MODIFICATION 1 CONDITIONS(%player_name%==Vayk_&&%var_level%<10)'
```

{% hint style="info" %}
With this you could create for example:

* Item that levels up your items
* Items that increases the damage of your item
  * let's say you have a variable called damagevalue and player hit activators with the command DAMAGE %var\_damagevalue%
* Item that triggers an ability
  * You can hide activators in your items, and you can toggle them using this method, for example "certain ability" that only works if "x" variable is 1, and by default is 0, you can then create an item called "Explosion arrows" that when its added to your bows their variables "x" set to 1 so now that activator works.
{% endhint %}

***

### Modify the customModelData

* ```
  EC EANVIL CUSTOMMODELDATA <SET/MODIFICATION> <VALUE>
  ```

**Explanation in todo list, but its the same idea than the previous commands, I will try to add the explanation with photos in the next days**

### Modify the lore

* Info: It modifies the usage of the EI in (1) slot (\<item.1>)
* Command: EC EANVIL LORE \<ADD/REMOVE> \<VALUES>
* Example:

<pre class="language-yaml"><code class="lang-yaml"><strong>- EC EANVIL LORE ADD This is my lore XD
</strong></code></pre>

&#x20;
