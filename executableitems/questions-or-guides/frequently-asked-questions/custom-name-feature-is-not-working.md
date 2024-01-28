# Custom name feature is not working

If you enabled&#x20;

```
dropOptions:
  displayNameDrop: true
```

and the displayNameDrop is **not** showing as this

<figure><img src="../../../.gitbook/assets/image (304).png" alt=""><figcaption></figcaption></figure>

It may be because one of your plugins.

### WildStacker

Right now we know that Wildstacker causes problems with this feature. To fix that in their case you have to blacklist the item on their config

```
  # Material list: https://bg-software.com/materials/
  # Make sure you follow the "TYPE" and "TYPE:DATA" formats.
  # If you wish to disable blacklisted items, use "blacklist: []"
  blacklist: 
```

