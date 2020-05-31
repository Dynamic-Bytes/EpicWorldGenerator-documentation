---
description: Most basic guide on installing the plugin
---

# Basic installation

This is the simplest and fastest way of installing this plugin. You can also follow the [recommended installation](https://docs.dynamic-bytes.com/beginner/recommended-installation). If you have any issues with any of the steps in this process, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

1. Stop your server.   
2. Delete the `*/world` folder.

> This will remove **everything** in your main world.

3. Download and put the [EWG](https://www.spigotmc.org/resources/epicworldgenerator-1-14-1-15-2-support-all-update-aquatic-features.8067/) and [WorldEdit](https://dev.bukkit.org/projects/worldedit) plugins in the `*/plugin` folder.  
4. Start the server, wait for it to load, and then stop the server.

> If you don\'t have any worlds you do not want EWG to generate in, you can skip to step 6.

5. Go to the `settings.json` file, which you can find at `*/plugins/EpicWorldGenerator/` and locate the `worldsWithDefaultWG` section. 

This section should look like this:

```javascript
"worldsWithDefaultWG": [
 "myvanillaworld"
],
```

Inside of this section, add the worlds you do not want EWG to generate inside of / edit.

> EpicWorldGenerator will not touch your Nether, End or flat worlds. It might touch plot worlds, so add them to the config.

Example: I have two worlds named `pumpkin` and `melon` in my server. I do not want this plugin to change these worlds so I change the `worldsWithDefaultWG` sections to this:

```javascript
  "worldsWithDefaultWG": [
    "pumpkin",
    "melon"
  ],
```

6. Possibly install the add-on [Tree Feller](https://www.spigotmc.org/resources/tree-feller-ewg-addon.20385/).  
7. Start the server.  
8. Enjoy the plugin!

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

