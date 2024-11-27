# Features per recipe type

The config of the recipe may have a config more than the one shown on "Recipe Configuration" and its related to its custom recipe type, here is the config and tip for each type of crafting method:

### Furnace

```yaml
furnaceConfig:
  experience: '500' #experiencePoints
  cookingTime: '50' #ticks
```

{% hint style="info" %}
For the furnace the&#x20;

```yaml
RecipeConfig:
  material: 'false' #It will always be true
```

is ignored because it is not possible to force the fuel event for items that are not registered, and they are registered as the material of the block.
{% endhint %}

{% hint style="warning" %}
The furnace conditions and commands needs an EB owner on the furnace to be used. If the furnace doesn't have an EB owner the recipe won't work. If you want the recipe to work as normal just disable furnaceRestrictions: true on config.yml
{% endhint %}
