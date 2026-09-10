# Elements 3D

**[English ↗](README.md)**

Banque d'assets 3D rassemblée pour le jeu **Enigmacube**. Le dépôt regroupe des
modèles prêts à importer dans un moteur temps réel, leurs textures d'origine et
des planches de textures servant de références visuelles.

C'est une archive de ressources, pas une bibliothèque de code : rien à installer,
rien à compiler.

## Contenu

| Dossier | Contenu |
| --- | --- |
| `Model/` | 43 dossiers, un par élément : le maillage dans un ou plusieurs formats, ses textures, et le fichier de licence de l'auteur quand il en fournit un |
| `imagerie/` | 67 planches de textures `.tga` utilisées comme références de direction artistique |

### Les éléments

- **Végétation** — `tree`, `Maple Tree`, `palmier`, `duions_fishtail_palm_blendswap`, `foliege`, `Plant1`, `Plant2`, `durian`
- **Architecture** — `chapel`, `cathedralbase`, `mayantemple`, `medieval house`, `Medieval`, `windmill`, `dungeon_stairs`, `flay_city`
- **Décors et props** — `colonne_en_ruine`, `statue`, `pont`, `rope_bridge`, `fence` (5 variantes), `table`, `trashbox`, `props1`, `MetalSheet`
- **Véhicules** — `jeep`, `Bus Ruin`, `heli`, `Helicopter blend`
- **Objets** — `gun`, `munition`, `pomme`, `poire`
- **Divers** — `model1`, `model2`, `model5`, `Model8`, `Model9`, `Model10`

### Formats présents

Maillages : `.blend` (23), `.obj` (37), `.md2` (43), `.3ds` (6), `.ms3d` (2),
`.c4d` (2), `.fbx`, `.dae`, `.lwo`.
Textures : `.tga` (84), `.png` (48), `.jpg` (24), `.bmp` (16), `.pcx` (11),
`.dds` (3), `.tif` (2).

Les sources `.blend` sont conservées telles quelles pour pouvoir retoucher un
modèle avant de le réexporter, plutôt que de repartir d'un maillage figé.

## Import dans Three.js

Onze éléments — `gun`, `mayantemple`, `munition`, `palmier`, `poire`, `pomme`,
`pont`, `statue`, `table`, `Plant2`, `Helicopter blend` — portent un `json.js`
exporté depuis Blender au format JSON de Three.js.

> **Attention** : ce format visait `JSONLoader`, retiré de Three.js à la version
> r99. Sur un Three.js moderne, réexportez la source `.blend` en glTF 2.0
> (`.glb`) plutôt que de charger ces fichiers.

```js
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js'

const loader = new GLTFLoader()
const { scene: statue } = await loader.loadAsync('/assets/statue.glb')
```

Les `.obj` restent utilisables directement via `OBJLoader` et son `MTLLoader`,
en gardant le `.mtl` à côté du `.obj` pour que les chemins de textures résolvent.

## Provenance et licences

**Aucun de ces assets n'est de moi.** Ils ont été collectés sur le web et via la
communauté Open RPG en 2020, et restent la propriété de leurs auteurs. Le dépôt
n'ajoute aucune licence par-dessus : c'est celle de chaque auteur qui s'applique,
fichier par fichier.

- Une quinzaine de dossiers (`fence*`, `model1`, `model2`, `model5`, `Model8`,
  `Model9`, `Model10`, `heli`) viennent de **W. Sitters** et sont sous double
  licence **GPL v2+ ou CC-BY 3.0**, au choix, avec obligation de créditer
  l'auteur. Leurs `Readme.txt`, `GNU_licence.txt` et `CC_attribution_licence.txt`
  accompagnent les fichiers.
- `jeep` vient de **Psionic** ([psionicdesign.com](http://www.psionicdesign.com)),
  libre d'usage, crédit apprécié.
- `duions_fishtail_palm_blendswap` provient de **BlendSwap**.
- Le reste ne documente pas sa source. Le contenu de `imagerie/` est en
  particulier constitué de planches extraites de jeux commerciaux (les noms de
  fichiers renvoient à des niveaux de *Tomb Raider Legend* et *Anniversary*) :
  ce sont des références de travail, elles ne sont pas redistribuables.

Avant de réutiliser un élément ailleurs, vérifiez le dossier dont il vient et
remontez à son auteur.
