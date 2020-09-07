---
description: >-
  This page describes a FAQ in more detail, namely "How can I re-generate a
  chunk?"
---

# Regenerating chunks

#### Using WorldEdit's //regen

{% hint style="warning" %}
> If you are lucky, this method \(which is by far the easiest\) works for your usecase.  
> This may result in the chunk becoming vanilla, if it does not work for you.
>
> We have noticed that having the EWG world as a secondary world \(meaning not the main one\), will improve the odds of this method working.
{% endhint %}

1. Select any number of blocks inside the chunk you want to re-generate

   For this, you can use `//wand` and left- and rightclick on one or two blocks in the area you want to remove. This will then create a normal cubic WorldEdit selection.

2. Select all the chunks with which the selection overlaps using `//chunk -s` 

   This will select all chunks \(which overlap with any number of blocks inside your selection\) in their entirety.

3. Run `//regen` to regenerate all the selected chunks.

{% hint style="info" %}
> If this does not work, and it creates vanilla biomes, do the following:
>
> Instead of using `//regen` with step 3, run `/delchunks` and also restart the server afterwards.
{% endhint %}

{% hint style="warning" %}
> If neither `//regen` or `/delchunks` worked for you, or they caused too much lag for the server to handle, there is another method, which is more time intensive, but very likely to work.
{% endhint %}

#### Using Dinnerbone's tool and the region files

1. Enter your world and write down / memorize the coordinates of the chunk you want to reset \(any block inside the chunk works\).
2. Open [Dinnerbone's Coordinate Tool](https://dinnerbone.com/minecraft/tools/coordinates/).
3. Enter the coordinates you wrote down in the second row under "Chunk Section Information".
4. Write down / memorize the name of the file as described in the box next to "Filename:".
5. Open your server's root folder and locate the `*/<worldName>` folder, where `<worldName>` is the name of the world in which the to-be-replaced chunk is.
6. Open that folder, then open the `region` folder: `*/<worldName>/region`.
7. Inside that folder, find the file with the name you wrote down / memorized with step 4, and delete it.
8. Restart the server

{% hint style="info" %}
> If none of these work, there is another method which we will not present here, as it can seriously harm your server. Contact @Support in Discord for more info on that \(links below\).
{% endhint %}

#### Support

If you are still having issues after attempting to resolve your issue using any of these methods, make sure to contact support on our [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

