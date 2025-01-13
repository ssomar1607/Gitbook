# Recipe Configuration

### Type

* Its the type of crafting station of the recipe
* Example:

```yaml
Type: FURNACE
```

### typeOfBlock

* Its the configuration for the type of block that the recipe block must be



| typeOfBlock | Description                                                                                                                                                                           | Example                                                                                            |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| all         | If you want the recipe to work on all possible recipe stations.                                                                                                                       | My crafting recipe will work on all crafting tables.                                               |
| vanilla     | If you want the recipe to only work on vanilla crafting tables.                                                                                                                       | My crafting recipe will only work on vanilla crafting table and not in EB blocks.                  |
| EB:\<ID>    | <p>If you want the recipe to work on a specific EB <br><br>If you want to add more than one EB id instead of using this you can use placeholders conditions and use %block_eb_id%</p> | My crafting recipe will only work on the EB called "epicCrafting" so I will write EB:epicCrafting. |

### Recipe

* Its the configuration of each item of the recipe, it divides up to 9 items depending on the crafting station
* Example:

```yaml
Recipe:
  item1:
    NBT: '{components:{"minecraft:custom_name":''"pepardo"''},count:1,id:"minecraft:crafting_table"}'
    material: CRAFTING_TABLE
    amount: 1
    durability: 0
    displayName: pepardo
    ExecutableItemsID: ''
```

### Result

* Its the configuration of the result item of the recipe
* Example:

```yaml
Result:
  material: SOUL_LANTERN
  amount: 1
  durability: 0
  NBT: '{count:1,id:"minecraft:soul_lantern"}'
  ExecutableItemsID: ''
```

### Commands

* Here is the list of commands that are run after the player made the recipe
* Example:

```yaml
Commands:
- say hi
```

### RecipeConfig

* Here you can apply the configuration of how strict the recipe will be
* Example:

```yaml
RecipeConfig:
  nbt: 'false' #If you want the items of the recipe must MATCH THE SAME NBT
  name: 'false' #If you care about the name of the recipe
  material: 'true' #If you care about the material of the recipe
  customModelData: 'false' #So on..
  lore: 'false'
  durability: 'false'
  ExecutableItemsID: 'true'
```

{% hint style="info" %}
For example ! If you just want the recipe to match the ExecutableItem ID of the recipe item you created, and you don't care if the player changes the name, if the lore is different, anything, you said "I just want that the item input of this recipe must be the EI, the other stuff I don't care" you only enable "ExecutableItemsID" and disable everything else
{% endhint %}

### placeholdersConditions

* Here you can set up placeholders conditions. If they don't match the result won't be shown.
* Example:

```yaml
placeholdersConditions:
  '0': #The condition that the recipe will only work with low health
    Type: NUMBER
    part1: '%player_health%'
    comparator: INFERIOR
    part2: '10'
    recipeBook:
      itemNameIfNotMet: ''
      itemLoreIfNotMet: 'you dont know what its like to suffer'
      itemMaterialIfNotMet: 'REDSTONE_BLOCK'
      itemCustomModelDataIfNotMet: 0
      itemPlayerHeadIfNotMet: ''
      recipeStationNameIfNotMet: ''
      recipeStationLoreIfNotMet: ''
      recipeStationMaterialIfNotMet: ''
      recipeStationCustomModelDataIfNotMet: 0
      recipeStationPlayerHeadIfNotMet: ''
  '1': #The condition that this recipe will only work in those specifics EB(s)
    Type: STRING
    part1: '%block_eb_id%'
    comparator: EQUALS
    part2: 'furnaceCommon<OR>furnaceEpic<OR>furnaceLegendary'
    recipeBook:
      itemNameIfNotMet: ''
      itemLoreIfNotMet: ''
      itemMaterialIfNotMet: ''
      itemCustomModelDataIfNotMet: 0
      itemPlayerHeadIfNotMet: ''
      recipeStationNameIfNotMet: ''
      recipeStationLoreIfNotMet: 'It will work on all types;;;of recipe stations'
      recipeStationMaterialIfNotMet: ''
      recipeStationCustomModelDataIfNotMet: 0
      recipeStationPlayerHeadIfNotMet: ''
```

{% hint style="info" %}
Here you can add luck perms conditions and show different results for the same recipe depending on the group they are. For example for default users a normal sword but for vip users a epic sword.
{% endhint %}

| Placeholder     | Description                                                                                                                                                   | Example                                                                                                                                              |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| %block\_eb\_is% | It checks if the current block of the recipe is a Executable Block.                                                                                           | <p>For example having a furnace recipe, it will check if the block of furnace is an eb or not, it will return<br>- true<br>- false</p>               |
| %block\_eb\_id% | <p>It checks if the current block of the recipe is an ExecutableBlock and it returns the id of it.<br><br>If the block is not an eb it will return "null"</p> | Having a tier of furnaces, you only want the recipe to work on the EB furnace called "LegendaryFurnace" then you use PLAYER\_STRING to achieve this. |
|                 |                                                                                                                                                               |                                                                                                                                                      |
|                 |                                                                                                                                                               |                                                                                                                                                      |

