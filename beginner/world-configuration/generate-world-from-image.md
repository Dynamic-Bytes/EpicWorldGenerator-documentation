---
description: 'You can take full control over the generation of your world, block by block.'
---

# Generate World from Image

![Custom world](http://i.imgur.com/b84tZgQ.png)

Take full control over the plugin by telling the plugin to create a world based on an image you give it. Paint every detail of the world. For example, you can make islands, rivers, or even generate a world based on your server logo or a map of the planet itself \(check the example below\).

### Example

![Map](http://i.imgur.com/AV2md6W.png)

#### Image vs Dynmap

[http://i.imgur.com/SiJ6ccr.mp4](http://i.imgur.com/SiJ6ccr.mp4)

#### In-game Images

![ingame](http://i.imgur.com/b84tZgQ.png) ![ingame](http://i.imgur.com/O4uIC8B.png) ![ingame](http://i.imgur.com/4MuaNdJ.png)

### Generate your own image-based world

1. Create a new image in your favorite editor \(Photoshop, Gimp, Paint, etc\). Each pixel of your image will equal 1 in-game block \(i.e. a 5000x5000px image will create a 5000x5000 block map\). Once you've created your map, save it as a PNG called `map.png` \(it must be in the PNG format with this exact name\). Upload the image to your server.

{% hint style="info" %}
> If you want to change the default 1-to-1 scale to something else, you can do so using the "Map Scale" setting found halfway down [this page](./).
{% endhint %}

2. Enable the feature in the config file of EWG \(located at `*/plugins/EpicWorldGenerator/settings.json` \) and set`"enableGeneratorSwap":` to `true`

3. Place the map.png image file into the `<world folder>` of the world you want to create at  
`*/<world folder>/settings/map.png`

{% hint style="warning" %}
> If the world has already been created \(which is normal\), then you have to delete all files in that folder and then add the `map.png` file there. Note that this will wipe that map.
{% endhint %}

{% hint style="danger" %}
> The file must be named `map.png`
{% endhint %}

4. Start the server

5. [Pre-generate](https://docs.dynamic-bytes.com/beginner/world-configuration/generate-world-from-image) the map \(highly recommended\)

6. Join the world \(using `/mv teleport` if you use [MultiVerse - core](https://dev.bukkit.org/projects/multiverse-core)\)

In the example above. We used this image, named it `map.png` and placed it in the folder; 

![https://upload.wikimedia.org/wikipedia/commons/8/8f/Whole\_world\_-\_land\_and\_oceans\_12000.jpg](https://upload.wikimedia.org/wikipedia/commons/8/8f/Whole_world_-_land_and_oceans_12000.jpg)

### Take control

Each biome has its own color property. This property is used to find the biome to match any pixel in the image. You can add multiple colors to each biome using the config files for each biomes. Inside the config file, you will find something like this:

```javascript
  "biomeColors": [
      "#030605",
      "#130605"
   ],
```

Add or change colors here to link the biomes to different colors on the image.

{% hint style="info" %}
> Note that it does pick the biome which has the `"biomeColors"` value that is the closest to the color on the `map.png`
{% endhint %}

#### Support

If you have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

