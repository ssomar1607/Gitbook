# Activators Descriptions / GIFs

### **PLAYER\_ACTIVE\_FLY:** <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player starts and stops flying.
* Example Situations:
  * `When you start flying, the activator activates. If you stop flying, the activator activates again.`

![](https://media.giphy.com/media/ctwkinfBSw1PvZsXQ9/giphy.gif)

{% hint style="info" %}
This activator will still not run even if you have the ability to fly if you haven't toggled flight by pressing the space-bar twice.
{% endhint %}

### PLAYER\_ACTIVE\_SNEAK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player starts sneaking.
* Example Situations:
  * `When you press the keyboard button to sneak, the activator activates.`

![](https://media.giphy.com/media/s4BrDGnAtLzVYBTa4P/giphy.gif)

### PLAYER\_ACTIVE\_SPRINT <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player starts sprinting.
* Example Situations:
  * `When you press the keyboard button to sprint or double-press the forward walk, the activator activates.`

![](https://media.giphy.com/media/B8buoYm3zYCM65ESSE/giphy.gif)

### PLAYER\_ALL\_CLICK

* Description: Activates when the player presses the left or right-click
* Example Situations:
  * `When you press any of the 2 buttons in your mouse (left or right click), it will run`

![](https://media.giphy.com/media/o1OceewKDsM7X43Jyt/giphy.gif)

<details>

<summary>Specifics options</summary>

**➤ In-game editing :**&#x20;

**Option Type Target:**

* **ONLYAIR**
* **ONLYBLOCK**
* **NO TYPE TARGET**

**➤ File editing:**

```yaml
onlyAirClick: false
```

```yaml
onlyBlockClick: true
```



If you have chosen BLOCKONLY you will have access to features:

* **blockCommands**, it will allow you to run command for the block clicked.
* **detailedBlocks,** the activator will work only when the type of the clicked block is in this list. (No list = All block types accepted)

```yaml
blockCommands:
 - SETBLOCK DIAMOND_BLOCK
detailedBlocks:
 - DIRT
 - SPONGE
 - STONE
```



</details>

### PLAYER\_BED\_ENTER <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player right-clicks a bed.
* Example Situations:
  * `When the player right-clicks the bed and enters the bed, the activator will activate`
  * `When the time is day and the player attempts to right-click the bed, the activator will activate even if the player didn't lay down on the bed.`

![](https://media.giphy.com/media/W1eb8XObBcrxXKNO1M/giphy.gif)

### PLAYER\_BED\_LEAVE <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player leaves the bed.
* Example Situations:
  * `When the player leaves the bed while laying in the bed, the activator will activate.`

![](https://media.giphy.com/media/IPS0CfyIqMCLOs5Bwc/giphy.gif)

### PLAYER\_BEFORE\_DEATH

* Description: Saves the player from certain death and activates.
* Example Situations:
  * `When the player is ran into multiple enemies, the ei item saves the player from certain death.`

![](https://media.giphy.com/media/4uv4jsPFcNFitcPnv2/giphy.gif)

{% hint style="success" %}
Totems activate this activator when the totems are activated
{% endhint %}

{% hint style="info" %}
This activator does not check armor protection so if your target's HP is 20 and your damage is 20 or higher, you will still trigger your target's EI item even though your target is supposed to survive.
{% endhint %}

{% hint style="info" %}
This activator is useless when using PaperSpigot (You can directly use PLAYER\_DEAT&#x48;_)_
{% endhint %}

{% hint style="warning" %}
It only works when the death is caused by mobs for the moment
{% endhint %}

### PLAYER\_BLOCK\_BREAK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player mines/breaks a block.
* Example Situations:
  * `When the player breaks some stone with a ei pickaxe, the activator will activate.`
  * `If the detailedSlot attribute is enabled on all slots, even if you are not holding the ei item, as long as you break a block, the activator will activate.`
* Options/Attributes specifically for this activator:
  * **➤ blockCommands**
  * **➤ detailedBlocks**
  * **➤ desactiveDrops**

![](https://media.giphy.com/media/HCv9F2Kbp0XbNWytEA/giphy.gif)

<details>

<summary>Specifics options</summary>

In this activator you will have access to features:

* **blockCommands**, it will allow you to run command for the block clicked.
* **detailedBlocks,** the activator will work only when the type of the clicked block is in this list. (No list = All block types accepted)
* **desactiveDrops,** to remove the drop of the block broken

```yaml
blockCommands:
 - SETBLOCK DIAMOND_BLOCK
detailedBlocks:
 - DIRT
 - SPONGE
 - STONE
desactiveDrops: true
```

</details>

### PLAYER\_BLOCK\_PLACE <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player places a block.
* Example Situations:
  * `When the player places some torch with a ei pickaxe, the activator will activate.`
  * `If the detailedSlot attribute is enabled on all slots, even if you are not holding the ei item, as long as you place a block, the activator will activate.`
* Options/Attributes specifically for this activator:
  * **➤ blockCommands**
  * **➤ detailedBlocks**

![](https://media.giphy.com/media/CyjRIsYzOEHgrj9ZwK/giphy.gif)

<details>

<summary>Specifics options</summary>

In this activator you will have access to features:

* **blockCommands**, it will allow you to run command for the block clicked.
* **detailedBlocks,** the activator will work only when the type of the clicked block is in this list. (No list = All block types accepted)

```yaml
blockCommands:
 - SETBLOCK DIAMOND_BLOCK
detailedBlocks:
 - DIRT
 - SPONGE
 - STONE
```

</details>

### PLAYER\_CHANGE\_WORLD

* Description: Activates when the player moves to a different world.
* Example Situations:
  * `When you travel from the overworld to the nether, this activator will activate.`
  * `When you travel from one multiverse to another (Multiverse Plugin), this activator will activate.`

![](https://media.giphy.com/media/GR6mvoKNdjsP9Vr44a/giphy.gif)

### PLAYER\_CLICK\_ON\_ENTITY <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player clicks on entities and Citizens NPCs.
* Example Situations:
  * `When the player hits a cow with the ei item, the activator will run.`
* Options/Attributes specifically for this activator:
  * **➤ entityCommands**
  * **➤ detailedEntities**
  * **➤ detailedClick**

![](https://media.giphy.com/media/JCVFT28vCClMbxgEGG/giphy.gif)



<details>

<summary>Specifics options</summary>

In this activator you will have access to features:

* **entityCommands**, it will allow you to run command for the clicked entity.
* **detailedEntities,** the activator will work only when the type of the clicked entity is in this list. (No list = All entity types accepted)
* **detailedClick,** Chose the click accepted for this activator
  * RIGHT
  * LEFT
  * RIGHTORLEFT

```yaml
entityCommands:
 - SETGLOW
detailedEntities:
 - ZOMBIE
 - SKELETON
 - BLAZE
detailedClick: RIGHT
```

</details>

### PLAYER\_CLICK\_ON\_PLAYER

* Description: Activates when the player click on a player.
* Example Situations:
  * `When a player left-clicks another player the activator will activate. (IT WILL NOT WORK FOR THOSE WHO ARE IN CREATIVE)`
  * `When a player right-clicks another player even in creative mode, it will activate.`
* Options/Attributes specifically for this activator:
  * **➤ targetCommands**
  * **➤ detailedClick**

![](https://media.giphy.com/media/cgQPX8UuyM3N47OW9L/giphy.gif)

<details>

<summary>Specifics options</summary>

In this activator you will have access to features:

* **targetCommands**, it will allow you to run command for the clicked player.

- **detailedClick,** Chose the click accepted for this activator
  * RIGHT
  * LEFT
  * RIGHTORLEFT

```yaml
targetCommands:
 - SENDMESSAGE Someone click on you !
detailedClick: RIGHT
```

</details>

### PLAYER\_CONNECTION <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player log into the server. (Does not activate when you log out)
* Example Situations:
  * `The player left the server and logged back on and the activator activates.`

![](https://media.giphy.com/media/ck2hQFl4CUDMZTp9Pu/giphy.gif)

### PLAYER\_CONSUME

* Description: Activates when the player successfully eat/consume the item.
* Example Situations:
  * `The player eats a steak and the activator activates`

![](https://media.giphy.com/media/s4CtBUze3s3E0RxcPr/giphy.gif)



### PLAYER\_DEATH

* Description: Activates when the player dies.
* Example Situations:
  * `When the player dies, the activator activates`.
  * `If the EI's material is a totem of undying, triggering the totem will activate the activator.`

![](https://media.giphy.com/media/fiuuSyhHE3PAN8KMRa/giphy.gif)

{% hint style="info" %}
If you want cancel the death of the player and you use Spigot, use PLAYER\_BEFORE DEATH instead of this activator.
{% endhint %}

### PLAYER\_DECONNECTION

* Description: Activates when the players disconnect from the game
* Example Situations:
  * `If you log out, the activator activates`

![](https://media.giphy.com/media/hJKC9we5xioqqzEArJ/giphy.gif)

### PLAYER\_DESACTIVE\_SNEAK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player stops sneaking.
* Example Situations:
  * `When the player presses the keyboard button to sneak, then release it, the activator activates.`

![](https://media.giphy.com/media/qbeUGeHlCYlI0s9019/giphy.gif)

####

### PLAYER\_DESACTIVE\_SPRINT <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player stops sprinting.
* Example Situations:
  * `When the player stops sprinting, the activator activates.`

![](https://media.giphy.com/media/vVQo5wNQtdsEb6gvuH/giphy.gif)

### PLAYER\_DESELECT\_THE\_EI <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates if you deselect the EI item in the hot-bar.
* Example Situations:
  * `When the player deselects the item, the activator activates.`

![](https://media.giphy.com/media/7xxhSVj3mrie8GaG3t/giphy.gif)

### PLAYER\_DISMOUNT

* Description: Activates when the player dismounts from any entity
* Example Situations:
  * If you go down from riding a pig with a saddle, the activator activates

![](https://media.giphy.com/media/d7fNu5YkFkb3skF7sj/giphy.gif)

### PLAYER\_DROP\_ITEM

* Description: Activates when the player drops an item. It will activate as long as you drop any item
* Example Situations:
  * `If you drop any item as long as the ei item is present in your inventory, the activator will activate`

![](https://media.giphy.com/media/xE1FdAsWyIGktQL1gZ/giphy.gif?cid=790b761135e83e9f9ce6349c457ceeb19759221a00e6ffd5\&rid=giphy.gif\&ct=g)



### PLAYER\_DROP\_THE\_EI <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player drops the EI item.
* Example Situations:
  * `When you drop the EI item even in any slot, it will activate.`

![](https://media.giphy.com/media/JiNL7d9IGEuofEiFTa/giphy.gif?cid=790b7611aa84ec9d384b1cd0015cf8ae1435f8bc97d7a458\&rid=giphy.gif\&ct=g)



### PLAYER\_EDIT\_BOOK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player made changes to the book and quill and pressed done or sign the book.
* Example Situations:
  * `If the player writes anything in the book and presses done, the activator activates.`
  * `If the player writes anything in the book and signs it, the activator activates.`
  * `If the player writes anything and does not press done, the activator will not activate.`

![](https://media.giphy.com/media/MlUDKn2z5ARxLmbuAl/giphy.gif)



### PLAYER\_EI\_BREAK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player breaks the executableItem by making it loose all its durability.

![](https://media.giphy.com/media/0BHA8GLRCEfOdg55JH/giphy.gif)

### PLAYER\_EQUIP\_THE\_EI <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates if the layer puts the armor-piece in the armor slot or when using the HEAD custom command
* Example Situations:
  * `If you place the EI item in your head slot manually, the activator activates.`
  * `If you try using the HEAD command to put the item in the head slot, the activator activates.`

![](https://media.giphy.com/media/JGvUqBGForRUXnelMa/giphy.gif?cid=790b7611ba0b7cba0686c4f38cc893b4a923dde8dfdb3378\&rid=giphy.gif\&ct=g)

{% hint style="danger" %}
A Fabric addon can bypass the the setting cancelEvent, so even if you have it on true, the player can potentialy equip the EI.
{% endhint %}



### PLAYER\_ENTER\_IN\_HIS\_PLOT <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates if the player enters their plot
*   Example Situations:

    * `If you enter your plot, the activator activates.`



![](https://media.giphy.com/media/0CCTX2IpqmidYQzmp7/giphy.gif)



### PLAYER\_FERTILIZE\_BLOCK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

{% hint style="danger" %}
Not compatible with the 1.12 version
{% endhint %}

* Description: Activates if the player fertilizes blocks with bone meal
* Example Situations:
  * `If you try to speed up sapling growth by right clicking the sapling, the activator activates.`
  * `If you try to bone meal grass blocks to spawn grass.`

![](https://media.giphy.com/media/k3Ty96Jsd0ykoBpFTx/giphy-downsized-large.gif?cid=790b76115c50ad460a729e72dc4c1e31083d3192a8fb8c50\&rid=giphy-downsized-large.gif\&ct=g)

### PLAYER\_FILL\_BUCKET

* Description: Activates when the player attempts to pickup water or lava with a bucket.
* Example Situations:
  * `When the person attempts to pickup the water in creative, the activator activates.`
  * `When the player attempts to pickup the water even if cancelEvent is set to true, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ blockCommands**
  * **➤ detailedBlocks**
* **NOTE**
  * **IN THE GIF, YOU WILL SEE THE 2ND TIME THE PLAYER PICKS UP WATER WITH THE BUCKET, NO MESSAGE APPEARS BECAUSE WHEN THE EI PICKS UP WATER USING A BUCKET, IT TURNS INTO A VANILLA WATER BUCKET. PLACING DOWN THE WATER FROM THE BUCKET WILL JUST REVERT IT BACK TO A VANILLA BUCKET.**

![](https://media.giphy.com/media/6ckobMcUqVTTCZMKQX/giphy.gif)

### PLAYER\_FISH\_BLOCK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* **(NOT COMPATIBLE WITH VERSION 1.12)**
* Description: Activates when the player right-clicks the fishing rod when the fishing rod bobber is on top of a block.
* Example Situations:
  * `When the fishing bobber is on top of a block and the player right-clicks the rod, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ blockCommands**
  * **➤ detailedBlocks**

![](https://media.giphy.com/media/c33cyblJgVJfzFjZCx/giphy.gif)

### PLAYER\_FISH\_ENTITY <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player right-clicks the fishing rod when the fishing rod bobber is on an entity or on a Citizens NPC.
* Example Situations:
  * `When the fishing bobber is on an entity and the player right-clicks the rod, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ entityCommands**
  * **➤ detailedEntities**

![](https://media.giphy.com/media/Qqndlf4ntDmh9SNmtN/giphy.gif)

### PLAYER\_FISH\_FISH <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player right-clicks the fishing rod when the fishing rod bobber catches something.
* Example Situations:
  * `When the fishing bobber catches something (extra splashes and the bobber sinks a bit), the player right-clicks the rod and the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ desactiveDrops**

![](https://media.giphy.com/media/zaXG1kATOJMuKHRHBY/giphy.gif)

### PLAYER\_FISH\_NOTHING <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player fishes nothing.
* Example Situations:
  * `When the fishing bobber is on a player and the player right-clicks the rod, the activator will not activate.`
  * `When the fishing bobber has yet to hold onto something and the player right-clicks to retract the bober, the activator activates.`

![](https://media.giphy.com/media/5e43GXF608b5Wnfmn8/giphy.gif)

### PLAYER\_FISH\_PLAYER <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player right-clicks the fishing rod when the fishing rod bobber is on a player.
* Example Situations:
  * `When the fishing bobber is on a player and the player right-clicks the rod, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ targetCommands**
  * **➤ detailedClick**

![](https://media.giphy.com/media/zcR5QLlRPYWiXt7uGR/giphy.gif)

### PLAYER\_HIT\_ENTITY <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player hits an entity.
* Example Situations:
  * If the entity received damage because the hit landed, the activator runs
  * If the entity didn't receive hits because it has the invulnerable nbt, the activator will not run
    * HOWEVER, if you are in creative, you can hit invulnerable mobs, making the activator run

<figure><img src="https://media.giphy.com/media/GaY56vFp2nToLDuQt1/giphy.gif" alt=""><figcaption></figcaption></figure>

### PLAYER\_HIT\_PLAYER&#x20;

* Description: Activates when the player hits a player.
* Example Situations:
  * If the hits manages to land, causing the player target to take damage, the activator runs
  * If the player attempts to hit its target on a region where pvp is disabled, the activator will not run
  * If the player attempts to hit its target even though the target's in creative, the activator will not run
  * Options/Attributes specifically for this activator:
    * **➤ targetCommands**
    * **➤ detailedClick**

<figure><img src="https://media.giphy.com/media/GMgOG2isxTRkzH6JGx/giphy.gif" alt=""><figcaption></figcaption></figure>

### PLAYER\_ITEM\_BREAK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player breaks the item by making it loose all its durability.
* Example Situations:
  * `When the player uses the diamond pickaxe and making the pickaxe loose all of its durability and break, the activator activates.`

![](https://media.giphy.com/media/0BHA8GLRCEfOdg55JH/giphy.gif)

### PLAYER\_JUMP <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player jumps.
* Example Situations:
  * `When the player auto-jumps, the activator will still activate because in the end, the player jumped.`

![](https://media.giphy.com/media/Me4dfTEKd3itkEdtHP/giphy.gif)

{% hint style="info" %}
In 1.21.2+, it's now possible for it to trigger even if the player attempted to jump mid-air
{% endhint %}

### PLAYER\_KILL\_ENTITY <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player kills an entity or a Citizens NPC.
* Example Situations:
  * `When the player kills a cow with an enchanted diamond sword, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ entityCommands**
  * **➤ detailedEntities**
  * **➤ desactiveDrops**

![](https://media.giphy.com/media/EETpl8jD3XCv0fweLU/giphy.gif)

{% hint style="info" %}
This activator gets triggered when you kill mobs using the MOB\_AROUND + DAMAGE ei cmd. Same goes to using MOB\_AROUND + DAMAGE on mobCommands
{% endhint %}

### PLAYER\_KILL\_PLAYER <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player kills a player.
* Example Situations:
  * `When the player kills another player with an enchanted diamond sword, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ targetCommands**
  * **➤ detailedClick**
  * **➤ desactiveDrops**

![](https://media.giphy.com/media/qVYAHA2HT4ZgzVv0Rs/giphy.gif)

### PLAYER\_LAUNCH\_PROJECTILE

* Description: Activates when the player shoots a projectile.
* Example Situations:
  * `When the player throws a snowball, the activator activates.`
  * `If the player shoots an arrow with a bow, the activator activates.`

![](https://media.giphy.com/media/JIPh5gZBCCBEjt4NCj/giphy.gif)

{% hint style="danger" %}
Keep in mind that if you use this activator in a trident, the trident will be practically thrown **BUT** the trident will retain, duping the tridents.
{% endhint %}

{% hint style="info" %}
For example, you have 2 `PLAYER_LAUNCH_PROJECTILE` activators, the last/bottom one in the config will always be superior to who decides if the event is cancelled or not
{% endhint %}

####

### PLAYER\_LEAVE\_HIS\_PLOT <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates if the player leaves their plot
* Example Situations:
  * `If you leave your plot, the activator activates.`

![](https://media.giphy.com/media/IflJn4tYkJv7DYrYlU/giphy.gif)

### PLAYER\_LEFT\_CLICK

* Description: Activates when the player left-clicks the item.
* Example Situations:
  * `When the person presses the left-click button of the mouse, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ onlyAirClick**
  * **➤ onlyBlockClick**
  * **➤ blockCommands**
    * **(IT WILL ONLY APPEAR IN THE GUI IF YOU SELECT THE TYPE TARGET TO ONLY BLOCK IN THE TYPE TARGET IN THE GUI)**
  * **➤ detailedBlocks**
    * **(IT WILL ONLY APPEAR IN THE GUI IF YOU SELECT THE TYPE TARGET TO ONLY BLOCK IN THE TYPE TARGET IN THE GUI)**

![](https://media.giphy.com/media/BffMUxpU9bD1ZSokhl/giphy.gif)

### PLAYER\_WALK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player walks.
* Example Situations:
  * `When the person walks, the activator activates.`

![](https://media.giphy.com/media/NddMRUpEnRf8U2p6Aj/giphy.gif)

{% hint style="warning" %}
The activator in the GIF has a cool down of 1. If the activator doest have cooldown, it will be runned every tick if the player is moving. So becareful with that !
{% endhint %}

### PLAYER\_WRITE\_COMMAND <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player enters commands
* Example Situations:
  * `When the player writes a command, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ detailedCommands** **REQUIRED FOR IT TO WORK**

![](https://media.giphy.com/media/dIfxVKQnihDrpsQIKB/giphy.gif)

{% hint style="info" %}
Enabling cancelEvent prevents the "unknown command" message from showing up when the activator activates
{% endhint %}

### PLAYER\_RECEIVE\_HIT\_BY\_ENTITY <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player gets hit by anything from an entity or a Citizens NPC.
* Example Situations:
  * `When the player gets hit by the husk, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ detailedDamageCauses**

![](https://media.giphy.com/media/f34xjFcfeVTdvLKWNX/giphy.gif)

{% hint style="success" %}
If the entity is a projectile, you can use the projectile placeholders in the activator. Check the example below:
{% endhint %}

```yaml
# This config allow to run custom things if the player receive 
# an hit by a custom EI projectile, in this example the custom projectile
# is named 'ak'
activator3:
    activator: PLAYER_RECEIVE_HIT_BY_ENTITY
    displayName: Activator name
    usageModification: 0
    usePerDay: -1
    cancelEventIfMaxUsePerDay: false
    autoUpdateItem: false
    commands:
    - 'SENDMESSAGE §6You received a projectile named &eak'
    conditions:
      placeholdersConditions:
        plchC1:
          type: PLAYER_STRING
          part1: '%projectile_name%'
          comparator: EQUALS
          messageIfNotValid: '&e'
          cancelEventIfNotValid: false
          part2: ak
    silenceOutput: false
    entityCommands: []
    entity:
     - PROJECTILE
    cancelEventIfInvalidRequiredExecutableItems: false
    cancelEvent: false
    detailedSlots: []
```

### PLAYER\_RECEIVE\_HIT\_BY\_PLAYER <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player gets hit by anything from a player.
* Example Situations:
  * `When the player gets hit by another player, the activator activates`.
* Options/Attributes specifically for this activator:
  * **➤ detailedDamageCauses**

![](https://media.giphy.com/media/TzPkHN5IQ3CKPFmdmy/giphy.gif)

### PLAYER\_RECEIVE\_HIT\_GLOBAL <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player gets hit by something.
* Example Situations:
  * `When the player gets damaged by hugging a cactus, the activator activates.`
*   Options/Attributes specifically for this activator:

    * **➤ detailedDamageCauses**



{% embed url="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html" %}



![](https://media.giphy.com/media/i5vqcu2y5Mow3uZWTy/giphy.gif)

####

### PLAYER\_RESPAWN <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player respawns.
* Example Situations:
  * `When the player kills himself/herself via /kill command and respawns, the activator runs.`
* **NOTE: THE ITEM MUST STAY IN THE INVENTORY WHEN THE PLAYER DIES AND RESPAWN. IF THE PLAYER LOOSES THE ITEM WHEN DYING, THE ACTIVATOR WILL NOT ACTIVATE.**

![](https://media.giphy.com/media/UdDTlLovqj6AHXrUfa/giphy.gif)

### PLAYER\_RIGHT\_CLICK

* Description: Activates when the player right-clicks the item.
* Example Situations:
  * `When the person presses the right-click button of the mouse to use the shield, the activator activated.`
* Options/Attributes specifically for this activator:
  * **➤ onlyAirClick**
  * **➤ onlyBlockClick**
  * **➤ blockCommands**
    * **(IT WILL ONLY APPEAR IN THE GUI IF YOU SELECT THE TYPE TARGET TO ONLY BLOCK IN THE TYPE TARGET IN THE GUI)**
  * **➤ detailedBlocks**
    * **(IT WILL ONLY APPEAR IN THE GUI IF YOU SELECT THE TYPE TARGET TO ONLY BLOCK IN THE TYPE TARGET IN THE GUI)**

![](https://media.giphy.com/media/PXs3B2wPqB6VMIWnIm/giphy.gif)

{% hint style="info" %}
If the type of target is ONLY\_AIR you MUST HAVE AN ITEM ON YOUR HAND OR THE ACTIVATOR IS NOT REGISTERED BY SPIGOT. (It can't be fixed by our side)
{% endhint %}

### PLAYER\_SELECT\_THE\_EI <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates if you select the EI item in the hotbar.
* Example Situations:
  * `The player scrolls through the hotbar and selects the EI item then the activator activates.`

![](https://media.giphy.com/media/fOdNa4wclGRBtNF5nU/giphy.gif)

### PLAYER\_TARGETED\_BY\_AN\_ENTITY <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when an entity sets it's sights and targets you
* Example Situations:
  * When you roam around your world and a random zombie sees you and decides to fight you, the activator activates

<figure><img src="https://media.giphy.com/media/DOqXRqYNwjkn7yYTQF/giphy.gif" alt=""><figcaption></figcaption></figure>

* Options/Attributes specifically for this activator:
  * **➤ entityCommands**
  * **➤ detailedEntities**

### PLAYER\_TRAMPLE\_CROP

* Description: Activates when the player tramples a crop
* Example Situations:
  * When you are in your Minecraft garden, and jump above a wheat, it gets trample after falling equals the activator gets activated.
  *   When you managed to successfully destroy the farmland after 1 or more jumps, the activator runs\


      <figure><img src="https://media.giphy.com/media/XpnXZxk6Wo0ZNxOqDa/giphy-downsized-large.gif" alt=""><figcaption></figcaption></figure>
* Options/Attributes specifically for this activator:
  * **➤detailedBlocks**

### PLAYER\_SHEAR\_ENTITY <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player shears an entity.
* Example Situations:
  * `The player right-clicks the sheep and the mushroom with the shears to shear them and the activator activates.`

![](https://media.giphy.com/media/wd7fqctyHhUFYNfQAg/giphy.gif)

### PLAYER\_UNEQUIP\_THE\_EI <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates if you un-equip the EI.
* Example Situations:
  * `The player takes off the EI armor from the armorslot and the activator activates.`

![](https://media.giphy.com/media/mtXdexOt5uiz1BwxW5/giphy.gif)

### PROJECTILE\_ENTER\_LIQUID <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates if the launched projectile enters and stays long enough in water
* Example Situations:
  * If you try to throw the snowball into a shallow water, the activator will not run
  * If you try to throw your projectile to lava, the activator will not run
  * If you throw a snowball into the ocean, the activator will run after under a second.
  * If you throw 5 snowballs into the air and enters the ocean almost in the same time, the activator will run 5 times instantly.



### PROJECTILE\_HIT\_BLOCK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the projectile of the player hits a block.
* Example Situations:
  * `When the player throws the snowball and it hits a block, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ detailedBlocks**
  * **➤ blockCommands**

![](https://media.giphy.com/media/hrsXAyMqeWnoBdZV2M/giphy.gif)

### PROJECTILE\_HIT\_ENTITY <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the projectile of the player hits an entity or a Citizens NPC.
* Example Situations:
  * `When the player throws the snowball and it hits a cow, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ detailedEntities**
  * **➤ entityCommands**

![](https://media.giphy.com/media/YreIrUif7Ihqu3b36z/giphy.gif)

### PROJECTILE\_HIT\_PLAYER

* Description: Activates when the projectile of the player hits a player.
* Example Situations:
  * `When the player throws the snowball and it hits a player, the activator activates.`
* Options/Attributes specifically for this activator:
  * **➤ targetCommands**

![](https://media.giphy.com/media/eALgBrxemIz8SFFIdW/giphy.gif)

### INVENTORY\_CLICK <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates when the player clicks the item in its inventory.
* Example Situations:
  * `When you click the dirt in your inventory, the activator activates.`
  * `When you wear the EI boots and pressed the drop button, the activator activates.` **(detailedClick MUST BE RIGHTORLEFT)**.
* Options/Attributes specifically for this activator:
  * **➤ detailedClick**
* **NOTE: IT WILL ONLY WORK AT SURVIVAL.**

![](https://media.giphy.com/media/4ZcTvcvkP3JfOVdlcE/giphy.gif)

### LOOP <img src="../../../.gitbook/assets/Executable Items Color3.png" alt="" data-size="line">

* Description: Activates in repeat as long as the item is in the player's inventory.
* Example Situations:
  * `When you keep the item in your inventory, the activator will run in repeat.`
* Options/Attributes specifically for this activator:
  * **➤ delay**
  * **➤ delayTick**

![](https://media.giphy.com/media/OMqQHUWog9KfS6fnl5/giphy.gif)
