# Recipe groups

What if you would like a group of recipes to have the same conditions or the same commands ? well, instead of adding the same thing on each recipe you can just group them in this format

In this example I will add to all recipes that starts with "bloody"



```yaml
recipeGroups:
  '1':
    recipes:
      - bloody_*
    placeholdersConditions:
      '0':
        Type: NUMBER
        part1: '%player_health%'
        comparator: INFERIOR
        part2: '10'
        recipeBook:
          itemNameIfNotMet: ''
          itemLoreIfNotMet: 'you dont know what itss like to suffer'
          itemMaterialIfNotMet: 'REDSTONE_BLOCK'
          itemCustomModelDataIfNotMet: 0
          itemPlayerHeadIfNotMet: ''
          recipeStationNameIfNotMet: ''
          recipeStationLoreIfNotMet: ''
          recipeStationMaterialIfNotMet: ''
          recipeStationCustomModelDataIfNotMet: 0
          recipeStationPlayerHeadIfNotMet: ''
```
