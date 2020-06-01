---
description: Advanced block placing for masters
---

# Block conditions and probability

All blocks are placed based on configuration options. To accompany this, some additional advanced settings were implemented.

The settings that were implemented may look simple, but they offer quite advanced features. It implements support for dependent and interdependent probability and also condition based block selections.

### Conditions

There are multiple conditions under which a block can be placed. You can combine them however you want. "Or" statements can be a applied by adding the block multiple times.

These are the current possible conditions;

* Height condition
* Inclination condition
* Relative altitude condition

**Height condition**

```text
"heightConditions": [
  {
    "minHeight": 54,
    "maxHeight": 54
  },
  {
    "minHeight": 60,
    "maxHeight": 70
  }
]
```

This condition allows you to make the block only spawn between certain heights.

**Inclination condition**

The plugin takes raw data of the terrain and finds the height differences between the location and the locations around it. This value can then be compared with the absolute value of the derivative to the terrain generated in a 3D environment. See [this ](https://en.wikipedia.org/wiki/Derivative)Wikipedia page on the derivative.

```text
"inclinationsConditions": [
  {
    "minInclination": 0.0,
    "maxInclination": 1.7
  },
  {
    "minInclination": 2.2,
    "maxInclination": 3.5
  }
]
```

This condition is mostly used to place blocks in crags.

### Probability

Block groups are automatically assigned into dependent and independent groups.

Two events are dependent on the outcome or occurrence of the first. This affects the outcome or occurrence of the second so that the probability is changed. To make it a bit more complex \(because why not\), the generator operates with two different probabilities each time a location is checked to see if a block should be placed.

Lets explain using an example. Taken this configuration;

```text
    "surfaceBlocks": [
      [
        [
          {
            "type": "SAND",
            "data": 1,
            "heightConditions": [
              {
                "minHeight": 80,
                "maxHeight": 256
              }
            ],
            "inclinationsConditions": [
              {
                "minInclination": 0.0,
                "maxInclination": 0.5
              }
            ]
          },
          0.6
        ]
      ],
      [
        [
          {
            "type": "STAINED_CLAY",
            "data": 6,
            "heightConditions": [
              {
                "minHeight": 80,
                "maxHeight": 81
              }
            ]
          },
          0.8
        ],
        [
          {
            "type": "STAINED_CLAY",
            "data": 7,
            "heightConditions": [
              {
                "minHeight": 84,
                "maxHeight": 85
              }
            ]
          },
          0.8
        ],
        [
          {
            "type": "STAINED_CLAY",
            "data": 8,
            "heightConditions": [
              {
                "minHeight": 88,
                "maxHeight": 89
              }
            ]
          },
          0.8
        ],
        [
          {
            "type": "STAINED_CLAY",
            "data": 9,
            "heightConditions": [
              {
                "minHeight": 92,
                "maxHeight": 57
              }
            ]
          },
          0.8
        ],
        [
          {
            "type": "STAINED_CLAY",
            "data": 10,
            "heightConditions": [
              {
                "minHeight": 96,
                "maxHeight": 97
              }
            ]
          },
          0.8
        ]
```

The example above is using independent probability by putting each of the blocks that can be generated into its own group. This means the plugin go through to each of the groups until it find a block that fits the location.

Normally, by putting all of the blocks into the same group, the probability for the next block to be chosen would increase with the probability of the previous picked block.

#### Support

Please try to resolve this yourself, as even the most experienced among our support have serious trouble doing this themselves, let alone explain it.

If you don't care, and have any issues with any of the settings in this file, make sure to contact our support team at [Discord](https://discord.gg/Jq3ecb3).

**Back to:** [**Table of contents**](https://docs.dynamic-bytes.com/table-of-contents)**.**

