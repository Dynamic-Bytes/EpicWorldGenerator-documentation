# Create a custom biome

### Create a new biome

Custom biomes can be easly created by copying a default biome by doing the following;

1. Go to the folder of your specified world, then travel into settings, then biomes, then default.
2. Find your desired biome to work out from.
3. Copy the &lt;biome&gt;.json file \(FileZilla is recommended for this procedure\), then upload \(or paste\) it onto  the custom folder located under the same biomes folder.
4. Change the name to your desired name. \(DO NOT CHANGE .JSON\)
5. Empty the world folder \(or any world name you have\) EXCEPT the settings folder.
6. Start the server your server and make sure the "custom" biome is listed when you do /ewg tp &lt;name&gt; or by checking the list.

### Configure spawning properties

```javascript
"biomeType": "<type>"
```

You can pick between, DESERT, AQUATIC, GRASSLAND, FOREST and TUNDRA.  
Where desert is the place for hot biomes and tundra is the place for cold biomes.

### Configure terrain

```javascript
{
  "terrainSettings": {
    "subTerrains": [ //List of the biomes included in the custom biome. Do this by copying the same format and pasting but changing the name of the                biome provided
      {
        "provider": "EWG", //This lets the plugin know whether the actual plugin is generating the biome or Minecraft is
        "name": "Bonsai Forest", //This lets the plugin know the terrain that it is loading
        "xModifier": 1.0, //Stretches the biome, create bigger mountains.
        "yModifer": 0.5, //Higher numbers, more height in terrain. It generally creates more mountains and makes them higher.
        "zModifer": 1.0, //Same concept as X
        "yOffset": 0 //Cuts off rows of the bottom layer of the world. Best to not touch.
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

All vanilla biome names can be found at;    
  
[http://minecraft.gamepedia.com/Biome\#Biome\_types](http://minecraft.gamepedia.com/Biome#Biome_types)

### Configure overlay

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

