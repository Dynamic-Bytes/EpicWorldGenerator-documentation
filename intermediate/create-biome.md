---
description: 'Create your own biomes, create your own world'
---

# Create a custom biome

## Installation

Custom biomes can easily be created by copying and modifying a default biome. Here is a guide on how to do just that;

1. Navigate to the following folder in your world: `*/<world name>/settings/biomes/default`.  
2. Pick a biome to base your new biome off of.  
3. Copy the `<biome>.json` file and paste it into the custom biome folder located at `*/<world name>/settings/biomes/custom`  
4. Change the name of the biome to any name you desire. 

{% hint style="warning" %}
> Do not change the file extensions `(.json)` as it will not be recognized if you do.
{% endhint %}

5. Remove the region folder from the world you are making the custom biome for. \(The regions folder can be found at `*/<world name>/regions`\)  
6. Start the server your server and make sure the "custom" biome is enabled when you do `/ewg tp <name>`, replacing `<name>` by the name you gave the file.

 or by checking the list.

{% hint style="info" %}
> If the biome is not recognized in game, check your console log. All biomes are listed there upon server startup.
{% endhint %}

## Customization

{% hint style="success" %}
> You can check [this ](https://docs.dynamic-bytes.com/beginner/world-configuration/biome-settings)for a full guide on biome settings.
{% endhint %}

#### Configure spawning properties

Listed here are the most important ones.

```javascript
"biomeType": "<type>"
```

You can replace `<type>` with: `DESERT, AQUATIC, GRASSLAND, FOREST`and `TUNDRA`. This setting groups this biome with other, similar biomes to make the world feel more natural. This prevents unrealistic scenarios, like deserts and ice biomes spawning next to one-another.

#### Configure terrain properties

```javascript
{
  "terrainSettings": {
    "subTerrains": [ //List of the biomes included in the custom biome. Do this by copying the same format and pasting but changing the name of the biome provided
      {
        "provider": "EWG", //This lets the plugin know whether the plugin is generating the biome or Minecraft is
        "name": "Bonsai Forest", //This lets the plugin know the terrain that it is loading
        "xModifier": 1.0, //Stretches the biome, create bigger (not taller) mountains.
        "yModifer": 0.5, //Higher numbers, more height in terrain. It generally creates more mountains and makes them higher.
        "zModifer": 1.0, //Same concept as X
        "yOffset": 0 //Cuts off rows of the bottom layer of the world. No touchy.
      },
      {
        "provider": "MINECRAFT", //Telling the plugin that the terrain provider is a vanilla biome
        "name": "mutated_ice_flats", //Telling the plugin the name of the biome, mutated_<name>
        "xModifier": 1.0,
        "yModifer": 0.5,
        "zModifer": 1.0,
        "yOffset": 0
      }
    ]
  }
}
```

{% hint style="info" %}
> There is a scrollbar at the bottom, so you can see the full comment lines.
{% endhint %}

All vanilla biome names can be found [here](http://minecraft.gamepedia.com/Biome#Biome_types).

#### Configure overlay

```javascript
      "overlaySettings": {
        "spawnLillypads": false,
        "spawnCactus": false,
        "spawnSnowLayers": false,
        "spawnIceOnWater": false,
        "minRiver": 2.0,
        "groundDepth": 4,
        "surfaceDepth": 1,
        "surfaceBlocks": [ //The blocks that will spawn on top of the terrain
          [//Define group, this is group 1, meaning this is the first group of blocks the plugin loop thru
           //When a block is choosed in a group and the conditions of the block does not match, then the plugin will go to next group. 
            [//Define the list of blocks in the group
              {//Define the first block in the group
                "type": "STAINED_CLAY", //Block type
                "data": 9, //Block data
                "inclinationsConditions": [ //A condition on when this block should spawn, this is why they are grouped, becaused even if their is a 100% chance for this to spawn, if the condition is wrong, then then it will jump to next group
                  {
                    "minInclination": 2.3, //When the height difference between 4 blocks is 2.3 of bigger
                    "maxInclination": 99.0 //"infinity"
                  }
                ]
              },
              1.0 //Chance for the block to spawn
            ]
          ],
          [//Next group
            [
              {
                "type": "STONE",
                "data": 0,
                "inclinationsConditions": [
                  {
                    "minInclination": 1.3,
                    "maxInclination": 1.7
                  }
                ]
              },
              0.4
            ],
            [
              {
                "type": "COBBLESTONE",
                "data": 0,
                "inclinationsConditions": [
                  {
                    "minInclination": 1.3,
                    "maxInclination": 1.7
                  }
                ]
              },
              0.3
            ],
            [
              {
                "type": "STONE",
                "data": 5,
                "inclinationsConditions": [
                  {
                    "minInclination": 1.3,
                    "maxInclination": 1.7
                  }
                ]
              },
              0.3
            ]
          ],
          [//Last group, sort of fallback group if non of the groups above went thru
            [
              {
                "type": "GRASS",
                "data": 0
              },
              1.0
            ]
          ]
        ],
        "oceanBlocks": [], //Same goes here, with groups etc
```

#### Support

If you have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

