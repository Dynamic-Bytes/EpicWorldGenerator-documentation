---
description: >-
  This page is a tutorial on migrating a world between minecraft versions. This
  is used when you want to use a previous EWG version than the MC version your
  server is on.
---

# How to migrate a world

### 0. Download all required .jar files and install the server

{% hint style="info" %}
> You only need to do this step if you are trying to make an entirely new world.
{% endhint %}

You will need the following 4 .jar files:

* [Paper older than 1.15](https://papermc.io/legacy), [Paper 1.15 or 1.16 ](https://papermc.io/downloads)or [Spigot ](https://getbukkit.org/download/spigot)\(your server .jar\) which corresponds with
* Any version of [EWG](https://www.spigotmc.org/resources/epicworldgenerator-1-14-1-15-1-support-all-update-aquatic-features.8067/) \(see [Versioning ](https://docs.dynamic-bytes.com/versioning)for which server .jar version you need\)

{% hint style="info" %}
> To find out which version you like most, please visit [Known Bugs](https://docs.dynamic-bytes.com/known-bugs).
{% endhint %}

* The corresponding version of [WorldEdit](https://dev.bukkit.org/projects/worldedit/files)
* Any pre-generator [WorldBorder \(1.12 and lower\)](https://dev.bukkit.org/projects/worldborder/files), [WorldBorder \(1.13 and 1.14\)](https://www.spigotmc.org/resources/worldborder.60905/), [Chunkmaster \(1.15 and higher\)](https://www.spigotmc.org/resources/chunkmaster.71351/) or [Chunky \(1.15 and higher\)](https://www.spigotmc.org/resources/chunky.81534/)

{% hint style="info" %}
> We recommend WorldBorder for 1.14 and lower \(only option\), Chunkmaster for 1.15 and Chunky for 1.16 servers.
{% endhint %}

You must then setup the server like normal, install the plugins \(EWG, W/E and any pre-generator\) and restart the server \(start it until you can join, and then shut it down\).

### 1. Creating the world

First you have to create the world with the settings that you want. You can do so by simply removing the main overworld on the server and having EWG create a new EWG overworld for you, or by installing  [Myworlds](https://www.spigotmc.org/resources/myworlds.39594/) and creating a new world through `/world create <worldname>`. 

### 2. Pre-generating the world

Please follow the tutorial in the following page:

{% page-ref page="pre-generation.md" %}

### 3. Moving the world to a different server .jar version

{% hint style="warning" %}
> Before proceeding, we recommend you make a back-up from your world by making a .zip file out of it. You can do so \(using [WinZip](https://download.winzip.com/gl/nkln/winzip24-downwz.exe)\) by selecting the world folder \(should be in the same folder as your server .jar file and with the name which you specified in step 1. or, if you haven't changed anything, the default `world`\) by left clicking on it. Then right clicking on it and pressing `Add to Zip`.
{% endhint %}

You now have a folder which contains all the information on the world you created. You can move this folder to any new server and install it with \`/world load &lt;worldname&gt;\` after installing [Myworlds](https://www.spigotmc.org/resources/myworlds.39594/) for that server as well.

{% hint style="info" %}
> You must not install a new version of EWG. You will only use the world which you generated in step 1.
{% endhint %}

### Drawbacks of migrating a world

Migrating a world can come with several downsides. It will vary how many, if any, will apply to your specific usecase.

Known possible issues:

* Leaves decay oddly \(leaving trees with too little leaves\).
* Water streams \(especially the elevated ones\) flow weirdly.
* Mobs spawn less often \(can be changed in the Spigot and / or Paper settings\).
* Broken / missing chunks may appear where they were not previously.

{% hint style="danger" %}
> Note that since you have to uninstall EWG, any and all new chunks will be vanilla. Make sure you have properly set-up a world border.
>
> WorldEdit's //regen command will also not work to repair the terrain. We recommend CoreInspect if you want to reverse changes to terrain made by players. Keep in mind that that is a fairly heavy-to-run plugin.
{% endhint %}

#### Support

If you run into issues with any of these steps, make sure to contact our support team on our [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

