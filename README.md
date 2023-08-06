# NNT5 Stream Overlay (fork from 4WC by shdewz)

## OBS Setup

### intro*
| source           | url/path                        | width | height | x | y   |
|------------------|---------------------------------|-------|--------|---|-----|
| intro_overlay    | `http://localhost:24050/nnt-overlay/intro/`   | 1920  | 1080   | 0 | 0   |

<sup>*data pulled from `_data/coming_up.json`, requires exchanging between matches</sup>

### main scene  
| source        | url/path                     | width | height | x         | y         |
|---------------|------------------------------|-------|--------|-----------|-----------|
| vc_overlay*   |                              | 480   | 100    | 0         | 880       |
| osu clients** |                              | 960   | 360    | see below | see below |
| main_overlay  | `http://localhost:24050/nnt-overlay/main/` | 1920  | 1080   | 0         | 0         |

<sup>*url from discord, replace custom css with [vc.css](vc.css)</sup><br>
<sup>**normal 2v2 placement according to the following table:</sup>
| client | x    | y    |
|--------|------|------|
| 0      | 0    | 160  |
| 1      | 0    | 520  |
| 2      | 960  | 160  |
| 3      | 960  | 520  |

### mappool
| source           | url/path                        | width | height | x | y   |
|------------------|---------------------------------|-------|--------|---|-----|
| vc_overlay       |                                 | 480   | 100    | 0 | 880 |
| mappool_overlay* | `http://localhost:24050/nnt-overlay/mappool/` | 2320  | 700    | 0 | 220 |
| main_overlay     | `http://localhost:24050/nnt-overlay/main/`    | 1920  | 1080   | 0 | 0   |

<sup>*position changes per round depending on mappool size to center in the middle, try to line up manually</sup>

### winner
| source           | url/path                        | width | height | x | y   |
|------------------|---------------------------------|-------|--------|---|-----|
| winner_overlay   | `http://localhost:24050/nnt-overlay/winner/`  | 1920  | 1080   | 0 | 0   |

Intro and winner scenes can also have the vc overlay bottom left if needed

Add a **300ms `linear horizontal` luma wipe** transition between the scenes with **`0.05`** smoothness and enable **`invert`**

### Interacting with the mappool
- Left click: left (red) team pick
- Right click: right (blue) team pick
- Ctrl+Click: ban
- Shift+Click: clear

## Other

### `_data` folder

Not included here. Contains the following items:
- `teams.json` - list of teams, static
- `beatmaps.json` - simple beatmap list, exchanged weekly
- `beatmap_data.json` - full beatmap data for mappool screen, exchanged weekly
- `coming_up.json` - time and team names for a match, exchanged every match, used for intro screen
