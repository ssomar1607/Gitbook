# General Configuration

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
#Configuration related to eAnvil
eAnvil:
  EAnvilGlobal: false #If the EAnvil can work on global anvils or can only work if its added manually
  EAnvilForgeLore: false #If the anvil should add "&fForged with <item2.name>" to item1 on anvil forge.



```
