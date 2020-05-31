---
description: Individual biome settings
---

# Biome settings

Each world has it is own set of settings that apply to individual biomes. This contains general settings like ore configuration, biome terrain modifiers, custom structures and much more.

> For a guide on editing custom structures, click [here](https://docs.dynamic-bytes.com/intermediate/create-structure). We will not go over custom structure and tree settings here.

#### Settings

At first the biome settings look overwhelming. This is just one of the biomes.

Next to each of the biomes is a comment line, with information about that setting. If there is an exclamation mark `!` in the comment, it will contain a number as well. This corresponds to a list of additional information at the bottom.

> Note that you **can not** copy paste this file into your own, since comments are not supported in the used file format.
>
> Also note that these settings only apply to **this** biome.
>
> ```javascript
> {
>   "enabled": true, "Enables or disables this biome. !-1."
>   "rarity": 1.0, "Changes the amount this biome will spawn, lower is less."
>   "biomeType": "GRASSLAND", "Defines the type of the biome. !-2."
>   "useDungeons": true, "Toggles dungeons (spawner rooms)."
>   "dungeonChance": 8, "Changes the amount dungeons (spawner rooms) spawn."
>   "useMineShafts": true, "Toggles mineshafts."
>   "useStrongholds": true, "Toggles strongholds (end portal)."
>   "useVillages": true, "Toggles villages."
>   "useTemples": false, "Toggles temples."
>   "useNetherFortress": false, "Toggles nether fortresses (doesn't belong here, remnant from ENG). Doesn't do anything."
>   "useCaves": true, "Toggles caves."
>   "useMonuments": false, "Toggles the drowned infested buildings, usually used in ocean biomes."
>   "useWoodlandMansion": false, "Toggles woodland mansions."
>   "useRavines": true, "Toggles ravines."
>   "useWitchHuts": false, "Toggles witchhuts."
>   "usePyramids": false, "Toggles desert pyramids."
>   "useJungleTemples": false, "Toggles jungle temples."
>   "useIgloos": false, "Toggles igloos."
>   "useFossils": false, "Toggles fossils (bone block structures)."
>   "useWaterLakes": true, "Toggles water lake spawns. Do not use in ocean biomes."
>   "useLavaLakes": false, "Toggles if lava lakes spawn."
>   "useBedrock": true, "Toggles if there is any bedrock under the biome. Useful for sky island maps."
>   "useRivers": true, "Toggles rivers."
>   "useNativePainting": true, "Unknown by me, needs modifying!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"
>   "useNativeStructure": true,
>   "useNativeDecorations": true,
>   "nativeBiome": "BAMBOO_JUNGLE", "Changes the native biome. Modifies mob spawns."
>   "biomeColors": [ "Used in image generation. !-3."
>     "0cff00" "Color is the same as the color on the map. EWG always picks the closest one if not the exact color."
>   ],
>   "fossilChance": 64, "Changes the rate at which the skeletons spawn."
>   "lavaLakeChance": 70, "Changes the rate at which lava lakes spawn."
>   "waterLakeChance": 4, "Changes the rate at which water lakes spawn."
>   "vanillaFeatures": [ "Modifies which vanilla features do and do not apply. !-4."
>     "UNDERGROUND_DECORATION",
>     "UNDERGROUND_STRUCTURES",
>     "SURFACE_STRUCTURES",
>     "TOP_LAYER_MODIFICATION",
>     "RAW_GENERATION"
>   ],
>   "ores": [ "Modifies ores. Only the first ore in this section has comments."
>     {
>       "type": "DIRT", "Type of block. Note: for grass blocks use GRASS_BLOCK instead of GRASS."
>       "size": 33, "The size at which the patches of these blocks spawn. Higher is more spread out / larger."
>       "count": 10, "The quantity with which they spawn."
>       "minHeight": 0, "The minimal height for the blocks to spawn."
>       "maxHeight": 256 "The maximal height for the blocks to spawn."
>     },
>     {
>       "type": "GRAVEL",
>       "size": 33,
>       "count": 8,
>       "minHeight": 0,
>       "maxHeight": 256
>     },
>     {
>       "type": "GRANITE",
>       "size": 33,
>       "count": 10,
>       "minHeight": 0,
>       "maxHeight": 80
>     },
>     {
>       "type": "DIORITE",
>       "size": 33,
>       "count": 10,
>       "minHeight": 0,
>       "maxHeight": 80
>     },
>     {
>       "type": "ANDESITE",
>       "size": 33,
>       "count": 10,
>       "minHeight": 0,
>       "maxHeight": 80
>     },
>     {
>       "type": "COAL_ORE",
>       "size": 17,
>       "count": 20,
>       "minHeight": 0,
>       "maxHeight": 128
>     },
>     {
>       "type": "IRON_ORE",
>       "size": 9,
>       "count": 20,
>       "minHeight": 0,
>       "maxHeight": 64
>     },
>     {
>       "type": "GOLD_ORE",
>       "size": 9,
>       "count": 2,
>       "minHeight": 0,
>       "maxHeight": 32
>     },
>     {
>       "type": "REDSTONE_ORE",
>       "size": 8,
>       "count": 8,
>       "minHeight": 0,
>       "maxHeight": 16
>     },
>     {
>       "type": "DIAMOND_ORE",
>       "size": 8,
>       "count": 1,
>       "minHeight": 0,
>       "maxHeight": 16
>     },
>     {
>       "type": "LAPIS_ORE",
>       "size": 7,
>       "count": 1,
>       "minHeight": 0,
>       "maxHeight": 32
>     },
>     {
>       "type": "EMERALD_ORE",
>       "size": 4,
>       "count": 2,
>       "minHeight": 4,
>       "maxHeight": 32
>     }
>   ],
>   "customTerrain": { "Adds noise layer capability, lets you modify how high and how many mountains spawn. !-5."
>     "noiseLayers": []
>   },
>   "terrainSettings": { "Settings for the terrain."
>     "subTerrains": [
>       {
>         "provider": "MINECRAFT", "Either MINECRAFT or EWG. Decides where the biome comes from."
>         "name": "BAMBOO_JUNGLE", "The name of the biome"
>         "xModifier": 1.0, "Changes the width at which the biome stretches out. Goes hand-in-hand with the noiseLayers above."
>         "yModifier": 1.0, "Changes the height at which the biome generates, same as ^ applies."
>         "zModifier": 1.0, "Changes the length at which the biome stretches out, same as ^ applies."
>         "yOffset": 0 "Changes the position of the noise layer."
>       }
>     ]
>   },
>   "overlaySettings": {
>     "spawnLilyPads": false,
>     "fastLeavesPlacing": true,
>     "spawnCactus": false,
>     "spawnSnowLayers": false,
>     "spawnHangingLeaves": false,
>     "spawnIceOnWater": false,
>     "groundDepth": 4,
>     "surfaceDepth": 1,
>     "surfaceBlocks": [
>       [
>         {
>           "type": "CYAN_TERRACOTTA",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 2.3,
>               "maxInclination": 99.0
>             }
>           ],
>           "chance": 1.0
>         }
>       ],
>       [
>         {
>           "type": "STONE",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 1.3,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.4
>         },
>         {
>           "type": "COBBLESTONE",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 1.3,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.3
>         },
>         {
>           "type": "STONE",
>           "data": 5,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 1.3,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.3
>         }
>       ],
>       [
>         {
>           "type": "GRASS_BLOCK",
>           "data": 0,
>           "tags": {},
>           "chance": 1.0
>         }
>       ]
>     ],
>     "oceanBlocks": [],
>     "groundBlocks": [
>       [
>         {
>           "type": "CYAN_TERRACOTTA",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 2.3,
>               "maxInclination": 99.0
>             }
>           ],
>           "chance": 1.0
>         }
>       ],
>       [
>         {
>           "type": "STONE",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 1.3,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.4
>         },
>         {
>           "type": "COBBLESTONE",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 1.3,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.3
>         },
>         {
>           "type": "STONE",
>           "data": 5,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 1.3,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.3
>         }
>       ],
>       [
>         {
>           "type": "DIRT",
>           "data": 0,
>           "tags": {},
>           "chance": 1.0
>         }
>       ]
>     ],
>     "beachBlocks": [
>       [
>         {
>           "type": "DIRT",
>           "data": 0,
>           "tags": {},
>           "heightConditions": [
>             {
>               "minHeight": 0,
>               "maxHeight": 70
>             }
>           ],
>           "chance": 1.0
>         }
>       ]
>     ],
>     "pathBlocks": [],
>     "farmlandBlocks": [],
>     "slabBlocks": [],
>     "stairBlocks": [],
>     "plantBlocks": [
>       [],
>       [],
>       [
>         {
>           "type": "SUGAR_CANE",
>           "data": 0,
>           "tags": {},
>           "heightConditions": [
>             {
>               "minHeight": 54,
>               "maxHeight": 54
>             }
>           ],
>           "chance": 0.1
>         },
>         {
>           "type": "GRASS",
>           "data": 1,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.25
>         },
>         {
>           "type": "SUNFLOWER",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "LILAC",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "TALL_GRASS",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "LARGE_FERN",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "ROSE_BUSH",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "PEONY",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "DANDELION",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "POPPY",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "BLUE_ORCHID",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "ALLIUM",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "AZURE_BLUET",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "RED_TULIP",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "ORANGE_TULIP",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "PINK_TULIP",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "WHITE_TULIP",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         },
>         {
>           "type": "SWEET_BERRY_BUSH",
>           "data": 0,
>           "tags": {},
>           "inclinationsConditions": [
>             {
>               "minInclination": 0.0,
>               "maxInclination": 1.7
>             }
>           ],
>           "chance": 0.001
>         }
>       ]
>     ],
>     "riverBlocks": [
>       [
>         {
>           "type": "SAND",
>           "data": 0,
>           "tags": {},
>           "heightConditions": [
>             {
>               "minHeight": 0,
>               "maxHeight": 70
>             }
>           ],
>           "chance": 1.0
>         }
>       ]
>     ],
>     "leavesBlock": {
>       "type": "OAK_LEAVES",
>       "data": 0,
>       "tags": {},
>       "inclinationsConditions": [
>         {
>           "minInclination": 0.44999998807907104,
>           "maxInclination": 0.6000000238418579
>         }
>       ],
>       "chance": 0.0
>     }
>   },
>   "customTrees": [], "Check at the very top. We do not go over these here."
>   "customStructures": [ "Check at the very top. We do not go over these here."
>     {
>       "name": "DECO_forest_house",
>       "density": 0.002,
>       "size": "MEDIUM",
>       "provider": "EWG",
>       "type": "DECO",
>       "blocksRequiredUnderneath": [
>         "GRASS_BLOCK"
>       ],
>       "blacklistedDecoBlocks": [],
>       "chestConfig": "default.json",
>       "spawnUnderWater": false,
>       "spawnOnGround": true,
>       "overrideExsistingBlocks": false,
>       "allowRotation": false,
>       "applyPhysics": false,
>       "applyAir": true,
>       "fixFlyingRoots": false,
>       "replaceAir": true,
>       "minY": 67,
>       "maxY": 107,
>       "maxSlope": 0.5,
>       "minSlope": 0.0,
>       "transitionClearance": -1.0,
>       "snapToXGrid": 150,
>       "snapToYGrid": 150,
>       "gridXOffset": 0,
>       "gridYOffset": 0,
>       "anchorYOffset": 0
>     },
>     {
>       "name": "DECO_jungle_tower",
>       "density": 0.005,
>       "size": "MEDIUM",
>       "provider": "EWG",
>       "type": "DECO",
>       "blocksRequiredUnderneath": [
>         "GRASS_BLOCK"
>       ],
>       "blacklistedDecoBlocks": [],
>       "chestConfig": "default.json",
>       "spawnUnderWater": false,
>       "spawnOnGround": true,
>       "overrideExsistingBlocks": false,
>       "allowRotation": false,
>       "applyPhysics": false,
>       "applyAir": true,
>       "fixFlyingRoots": false,
>       "replaceAir": true,
>       "minY": 67,
>       "maxY": 107,
>       "maxSlope": 0.5,
>       "minSlope": 0.0,
>       "transitionClearance": -1.0,
>       "snapToXGrid": 150,
>       "snapToYGrid": 150,
>       "gridXOffset": 0,
>       "gridYOffset": 0,
>       "anchorYOffset": 0
>     }
>   ],
>   "maxEWGObjectsPerChunk": 4, "Modifies the cap on EWG structures (custom structures) per chunk."
>   "xNoiseModifier": 1.2, "Random modifier to how stretched out the land is. Higher means flatter."
>   "yNoiseModifier": 0.7, "Random modifier on how high the land is. Lower means flatter."
>   "zNoiseModifier": 1.2, "Same as xNoiseModifier."
>   "lakeDepth": 0.0, "Depth of lakes, make 0.0 for no lakes."
>   "baseHeight": 67, "Default height for the land. Any custom noise baselines from here."
>   "nativeBiomes": [ "Defines the native biome that shows up in F3. Can be multiple."
>     {
>       "nativeBiome": "BAMBOO_JUNGLE", "Can be the same as any vanilla minecraft biome."
>       "chance": 1.0 "Modifies the chance at which this biome is applied."
>     }
>   ],
>   "groundBlockSettings": { "Defines the blocks out of which the ground layer is built."
>     "layers": [ "Contains the layers."
>       {
>         "maxAmplitude": 10, "Max height at which these blocks spawn, based off of 'baseHeight'"
>         "minAmplitude": 5, "Minimal height (.^.)."
>         "xScale": 30, "X-size."
>         "zScale": 30, "Z-size."
>         "minWidth": 4, "Minimal width to spawn."
>         "maxWidth": 5, "Maximal width to spawn."
>         "groundMaterials": [ "Defines the blocks."
>           {
>             "material": "DIRT", "Can be any vanilla or modded block."
>             "data": 0, "Datatag, used for stuff like the old colored wool. Not sure if this works anymore."
>             "chance": 1.0 "Chance at which this block spawns. Make sure the total chance (all chances added up) is 1."
>           }
>         ]
>       },
>       { "A second layer for this biome. Adds cobble."
>         "maxAmplitude": 10,
>         "minAmplitude": 5,
>         "xScale": 30,
>         "zScale": 30,
>         "minWidth": 13,
>         "maxWidth": 14,
>         "groundMaterials": [
>           {
>             "material": "COBBLESTONE",
>             "data": 0,
>             "chance": 1.0
>           }
>         ]
>       }
>     ],
>     "repeat": true "Don't change."
>   },
>   "groundMaterials": [] "Can add more blocks to the ground generation. We will not go over this here."
> }
> ```

#### Reference `!`

* !-1 Used in [enabling and disabling biome files](../beginner/world-configuration-biomes.md).
* !-2 Can be: Desert, aquatic, grassland, forest and tundra. In all CAPS.
* !-3 Find out more on Image Generation [here](../beginner/generate-world-from-image).
* !-4 These are pulled straight from Minecraft's code. It is unclear what they do precisely, but they do have effect.
* !-5 More on noise layers can be found [here](../advanced/custom-terrains-using-noise.md). \(might be outdated, above my paygrade.\)

#### Support

If you have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

