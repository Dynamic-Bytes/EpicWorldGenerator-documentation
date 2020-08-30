---
description: Recommended and more detailed way of installing the plugin.
---

# Recommended installation

This is our recommendation as to how to install the plugin to make it perform as best as possible. You can also follow a more [basic instruction](https://docs.dynamic-bytes.com/basic-installation). If you have any issues with any of the steps in this process, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

You can follow parts of this tutorial and skip others. For example, you can skip the entire **I.** section if you already have a server set-up \(it is advisable to check out **I.IV.** for the `run.bat` flags\).

{% hint style="info" %}
> Following this tutorial in its entirety can take anywhere between 1 and 3 hours. Be prepared for a long ride.
{% endhint %}

{% hint style="success" %}
> This tutorial includes a part in which you set-up and configure the server.  
> Even if you already have a server configured, we recommend you follow the steps and chance certain configuration files in order to achieve better performance.
{% endhint %}

## I. Installing the server

#### I.I. Creating a location for the server on the machine

It is best to always make a master folder in which you make your server. For this tutorial, we create a folder called `server` on our desktop. You can rename or move this folder at any time if you want, as long as the server is offline when you do.

![Empty server folder on the desktop](../../.gitbook/assets/image%20%287%29.png)

#### I.II. Downloading and installing paper

After making a folder on your desktop or offsite server, download the latest build of paper [here](https://papermc.io/downloads), by clicking the download button for the latest build. At the moment of making this tutorial, that number is \#353.

![PaperMC download page](../../.gitbook/assets/image%20%2822%29.png)

Move paper from your downloads folder to the `server` folder we created earlier.

![Paper jar in the server folder](../../.gitbook/assets/image%20%2825%29.png)

{% hint style="warning" %}
> Your paper jar file will have 3 digits instead of \#\#\#. This number changes depending on what build PaperMC currently provides.
{% endhint %}

#### I.III. Installing Java

If you do not have Java installed already, download it [here](https://www.oracle.com/java/technologies/javase-jdk14-downloads.html) by scrolling down to the bottom, clicking the blue `jdk-14.0.1_windows-x64_bin.exe` button and running the file from your downloads folder.

![Download button](../../.gitbook/assets/image.png)

Follow the steps from there and hit close at the last screen.

#### I.IV. Running Paper

Go back to the `server` folder we created earlier, and create a new text file called `run.txt`.

![The new run.txt file](../../.gitbook/assets/image%20%2816%29.png)

Open the `run.txt` file and paste in the following startup flags and runtime settings:

```text
java -Xms10G -Xmx10G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:InitiatingHeapOccupancyPercent=15 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=https://mcflags.emc.gs -Daikars.new.flags=true -jar paper-###.jar
PAUSE
```

{% hint style="success" %}
> You can copy the text by clicking in the top rigth-hand side of the codeblock.
{% endhint %}

{% hint style="warning" %}
> You should replace `-Xms10G` and `-Xmx10G` with the amount of RAM your server can and will use. This is done by replacing the `10` in both to the desired amount.
{% endhint %}

{% hint style="danger" %}
> You must replace `paper-###.jar` with the name of the paper installation you have. Otherwise the file is not found and nothing will happen.
{% endhint %}

After replacing the `paper-###.jar` filename with the correct name, click `File`, followed by `Save As...` 

![File and Save As...](../../.gitbook/assets/image%20%2824%29.png)

Then rename `run.txt` to `run.batr` and click save.  


![Renamed to run.bat](../../.gitbook/assets/image%20%2820%29.png)

Run the server by double-clicking run.bat

![Doubleclick run.bat](../../.gitbook/assets/image%20%289%29.png)

run the `paper-###.jar` file.

{% hint style="warning" %}
> Once again, the `###` are different depending on your paper version.
{% endhint %}

![Console window that opens after executing run.bat](../../.gitbook/assets/image%20%288%29.png)

{% hint style="warning" %}
> If you get the following error: `The specified size exceeds the maximum representable size.`  
> You need to either uninstall existing versions of java, such as java 8, through windows or force the command prompt to use the correct version of java by replacing `java` in your `run.bat` file with`C:\Program Files\Java\jdk-14.0.1\bin\java.exe`.
{% endhint %}

#### I.V. Accepting the EULA

The server will throw an error every time you try to run it, unless you accept the [Minecraft EULA](https://account.mojang.com/documents/minecraft_eula) through the `eula.txt` file.

Open the `eula.txt` file and change `eula=false` to `eula=true` so your file looks like follows:

![EULA file after accepting the EULA.](../../.gitbook/assets/image%20%2814%29.png)

Close the file and save it.

#### I.VI. Initialising the server

After accepting the EULA you can now run the server and let it initialise all the configuration files we are about to edit.

{% hint style="warning" %}
> It can take up to 10 minutes for the server to initialise. Make sure not to close the command promt window, or the opened GUI window before completion.
{% endhint %}

After the console prompt's last message is `Timings reset`, close the console by running `stop`.or by simply closing the GUI window

{% hint style="danger" %}
> Never close the command prompt by simply clicking the red cross at the top. This will cause your server to not save and potentially ruin many different files, configurations and more.
{% endhint %}

![Server GUI with the stop command already entered](../../.gitbook/assets/image%20%2811%29.png)

The `server` folder should now look like this:

![Server folder with it&apos;s new contents](../../.gitbook/assets/image%20%284%29.png)

{% hint style="info" %}
> The images before all the `.json`and `.yml.`files may be different for me than for you. This is because of different default file editors. I will be using [Visual Studio Code](https://code.visualstudio.com/Download#) for editing configuration files throughout this tutorial. You don't have to download the editor, but I do recommend it as it easily shows errors in many different files \(with many different file types\).
{% endhint %}

##  II. Performance configuration

{% hint style="success" %}
> For most of the information in this section a [guide on server performance](https://www.spigotmc.org/threads/guide-server-optimization%E2%9A%A1.283181/?__cf_chl_jschl_tk__=89c0807000cc9867712da12bbf2d57073a6adc24-1592348530-0-ATlBqBnoVeHeKbw3XL5VZGXheexCJvSn_0WfS5tlOpAjqA6FbQxfoVQcbF49i-rayTM4AnxYnh0UFK_YClbIzGpYnLJVL7sdNozjW81dTvrIi7CuRELKucOsN6jDh8AIAQev4zLOpZX-ZcPFfQAmr2yUWSqkA5bl7IkKM9-0OaaX7uSnivrffYmD1jexaeennHQTtlXKGwz6-Mgo5JeCLR7cBvY78nqlqGuW38zf3fPSA0WwLX5pdf-OuszvVrLtbif87BTzwj2XZBAso9XNjwlUmluTOjSys1iJsQxMj4M7nxXDpZ2pJYeuwzAhoeAJrTBDcSQ55Fby76Cb-t5pkSo) was used as a reference. Credits go to the author of that piece.
{% endhint %}

Paper makes use of a layered setting structure, each layer of settings applying to a different layer of the server. The order of settings is Minecraft \(`sever.properties`\), Bukkit \(`bukkit.yml`\), Spigot   
\(`spigot.yml`\), and lastly Paper \(`paper.yml`\). Consider them as layers of both optimisations and added features.

#### II.I. server.properties

Open the server.properties file \(if you have installed [Visual Studio Code](https://code.visualstudio.com/Download#), right-click the file, click `Open with`, select Visual Studio Code and click open.

![server.properties file](../../.gitbook/assets/image%20%2829%29.png)

In this file, change the following settings:

```javascript
view-distance=10
network-compression-threshold=256
```

 to

```javascript
view-distance=6
network-compression-threshold=512
```

`view-distance` modifies the number of chunks a player can see in all directions. This increases server load when higher, and increases it exponentially \(10 to 12 adds more server load than 8 to 10\).

`network-compression-treshold` changes the compression for server-to-client data packets. Increasing this will make your server's internet speed more optimised \(must be a power of 2\).

Modify the max player count to your liking.

```javascript
max-players=20
```

Feel free to change any other settings in the file. They do not affect performance and therefore do not belong in this tutorial.

#### II.II. Bukkit.yml

Open `bukkit.yml` from the `server` folder.

![Bukkit.yml file](../../.gitbook/assets/image%20%283%29.png)

Change the spawn rates of mobs, animals and others to decrease lag if they cause lag. This setting affects mobs-per-player, meaning the more players, the higher the mobcap.

If you feel like there are not enough mobs in your server, increase these values. If you think there are too many, or if you experience lag because of them, decrease these values or the ones discussed after.

```javascript
spawn-limits:
  monsters: 70
  animals: 10
  water-animals: 15
  ambient: 15
```

If mob, animal, water or ambient spawn rates are affecting server performance, consider increasing the amount of time between checks. This can slightly decrease the number of mobs present in the world at the same time but will outweigh this by noticeably increasing performance. You can pair increasing these with increasing spawn-limits' mobcaps.

```javascript
ticks-per:
  animal-spawns: 400
  monster-spawns: 1
  water-spawns: 1
  ambient-spawns: 1
  autosave: 6000
```

The last setting for this file is `autosave: 6000` this setting affects the frequency at which your server automatically saves the state of the server to actual files. Though this is notorious for causing lag on Bukkit servers, paper servers are much less affected by this process. You can increase or decrease this setting to your liking. Make sure not to make it lower than 300 because doing so might cause overlapping auto-save cycles, with possible implications as a result.

{% hint style="warning" %}
> If you are planning on using / are already using Multiverse to save your worlds, STOP. This plugin uses the extremely inefficient `/save-all` command, which causes much higher server loads than needed.
{% endhint %}

Feel free to change any other settings like `shutdown-message: Server closed` . They do not affect server performance and therefore do not belong in this tutorial.

#### II.III. Spigot.yml

```javascript
save-user-cache-on-stop-only: true
```

This setting dictates whether or not the server constantly updates player data \(false\) or only on a server restart or server stop \(true\). Can seriously impact server performance with high player counts.

```javascript
log-villager-deaths: true
```

This setting toggles villager death logs. This can be useful if you are modifying villager settins but causes a very slight performance decrease when turned on because of additional checks.

```javascript
restart-script: run.bat
```

This setting changes the script with which the server restarts in the event of a crash or when using the `/restart` command in-game or `restart` in the console. We change this to match our running script file name.

```javascript
nerf-spawner-mobs: false
```

This setting toggles spawner mob AI. Turning this to false can drastically increase performance on servers with minable spawners and/or many mob farms. This setting has an additional setting in paper's settings, where the swimming & jumping AI is still active, making sure water-based mob grinders still work properly while keeping most of the performance benefits.

```javascript
item-despawn-rate: 6000
```

This setting dictates the time in ticks \(20 TPS is normal\) which it takes for any dropped item to despawn. The default 6000 equals 5 minutes. Decreasing this will increase server performance but might cause annoyances with your players because their items despawn quickly.

```javascript
hopper-amount: 1
```

This setting changes the number of items a hopper 'hops' per update. Increasing this alongside increasing the time between updates can drastically increase performance, while possibly breaking certain hopper-based storage systems.

```javascript
mob-spawn-range: 8
```

This setting dictates the range in chunks in which mobs can spawn \(relative to the player\). The larger this number, the more spread-out the mobs will be. Decreasing this number might add to the feeling there are more mobs than there actually are, increasing server performance when used alongside a decrease in the setting in bukkit.yml for the mobcaps.

```javascript
max-entity-collisions: 8
```

Reducing this number can improve performance with farms where there are many entities in a confined area. It can cause funky behaviour when lower than 4.

```javascript
merge-radius:
  item: 2.5
  exp: 3.0
```

Increasing the distance in blocks in which items and experience points merge can increase performance by quite a bit, especially with large farms like cactus or sugarcane farms. Both items and experience orbs can merge through walls, so make sure that that is what you want.

```javascript
entity-tracking-range:
  players: 48
  animals: 48
  monsters: 48
  misc: 32
  other: 64
```

This can be considered as the view-distance in which mobs can see the player. When not using the AI modifications for spawner mobs or when enderman farms are an issue on your server, decreasing these values can substantially increase server performance. You can halve all of them without noticeable effects, except for naturally generated enderman farms and pigman farms becoming much less efficient and profitable.

```javascript
entity-activation-range:
  animals: 32
  monsters: 32
  raiders: 48
  misc: 16
  water: 16
  villagers: 32
  flying-monsters: 32
  villagers-work-immunity-after: 100
  villagers-work-immunity-for: 20
  villagers-active-for-panic: true
  tick-inactive-villagers: true
  wake-up-inactive:
    animals-max-per-tick: 4
    animals-every: 1200
    animals-for: 100
    monsters-max-per-tick: 8
    monsters-every: 400
    monsters-for: 100
    villagers-max-per-tick: 4
    villagers-every: 600
    villagers-for: 100
    flying-monsters-max-per-tick: 8
    flying-monsters-every: 200
    flying-monsters-for: 100
```

All of these values can be decreased to increase performance when a particular group of entities is causing lag. Villagers, for example, can cause extreme lag, even with a high-end server, when grouped with high numbers. Changing the `tick-inactive-villagers:` setting to `false` can already improve server performance severely. I recommend always preemptively using that setting.

```javascript
growth:
  cactus-modifier: 100
  cane-modifier: 100
  melon-modifier: 100
  mushroom-modifier: 100
  pumpkin-modifier: 100
  sapling-modifier: 100
  beetroot-modifier: 100
  carrot-modifier: 100
  potato-modifier: 100
  wheat-modifier: 100
  netherwart-modifier: 100
  vine-modifier: 100
  cocoa-modifier: 100
  bamboo-modifier: 100
  sweetberry-modifier: 100
  kelp-modifier: 100
```

Each of these settings can affect growth rates for a specific group of crops. Just like with the previous section on entity groups, you can modify these to directly improve performance when, for example, massive cactus farms are lagging your server. I recommend not changing any of these before you have issues with them.

Lastly, a generally unknown/hidden feature within the `Spigot.yml` file are per-world settings. You can add the following lines at the bottom of the settings file in order to disable things like anti-xray in the end and nether. This way, you can also make mobs be less active in the end than in the overworld, increasing performance with multiple enderman farms, for example.

```javascript
 world_nether:
  keep-spawn-loaded: false
  auto-save-interval: 9020
  anti-xray:
   enabled: false
 world_the_end:
  keep-spawn-loaded: false
  auto-save-interval: 11050
  anti-xray:
   enabled: false
```

world\_nether: keep-spawn-loaded: false auto-save-interval: 9020 anti-xray: enabled: false world\_the\_end: keep-spawn-loaded: false auto-save-interval: 11050 anti-xray: enabled: false

#### II.IV. Paper.yml

![Paper.yml file](../../.gitbook/assets/image%20%286%29.png)

```javascript
enable-player-collisions: true
```

Toggles player collisions. When you have high player counts and a centralised spawn point, it is useful to turn this to `false`, in order to reduce performance impact.

```javascript
console-has-all-permissions: true
```

This setting grants the console all permissions on the server. This is advisable for more control, where you might \(though very rarely\) run into limitations.

```javascript
async-chunks:
  enable: true
  threads: -1
```

{% hint style="danger" %}
> With the current version of EWG \(version 8.1.26\) this feature is **NOT** supported. Therefore, the `threads:` setting must equal `-1`. You can [pre-generate a world](https://docs.dynamic-bytes.com/beginner/pre-generation) first
{% endhint %}

Changing the `threads:` setting to equal 2 \* CPU\_cores will drastically improve chunk generation and loading. When not using EWG \(uninstalled the plugin entirely\) you can use this setting.

```javascript
book-size:
  page-max: 2560
  total-multiplier: 0.98
```

To prevent an unintended result of Minecraft's mechanics a bug called 'book banning' was introduced alongside writable books. This setting prevents players from making books with more than `page-max:` pages, which prevents this issue. This also prevents a duplication glitch using a similar method as the book-banning does.



All of the settings under `world-settings:` at the bottom affect certain elements in the server that could cause lag. Many of these are case-specific and will not be mentioned here.

```javascript
keep-spawn-loaded: true
```

Turns spawn chunks on and off. Useful for spawn-less worlds like resource worlds.

```javascript
prevent-moving-into-unloaded-chunks: false
```

Prevents players from moving into chunks that are not yet loaded. Prevents deaths by collision or void in case of severe server-lag spikes.

```javascript
spawner-nerfed-mobs-should-jump: false
```

This setting goes hand-in-hand with the `nerf-spawner-mobs` setting found in the Spigot settings. Enables water-based mob grinders while also disabling spawned mobs' AI.

```javascript
use-faster-eigencraft-redstone: true
```

Removes 95% of redstone update checks that are completely redundant and useless. Tests show an increase of performance of up to 10x!

```javascript
optimize-explosions: true
```

Drastically optimises explosions of all kinds \(wither heads, TNT, creepers\). No noticeable changes to the explosion itself, other than the performance improvements.

```javascript
per-player-mob-spawns: false
```

Turns per-player mob-spawns on or off. Recommended to be set to true in order for players to have a more immersive experience. 

```javascript
max-auto-save-chunks-per-tick: 6
```

Serious impact on server performance when saving worlds. No noticeable effect unless a server crashes. In the event of a crash, a couple of loaded chunks may not get saved.

```javascript
anti-xray:
  enabled: true
  engine-mode: 2
```

While this actually costs some server performance, it is the single best anti-X-Ray measure you can take. It replaces blocks \(only clientside\) with a random selection from the list below these 3 lines, making it impossible to use X-Ray on a server effectively.

{% hint style="info" %}
> If your players regularly see the blocks while mining \(especially with server lag and/or high efficiency pickaxes\) you can increase the `update-radius: 2` setting to equal a higher value. Making this more than 3 will enable X-Ray users to X-Ray profitably.
{% endhint %}

{% hint style="success" %}
> Remove `- oak_planks`from the `replacement-blocks:` section, or X-Ray can target wood blocks and still find ores effectively.
{% endhint %}

```javascript
disable-chest-cat-detection: false
```

This \(arguably\) useless vanilla Minecraft feature can actually amount to quite some performance loss. Turn this to `true` to disable this check.

```javascript
nerf-pigmen-from-nether-portals: false
```

This applies the AI-nerfs to nether-portal spawned pigmen, preventing massive portal-based pigman farms.

```javascript
alt-item-despawn-rate:
  enabled: false
  items:
    COBBLESTONE: 300
```

This setting allows you to customise items' despawn times individually. For example, adding `NETHERRACK: 300` will make both cobblestone and nether-rack despawn after 15 seconds.

```javascript
hopper:
  cooldown-when-full: true
  disable-move-event: true
```

Toggling `disable-move-event:` to `true` will drastically improve hopper performance. Whereas without this setting, hoppers will update all 5 slots every tick to check stuff, causing serious performance impact, especially on large scales.

{% hint style="success" %}
> The same applies as with Spigot.yml, you can add per-world settings at the bottom of the file in the same fashion.
{% endhint %}

##  III. Installing EWG \(and related plugins\)

#### III.I.

Download the following files:

- [EWG](https://www.spigotmc.org/resources/epicworldgenerator-1-14-1-15-2-support-all-update-aquatic-features.8067/),  
- [WorldEdit](https://dev.bukkit.org/projects/worldedit),

{% hint style="danger" %}
> EWG does sometimes work with FAWE \(Fast Async World Edit\) or Asynchronous World Edit \(World Edit Add-on\), but we strongly advise against using these while pre-generating. They provide barely, if any, performance increase at the cost of stability.
{% endhint %}

- [Chunkmaster](https://www.spigotmc.org/resources/chunkmaster.71351/),  
- [Multiverse Core](https://dev.bukkit.org/projects/multiverse-core) \(if you are looking to make additional worlds, other than the default worlds\),  
- [ENG](https://www.spigotmc.org/resources/epicnethergenerator-ewg-add-on-new-version.25678/) and EEG \(these two are optional\),  
- And any additional add-ons

{% hint style="info" %}
> A strongly recommended, yet optional, add-on is the [Maiskorf's Additional Biome Pack \(Guide\)](https://docs.dynamic-bytes.com/beginner/recommended-installation/maiskorfs-additional-biome-pack). If you want to add these later on, make sure to download them now, before continuing using [this link](https://1drv.ms/u/s!AmrRJ70wu8OUgZQbXJeaeZmp1FT41A?e=1Oejej). The link to the guide will be re-posted at the time it should be installed.
{% endhint %}

![Maiskorf&apos;s Additional Biome Pack](../../.gitbook/assets/afbeelding%20%281%29.png)

{% hint style="success" %}
> Other options would be the [Maiskorf's Mars and / or Moon Landscapes](https://discordapp.com/channels/576841187256827905/576844840847802398/714083091504693278). Installing these is similarly done as to [Maiskorf's Additional Biome Pack \(Guide\)](https://docs.dynamic-bytes.com/beginner/recommended-installation/maiskorfs-additional-biome-pack)
{% endhint %}

![Maiskorf&apos;s Mars Landscapes](../../.gitbook/assets/afbeelding%20%287%29.png)

![Maiskorf&apos;s Moon Landscapes](../../.gitbook/assets/afbeelding%20%286%29.png)

![Zikiv&apos;s Mushroom Biome \(Included in the latest version of Maiskorf&apos;s pack\)](../../.gitbook/assets/afbeelding%20%288%29.png)

#### III.II. Installing the plugins

After downloading all the plugins, move them to the `*/plugins` folder in your server.

{% hint style="info" %}
> The Epic Nether Generator plugin comes in the form of a zip file. Extract the file and remove all that comes out except for the EpicNetherGenerator-2.\#.\#.jar file.
{% endhint %}

Your plugin folder should now look likes this:

![Plugin folder](../../.gitbook/assets/image%20%281%29.png)

Start the server and stop it once the last message in the console is `Timings reset`.

#### III.III. Creating a new world and adding biomes

After installing the plugins and running the server your plugin folder should now look like this:

![Plugin folder after installation](../../.gitbook/assets/image%20%2818%29.png)

For the sake of explaining Multiverse Core we will be making a new world for the tutorial.

Start the server and wait for it to initialise \(last entry in the console should be `Timings reset`\).  
Run the `/mv create WorldName normal` command from in game, or without the `/` from the console.  
Wait for the server to notify you `CONSOLE: Complete!` and stop the server.

You now have a new folder in the server folder:

![World created with /mv create TestWorld normal](../../.gitbook/assets/image%20%2819%29.png)

This is where you would follow the [Maiskorf's Additional Biome Pack \(Guide\)](https://docs.dynamic-bytes.com/beginner/recommended-installation/maiskorfs-additional-biome-pack) and install the settings into the newly created world `TestWorld` \(if you are following along with Multiverse\) or the default `world` folder \(if you are not\).

**III.IV. Preventing cartographer crashes**

Run the following two commands to prevent cartographers from crashing your server

{% hint style="warning" %}
> You must have `enable-command-block=true` on line 25 of the `server.properties`file.
{% endhint %}

```text
/setblock 0 1 0 minecraft:bedrock
```

```text
/setblock 0 0 0 minecraft:repeating_command_block[conditional=false,facing=up]{Command:'kill @e[type=villager,nbt={profession:cartographer}]',auto:1} destroy
```

## IV. Pre-generating the world

To keep this tutorial from being even longer than it already is, follow [this](https://docs.dynamic-bytes.com/beginner/pre-generation) tutorial in order to pre-generate the world. There is also a tutorial for WorldBorder in there, but we are using Chunkmaster because of better performance.



Wow, you made it through the tutorial. Congratulations!

I hope you can still breathe and your heart still beats, could be useful.

Let me know if any of the links don't work, I just copy-pasted most of them and there can be typos in the URL's, who knows. It's 3:30 AM at the time I'm finishing this so I'm not very sharp. 

Feel free to ask in the support channels on Discord for any help with this. I expect many to have issues with installing Java, the runtime flags or people making mistakes in the settings files. Hopefully, I can make those parts clearer and more idiot-proof over time. 

Thanks for reading! Coco.

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

