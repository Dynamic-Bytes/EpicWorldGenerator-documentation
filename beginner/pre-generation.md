---
description: Guide on pre-generating your map. Advisable to prevent lag.
---

# Pre-generation

This is a dual guide on both WorldBorder and Chunkmaster. WorldBorder is a more well-known and overall better integrated plugin \(works better with other plugins, usually\). Though, on the other side, Chunkmaster is much, much faster when it comes to generating a world.

{% hint style="success" %}
> We advise you to make use of Chunkmaster for pre-generating your world over WorldBorder. This is because \(after thorough testing\) we found a 50% speed increase at the start, and no memory leak in the long term. You can use WorldBorder alonside Chunkmaster.
{% endhint %}

{% hint style="warning" %}
> In order to be able to use this, make sure you [have EWG installed](basic-installation.md)
{% endhint %}

{% hint style="info" %}
> EpicWorldGenerator comes with a setting that allows you to cut off the world at a certain square size. Check [this](https://docs.dynamic-bytes.com/beginner/world-settings) under the world border header.
{% endhint %}

{% hint style="warning" %}
> With both of the installations, the plugin may very well throw errors where it either `Tried to load a block entity for block` or `Tried to load a DUMMY block entity` and failed. Do not worry, this will have no noticeable effect on the map.
{% endhint %}

#### [World Border](https://www.spigotmc.org/resources/worldborder.60905/)

_\(Click the title for a link to the plugin\)_

{% hint style="info" %}
> Note that it is advisable to use 8 GB of RAM **at a bare minimum** in this process. 10 GB or more is preferred.
{% endhint %}

After completing the basic EWG installation, adding any custom biomes you might want \(like: [Maiskorf's Additional Biome Pack](https://docs.dynamic-bytes.com/beginner/recommended-installation/maiskorfs-additional-biome-pack)\), follow the upcoming list of actions, in order to fully pre-generate your world.   
  
1. Download [World Border](https://www.spigotmc.org/resources/worldborder.60905/) and put it in your `*/plugins` folder.   
2. Start the server.   
3. Set a default world border shape: `/worldborder shape <round|square>`   
4. Set a world border \(in the main world which you want to generate\): `/wb set <sizeX> <centerX> <centerZ>`

{% hint style="info" %}
> The `<sizeX>` parameter is replaced by the distance from `<centerX>, <centerZ>` to the border. `<centerX> and <centerZ>` are the \(rounded\) coordinates of the center of the world, usually 0 and 0.
{% endhint %}

5. Fill the world with chunks: `/wb <world name> fill 20 <padding> true` 

{% hint style="info" %}
> Replace `<world name>` by the exact, higher- and lowercase sensitive, name of the world \(usually "world"\). Also, replace `<padding>` with the outcome of the following function: `32 * (renderdistance + 1)`. You can find the render distance in your `*/server.properties` file on the fourth line: `view-distance=8`. Eg. \(using 8 as the render distance in the "world" world\): `32 * (8+1) = 288`, so you would ultimately run `/wb world fill 20 288 true`.
{% endhint %}

6. Confirm the fill command by using `/wb fill confirm`. 

{% hint style="warning" %}
> Note that if, at any point in the process of the filling process, the server **crashes** \(restarting doesn't matter\), you must run `/wb fill cancel` as soon as the server starts again, and continue the process with the same command as before, but using `false` at the end \(to stick with the example: `/wb world fill 20 288 false`, followed, once again, by `/wb fill confirm`\)
{% endhint %}

7. Wait for the world generation to be done and enjoy the map! 

{% hint style="info" %}
> You can check on the progress of the generation task in the console.
{% endhint %}

#### [Chunkmaster](https://www.spigotmc.org/resources/chunkmaster.71351/)

_\(Click the title for a link to the plugin\)_

{% hint style="warning" %}
> Note that a pre-generation process can take a large amount of RAM. This plugin is more lightweight and generally better at managing RAM than WorldBorder, but keep in mind that 5 GB or more is still advisable for this to work at reasonable performance or better.
{% endhint %}

{% hint style="success" %}
> For the highest speed of generation, use this plugin on [Paper](https://papermc.io/downloads), rather than [Spigot](https://hub.spigotmc.org/jenkins/job/BuildTools/org.spigotmc$builder/lastBuild/).
{% endhint %}

After completing the basic EWG installation, adding any custom biomes you might want \(like: [Maiskorf's Additional Biome Pack](https://docs.dynamic-bytes.com/beginner/recommended-installation/maiskorfs-additional-biome-pack)\), follow the upcoming list of actions, in order to fully pre-generate your world. 

1. Download [Chunkmaster](https://www.spigotmc.org/resources/chunkmaster.71351/) and put it in your `*/plugins` folder.   
2. Start the server to generate a configuration file for the plugin, and stop the server.   
3. Locate and open the configuration file at `*/plugins/chunkmaster/config.yml`.   
4. In this file, consider the following presets:

Low-end machines \(~5 GB RAM and low-end CPU's\):

```text
generation:
  period: 2
  chunks-per-step: 4
  chunk-skips-per-step: 100
  mspt-pause-threshold: 500
  pause-on-join: false
  max-pending-chunks: 15
  max-loaded-chunks: 15
  ignore-worldborder: true
database:
  filename: chunkmaster.db
language: en
dynmap: true
```

Mid-end machines \(~7 GB RAM and medium-end CPU's\):

```text
generation:
  period: 2
  chunks-per-step: 4
  chunk-skips-per-step: 100
  mspt-pause-threshold: 500
  pause-on-join: false
  max-pending-chunks: 20
  max-loaded-chunks: 20
  ignore-worldborder: true
database:
  filename: chunkmaster.db
language: en
dynmap: true
```

High-end machines \(&gt;8 GB RAM and medium-high-end CPU's\):

```text
generation:
  period: 2
  chunks-per-step: 4
  chunk-skips-per-step: 100
  mspt-pause-threshold: 500
  pause-on-join: false
  max-pending-chunks: 25
  max-loaded-chunks: 25
  ignore-worldborder: true
database:
  filename: chunkmaster.db
language: en
dynmap: true
```

Hosting server machines or extreme servers \(&gt;10 GB RAM and industrial CPU's used by hosting websites, many cores and threads\):

```text
generation:
  period: 2
  chunks-per-step: 4
  chunk-skips-per-step: 100
  mspt-pause-threshold: 500
  pause-on-join: false
  max-pending-chunks: 30
  max-loaded-chunks: 30
  ignore-worldborder: true
database:
  filename: chunkmaster.db
language: en
dynmap: true
```

{% hint style="info" %}
> In all of these presets the `dynmap:`setting is on `true`.  
> This allows you to render a [Dynmap](https://shockbyte.com/billing/knowledgebase/92/How-to-Set-Up-Dynmap.html) alongside generating the world, at the cost of about 10% performance. If you're not interested in a Dynmap, you are best off turning `dynmap:` to `false`.
{% endhint %}

5. Start the generation by using: `/chunkmaster generate <world name> <distance> blockradius`.

{% hint style="info" %}
> Replace `<world name>` by the exact, higher- and lowercase sensitive, name of the world \(usually "world"\). Also, replace `<distance>` with the amount of blocks you want in all directions \(makes a square\). Example \(using "world" and a 10,000 block radius\): `/chm generate world 10000 blockradius`.
{% endhint %}

6. Leave the server \(so the generation task starts, unless you have `pause-on-join:` set to `false`\).

{% hint style="danger" %}
> Right after running the command and leaving the server, you **must** check the console to see if it actually started. If it did not, use `chm resume 1` in the console. The 1 changes to a two, if this is the second time you run the plugin.
{% endhint %}

7. Wait for the world generation to be done and enjoy the map!

{% hint style="info" %}
> You can check up on the progress of the generation task in the console.
{% endhint %}

{% hint style="success" %}
> Please contact Coco if you are **not** getting more than an average of 25 chunks per seconds in the generation task, so we can improve performance and improve this tutorial.  
> \(Please don't jump to conclusions, and wait for at least 15 minutes to get an accurate speed\)
{% endhint %}

#### Support

If you run into issues with any of these steps, make sure to contact our support team on our [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

