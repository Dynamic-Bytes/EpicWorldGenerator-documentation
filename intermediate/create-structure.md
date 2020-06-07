---
description: 'Create your own, custom, structures for your world'
---

# Create structures

#### EWG objects

In EpicWorldGenerator, all structures is generated using "EWG Object". The object has multiple properties that can be defined using `.json` syntax. The most important property is the file the object refer to. All structures in EpicWorldGenerator needs to be saved as its own file with a .EWG extension. This file is made to optimize the speed and also store the anchor point to the object.

An EWG object can be used both under `"customTrees"` and `"customStructures"`.

{% hint style="success" %}
> A video tutorial on this process was made by Maiskorf. You can find this video [here](https://www.youtube.com/watch?v=q1sa6oVrN8Q&feature=youtu.be).  
> Keep in mind that this video might sligthly differ from the latest version.
{% endhint %}

#### Create a new structure file

1. Select an object using world edit
2. After, stand in the middle of the structure, or the center. click F3 and look at the column that shows the XYZ values. This feature is included in the installation of structures to prevent buildings being flown in mid-air.  Example: `/ewg create <center X> <center Y> <center Z> <name>`; type in only whole numbers, not decimals. 
3. The structure is now saved under the EpicWorldGenerator folder named `"EWGFiles"` , which you can find in your `*/plugins` folder.

#### Make the file generate

The file can be generated using different configurations. Each configuration has to contain the file name.

1. Open the biome file located at `*<world name>/settings/biomes/default/<biome>.json`
2. Find the `"customTrees"` or `"customStructures"` section, depending on if you want it to generate a tree or a structure
3. Put the following content in the list
4. Change where is specifies `"CUSTOM_jungle_tower"` to `"CUSTOM<name>"` _Be aware that_ an underscore represents a space.
5. All other categories are explained in the Biomes Wiki. However, most of the other information provided is not required to be touch, and doesn't need to be in most cases.
6. Congrats, now go show off your new build!

```javascript
{
  "name":  "CUSTOM_<name>", //The file it is referring to
  "density": 0.002, //Chance per X and y coordinate in a chunk
  "size": "MEDIUM", //Can often be ignored, used for trees in some cases
  "type": "DECO", //Tells the plugin if it is an tree or an structure that is a bit bigger
  "blocksRequiredUnderneath": [ //Blocks that need to be under the object to spawn
    "GRASS"
  ],
  "blacklistedDecoBlocks": [], //Blocks in the 
  "spawnOnGround": true, //If the structure has to be placed on the ground
  "overrideExsistingBlocks": false, //If the structure should remove exsisting blocks in the terrain
  "allowRotation": false, //If it should be randomly rotated
  "applyPhysics": true, //If it should apply physics like block updated under creation
  "replaceAir": false, //If the structure only should replace air
  "minY": 50, //Minimum y coordinate for spawning
  "maxY": 90, //Maximum y coordinate for spawning
  "maxSlope": 0.0, //Maximum slope, slop is the derivated to the curve of the terrain
  "minSlope": 0.0 //Minimum slope
  "snapToXGrid": 150, //If you want the object to spawn in a grid, where in this case it is 150 blocks between the objects at the x-axis. You can disable it by setting the number to -1. If you have it enabled, keep in mind to increase the density option.
  "snapToYGrid": 150,//Same as "snapToXGrid", just y-axis. (z-axis in minecraft)
  "gridXOffset": 0, //Offset from center, used if you have multiple objects with the same grid size to prevent them from spawning at the same places
  "gridYOffset": 0, //Same as above
  "anchorYOffset": 0 // Offset of the files y-center (or floor). Used to lift the object up or down. Positive numbers will lift the object up.

}
```

{% hint style="success" %}
> Adding contents to chests in your structures is a possibility. Check [this ](https://docs.dynamic-bytes.com/beginner/world-configuration/biome-settings/customise-chests)for a guide on how to do just that.
{% endhint %}

#### Support

If you have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

