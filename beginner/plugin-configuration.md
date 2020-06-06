---
description: >-
  This describes the settings which you can find in the settings file in your
  plugin folder.
---

# Plugin configuration

{% hint style="success" %}
> This is not where you get information on how to edit your biomes / customise your world. You can find that [here](https://docs.dynamic-bytes.com/beginner/world-configuration).
{% endhint %}

The plugin mainly uses the `settings` folder for individual biome / world generation settings. However, the plugin also has a few server-wide settings. These settings contain settings like a blacklist for which worlds to apply EWG to.

The setting file is location at

```text
*/plugins/EpicWorldGenerator/settings.json
```

### Settings

Although the file starts with an `"info"` setting, you can completely ignore that line. It does not affect anything.

#### Worlds With Default World Generation

This setting contains a list of the worlds that you do not want EWG to apply to. The default looks similar to this:

```text
  "worldsWithDefaultWG": [
    "world"
  ],
```

{% hint style="warning" %}
> The worlds in this list are CaPs SeNsItIvE. Meaning `"World"` does not world for `"world"`.
{% endhint %}

If you want to add more than one world to this setting, the list must continue like follows:

```text
  "worldsWithDefaultWG": [
    "world1",
    "world2",
    "world3",
    "world4"
  ],
```

{% hint style="info" %}
> After each `"world"` comes a comma, except for the last, where it does not.
{% endhint %}

#### 1.7 Map

This feature is toggled on when you are in need of a 1.7 map generation algorithm. It's not a good idea to use this, since it isn't properly supported anymore.

```text
  "minecraft_1_7_Map": false,
```

#### Control Water Flow

This setting can be turned off in the event you do not want EWG to take over water flowing in the world. It is not advisable to use this setting, since there might be a lot of issues and even errors as a result.

```text
  "controlWaterFlow": true,
```

#### Enable Generator Swap

This setting is used in [image to world generation](https://docs.dynamic-bytes.com/beginner/world-configuration/generate-world-from-image).

```text
  "enableGeneratorSwap": false
```

#### Support

If you have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

