# Customize ores

Ores can be configured individually for each biome, this means you will find the ore settings within each biome file.

```bash
<world folder>/settings/biomes/default/<biome name>.json
```

The plugin allows you to have full control over the ores. You can create your own ores, remove the default ores or change the way that the default ores spawn in around the world.

Keep in mind that by stating, "ores," it doesn't always refer to diamonds, emeralds, or similar items. Ores can be blocks as well like dirt. Visit here the link to see all types of ores. [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)

Ores has the following properties;

```javascript
  {
      "type": "DIRT", // Specify the block that you are customizing. MUST BE A NAME, NOT ID. For a list of valid names, see https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html
      "data": 0, // The number after the actual ID (Usually represented after "colon," or "slash" in game}. For a list of block data values, see http://minecraft-ids.grahamedgecombe.com/ (Example: <id>:<data>)
      "size": 33, //The maximum number of blocks that can be spawned in as a group. 
      "count": 10, //The number of times the world generator attempts to place a vein (or group) of the ores in a chunk. (higher value = more veins, and therefore more of this ore)
      "minHeight": 0, //The minumum height the ore can spawn at
      "maxHeight": 256 //The maximum height the ore can spawn at (256 is Minecrafts default height limit) (Should be around 30-50 for ores in styles of diamond, emerald, and red stone).
    }
```

By default, all the ores has the same spawning properties as you find in vanilla minecraft \(expect from emerald ore\). Here is the default configuration;

```javascript
  "ores": [
    {
      "type": "DIRT",
      "data": 0,
      "size": 33,
      "count": 10,
      "minHeight": 0,
      "maxHeight": 256
    },
    {
      "type": "GRAVEL",
      "data": 0,
      "size": 33,
      "count": 8,
      "minHeight": 0,
      "maxHeight": 256
    },
    {
      "type": "STONE",
      "data": 1,
      "size": 33,
      "count": 10,
      "minHeight": 0,
      "maxHeight": 80
    },
    {
      "type": "STONE",
      "data": 3,
      "size": 33,
      "count": 10,
      "minHeight": 0,
      "maxHeight": 80
    },
    {
      "type": "STONE",
      "data": 5,
      "size": 33,
      "count": 10,
      "minHeight": 0,
      "maxHeight": 80
    },
    {
      "type": "COAL_ORE",
      "data": 0,
      "size": 17,
      "count": 20,
      "minHeight": 0,
      "maxHeight": 128
    },
    {
      "type": "IRON_ORE",
      "data": 0,
      "size": 9,
      "count": 20,
      "minHeight": 0,
      "maxHeight": 64
    },
    {
      "type": "GOLD_ORE",
      "data": 0,
      "size": 9,
      "count": 2,
      "minHeight": 0,
      "maxHeight": 32
    },
    {
      "type": "REDSTONE_ORE",
      "data": 0,
      "size": 8,
      "count": 8,
      "minHeight": 0,
      "maxHeight": 16
    },
    {
      "type": "DIAMOND_ORE",
      "data": 0,
      "size": 8,
      "count": 1,
      "minHeight": 0,
      "maxHeight": 16
    },
    {
      "type": "LAPIS_ORE",
      "data": 0,
      "size": 7,
      "count": 1,
      "minHeight": 0,
      "maxHeight": 32
    },
    {
      "type": "EMERALD_ORE",
      "data": 0,
      "size": 4,
      "count": 2,
      "minHeight": 4,
      "maxHeight": 32
    }
  ],
```

The settings should be changed to your liking, and keeping them as default wouldn't be the best decision. Ores can give your server a new kind of customization that your players will enjoy and love. Most importantly, you can customize the ores in order to make it fit with the style of your server. OP Factions for instance should have a more common way of getting ores like diamonds and emerald. However, servers like Hardcore Survival, or other types, should have a much harder way of getting ores. You can make ores hard to get by decreasing the maximum height \(Y in minecraft\) value, and decreasing the size and count, or vise versa. Good luck!

