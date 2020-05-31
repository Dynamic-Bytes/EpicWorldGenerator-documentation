# Pre-generation
This is a dual guide on both WorldBorder and Chunkmaster.
WorldBorder is a more well-known and overall better integrated plugin (works better with other plugins, ususally).
Though, on the other side, Chunkmaster is much, much faster when it comes to generating a world.

> In order to be able to use this, make sure you [have EWG installed](basic-installation.md "Link to EWG installation")


> EpicWorldGenerator comes with a setting that allows you to cut off the world at a certain square size. Check [this]( "Link to world configuration") under the world border header.

### [World Border](https://www.spigotmc.org/resources/worldborder.60905/ "Link to WorldBorder")
*(Click the title for a link to the plugin)*

> Note that it is advisable to use **at a bare minumum** 8 GB of RAM in this process. 10 GB or more is preffered.

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

### [Chunkmaster](https://www.spigotmc.org/resources/chunkmaster.71351/ "Link to Chunkmaster")
*(Click the title for a link to the plugin)*
