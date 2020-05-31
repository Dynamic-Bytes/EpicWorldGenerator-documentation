---
description: Importing vanilla biomes to co-exist with the custom terrain
---

# Importing vanilla biomes

The plugin allow you to import vanilla biomes into the plugin. You will need to follow a couple of steps to do this without corrupting or ruining the world.

1. Create a new custom biome \([see this guide](https://docs.dynamic-bytes.com/intermediate/create-biome)\)
2. Make the custom biome spawn by editing the world settings \([see this guide](https://docs.dynamic-bytes.com/beginner/world-settings)\)
3. Add the native biome settings;

```javascript
  "nativeBiome": "mutated_jungle", //Tells the plugin the name of the native biome. Native biome names, names for 1.10 is listed here; http://jetpad.io/65d7ba2
  "useNativePainting": true, //Spawn grass on the floor, stone in hilly areas etc.
  "useNativeStructure": true, //Spawns trees and small structures like lakes, ice spikes etc.
  "terrainSettings": {
    "subTerrains": [
      {
        "provider": "MINECRAFT",//Tells the plugin that minecraft provide the biome and not the plugin
        "name": "mutated_jungle", //Native biome name
        "xModifier": 1.0,
        "yModifer": 1.0,
        "zModifer": 1.0,
        "yOffset": 0
      }
    ]
  },

  "nativeBiomes": [ //Need to match the native biome name to work correctly (Bukkit name)
    {
      "nativeBiome": "JUNGLE",
      "chance": 0.8
    }
  ],
```

The native biome name can be found using the ID to the biome. The ID to biome can be found here;  
[http://minecraft.gamepedia.com/Biome](http://minecraft.gamepedia.com/Biome)

The table to find the right name can be found here. It is snippet of the biome code in spigot 1.11 \(second name in the "table", eg "mushroom\_island\_shore"\);  
[http://pastebin.com/ZqPqWhGq](http://pastebin.com/ZqPqWhGq)

#### Support

If you have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

