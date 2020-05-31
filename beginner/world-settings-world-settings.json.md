# World settings \(world-settings.json\)

Each world has it is own settings that applies for all of the biomes, it is general settings like sea level, biome sizes and so on. It has to be in its own file to make sure the biomes fade correctly without borders between them.

The setting file is location at;

```c
<server directory>/<world name>/settings/world-settings.json
```

## General setting

Used internal in the plugin to provide correct algorithms that matches the the already generated chunks. The version listed is the version the first chunks in the world got generated with. The only times you need to change this option is if you reset your world and want to keep the current settings.

```javascript
"pluginVersion": "7.2.9"
```

The setting determines whether all the world's oceans and rivers should be filled with lava. If they are filled with lava, all combustible materials on their shores catch on fire when a player is nearby.

```javascript
  "useLavaOceans": false
```

Noise algortihm used to generate terrain. Small differences, by default it will use perlin noise. See [https://en.wikipedia.org/wiki/Perlin\_noise](https://en.wikipedia.org/wiki/Perlin_noise) and [https://en.wikipedia.org/wiki/Simplex\_noise](https://en.wikipedia.org/wiki/Simplex_noise) for comparison

```javascript
  "useOpenSimplexNoise": true
```

The world generator have an insane amount of random calls to determine how the terrain should be generated and what blocks it should paint the terrain with. Within a few minutes of chunk generating has the plugin generated millions upon millions of random numbers to take dedications. The plugin try to decrease numbers by using the same numbers multiple times as often as it can. It still not fast enough. Turing on this option improves the performance but the quality decrease slightly. See [http://xoroshiro.di.unimi.it/](http://xoroshiro.di.unimi.it/) \("xoroshiro128+"\)

```javascript
  "useFastRandomAlgorithm": true
```

If you want the plugin to generate custom trees instead of the default minecraft trees, set this to true. Please note that the plugin only generate its custom trees if it has a tree type that matches the sapling.

```javascript
  "overrideSaplings": true
```

Makes the fading between biomes more rough by randomly select one of the biomes near the borders

```javascript
  "roughFading": true
```

Removes bedrock fading at the bottom if set to true. It will make bedrock to a flat layer at the bottom of the world. The amount of layers \(in y-axis\) is defined in the next option.

```javascript
  "flatBedrock": false,
  "bedrockLevel": 1
```

The surface level of all oceans and rivers. If the level is set below the default, land masses are bigger, and rivers may be shallow or dry. All land below level 63 is gravel. For low settings, the ocean may be reduced to small lakes, may be restricted to underground caves and caverns, or sometimes even doesn't exist. If the level is set above the default, low-lying biomes such as swamps are fragmented or nonexistent, creating a world with smaller land masses. Rivers are not "rivers" in the literal sense, but are more like subsurface valleys. The world may, at high levels, consist of sparse islands separated by very deep water or may be all ocean, as in the Water World preset.

```javascript
  "seaLevel": 62
```

The max height caves will generate

```javascript
  "maxCaveHeight": 50
```

The minimum height caves will generate

```javascript
  "minCaveHeight": 8
```

The chance for a mineshaft to be generated per chunk \(percentage value\). This example \(0.01\) gives mineshafts a 1% chance to generate per chunk

```javascript
  "mineshaftChance": 0.01,
```

## World border

The plugin allows you to make the world stop generating after it has reached a world border that is square shaped. You can set the radius \(technical half of the length of the square, since it is not a circle\) by using the following option;

![World border](http://i.imgur.com/X9xBvlG.png)

```javascript
  "worldSize": 500, //Disable = -1
```

The center of the world border will be at;

```javascript
  "worldCenterX": 0,
  "worldCenterZ": 0,
```

## Flat areas

![Flat area](http://i.imgur.com/MzXyi83.png)

The plugin can generate mutliple flat areas around the world. It will have a random shape that should fit the terrain. On the image above is it shaped like a sphere, something that now has been replaced with random natural shapes.

The flat areas can be usefull for multiple spawnpoints around the world and also saves you the time of flatting out the terrain around your spawn area.

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

## Biome types

The next parts of the configuration file is about biomes. In EWG, they are grouped into different types. Desert, aquatic, grassland, forest and tundra. Desert and tundra will spawn as long as possible from each other, while grassland and forest will spawn next to each other. Same goes for desert and aquatic, aquatic and grassland and forest and tundra. Each of the types contains a set of biomes. By default will all biomes have the same size and spawn at the same amount as other biomes.

Here is a illustration created by xemnes that shows the difference between biome and biome types;

![Biome sizes](http://i.imgur.com/BOfhWoy.png)

The red line can be decreased or increased by editing the following option;

```javascript
  "biomeTypeSize": 600.0
```

The gray line can be increased or decreased by editing the following option;

```javascript
  "biomeSize": 400.0
```

> You can make individual changes for each biome within a red line by changing the following option the biome configuration; "rarity":1, increasing it will make it bigger.

The red lines is by default adjusted to a size that fits the amount of biomes inside of the border. You can decrease the size of each of the red lines by editing the following options. Just make sure it all adds up to 1.

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

