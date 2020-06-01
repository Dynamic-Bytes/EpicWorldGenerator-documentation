---
description: Customise the ores in your world
---

# Customise ores

{% hint style="info" %}
> Ores can be configured individually for each biome, this means you will find the ore settings within each individual biome file at `*/<world folder>/settings/biomes/default/<biome name>.json`
{% endhint %}

The plugin allows you to take full control over the ores. You can create your own ores, remove the default ores or change the way that the default ores spawn in around the world.

{% hint style="info" %}
> Note that "ores" does not have to mean the generic ores like diamonds, emeralds, or similar blocks. Ores can be any block, like dirt for example. Click [here ](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)for a list of all types of blocks, which you can all use as ores.
{% endhint %}

By default, EWG will not directly handle ores, but let vanilla generation take over. To enable custom ore generation, make sure the following vanilla property is **not** in the list of `"vanillaFeatures"`:

```javascript
"vanillaFeatures": [ 
  "UNDERGROUND_ORES",
  ...
]
```

If it is in there, disable it by removing the property. 

Here is the default configuration to make ores spawn **exactly** like in vanilla, using the custom generation tool.

{% hint style="info" %}
To apply this setting to any of your biome files, replace the **entire** `"oreGenerators": []`section. Make sure to also remove all the comments which start with `//` because they will prevent the ores from generating altogether. 
{% endhint %}

```javascript
  "oreGenerators": [
    {
      "type": "NATURAL_STONE", // ore generator algorithm (in this case, vein)
      "block": {
        "type": "DIRT", // ore material
        "tags": {} // block state tags https://minecraft.gamepedia.com/Block_states
      },
      "size": 33, // The maximum number of blocks that can be spawned in as a group. 
      "count": 10, // The number of times the world generator attempts to place a vein (or group) of the ores in a chunk. (higher value = more veins, and therefore more of this ore)
      "bottomOffset": 0, // spawn from y level
      "topOffset": 0, // Offset from surface level
      "maximum": 256 // Max y level (bottomOffset + maximum)
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "GRAVEL",
        "tags": {}
      },
      "size": 33,
      "count": 8,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 256
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "GRANITE",
        "tags": {}
      },
      "size": 33,
      "count": 10,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 256
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "DIORITE",
        "tags": {}
      },
      "size": 33,
      "count": 10,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 256
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "ANDESITE",
        "tags": {}
      },
      "size": 33,
      "count": 10,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 256
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "COAL_ORE",
        "tags": {}
      },
      "size": 17,
      "count": 20,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 128
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "IRON_ORE",
        "tags": {}
      },
      "size": 9,
      "count": 20,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 64
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "GOLD_ORE",
        "tags": {}
      },
      "size": 9,
      "count": 2,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 32
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "REDSTONE_ORE",
        "tags": {}
      },
      "size": 8,
      "count": 10,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 16
    },
    {
      "type": "NATURAL_STONE",
      "block": {
        "type": "DIAMOND_ORE",
        "tags": {}
      },
      "size": 8,
      "count": 1,
      "bottomOffset": 0,
      "topOffset": 0,
      "maximum": 16
    },
    {
      "type": "EMERALD", // different generator algorithm, different options
      "block": {
        "type": "EMERALD_ORE",
        "tags": {}
      },
      "replaceBlock": {
        "type": "STONE", //block to replace
        "tags": {}
      }
    },
    {
      "type": "LAPIS", 
      "block": {
        "type": "LAPIS_ORE",
        "tags": {}
      },
      "size": 7,
      "count": 1,
      "baseline": 16, // distribution top, see https://upload.wikimedia.org/wikipedia/commons/8/8c/Standard_deviation_diagram.svg
      "spread": 16 // distrubtion spread
    }
  ],
```

You can modify all these settings to your liking, or you can keep them them as default, though that wouldn't be any fun, would it? Ores can take your server to the next level, using in-depth customization that your players will enjoy and love. Most importantly, you can customize the ores in order to make it fit with the style of your server; OP Factions, for instance, should have a more common way of getting ores like diamonds and emerald. However, servers like Hardcore Survival, or other types, should have a much harder way of getting ores. Lastly, if you were to make a modded server, you can add the custom ores to the generation. You can make ores hard to get by decreasing the maximum height \(Y-level\) value, and decreasing the size and count, or make them more common by taking those steps in reverse. Good luck!

#### Support

If you have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

