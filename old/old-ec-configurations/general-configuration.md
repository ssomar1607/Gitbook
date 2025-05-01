# General Configuration



## Configuration of the plugin

```yaml
# ----------------------------------
# -
#       ExecutableCrafting
# -
#         By: Vayk
# -
# ----------------------------------
# -
# WIKI HERE : https://docs.ssomar.com
# DISCORD HERE : https://discord.com/invite/TRmSwJaYNv
# -
locale: EN_US
#Configuration related to recipe
recipeConfig:
  global:
    exactItemAmount: false #If you want the result only to be shown if the items match the same amount
    eventsPriority: NORMAL #In case some plugin is causing problems you can set this to NORMAL, HIGH or HIGHEST
  craftingTable:
    castResultAsMaxAmount: false #If you want the result to stack on the result slot of the crafting inventory
  furnace:
    furnaceRestrictions: true #If you want to disable the restrictions of furnace.
#Configuration related to recipe books
recipeBook:
  recipeBookNameOfID: true #If you want inside the recipe book the name of the items to be the ID, otherwise it will be the result name
  recipesInternal: true #If you want to be able to check the recipes inside recipes.
  recipesInternal_ShiftClickToRecipesInternal: true #If you want to only click the items inside of recipes to get the recipe then disable this.
  recipesInternal_checkRecipesFromInventory: false #If you want to also be able to check the recipes of the items in your inventory then enable this
  plchdLore: true #If you want to be shown if the player can craft the item or not if the plchd doesn't match
  plchdShowAll: true #If you want to be shown all conditions, or only the first one that doesn't match
#Configuration related to eAnvil
eAnvil:
  EAnvilGlobal: false #If the EAnvil can work on global anvils or can only work if its added manually
  EAnvilForgeLore: false #If the anvil should add "&fForged with <item2.name>" to item1 on anvil forge.



```

## Visual configuration of recipeBook



```yaml
#Customization of the messages that the plugin send
message:
  command:
    reloadMessage: "Recipes reloaded successfully!"
    debugActivated: "You activated the debug mode"
    debugDeactivated: "You deactivated the debug mode"
#Customization of the aspects of the recipe book
recipeBook:
  title:
    recipe: "Recipe book: %bookID% - Recipe: %recipe%"
    mainGUI: "Recipe book: %bookID% - %page%"
    folder: "Recipe book: %bookID% - %folder% - %page%"
  item:
    craftingStations:
      craftingTable:
        name: "Crafting Table"
        lore: ";;;You need this crafting;;;station to craft this;;;recipe :D"
        customModelData: "0"
        playerHead: ""
      furnace:
        name: "Furnace"
        lore: "You need this crafting;;;station to craft this;;;recipe :D"
        customModelData: "0"
        playerHead: ""
    nextPage:
      name: "Next page TEST"
      material: "ANVIL"
      customModelData: "0"
      playerHead: "eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvMzdhZWU5YTc1YmYwZGY3ODk3MTgzMDE1Y2NhMGIyYTdkNzU1YzYzMzg4ZmYwMTc1MmQ1ZjQ0MTlmYzY0NSJ9fX0"
    previousPage:
      name: "Previous page TEST"
      material: "ANVIL"
      customModelData: "0"
      playerHead: ""
    noMorePages:
      name: "No more pages TEST"
      material: "PLAYER_HEAD"
      customModelData: "0"
      playerHead: "eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvMzdhZWU5YTc1YmYwZGY3ODk3MTgzMDE1Y2NhMGIyYTdkNzU1YzYzMzg4ZmYwMTc1MmQ1ZjQ0MTlmYzY0NSJ9fX0"
    noPreviousPages:
      name: "No previous pages TEST"
      material: "RED_STAINED_GLASS_PANE"
      customModelData: "0"
      playerHead: ""
    goBack:
      name: "Go Back TEST"
      material: "ANVIL"
      customModelData: "0"
      playerHead: ""
    default:
      name: ""
      material: "BLACK_STAINED_GLASS_PANE"
      customModelData: "0"
      playerHead: ""
  plchdPositive: ";;;&eYou can craft this item ^^;;;multiple lines;;;bomb"
```
