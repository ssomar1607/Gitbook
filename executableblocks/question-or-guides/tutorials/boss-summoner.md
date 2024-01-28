# Boss summoner

Here you will learn how to create a block that summons a boss, has a cooldown, it is displayed on top of the block, and you can't spawn 2 bosses at the same time, let's do it !!

* First create your eb with /eb create \<id>
  * ![](<../../../.gitbook/assets/image (284).png>)
* Then edit the block you would want the spawner to be, in this case it will be a bedrock.
  * ![](<../../../.gitbook/assets/image (99).png>)
* Now, llet's create a timer action following the steps explained on the methods section of EB.
* Once we have everything done, the trigger for the method will be RIGHT CLICK, so when you summon the boss you will need to wait "x" time to summon another again.
* ![](<../../../.gitbook/assets/image (288).png>)
* Just follow the steps and the only thing you have to change is the command, where according to what is said on [Compatible Plugins](../../../tools-for-all-plugins-score/compatible-plugins.md) would be something like this:
  * ```
    mm m spawn (mob_id) 1 %block_world%,%block_x%,%block_y%+1,%block_z%
    ```

Finally it would look like this:

<figure><img src="../../../.gitbook/assets/2023-01-16 16-50-55.gif" alt=""><figcaption></figcaption></figure>

