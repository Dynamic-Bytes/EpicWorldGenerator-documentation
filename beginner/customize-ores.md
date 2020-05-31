# Customize ores

Ores can be configured individually for each biome, this means you will find the ore settings within each biome file.

```bash
<world folder>/settings/biomes/default/<biome name>.json
```

The plugin allows you to have full control over the ores. You can create your own ores, remove the default ores or change the way that the default ores spawn in around the world.

Keep in mind that by stating, "ores," it doesn't always refer to diamonds, emeralds, or similar items. Ores can be blocks as well like dirt. Visit here the link to see all types of ores. [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)



By default, EWG will not directly handle ores, if the following vanilla property is enabled:

```javascript
"vanillaFeatures": [ 
  "UNDERGROUND_ORES",
  ...
]
```

Disable it by removing the property. Here is the default configuration to make ores spawn **exactly** like in vanilla.

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

The settings should be changed to your liking, and keeping them as default wouldn't be the best decision. Ores can give your server a new kind of customization that your players will enjoy and love. Most importantly, you can customize the ores in order to make it fit with the style of your server. OP Factions for instance should have a more common way of getting ores like diamonds and emerald. However, servers like Hardcore Survival, or other types, should have a much harder way of getting ores. You can make ores hard to get by decreasing the maximum height \(Y in minecraft\) value, and decreasing the size and count, or vise versa. Good luck!

