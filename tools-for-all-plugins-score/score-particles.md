# ✨    Score particles

{% embed url="https://youtu.be/_GavkHnQcvg?si=UaRm9LlUomDzoveQ" %}

Score includes 34 custom pre-made particles shapes from Xparticle library. You can check all the information on their github.&#x20;

The attached link will direct you to the list of all **available particle types**.

{% embed url="https://github.com/CryptoMorin/XSeries/blob/master/src/main/java/com/cryptomorin/xseries/particles/XParticle.java" %}

<details>

<summary>Shapes</summary>

* &#x20;atom&#x20;
* &#x20;atomic&#x20;
* blackSun&#x20;
* blackhole&#x20;
* cage&#x20;
* chaoticDoublePendulum&#x20;
* circle&#x20;
* circularBeam&#x20;
* cone&#x20;
* crescent&#x20;
* cube&#x20;
* cylinder&#x20;
* diamond&#x20;
* dna&#x20;
* dnaReplication&#x20;
* ellipse&#x20;
* explosionWave&#x20;
* eye&#x20;
* filledCircle&#x20;
* filledCube&#x20;
* flower&#x20;
* guard&#x20;
* heart&#x20;
* helix&#x20;
* hypercube&#x20;
* illuminati&#x20;
* infinity&#x20;
* julia&#x20;
* magicCircles&#x20;
* mandelbrot&#x20;
* meguminExplosion&#x20;
* moveRotatingAround&#x20;
* polygon&#x20;
* rainbow&#x20;
* rectangle&#x20;
* ring&#x20;
* sphere&#x20;
* spikeSphere&#x20;
* spread&#x20;
* star&#x20;
* structuredCube&#x20;
* tesseract&#x20;
* vortex&#x20;
* waveFunction

</details>

## Parameters

Each shape has some **custom parameters to configure**, to see these parameters use the following command:

```yaml
/score particles-info 
#Example
/score particles-info shape:blackhole
```

## Display the particle

To display the shape use the following command:

```
/score particles
```

To change the parameters of your shape just add into your current command

```
{the parameter name}:{the value}
```

{% hint style="info" %}
You can add as much parameters as you want in the same line
{% endhint %}

## Target&#x20;

Normally the shape is in the player who is running the command, to change this use:

```
target:{uuid of the target}
```

{% hint style="danger" %}
THE **UUID** not the name of the player, not the name of the target, not the name of the entity, the **UUID**.
{% endhint %}

If don't want to target someone but targetting a specific location use:

```
location:{world},{x},{y},{z}
```

{% hint style="info" %}
Example:\
\
score particles location:%block\_world%,%block\_x%+0.5,%block\_y%+0.5,%block\_z%+0.5 shape:circularBeam particle:flame color:ORANGE maxRadius:14 rate:500 radiusRate:15 extend:1 time:12\
\
The 0.5 is added to make the particles appear on the center of the block
{% endhint %}

### Particle type

Default, the shape will use the FLAME particle, to change this use

```
particle:{the particle type}
```

### Color of redstone particle

**Instead** of using `particle:{particle name}` to use the restone particle with a [custom color](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Color.html), add the next parameter:

```
color:{color Name}
```

## Example

* **"heart"**
  * "/score particles shape:heart particle:HEART cut:4 cutAngle:2 depth:2 compressHeight:1 rate:100"
* **"blackhole"**
  * "/score particles target:731bec03-102e-3179-b676-04de47c40580 particle:SMOKE\_NORMAL shape:blackhole points:30 radius:2.5 rate:1 mode:2 time:50"
* **"vortex"**
  * "/score particles shape:vortex particle:crit points:5 rate:25 time:100"
* **"diamond"**
  * "/score particles shape:diamond particle:glow radiusRate:0.6 rate:0.4 height:3"
* **"ring"**
  * "/score particles shape:ring particle:PORTAL rate:100 radius:2 tubeRadius:1"
* **"illuminati"**
  * "/score particles shape:illuminati particle:NAUTILUS size:5 extension:20"
* **"meguminExplosion"**
  * "/score particles shape:meguminExplosion color:RED size:5"
* **"circularBeam"**
  * "/score particles shape:circularBeam color:PURPLE maxRadius:5 rate:500 radiusRate:15 extend:1 time:100"
* **"cone"**
  * "/score particles shape:cone color:GREEN height:5 radius:1 rate:0.2 circleRate:10"

```
/score particles target:731bec03-102e-3179-b676-04de47c40580 shape:blackhole particle:SMOKE_NORMAL points:30 radius:2.5 rate:1 mode:2 time:50
```

{% hint style="info" %}
Normally you won't know the uuid of a player, but since you can run this command inside EI, EB or EE, you can use the placeholders of it, such as using %target\_uuid%.
{% endhint %}

