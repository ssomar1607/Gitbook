# ✨    SCore particles







## PAGE CREATION IN PROGRESS 19 may 2025

## PAGE CREATION IN PROGRESS 19 may 2025

## PAGE CREATION IN PROGRESS 19 may 2025

## PAGE CREATION IN PROGRESS 19 may 2025













{% embed url="https://youtu.be/_GavkHnQcvg?si=UaRm9LlUomDzoveQ" %}

Score includes many pre-made particles shapes from XParticle library and some custom other.&#x20;

The attached link will direct you to the list of all **available particle types**.

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

## How to display the particles

The command to display the particle is `/score particles`

You will have to select a shape and configure correctly the command to achieve to do what you want.



## General settings for all shapes

### Define the spawn point

To define where the shape will be displayed you have two choice, by mentioning directly the location or setting an entity UUID&#x20;

#### Using Player/Entity UUID

When you decide to use the entity UUID **the shape will follow en Player/Entity if he moves**. So it can deform the shape or make a cool effect.

```css
target:{uuid of the target}
/* Example using flat UUID */
target:b33183ad-e9c0-4d48-8eea-f8c9358d3568
/* Example using a placeholder */
target:%player_uuid%
```

{% hint style="danger" %}
You have to specify an UUID of a player or an entity. The player name doesn't work !
{% endhint %}

#### Using a specific location

Using location you are sure that the shape will not be deformed, it will stay static.

```css
location:{world},{x},{y},{z}
/* Example using flat location */
location:world,100,50,500
/* Example using placeholders */
location:%player_world%,%player_x%,%player_y%,%player_z%
```



### Particles definition

#### Particle type

Define the particle used by the shape. By default it will be the FLAME particle

```css
particle:{the particle type}
/* Example */
particle:CLOUD
```

List of particles available here: [List of Spigot particles ](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Particle.html)

#### Color

**Instead** of using `particle:{particle name}`  if you want to use REDSTONE / DUST particles you can directly use the setting color with a [custom color](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Color.html).

You can set two colors separated by a , to have a color transition.

```css
color:{color Name}
/* Example one color */
color:RED
/* Example two colors with transition */
color:AQUA,BLUE
```

#### Block particles

**Instead** of using `particle:{particle name}`  if you want to use BLOCK\_CRACK / BLOCK particles you can directly use the setting blockdata with a [material](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html).

```css
blockdata:{material}
/* Example */
blockdata:LAVA
```

#### Item particles

**Instead** of using `particle:{particle name}`  if you want to use ITEM\_CRACK/ ITEM particles you can directly use the setting itemstack with a [material](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html).

```css
itemstack:{material}
/* Example */
itemstack:DIAMOND_SHOVEL
```

### Offset / Shift the spawn point of the shape&#x20;

You can define an offset in a specific direction, it allows you for example to display the shape around the player / entity, without having to do complex calculation.

* offsetPitch: the pitch direction where the offset will be directed
* offsetYaw: the yaw direction where the offset will be directed
* offsetSitance: the distance of the offset
* offsetX: Increase the offset X location
* offsetY: Increase the offset Y location
* offsetZ: Increase the offset Z location

By default these settings are set to 0

```css
offsetPitch:{the pitch direction}
offsetYaw:{the yaw direction}
offsetDistance:{the distance}
offsetX:{x bonus}
offsetY:{y bonus}
offsetZ:{z bonus}
/* Example with flat values */
offsetPitch:0
offsetYaw:-90
offsetDistance:5
offsetY:-1
/* Example with placeholders */
offsetPitch:%player_pitch_initial%+30
offsetYaw:%player_yaw_initial%
offsetDistance:%var_myvar%
```

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Settings of the shapes

### Atom

Creates a set of elliptical orbits with a small particle sphere at the center, resembling an atom.

* `orbits`: Number of elliptical orbits.
* `radius`: Radius of the orbits.
* `rate`: Number of particles per orbit.

```yaml
# Examples that you can run manually in-game
/score particles shape:atom location:%loc% radius:2 rate:60 orbits:4

# Examples that you can include into your commands

```

### Atomic

Animated version of `atom` with orbiting particles.

