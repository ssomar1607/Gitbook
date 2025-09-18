# General config

```yaml
locale: EN # Lang available:  AR, DE, EN, ES, FR, ID, RU, ZH
useMySQL: false
dbIP: 127.0.0.1
dbPort: 3306
dbName: myDB
dbUser: root
dbPassword: rootPassword
reduceDamageIndicatorWithProtolcolLib: false # if you have ProtocolLib installed, you can reduce the damage indicator amount (The amount of hearts that are displayed when you take damage)
silenceOutputs: # You can blacklist sentences that are sent to the console by The Ssomar plugins
  - "blacklist the sentence here"
globalSilenceOutputs: # You can blacklist sentences that are sent to the console by any plugin
  - "blacklist the sentence here"
disableCustomMetadataOnEntities: false # to disable the metadata fromSpawner and bowForce to be added to entities

#MIN : it will save only the modified settings
#NORMAL : it will save modified settings + frequently used settings
#MAX : it will save all settings (its very verbose)
configVerbosity: "NORMAL" # "NORMAL" or "MIN" or "MAX"
enableCommentsInConfig: true # It will add a description of each setting in comment in the yaml config file.
hologramsPlugin: "NONE" # The holograms plugin you want to use. By default None , it uses the vanilla holograms. You can use CMI, HOLOGRAPHIC_DISPLAYS or DECENT_HOLOGRAMS
```
