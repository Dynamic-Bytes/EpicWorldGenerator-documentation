---
description: The FAQ section - Quite a few regular issues are listed here
---

# Frequently Asked Questions

### Contents:

* I. Where do I find the configuration files?
* II. Where can I find pre-made configurations?
* III. Why do "chunk borders", missing chunks and/or weird transitions appear in my world?
* IV. Why are there no ores in my world?
* V. Why does my server not start?
  * V.I Issue with verification / backend server
* VI. Why does my server randomly crash?
  * VI.I Issue with moisture
  * VI.II Issue with missing structure\(s\)
* VII. How do I pre-generate a world?
* VIII. How do I disable biomes I don't like?

#### I. Where do I find the configuration files?

All of the following settings can be found in this folder:

* World settings
* Default biome settings
* Custom biome settings \(if you added any\)
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

#### II. Where can I find pre-made configurations?

Type `/ewg createworld` for a default preset, or visit the media channel in our [Discord](https://discord.gg/Jq3ecb3), which you can access after you [\#verify-purchases](https://discordapp.com/channels/576841187256827905/588109256377499667/588110048543375391) \(make sure to carefully follow the instructions\) by clicking here: [\#media](https://discordapp.com/channels/576841187256827905/576844840847802398).

#### III. Why do "chunk borders", missing chunks and/or weird transitions appear in my world?

In the vast majority of the cases in which this occurs, it is cuased by user-error. The most common reasons are as follows;

* Changes have been made in the configuration files after the first chunks have already been generated.

  > Every time you do configuration changes that are not related to structures or terrain overlay, it is required to do a full reset of the world. You can do so by deleting the `*/<world name>/regions` folder from your world.

* You have updated the plugin and new and old versions are not compatible with eachother \(mainly occurs with transitions from v6 to v7, but the plugin should prevent you from updating by crashing the server and linking you to a guide on how you can migrate\)
* Chunks had been generated in the world by vanilla minecraft before you installed the plugin.

  > Before making a world with this plugin, you must make sure that the region folder \(`*/<world name>/regions`\) was removed after the plugin was installed.

It is limited what you can do to resolve the problem, but here are some tips;

* Delete the region files \(See [region file tool](https://dinnerbone.com/minecraft/tools/coordinates/) for chunk/coordinate to file conversion\). The chunk files are saved at `*/<world name>/region/`.
* Trim the world using world border, if the new chunks are on the edge of the map; [WorldBorder Plugin](https://www.spigotmc.org/resources/worldborder.60905/), using the `/worldborder trim` command.
* Overhaul **all** the chunks in the world using the force generation toold provided by [WorldBorder](https://www.spigotmc.org/resources/worldborder.60905/); `/worldborder fill 20 208 true`.
* Use the world edit's `//regen` command.

#### IV. Why are there no ores in my world?

The reason no ores are spawning in your world is because of recent changes to the way ores are generated. You can get your ores back by doing the following:

1. Find your world folder and locate the settings folder that EWG created \(`*<world name>/settings`\).
2. Download the .rar folder from [here](https://discord.com/channels/576841187256827905/576844840847802398/711257243953266755) and replace the biomes folders in the settings folder with its contents. \(`*/<world name>/settings/biomes`\).
3. Download the .zip file from [here](https://1drv.ms/u/s!AmrRJ70wu8OUgZFrT8lExKbsl8NSmw?e=CgumZH) and copy-paste **only** the EpicWorldGenerator folder to your `*/plugins` folder, replacing the one already in there.
4. Remove all the region files from your world after stopping your server. \(`*/<world name>/region`\).

   > This will remove the world in its whole.

5. Start the server \(and pre-generate the world\).

#### V. Why does my server not start?

**V.I Issue with verification / backend server**

Occasionally, upon a fresh install \(first time you run the server with the plugin on it\), the server will raise an error with the plugin not being able to activate. There are two types;   
  
Type 1 - Invalid license

 ![Invalid License Log](https://i.imgur.com/xzs3tsy.png)   
  
Type 2 - Unable to reach backend servers

 ![Connection error log](https://i.imgur.com/xnjGbb1.png)

These issues are ususally a connection issue between your and our server\(s\). The main way this can be resolved \(from your end, at first\) is by checking your firewall settings and making sure you have a working internet connection for your server. If you did both those things, and it is still not working, make sure to reach out to our [Discord](https://discord.gg/Jq3ecb3) support team.

#### VI. Why does my server randomly crash?

**VI.I Issue with moisture**

![Moisture crash log](https://i.imgur.com/3vTriQt.png) 

This issue is caused by an update to the way dataTags are handeled in EWG. It is no longer required to use the datatags, and they must be removed. This should be done by default in the latest version of the plugin. Navigate to the following file: `*/<world name>/settings/biomes/default/farmland.json`, Scroll down to the part that looks like the following \(should be around line 590, before the custom structures\):

```javascript
    "fieldGroundBlock": {
      "type": "FARMLAND",
      "data": 7,
      "chance": 0.0
    }
```

Replace this **entire** block of code with the following:

```javascript
    "fieldGroundBlock": []
```

Restart the server, and you should be good to go.

> Make sure to also remove the closing `}`.

#### VII. How do I pre-generate a world?

Pre-generating a world is always recommended in order to prevent issues with missing chunks. Example: ![Missing chunks](https://i.imgur.com/PGN28u3.png)

Click [here](beginner/pre-generation.md) to get a guide.

#### VIII. How do I disable biomes I don't like?

You might have biomes you do not like. There is a simple 4 step plan to disable them. 1. Find the biome, fly over it and do `/ewg info` and remember or write down the biome name. 2. Go into the following folder in your server: `*/<world name>/settings/biomes/` and open either `custom` or `default`, depending on which folder the specific biome is in. 3. Find and open the biome file with the same name as `/ewg info` returned. 4. Change `"enabled": true,` to `"enabled": false`. Repeat this for every biome you don't like.

> If you have any missing or broken chunks, check out **VII. How do I pre-generate a world?**, which is above here.

#### Support

If you are still having issues after attempting to resolve your issue using this file, make sure to contact support on our [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