* `orbits`: Number of orbiting paths.
* `radius`: Radius of orbit.
* `rate`: Rate of orbit.
* `time`: Duration in ticks.

<pre class="language-yaml"><code class="lang-yaml"><strong># Examples that you can run manually in-game
</strong>/score particles shape:atomic location:%loc% radius:2 rate:30 orbits:3 time:100

# Examples that you can include into your commands

</code></pre>

### BlackSun

Multiple concentric circles increasing in size.

* `radius`: Max radius.
* `radiusRate`: Difference in radius between each circle.
* `rate`: Particle density.
* `rateChange`: Change of rate per layer.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### BlackHole

A dynamic particle vortex effect.

* `points`: Number of spiral arms.
* `radius`: Distance from center.
* `rate`: Rotation rate.
* `mode`: 0 to 4 for different vortex styles.
* `time`: Duration in ticks.

<pre class="language-yaml"><code class="lang-yaml"><strong># Examples that you can run manually in-game
</strong>/score particles shape:blackhole location:%loc% points:8 radius:2 rate:10 mode:2 time:100

# Examples that you can include into your commands
</code></pre>

### Cage

Displays a 3D cage with vertical bars.

* `start`: Start location.
* `end`: End location.
* `rate`: Distance between bars.
* `barRate`: Frequency of bars.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### ChaoticDoublePendulum

Simulates a chaotic double pendulum effect.

* `radius`: Swing radius.
* `gravity`: Gravity force (typically -1).
* `length`, `length2`: Lengths of the pendulums.
* `mass1`, `mass2`: Mass of each pendulum.
* `dimension3`: Whether to use 3D rotation.
* `speed`: Animation speed.
* `time`: Duration.

<pre class="language-yaml"><code class="lang-yaml"># Examples that you can run manually in-game
<strong>/score particles shape:chaoticDoublePendulum location:%loc% radius:3 gravity:-1 length:200 length2:200 mass1:50 mass2:50 dimension3:true speed:2 time:200
</strong>
# Examples that you can include into your commands
</code></pre>

### Circle

Displays a circle of particles.

* `radius`: radius of the circle
* `density`: number of particles per block (higher = more dense).
* `drawMode`: clockWise, counterClockWise, random
* `fillMode`: disk, spiral, ring
* `timeToDisplay`: time in ticks to animate the full display.
* `directionPitch`: pitch direction of the square
* `directionYaw`: yaw direction of the square

Examples:

```yaml
# Examples that you can include into your commands
# Display multiple Green circles in front the player
commands:
- FOR [+20,-20,+40,-40,+60,-60,+80,-80,+100,-100] > for3
- score particles shape:circle location:%player_world_initial%,%player_x_initial%,%player_y_initial%,%player_z_initial% color:GREEN,WHITE radius:3 density:100 timeToDisplay:10 drawMode:clockwise offsetDistance:8 offsetPitch:0 offsetYaw:%player_yaw_initial%%for3%  directionYaw:%player_yaw_initial%%for3% fillMode:disk directionPitch:-90 offsetY:-1
- END_FOR for3
```

### CircularBeam

Animated beam with changing circle sizes over time.

* `maxRadius`: Max circle radius.
* `rate`: Point rate per circle.
* `radiusRate`: Change in radius.
* `extend`: Extension distance.
* `time`: Duration.

```yaml
# Examples that you can run manually in-game
/score particles shape:circularBeam location:%loc% maxRadius:2 rate:10 radiusRate:0.2 extend:0.5 time:100score particles shape:chaoticDoublePendulum location:%loc% radius:3 gravity:-1 length:200 length2:200 mass1:50 mass2:50 dimension3:true speed:2 time:200

# Examples that you can include into your commands
```

### Cone

Cone made of stacked circles.

* `height`: Height of the cone.
* `radius`: Base radius.
* `rate`: Circle spacing.
* `circleRate`: Point density.

<pre class="language-yaml"><code class="lang-yaml"># Examples that you can run manually in-game
<strong>/score particles shape:cone location:%loc% height:5 radius:2 rate:1 circleRate:50
</strong>
# Examples that you can include into your commands
</code></pre>

### Crescent

