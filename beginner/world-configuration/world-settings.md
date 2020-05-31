---
description: Settings for your entire world - world-settings.json
---

# World settings

Each world has it is own settings that apply to all the biomes. This contains general settings like sea level, biome sizes and much more. It has to be in its own file to make sure the biomes fade correctly, amongst other things.

The setting file is location at;

```bash
*/<world name>/settings/world-settings.json
```

#### Settings

**Plugin Version**

Used internally in the plugin to provide correct algorithms that match the already generated chunks. The version listed here is the version the first chunks in the world were generated with. The only times you need to change this, is if you full-reset your world, and want to keep the current settings.

```javascript
"pluginVersion": "8.1.23"
```

**Lava Oceans**

The setting determines whether all the world's oceans and rivers should be filled with lava. If they are filled with lava, all combustible materials on their shores catch on fire when a player is nearby. \(Unless you turn off firespread through `/gamerule doFireTick false`.\)

```javascript
  "useLavaOceans": false
```

**Fast Ores and Vanilla Ore Algorithms**

These settings affect ores in the world, though they can be a bit unstable they should slightly increase chunk generation speeds.

```javascript
  "useFastOres": false,
  "useVanillaOreAlgorithm": false,
```

**Simplex Noise**

Noise algortihm used to generate terrain. Small differences, by default it will use perlin noise. See [Wikipedia - Perlin Noise](https://en.wikipedia.org/wiki/Perlin_noise) and [Wikipedia - Simplex Noise](https://en.wikipedia.org/wiki/Simplex_noise) for a comparison.

```javascript
  "useOpenSimplexNoise": true
```

**Fast Random Algorithm**

The world generator has an insane amount of random calls to determine how the terrain should be generated and what blocks it should create the terrain with. Within a few minutes of chunk generating, the plugin has already generated millions upon millions of random numbers to take decisions. Using this setting, the plugin will try to decrease numbers by using the same numbers multiple times as often as it can. Turning on this option improves the performance but slightly decreases the quality of the terrain generation. See [http://xoroshiro.di.unimi.it/](http://xoroshiro.di.unimi.it/) \("xoroshiro128+"\) for reference.

```javascript
  "useFastRandomAlgorithm": true
```

**Rough Fading**

Makes the fading between biomes more rough by randomly selecting one of the biomes near the borders.

```javascript
  "roughFading": true
```

**Flat Bedrock**

Removes bedrock fading at the bottom if set to true. It will turn the bedrock into a flat layer at the bottom of the world. The amount of layers \(in y-axis\) is defined in the `"bedrockLevel"` option.

```javascript
  "flatBedrock": false,
  "bedrockLevel": 1
```

**Sea Level**

Defines the surface level of all oceans and rivers. If the level is set below the default, land masses are bigger, and rivers may be shallow or dry. Note that all land below level 63 is gravel. For low settings, the ocean may be reduced to small lakes, may be restricted to underground caves and caverns, or sometimes doesn't exist at all. If the level is set above the default, low-lying biomes such as swamps are fragmented, less frequent, or nonexistent, leading to a world with smaller land masses. Rivers are not "rivers" in the literal sense, but are more like subsurface valleys. The world may, at high levels, consist of sparse islands separated by very deep water or may be all ocean.

```javascript
  "seaLevel": 62
```

**Cave Height**

The max height at which caves will generate.

```javascript
  "maxCaveHeight": 50
```

The minimum height caves will generate.

```javascript
  "minCaveHeight": 8
```

**Map Scale**

Changes the scale between which your [generate-world-from-image](https://docs.dynamic-bytes.com/beginner/generate-world-from-image) image and the actual blocks in the world. If this setting is on `1.0`, it will generate 1 pixel per block.

```javascript
  "mapScale": 1.0,
```

**Ocean Modifier**

Changes the amount of oceans in your world, higher is more.

```javascript
  "oceanModifier": 1.0,
```

**Tree Modifier**

Chances the amount of trees in the world, higher is more.

```javascript
  "globalTreeModifier": 1.0,
```

**Mineshaft Chance**

The chance for a mineshaft to be generated per chunk \(percentage value\). This example \(0.01\) gives mineshafts a 1% chance to generate per chunk.

```javascript
  "mineshaftChance": 0.01,
```

**Biome types**

The next parts of the configuration file is about biomes. In EWG, they are grouped into different types. Desert, aquatic, grassland, forest and tundra. Desert and tundra will spawn as long as possible from each other, while grassland and forest will spawn next to each other. Same goes for desert and aquatic, aquatic and grassland and forest and tundra. Each of the types contains a set of biomes. By default, all biomes have the same size and spawn at the same frequency as other biomes.

Here is an illustration created by Xemnes that shows the difference between biomes and biome types;

![Image of biome sizes](http://i.imgur.com/BOfhWoy.png)

The size of the red line can be decreased or increased by editing the following option, where the oceanSize separately modifies the size of the oceans;

```javascript
  "biomeTypeSize": 600.0,
  "oceanSize": 450.0
```

The size of the gray line can be increased or decreased by editing the following option;

```javascript
  "biomeSize": 400.0
```

> You can make individual changes for each biome within a red line by changing the following option the biome configuration; "rarity":1, increasing it will make it bigger.

The red lines are by default adjusted to a size that fits the amount of biomes inside of the border. You can decrease the size of each of the red lines by editing the following options. Just make sure it **always** adds up to 1. You can find these settings at the bottom of the file.

```javascript
  "biomeTypes": { 
    "DESERT": {
      "enabled": true,
      "percentage": 0.13333333333333333
    },
    "AQUATIC": { // Islands and seas
      "enabled": true,
      "percentage": 0.06666666666666667
    },
    "GRASSLAND": {
      "enabled": true,
      "percentage": 0.3333333333333333
    },
    "FOREST": {
      "enabled": true,
      "percentage": 0.4666666666666667
    },
    "TUNDRA": {
      "enabled": false,
      "percentage": 0.0
    }
  }
```

**World border**

The plugin allows you to make the world stop generating after it has reached a certain square-shaped world border. You can set the radius \(technically half of the length of the square, since it is not a circle\) by using the following option;

![Image of a world border](http://i.imgur.com/X9xBvlG.png)

> You can disable the world size by replacing the value with -1.
>
> ```javascript
>   "worldSizeX": 500,
>   "worldSizeY": 500
> ```

The center of the world border will be at;

```javascript
  "worldCenterX": 0,
  "worldCenterZ": 0,
```

**Flat areas**

![Image of a flat area](http://i.imgur.com/MzXyi83.png)

The plugin can generate mutliple flat areas around the world. It will have a random \(circular based\) shape that should fit the terrain. On the image above is it shaped somewhat like a sphere, something that now has been replaced with more limiting circular shapes.

The flat areas can be useful for multiple spawnpoints around the world and also saves you the time of flattening the terrain around your spawn area.

```javascript
  "flatAreas": [ 
    {
      "radius": 70,
      "xLocation": 0,
      "zLocation": 0,
      "baseLevel": 60, //Height in y-axis
      "outerRadius": 40 //Cumulative length between the flat area and the normal terrain 
    },
    {
      "radius": 30,
      "xLocation": 1000,
      "zLocation": 2000,
      "baseLevel": 60,
      "outerRadius": 20
    }
  ]
```

**Override Saplings**

If you want the plugin to generate custom trees instead of the default minecraft trees from saplings, set this to true. Please note that the plugin only generates its custom trees if it has a tree type that matches the sapling.

```javascript
  "overrideSaplings": true
```

{% hint style="info" %}
> Below this setting are the individual tree files for each of the saplings respectively. You can remove default and add custom trees here to your liking.
{% endhint %}

#### Support

If you have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

