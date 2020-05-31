# Frequently Asked Questions

## Contents:
1. Where do I find the configuration files?
2. Where can I find pre-made configurations?
3. Why do "chunk borders", missing chunks and/or weird transitions appear in my world?
4. Why are there no ores in my world?

### 1. Where do I find the configuration files?

All of the following settings can be found in this folder:
* World settings
* Default biome settings
* Custom biome settings (if you added any)
* Chest settings

```bash
*/<world folder>/settings/
```

Each of the individual settings can then be found under:

```bash
 world-settings.json # World settings.
 biomes
    default # Default biome settings folder.
    custom # Custom biome settings folder.
 chest-configuration # Chest settings.
```

The schematics and general settings can be found at;

```bash
*/plugins/EpicWorldGenerator/settings.json # General settings.
*/plugins/EpicWorldGenerator/EWGFiles # Folder with schematics.
```

### 2. Where can I find pre-made configurations?

Type `/ewg createworld` for a default preset, or visit the media channel in our [Discord](https://discord.gg/Jq3ecb3), which you can access after you [#verify-purchases](https://discordapp.com/channels/576841187256827905/588109256377499667/588110048543375391) \(make sure to carefully follow the instructions\) by clicking here: [#media](https://discordapp.com/channels/576841187256827905/576844840847802398).

### 3. Why do "chunk borders", missing chunks and/or weird transitions appear in my world?

In the vast majority of the cases in which this occurs, it is cuased by user-error. The most common reasons are as follows;

* Changes have been made in the configuration files after the first chunks have already been generated.
> Every time you do configuration changes that are not related to structures or terrain overlay, it is required to do a full reset of the world. You can do so by deleting the `*/<world name>/regions` folder from your world.
* You have updated the plugin and new and old versions are not compatible with eachother \(mainly occurs with transitions from v6 to v7, but the plugin should prevent you from updating by crashing the server and linking you to a guide on how you can migrate\)
* Chunks had been generated in the world by vanilla minecraft before you installed the plugin.
> Before making a world with this plugin, you must make sure that the region folder (`*/<world name>/regions*`) was removed after the plugin was installed.

It is limited what you can do to resolve the problem, but here are some tips;

* Delete the region files \(See [Region file tool](https://dinnerbone.com/minecraft/tools/coordinates/) for chunk/coordinate to file conversion\). The chunk files are saved at `*/<world name>/region/*`.
* Trim the world using world border, if the new chunks are on the edge of the map; [WorldBorder Plugin](http://dev.bukkit.org/bukkit-plugins/worldborder/), using the `/worldborder trim` command.
* Overhaul **all** the chunks in the world using the force generation toold provided by [WorldBorder](http://dev.bukkit.org/bukkit-plugins/worldborder/); `/worldborder fill 20 208 true`.
* Use the world edit's `//regen` command.

### 4. Why are there no ores in my world?
The reason no ores are spawning in your world is because of recent changes to the way ores are generated.
You can get your ores back by doing the following:

1. Find your world folder and locate the settings folder that EWG created (`*<world name>/settings`).
2. Download the .rar folder from [here](https://discord.com/channels/576841187256827905/576844840847802398/711257243953266755) and replace the biomes folders in the settings folder with its contents. (`*/<world name>/settings/biomes`).
3. Download the .zip file from ([here](https://1drv.ms/u/s!AmrRJ70wu8OUgZFrT8lExKbsl8NSmw?e=CgumZH) and copy-paste **only** the EpicWorldGenerator folder to your `*/plugins` folder, replacing the one already in there.
4. Remove all the region files from your world after stopping your server. (`*/<world name>/region`).
> This will remove the world in its whole.
5. Start the server (and pre-generate the world).

### Support
If you are still having issues after attempting to resolve your issue using this file,
make sure to contact support on our [Discord](https://discord.gg/Jq3ecb3).

#### Back to: [Table of contents](table-of-contents.md).