Renders a crescent moon using two overlapping circles.

* `radius`: size of the outer arc.
* `rate`: resolution of the curve.

<pre class="language-yaml"><code class="lang-yaml"># Examples that you can run manually in-game
<strong>/score particles shape:cone location:%loc% height:5 radius:2 rate:1 circleRate:50
</strong>
# Examples that you can include into your commands
</code></pre>

### Cube

Displays a 3D cube, showing only its edges.

* `start`: Bottom corner of the cube.
* `end`: Top corner of the cube.
* `rate`: Particle density.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Cylinder

* `radius`: radius of the cylinder
* `height`: the height of the cylinder
* `density`: number of particles per block (higher = more dense).
* `drawMode`: clockWise, counterClockWise, random
* `timeToDisplay`: time in ticks to animate the full display.
* `directionPitch`: pitch direction of the square
* `directionYaw`: yaw direction of the square

Examples:

```yaml
# Examples that you can include into your commands
# Display two green cylinder in front of the player
- FOR [+20,-20] > for3
- score particles shape:cylinder location:%player_world_initial%,%player_x_initial%,%player_y_initial%,%player_z_initial% color:GREEN,WHITE radius:1 density:100 timeToDisplay:5 drawMode:clockwise offsetDistance:8 offsetPitch:0 offsetYaw:%player_yaw_initial%%for3%  directionYaw:%player_yaw_initial%%for3% directionPitch:-90 offsetY:-1 height:3
- END_FOR for3
```

### Diamond

Creates a diamond (rhombus) shape in 2D or 3D.

* `radiusRate`: Controls the width.
* `rate`: Spacing between points.
* `height`: Total height.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### DNA

Displays a DNA double helix with hydrogen bonds.

* `radius`: Radius of the helices.
* `rate`: Spacing between points.
* `extension`: Helix stretch factor.
* `height`: Total height.
* `hydrogenBondDist`: Distance between each hydrogen bond.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### DNA Replication

Simulates DNA replication with bonds and colors.

* `radius`, `rate`, `extension`, `height`: Same as `DNA`.
* `speed`: Animation speed.
* `hydrogenBondDist`: Distance between bonds.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Ellipse

* `start`, `end`: Start and end angles.
* `rate`: Angular spacing.
* `radius`, `otherRadius`: X and Y radii.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### ExplosionWave

Wavy animation representing an explosion shockwave.

* `rate`: Particle density within the wave.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Eye

Draws an oval eye-like shape.

* `radius`, `radius2`: Primary radii.
* `rate`: Resolution.
* `extension`: Elongation factor

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### FilledCube

Displays a cube fully filled with particles.

* `start`, `end`: Opposite corners of the cube.
* `rate`: Particle density.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Flower

Creates a floral effect with repeating patterns around a circle.

* `count`: Number of "petals".
* `radius`: Radius of the flower.
* `runnable`: The shape to display at each petal.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Guard

Makes a shape spin or oscillate around a point.

* `update`: Update interval.
* `rate`: Rotation speed.
* `offsetx/y/z`: Oscillation distance on each axis.
* `runnable`: The particle form to run.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Heart

Draws a heart using a polar curve.

* `cut`, `cutAngle`: Adjust the heart’s lobes.
* `depth`: Central notch depth.
* `compressHeight`: Vertical compression.
* `rate`: Resolution.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Helix

Draws animated 3D helices.

* `strings`: Number of helices.
* `radius`: Helix radius.
* `rate`, `extension`: Spacing and spiral strength.
* `height`: Total height.
* `speed`: Animation speed.
* `fadeUp`, `fadeDown`: Gradual change in radius.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Hypercube

Displays a structure of interlinked cubes simulating a hypercube.

* `startOrigin`, `endOrigin`: Bounding corners.
* `rate`: Particle spacing.
* `sizeRate`: Spacing between cubes.
* `cubes`: Number of cube iterations.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Illuminati

Creates a 3D infinity symbol shape.

* `radius`: Size of the shape.
* `rate`: Point density.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Julia

Displays a Julia fractal set.

* `size`, `zoom`, `colorScheme`: Visual settings.
* `moveX`, `moveY`: Position offset.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### MagicCircles

