---
description: >-
  A page dedicated for helping users of Ssomar's plugins to create more complex 
  things that require advanced math formulas
---

# Math Formulas

## Particle-Related Math Formulas

### Player-Direction Offset Formula

```
X: %math_2*SIN({player_yaw}*-1)*COS({player_pitch}*-1)%
Y: %math_2*SIN({player_pitch}*-1)%
Z: %math_2*COS({player_yaw}*-1)*COS({player_pitch}*-1)%
```

Requires:\
\- PlaceholderAPI & Math Expansion

Example Usage:&#x20;

```yaml
- execute at %player% run particle flame ~ ~1.6 ~ %math_2*SIN({player_yaw}*-1)*COS({player_pitch}*-1)% %math_2*SIN({player_pitch}*-1)% %math_2*COS({player_yaw}*-1)*COS({player_pitch}*-1)% 0.7 0
```

Command below shoots firework particles like a shotgun (Commands below are in config form)

```yaml
    - 'LOOP START: 20'
    - 'RANDON RUN: 1'
    - execute at %player% run particle firework ~ ~1.6 ~ %math_2*SIN(({player_yaw}+{rng_-10,10})*-1)*COS(({player_pitch}+{rng_-10,10})*-1)%
      %math_2*SIN(({player_pitch}+{rng_-10,10})*-1)% %math_2*COS(({player_yaw}+{rng_-10,10})*-1)*COS(({player_pitch}+{rng_-10,10})*-1)%
      0.%rng_5,70% 0
    - RANDOM END
    - LOOP END
```

{% hint style="info" %}
How this works is that, a RNG placeholder was used to add/subtract values from your yaw pitch values in the formula so it would try to "spread" out the particles.

Basically the rng placeholders are there just to "make" you look somewhere since the math formula depends on your yaw pitch values.

The reason why there's a \*-1 in the formula because when the original formula was used, it made particles move in complete opposite of where you're looking at
{% endhint %}

You can also use this very same method to perform directional dashes which FRONTDASH is unable to perform

<pre data-full-width="true"><code><strong>- CUSTOMDASH1 %math_{player_x_long}+(2*SIN({player_yaw}*-1)*COS({player_pitch}*-1))% 
</strong><strong>%math_{player_y_long}+(2*SIN({player_pitch}*-1))% %math_{player_z_long}+(2*COS({player_yaw}*-1)*COS({player_pitch}*-1))%
</strong></code></pre>

You could use (%x%) instead of {player\_x\_long] but I'll explain the more detailed stuff.

The formula above ONLY gets the displacement between 2 points but CUSTOMDASH1 requires the xyz location because it doesn't have your xyz location as a reference so you have to add your xyz values to the equation to properly launch yourself towards your direction. To increase the speed of the launch, increase the distance value which is the "2" value that you can see in the math formula.

As to why you have to use the xyz placeholder that gives decimal values instead of non-decimal values, it is to make sure you're landing at the correct location or else you would be flying off somewhere.

## Origin-Related Math Formulas

### Distance from XYZ

Requires:\
\- PlaceholderAPI \
&#x20; \- Math Expansion\
&#x20; \- Player Expansion

Example Usage:\
You want to get the distance between you and a specific XYZ location which is x:30, y:60, z:-120

```
%math_(SQRT(ABS(({x1})-({x2}))^2+ABS(({y1})-({y2}))^2+ABS(({z1})-({z2}))^2))%
```



## Using offsets to distance target from location

```
X: %math_(<x>)+(((<x>)-({player_x}))*-(<multiplier>))% 
Y: %math_(<y>)+(((<y>)-({player_y}))*-(<multiplier>))%
Z: %math_(<z>)+(((<z>)-({player_z}))*-(<multiplier>))%
```

{% hint style="info" %}
How this works is first, you get the displacement of 2 points.&#x20;

The formula above for example, would use the target block's xyz and the player's xyz values to get the displacement between the 2 points then add it along with the target block's xyz coordinates so you would be able to either pull yourself more towards the location or away from the location.&#x20;

The formula currently has `*-(<multiplier>)` at where it is at. The higher the number in `<multiplier>`, the greater the displacement value. If you want to distance the user away from that point, use the negative symbol. Otherwise, remove the negative symbol to further pull the player towards the location
{% endhint %}

Example Usage:

```
    commands:
    - CUSTOMDASH1 %math_(%block_x%)+(((%block_x%)-({player_x}))*-2)% %math_(%block_y%)+(((%block_y%)-({player_y}))*-2)%
      %math_(%block_z%)+(((%block_z%)-({player_z}))*-2)%
```

## Threshold Value Math Formula

{% code fullWidth="true" %}
```
%math_{player_health}-IF({player_health}>500, {player_health}-500, 0)%
```
{% endcode %}

{% hint style="info" %}
This is an example of a math formula where it deals with the player health placeholder. But if the player health value surpasses the value of 500, it will stop there.
{% endhint %}

The detailed explanation goes like this. in the IF() formula, it first checks if the placeholder would return a number greater than 500.&#x20;

* If the placeholder's value is greater than 500, it would get the difference between the placeholder's value and 500 and use that value to subtract from the placeholder's value to prevent it from going above 500.
* If the placeholder's value is less than 500, nothing happens



## Oscillating Formula

`f(x)=sin(2πx)`

<figure><img src="../../.gitbook/assets/image (437).png" alt=""><figcaption></figcaption></figure>

Example Usage:

```
    commands:
    - FOR [0.500 ,1.000 ,1.500 ,2.000 ,2.500 ,3.000 ,3.500 ,4.000 ,4.500 ,5.000 ,5.500
      ,6.000 ,6.500 ,7.000 ,7.500 ,8.000 ,8.500 ,9.000 ,9.500 ,10.000 ] > for1
    - execute at %player% run particle end_rod ~%math_(%for1%)*SIN({player_yaw}*-1)*COS({player_pitch}*-1)%
      ~%math_((%for1%)*SIN({player_pitch}*-1))+1.6+SIN(2*31.4*%for1%)% ~%math_(%for1%)*COS({player_yaw}*-1)*COS({player_pitch}*-1)%
    - score run-block-command block:%world%,%math_(%x%)+((%for1%)*SIN({player_yaw}*-1)*COS({player_pitch}*-1))%,%math_((%y%)+((%for1%)*SIN({player_pitch}*-1)))+1.6%,%math_(%z%)+((%for1%)*COS({player_yaw}*-1)*COS({player_pitch}*-1))%
      player:%player% AROUND 0.5 CONDITIONS(%::player_name::%!=%player%) DAMAGE 10
      <+> INVULNERABILITY 5
    - score run-block-command block:%world%,%math_(%x%)+((%for1%)*SIN({player_yaw}*-1)*COS({player_pitch}*-1))%,%math_((%y%)+((%for1%)*SIN({player_pitch}*-1)))+1.6%,%math_(%z%)+((%for1%)*COS({player_yaw}*-1)*COS({player_pitch}*-1))%
      player:%player% MOB_AROUND 0.5 DAMAGE 10
    - ENDFOR for1
```

{% hint style="info" %}
The main function of this method is the Y values

```markup
~%math_((%for1%)*SIN({player_pitch}*-1))+1.6+SIN(2*31.4*%for1%)%
```

Check the part of where the SIN() is at.&#x20;

* %for1% represents the increasing number
* 2 is just part of the formula
* The 31.4 is the number you have to properly adjust to produce bigger oscillations\

{% endhint %}
