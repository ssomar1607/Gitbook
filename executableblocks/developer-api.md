# ⚙ Developer API

## Add the dependency

### Manual dependency

To use the API, you need download the ExecutableBlocks jar (given when you download ExecutableBlocks on Spigot)

{% embed url="https://www.spigotmc.org/resources/custom-blocks-free-executable-blocks-1-14-1-18.93406" %}

### Maven dependency

<pre><code>&#x3C;dependency>
<strong>    &#x3C;groupId>com.ssomar.executableblocks&#x3C;/groupId>
</strong>    &#x3C;artifactId>ExecutableBlocks&#x3C;/artifactId>
    &#x3C;version>X.X.X&#x3C;/version>
    &#x3C;scope>system&#x3C;/scope>
    &#x3C;systemPath>${project.basedir}/src/main/resources/ExecutableBlocks.jar&#x3C;/systemPath>
&#x3C;/dependency>
</code></pre>

### Configure correctly your plugin.yml

```yaml
softdepend: [ExecutableBlocks, SCore]
```

## API Documentation

### ExecutableBlocksAPI class path

`com.ssomar.executableblocks.api.ExecutableBlocksAPI`

### Check if ExecutableItems is present and loaded on the server

You can check if the server has ExecutableItems installed and enabled by using

```java
public static boolean hasExecutableBlocks = false;
Plugin executableBlocks;
if(executableBlocks = Bukkit.getPluginManager().getPlugin("ExecutableBlocks") != null && executableBlocks.isEnabled()) {
    SCore.plugin.getServer().getLogger().info("["+NAME+"] ExecutableBlocks hooked !");
    hasExecutableBlocks = true;
}
```



### Methods

```java
public class ExecutableBlocksAPI {

     /**
     * Get the ExecutableBlocks Manager,
     * It allows you to get / retrieve the ExecutableBlocks Configurations
     **/
    public static ExecutableBlocksManager getExecutableBlocksManager() {
        return ExecutableBlocksManager.getInstance();
    }

    /**
     * Get the ExecutableBlocksPlaced Manager,
     * It allows you to get / retrieve the ExecutableBlocks Placed
     **/
    public static ExecutableBlocksPlacedManager getExecutableBlocksPlacedManager() {
        return ExecutableBlocksPlacedManager.getInstance();
    }


    /**
     * Get the ExecutableBlockObject
     * It allows you to get / retrieve the ExecutableBlocks Configurations under its item form
     **/
    public static ExecutableBlockObject getExecutableBlockObject(ItemStack itemStack) {
        return new ExecutableBlockObject(itemStack);
    }
}
```

_The static method to have access to the managers of the ExecutableBlocks and the ExecutableBlockPlaced._

### Examples

```java
/** Example you decide to support ExecutableBlocks in world generation plugin **/

public void placeExecutableBlock(String executableBlockId, Location location){
        Optional<ExecutableBlock> ebOpt = ExecutableBlocksAPI.getExecutableBlocksManager().getExecutableBlock(executableBlockId);
        ebOpt.ifPresent(executableBlock -> executableBlock.place(location, true, OverrideEBP.REMOVE_EXISTING_EBP, null, null, null));
}
```



### Questions ? Need another method ?

{% embed url="https://discord.com/invite/TRmSwJaYNv" %}
