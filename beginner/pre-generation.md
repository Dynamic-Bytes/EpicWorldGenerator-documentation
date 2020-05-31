# Pre-generation
This is a dual guide on both WorldBorder and Chunkmaster.
WorldBorder is a more well-known and overall better integrated plugin (works better with other plugins, ususally).
Though, on the other side, Chunkmaster is much, much faster when it comes to generating a world.

> In order to be able to use this, make sure you [have EWG installed](basic-installation.md "Link to EWG installation")


> EpicWorldGenerator comes with a setting that allows you to cut off the world at a certain square size. Check [this](world-configuration-world.md "Link to world configuration") under the world border header.

### [World Border](https://www.spigotmc.org/resources/worldborder.60905/ "Link to WorldBorder")
*(Click the title for a link to the plugin)*

> Note that it is advisable to use 8 GB of RAM **at a bare minumum** in this process. 10 GB or more is preffered.

After completing the basic EWG installation, adding any custom biomes you might want (like: [Maiskorf's Additional Biome Pack](https://1drv.ms/u/s!AmrRJ70wu8OUgZFrT8lExKbsl8NSmw?e=CgumZH "Link to the biomepack") and a [required fix](https://discord.com/channels/576841187256827905/576844840847802398/711257243953266755 "Link to the fix")), follow the upcoming list of actions, in order to fully pre-generate your world.
1. Download [World Border](https://www.spigotmc.org/resources/worldborder.60905/ "Link to WorldBorder") and put it in your `*/plugins` folder.
2. Start the server.
3. Set a default world border shape: `/worldborder shape <round|square>`
4. Set a world border (in the main world which you want to generate): `/wb set <sizeX> <centerX> <centerZ>`
> The `<sizeX>` parameter is replaced by the distance from `<centerX>, <centerZ>` to the border. `<centerX> and <centerZ>` are the (rounded) coordinates of the center of the world, usually 0 and 0.
5. Fill the world with chunks: `/wb <world name> fill 20 <padding> true`
> Replace `<world name>` by the exact, higher- and lowercase sensitive, name of the world (usually "world"). Also, replace `<padding>` with the outcome of the following function: `32 * (renderdistance + 1)`. You can find the render distance in your `*/server.properties` file on the fourth line: `view-distance=8`. Eg. (using 8 as the render distance in the "world" world): `32 * (8+1) = 288`, so you would ultimately run `/wb world fill 20 288 true`.
6. Confirm the fill command by using `/wb fill confirm`.
> Note that if, at any point in the process of the filling process, the server **crashes** (restarting doesn\'t matter), you must run `/wb fill cancel` as soon as the server starts again, and continue the process with the same command as before, but using `false` at the end (to stick with the example: `/wb world fill 20 288 false`, followed, once again, by `/wb fill confirm`)
7. Wait for the world generation to be done and enjoy the map!
> You can check on the progress of the generation task in the console.

### [Chunkmaster](https://www.spigotmc.org/resources/chunkmaster.71351/ "Link to Chunkmaster")
*(Click the title for a link to the plugin)*

> Note that a pre-generation process can take a large amount of RAM. This plugin is more lightweight and generally better at managing RAM, but keep in mind that 5 GB or more is still needed for this to work properly.

> For the highest speed of generation, use this plugin on Paper, rather than Spigot.

After completing the basic EWG installation, adding any custom biomes you might want (like: [Maiskorf's Additional Biome Pack](https://1drv.ms/u/s!AmrRJ70wu8OUgZFrT8lExKbsl8NSmw?e=CgumZH "Link to the biomepack") and a [required fix](https://discord.com/channels/576841187256827905/576844840847802398/711257243953266755 "Link to the fix")), follow the upcoming list of actions, in order to fully pre-generate your world.
1. Download [Chunkmaster](https://www.spigotmc.org/resources/chunkmaster.71351/ "Link to Chunkmaster") and put it in your `*/plugins` folder.
2. Start the server to generate a configuration file for the plugin, and stop the server.
3. Locate and open the configuration file at `*/plugins/chunkmaster/config.yml`.
4. In this file, consider the following settings:

| Setting: default | Options | Description | Recommended |
| ------- | ------- | ----------- | ----------- |
| dynmap: true | true or false | Turns Dynmap support on or off, increases speed when off. | false |
| max-loaded-chunks: 10 | positive round number (integer) | Higher means more RAM usage but higher speed, lower the opposite. | 10 to 20 |
| max-pending-chunks: 10 | positive round number (integer) | Comparable to the one before, but impacts RAM more and also impacts CPU. | 10 to 20 |
| period: 2 | positive round number (integer) | How many ticks between generation, best to keep at 2, unless your CPU runs full, then make it higher. | 2 |
| chunks-per-step: 2 | positive round number (integer) | How many chunks are generated per period (see setting above), higher means severe performance increase, but also speeds up generation. | 2 or 3 |
| chunk-skips-per-step: 20 | positive round number (integer) | How many already-generated chunks can be skipped every period (see setting on period). Higher means faster, but increases CPU load. | 20 |
| pause-on-join: true | true or false | Stops the generation task when a player joins, best to keep on true, but make sure not to AFK on the server. | true | 
5. Start the generation by using: `/chunkmaster generate <world name> <distance> blockradius`.
> Replace `<world name>` by the exact, higher- and lowercase sensitive, name of the world (usually "world"). Also, replace `<distance>` with the amount of blocks you want in all directions (makes a square). Example (using "world" and a 100.000 block radius): `/chm generate world 100000 blockradius`.  
6. Leave the server (so the generation task starts, unless you have `pause-on-join:` set to `false`).
7. Wait for the world generation to be done and enjoy the map!
> You can check up on the progress of the generation task in the console.

### Support
If you run into issues with any of these commands, make sure to contact our support team on our [Discord](https://discord.gg/Jq3ecb3 "Link to our discord").

#### Back to: [Table of contents](table-of-contents.md "Link to table of contents").