Displays expanding rings like magical glyphs.

* `radius`: Initial radius.
* `rate`: Point spacing.
* `radiusRate`: Growth speed.
* `distance`: Spacing between rings.
* `time`: Duration.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Mandelbrot

Displays a Mandelbrot fractal set.

* `size`, `zoom`, `rate`: Rendering settings.
* `x0`, `y0`: Center position.
* `color`: Iteration depth.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### MeguminExplosion

Stylized magical explosion effect.

* `size`: Overall explosion size.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Polygon

Draws a polygon with optional internal connections

* `points`: Number of corners.
* `connection`: How many corners to connect.
* `size`: Radius of the polygon.
* `rate`: Resolution.
* `extend`: Connection extension factor.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Rainbow

Displays stacked rainbow arcs with colored layers.

* `radius`, `rate`, `curve`: Shape and spacing.
* `layers`: Number of arcs.
* `compact`: Reduces spacing between arcs.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Rectangle

Draws a flat 2D rectangle.

* `start`, `end`: Opposite corners.
* `rate`: Point spacing.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Ring

Draws a flat ring (annulus).

* `radius`: Radius of the ring.
* `density`: Particle density.
* `height`: Ring thickness.
* `timeToDisplay`: Duration.
* `drawMode`: Drawing order.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Sphere

Draws a full 3D sphere.

* `radius`: Sphere radius.
* `rate`: Angular resolution

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### SpikeSphere

Draws a sphere with random spikes.

* `radius`, `rate`: Base sphere parameters.
* `chance`: Chance of spike.
* `minRandomDistance`, `maxRandomDistance`: Spike length range.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Spread

Randomly launches particles toward a target.

* `amount`: Number of launches.
* `rate`: Frequency.
* `start`, `originEnd`: Start and end positions.
* `offsetx/y/z`: Target randomness

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Square

* `height`: height in blocks along vertical axis.
* `length`: length in blocks along direction vector.
* `width`: width in blocks perpendicular to the wall direction.
* `density`: number of particles per block (higher = more dense).
* `timeToDisplay`: time in ticks to animate the full display.
* `drawMode`: "vertical" or "horizontal" — controls iteration order.
* `verticalOrder`: "up" or "down" — order along height.
* `horizontalOrder`: "near" or "far" — order along length.
* `directionPitch`: pitch direction of the square
* `directionYaw`: yaw direction of the square

```yaml
# Examples that you can run manually in-game
...

# Examples that you can include into your commands
commands:
# A line of explosion
- score particles shape:square location:%player_world_initial%,%player_x_initial%,%player_y_initial%,%player_z_initial% particle:EXPLOSION height:1 length:30 timeToDisplay:20 density:1 directionYaw:%player_yaw_initial% directionPitch:%player_pitch_initial% verticalOrder:up horizontalOrder:near offsetY:-1
# A wall of flame
- score particles shape:square location:%player_world_initial%,%player_x_initial%,%player_y
```

### Star

Creates a 3D star with animated spikes.

* `points`: Number of base sides.
* `spikes`: Number of star tips.
* `rate`: Resolution.
* `spikeLength`: Tip length.
* `coreRadius`: Core radius.
* `neuron`: Tip curvature.
* `prototype`: Use helices instead of lines.
* `speed`: Animation speed.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### StructuredCube

Draws a wireframe cube showing only its edges.

* `start`, `end`: Opposite corners.
* `rate`: Edge particle density.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Tesseract

Draws a rotating 4D cube (tesseract)

* `size`: Overall size.
* `rate`: Density.
* `speed`: Rotation speed.
* `time`: Display time.

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```

### Vortex

Spiral effect like a galaxy or tornado.

* `points`: Number of spiral arms.
* `rate`: Rotation speed.
* `time`: Duration.

```yaml
# Examples that you can run manually in-game
 

# Examples that you can include into your commands
```

### WaveFunction

Visualizes a quantum wave function.

* `extend`: Length.
* `heightRange`: Amplitude range.
* `size`: Overall size.
* `rate`: Point density

```yaml
# Examples that you can run manually in-game


# Examples that you can include into your commands
```



