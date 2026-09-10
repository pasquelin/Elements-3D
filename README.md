# Elements 3D

**[Documentation 🇫🇷](README.fr.md)**

A 3D asset bank gathered for the **Enigmacube** game. The repository collects models
ready to import into a real-time engine, their original textures, and texture sheets
kept as visual references.

It is an asset archive, not a code library: nothing to install, nothing to build.

## Contents

| Folder | Content |
| --- | --- |
| `Model/` | 43 folders, one per item: the mesh in one or more formats, its textures, and the author's licence file when one is provided |
| `imagerie/` | 67 `.tga` texture sheets used as art-direction references |

### The items

- **Vegetation** — `tree`, `Maple Tree`, `palmier`, `duions_fishtail_palm_blendswap`, `foliege`, `Plant1`, `Plant2`, `durian`
- **Architecture** — `chapel`, `cathedralbase`, `mayantemple`, `medieval house`, `Medieval`, `windmill`, `dungeon_stairs`, `flay_city`
- **Scenery and props** — `colonne_en_ruine`, `statue`, `pont`, `rope_bridge`, `fence` (5 variants), `table`, `trashbox`, `props1`, `MetalSheet`
- **Vehicles** — `jeep`, `Bus Ruin`, `heli`, `Helicopter blend`
- **Objects** — `gun`, `munition`, `pomme`, `poire`
- **Miscellaneous** — `model1`, `model2`, `model5`, `Model8`, `Model9`, `Model10`

### Formats present

Meshes: `.blend` (23), `.obj` (37), `.md2` (43), `.3ds` (6), `.ms3d` (2),
`.c4d` (2), `.fbx`, `.dae`, `.lwo`.
Textures: `.tga` (84), `.png` (48), `.jpg` (24), `.bmp` (16), `.pcx` (11),
`.dds` (3), `.tif` (2).

The `.blend` sources are kept as they are, so a model can be reworked before being
re-exported rather than starting again from a frozen mesh.

## Importing into Three.js

Eleven items — `gun`, `mayantemple`, `munition`, `palmier`, `poire`, `pomme`,
`pont`, `statue`, `table`, `Plant2`, `Helicopter blend` — carry a `json.js`
exported from Blender in Three.js's JSON format.

> **Warning**: that format targeted `JSONLoader`, removed from Three.js in r99. On a
> modern Three.js, re-export the `.blend` source to glTF 2.0 (`.glb`) rather than
> loading these files.

```js
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js'

const loader = new GLTFLoader()
const { scene: statue } = await loader.loadAsync('/assets/statue.glb')
```

The `.obj` files remain usable directly through `OBJLoader` and its `MTLLoader`,
keeping the `.mtl` next to the `.obj` so texture paths resolve.

## Provenance and licences

**None of these assets are mine.** They were collected on the web and through the
Open RPG community in 2020, and remain the property of their authors. This
repository adds no licence on top: each author's licence applies, file by file.

- About fifteen folders (`fence*`, `model1`, `model2`, `model5`, `Model8`,
  `Model9`, `Model10`, `heli`) come from **W. Sitters** and are dual-licensed
  **GPL v2+ or CC-BY 3.0**, at your choice, with a duty to credit the author.
  Their `Readme.txt`, `GNU_licence.txt` and `CC_attribution_licence.txt` ship
  alongside the files.
- `jeep` comes from **Psionic** ([psionicdesign.com](http://www.psionicdesign.com)),
  free to use, credit appreciated.
- `duions_fishtail_palm_blendswap` comes from **BlendSwap**.
- The rest does not document its source. The contents of `imagerie/` in particular
  are sheets extracted from commercial games (the file names point at levels of
  *Tomb Raider Legend* and *Anniversary*): they are working references and are not
  redistributable.

Before reusing an item elsewhere, check the folder it comes from and trace it back
to its author.
