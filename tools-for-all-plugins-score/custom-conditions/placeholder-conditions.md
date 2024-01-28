# Placeholder Conditions

### placeholdersConditions:

* Description: Parses the said placeholder and compares it with the said value.
  * type: Of how you want to compare placeholders
    * `PLAYER_STRING`: Parses the given placeholder in the first part with the item user and compares it to the second part
    * `PLAYER_NUMBER`: Same as `PLAYER_STRING` but you can use INFERIOR/SUPERIOR related comparators
    * `PLAYER_PLAYER`: Same as `PLAYER_STRING` but you can use placeholders in the second part and can use INFERIOR/SUPERIOR related comparators
    * `TARGET_STRING`: Same as `PLAYER_STRING` but you parse the placeholder with your target
    * `TARGET_NUMBER`: Same as `TARGET_STRING` but you can use INFERIOR/SUPERIOR related comparators
    * `TARGET_TARGET`: Same as `TARGET_STRING` but you can use placeholders in the second part and can use INFERIOR/SUPERIOR related comparators
    * `PLAYER_TARGET`: Parses the given placeholder in the first part with the item user and compares it to the second part which parses the target with the given placeholder and can use INFERIOR/SUPERIOR related comparators
  * comparator: Used to compare the given placeholder to the second part in numbers
    * `EQUALS`: Compares if the given placeholder gives the exact value as the given value in the second part
    * `DIFFERENT`: Compares if the given placeholder doesn't give the exact value as the given value in the second part
    * `INFERIOR`: Compares if the given placeholder gives a value lower than the given value in the second part
    * `SUPERIOR`: Compares if the given placeholder gives a value greater than the given value in the second part
    * `INFERIOR_OR_EQUALS`: Compares if the given placeholder gives a value lower than or equals to the given value in the second part
    * `SUPERIOR_OR_EQUALS`: Compares if the given placeholder gives a value greater than or equals to the given value in the second part
    * IS\_CONTAINED\_IN: Compares if the PART1 is cointained in the PART2, if it is, this placeholder is OK and the activator will run.
    * IS\_NOT\_CONTAINED\_IN: Compares if the PART1 is cointained in the PART2, if it isn't, this placeholder is OK and the activator will run.
  * `messageIfNotValid:`: The custom message if the custom placeholder condition didn't match with the first and second part
  * `cancelEventIfNotValid:`: If the custom placeholder condition didn't match with the first and second part, the activator's event will be cancelled. (Default: false)
* Example:

```yaml
placeholdersConditions:
    plchC0:
      type: PLAYER_STRING
      part1: '%checkitem_inhand,lorecontains:&7Grab%'
      comparator: EQUALS
      part2: 'no'
      messageIfNotValid: ''
      cancelEventIfNotValid: false
```

```yaml
placeholdersConditions:
    plchC0:
      type: PLAYER_STRING
      part1: 'Ssomar'
      comparator: IS_CONTAINED_IN
      part2: 'Ssomar<OR>Special70<OR>Vayk'
      messageIfNotValid: ''
      cancelEventIfNotValid: false
(ITS VALID)
```

```yaml
placeholdersConditions:
    plchC0:
      type: PLAYER_STRING
      part1: 'Ssomar'
      comparator: IS_NOT_CONTAINED_IN
      part2: 'Ssomar<OR>Special70<OR>Vayk'
      messageIfNotValid: ''
      cancelEventIfNotValid: false
(ITS NOT VALID)
```

* Example Situations:
  * If the player facing south west with this given placeholder condition, the activator will activate.

```yaml
placeholdersConditions:
    plchC0:
      type: PLAYER_STRING
      part1: '%player_direction%'
      comparator: EQUALS
      part2: 'SW'
      messageIfNotValid: ''
      cancelEventIfNotValid: false
```

* Required: NO

{% hint style="info" %}
In the PART2 you can add multiple things using \<OR> between each thing.
{% endhint %}
