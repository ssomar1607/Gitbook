# Recipe Configuration

### Type

* Its the type of crafting station of the recipe
* Example:

```yaml
Type: FURNACE
```

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
  '0':
    Type: STRING
    part1: '%player_name%'
    comparator: EQUALS
    part2: Vayk_
```
