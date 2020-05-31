---
description: 'Create a world from an image, take full control over the world'
---

# Generate world from image

![Custom world](http://i.imgur.com/b84tZgQ.png)

Take full control of the plugin by telling the plugin to create a world based on an image you give it. Paint every detail of the world, for example, islands, river etc., or even generate a world based on your server logo.

## Example

To give you an example, we created "The earth" as Minecraft map ![Map](http://i.imgur.com/AV2md6W.png)

### Image vs dynmap

[http://i.imgur.com/SiJ6ccr.mp4](http://i.imgur.com/SiJ6ccr.mp4)

### In-game images

![ingame](http://i.imgur.com/b84tZgQ.png) ![ingame](http://i.imgur.com/O4uIC8B.png) ![ingame](http://i.imgur.com/4MuaNdJ.png)

## Generate your own image based world

1. Enable the feature in the config file to EWG \(located in the plugin folder\) `"enableGeneratorSwap": true` 
2. Place a png image into the world folder of the world you want to create

   `<sever dir>/<world folder>/settings/map.png`

3. Start the server
4. Import the world with /mv import  normal

In the example above. We used this image, named it map.png and placed it in the folder; [https://upload.wikimedia.org/wikipedia/commons/8/8f/Whole\_world\_-\_land\_and\_oceans\_12000.jpg](https://upload.wikimedia.org/wikipedia/commons/8/8f/Whole_world_-_land_and_oceans_12000.jpg)

## Take control

Each biome have its own colour property. This property is used to find the closest biome match to an pixel in the image. You can add multiple colours to each biome using the config files for each biomes. Inside the config file, you will find something like this:

```javascript
  "biomeColors": [
      "#030605",
      "#130605"
   ],
```

Add or change colours here to link the biomes to different colours on the image.

