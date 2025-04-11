# ⚙️ Developer API

## Add the dependency

### Manual dependency

To use the API, you need download the [SCore](https://modrinth.com/plugin/score) jar , it's my lib plugin where all the API are packaged

### Maven dependency

Place the SCore jar in your resources project

and in maven add:

```xml
<dependency>
    <groupId>com.ssomar.score</groupId>
    <artifactId>SCore</artifactId>
    <version>4.24.1.15</version>
    <scope>system</scope>
    <systemPath>${project.basedir}/src/main/resources/SCore.jar</systemPath>
</dependency>
```

### Gradle dependency

```
compileOnly files('src/main/resources/Score.jar')
```

Configure correctly your plugin.yml

```yaml
softdepend: [ExecutableItems, SCore]
```

## API Documentation

### ExecutableItemsAPI class path

`com.ssomar.score.api.executableitems.ExecutableItemsAPI`

### Check if ExecutableItems is present and loaded on the server

You can check if the server has ExecutableItems installed and enabled by using

```java
public static boolean hasExecutableItems = false;
Plugin executableItems;
if(executableItems = Bukkit.getPluginManager().getPlugin("ExecutableItems") != null && executableItems.isEnabled()) {
    SCore.plugin.getServer().getLogger().info("["+NAME+"] ExecutableItems hooked !");
    hasExecutableItems = true;
}
```



### Methods

```java
public class ExecutableItemsAPI {

    /** Get the ExecutableItems Manager **/
    public static ExecutableItemsManagerInterface getExecutableItemsManager() {
        return ExecutableItemsManager.getInstance();
    }

}
```

_The static method to have access to the manager of the ExecutableItems._



```java
public interface ExecutableItemsManagerInterface {

    /** Verify if id is a valid ExecutableItem ID
     * @param id The ID to verify
     * @return true if it is a valid ID, false otherwise
     * **/
    boolean isValidID(String id);

    /** Get an ExecutableItem from its ID
     * @param id The ID of the ExecutableItem
     * @return The ExecutableItem or an empty optional
     * **/
    Optional<ExecutableItemInterface> getExecutableItem(String id);

    /** Get an ExecutableItem from its itemStack form
     * @param itemStack The itemStack to get the ExecutableItem from
     * @return The ExecutableItem or an empty optional
     * **/
    Optional<ExecutableItemInterface> getExecutableItem(ItemStack itemStack);

    /** Get all ExecutableItems Ids
     * @return All ExecutableItems ids
     * **/
    List<String> getExecutableItemIdsList();
}
```

_The methods of the manager._



```java
public interface ExecutableItemInterface extends SObject {

    /** To place at the end of your itemBuilder , it adds infos for item to be recognized as an ExecutableItem
     * It will take the lore / name of the ExecutableItems and Override yours (But it doesn't override the customModeldata tag)
     * @param item The item to add the ExecutableItem infos to
     * @param creator The optional creator of the ExecutableItem
     * */
    ItemStack addExecutableItemInfos(ItemStack item, Optional<Player> creator);

    /**
     * @param player The player to whom you want to check the possession of the permission
     * @param showError true if you want to show an error message to the player if he doesn't have the permission
     * @return The name of the ExecutableItem */
    boolean hasItemPerm(@NotNull Player player,  boolean showError);



    /**
     * Build the ExecutableItem
     * @param amount The amount of the ExecutableItem
     * @param usage The optional custom usage of the ExecutableItem, otherwise it will use the default one
     * @param creator The optional creator of the ExecutableItem
     * @return The ExecutableItem
     */
     ItemStack buildItem(int amount, Optional<Integer> usage, Optional<Player> creator);
}
```

The methods of the ExecutableItem



### Example

```java
/** Exemple you decide to support ExecutableItems in your shop plugin **/

public void giveExecutableItem(Player player, String executableItemId, int amount){
    ItemStack item = null;
    Optional<ExecutableItemInterface> eiOpt = ExecutableItemsAPI.getExecutableItemsManager().getExecutableItem(executableItemId);
    if(eiOpt.isPresent()) item = eiOpt.get().buildItem(amount, Optional.empty(), Optional.of(player));
    if(item != null)
        player.getInventory().addItem(item);
    /* else
         Your error message here */
}
```



### Event to call when you add an ExecutableItem in a player inventory

Since SCore 3.4.7, Please when you add an ExecutableItem in a player inventory call the following event:

```java
AddItemInPlayerInventoryEvent eventToCall = new AddItemInPlayerInventoryEvent(player, itemStack, firstEmptySlot);
Bukkit.getPluginManager().callEvent(eventToCall);
```

This event is particulary usefull for one of my custom activator/trigger:  EI ENTER IN PLAYER INVENTORY.

### Questions ? Need another method ?

{% embed url="https://discord.com/invite/TRmSwJaYNv" %}
