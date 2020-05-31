# Frequently Asked Questions

### Where do I find the configuration files?

All configuration options related to aspecific world, \(world settings\) can be found here;

```bash
<server folder>/<world folder>/settings/
```

Should contain;

```text
 world-settings.json
 biomes
    default (contains all configuration files for the default biomes)
    custom (folder where you can add new custom biomes)
```

Chest settings can be found here;

```bash
<server folder>/plugins/EpicWorldGenerator/chestconfig.json
```

General plugin settings can be found at;

```bash
<server folder>/plugins/EpicWorldGenerator/settings.json
```

### Where can I find pre-made configurations?

Type /ewg createworld  or visit [http://discuss.dynamic-bytes.com/t/configurations](http://discuss.dynamic-bytes.com/t/configurations)

### It appears "chunk borders" between the chunks, why and how can this be fixed?

In 95% of the cases is this created by the user by using the plugin wrong. Most common reasons;

* Changes has been made in the configuration files after the first chunks has been generated
  * Every time you do configuration changes that is not related to structure spawning or terrain overlay, will it be necessary to do a reset of the world.
* You have updated the plugin and the versions is not compatible with eachother \(mainly occur from v6 to v7, but the plugin should prevent you from updating by crashing the server and linking you to a guide how you can migrate\)
* Chunks had been generated in the world by vanilla minecraft before you installed the plugin.

It is limited what you can do with the problem, but here is some tips;

* Delete the chunk files \(See [https://dinnerbone.com/minecraft/tools/coordinates/](https://dinnerbone.com/minecraft/tools/coordinates/) for chunk to file conversion\). The chunk files is saved at /region/
* Trim the world using world border, if the new chunks is on the edge of the map; [http://dev.bukkit.org/bukkit-plugins/worldborder/](http://dev.bukkit.org/bukkit-plugins/worldborder/)
* Use the world edit's regen command

### How do I disable leaves on ground?

In the settings file for the biome, search for "leavesBlock" and remove the json section. If you are unsure on what the json section is, see [https://cdn.pbrd.co/images/7kTZdwxIe.png](https://cdn.pbrd.co/images/7kTZdwxIe.png). The text marked is the text you need to remove in order to prevent the leaves from spawing

