---
description: Disable and enable biomes
---

# Manage biomes

## Disable biomes

1. Go to the settings folder for biomes \(&lt;server dir&gt;/&lt;world&gt;/settings/biomes\)
2. Open the file to the biome\(s\) you want to disable
3. Set '"enabled": true,' to '"enabled": false,' 
4. Find out what kind of biome type it is by reading the value after "terrainType" that should be on the line under
5. Open the world-settings.json \(&lt;server dir&gt;/&lt;world&gt;/settings\)
6. Adjust "biomeTypes" to fit the changes. This means if the biome you disabled was the only one of that terrain type, you need to set the value for this type in "biomeTypes" to 0 and make sure all the other values adds up to 1.

