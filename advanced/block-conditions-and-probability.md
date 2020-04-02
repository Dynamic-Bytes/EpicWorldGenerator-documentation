# Block conditions and probability

All blocks is placed based on configuration options. To accomply with this, some more advanced settings was implemented.

The settings that was implemented may look simple, but they offer quite advanced features. It implement support for dependent and indepentendent proabillity and also condition based block selections.

## Conditions

Their are multiple conditions a block can be placed on. You can combine them how you want. "Or" statement can be a comlied by adding the block multiple times.

Here is the current conditions;

* Height condition
* Inclination condition
* Relative altitude condition

#### HEIGHT CONDITION

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

The conditon allows you to make the block only spawn between certain heights.

#### INCLINATION CONDITION

The plugin take out raw data of the terrain and find out the height differences between the location and the locations around. The value can be compared with the absolute value of derivative to the terrain generated in a 3D. See "derivative"; [https://en.wikipedia.org/wiki/Derivative](https://en.wikipedia.org/wiki/Derivative)

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

The condition is mostly used to place blocks in crags.

## Probability

Block groups are automaticly assigned into dependent and independent groups.

Two events are dependent if the outcome or occurrence of the first affects the outcome or occurrence of the second so that the probability is changed. To make it a bit more complex, the generator operates with two different probabilites each time a block is beinged considerted if it should be placed.

Lets explain with an example. Taken this configuration example;

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

The example above is using indepentent proability by putting each of the blocks that can be generated into its own group. This mean the plugin go thru to each of the groups until it find a block that fits.

Normally, by putting all of the blocks into the same group, the probillity for the next block to be choosen would increase with the proability of the other block to picked.

