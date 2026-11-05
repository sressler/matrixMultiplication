# matrixMultiplication

Interactive **4×4 matrix transform bench** for glTF models, built with Three.js — a revival of an old Bell Labs demo.

Three views side by side:

1. **Input model** — the original `.glb`
2. **Matrix M** — the 4×4 matrix as a grid of 2D tiles viewed in 3D, each tile carrying a bar whose height is that element's value (orange positive, blue negative)
3. **Result M · p** — the model with every vertex multiplied by M (homogeneous coordinates, column vectors)

All controls are drawn in WebGL with Three.js (no HTML form widgets):

- 16 sliders, one per matrix element (−3 … 3); drag, mouse wheel, or click a cell and type a value + Enter
- Arrow keys nudge / move between cells; double-click resets to identity; snaps to −1, 0, 1 (Shift to bypass)
- Presets: identity, rotations, scale, shear, mirror, translate, flatten, projective
- Animated rotation toggles for X / Y / Z (X and Z on by default) with a speed slider (0–180 °/s)
- Determinant readout with mirror/singular warnings and affine vs. projective type

## Models

- **Default:** Khronos *Duck*
- **Load .glb** button or drag-and-drop a `.glb` onto the window
- **Khronos samples** picker — 10 models bundled from [KhronosGroup/glTF-Sample-Assets](https://github.com/KhronosGroup/glTF-Sample-Assets)
- **Curious George** — 1970s plush scan by sressler

Every model is centred and scaled to fit a 2-unit cube before M is applied, so translations are in those units. Draco-compressed files are not supported.

## Running

The page loads models with `fetch()`, which browsers block on `file://` pages. Serve the folder:

```sh
python3 -m http.server 8000
# open http://localhost:8000/
```

It also works as-is on GitHub Pages.

## Model licenses

| Model | License | Credit |
|---|---|---|
| Duck | SCEA Shared Source | Sony |
| Fox | CC0 / CC-BY 4.0 | PixelMannen, tomkranis |
| Cesium Milk Truck | CC-BY 4.0 | Cesium |
| Cesium Man | CC-BY 4.0 | Cesium |
| Damask Chair | CC-BY 4.0 | Eric Chadwick |
| Damaged Helmet | CC-BY 4.0 / CC-BY-NC 4.0 | ctxwing, theblueturtle_ |
| Sheen Chair | CC0 | Eric Chadwick |
| Iridescence Lamp | CC-BY 4.0 | Eric Chadwick |
| Toy Car | CC0 | Eric Chadwick, Guido Odendahl |
| Avocado | CC0 | Microsoft |
| Curious George plush scan | CC-BY-NC 4.0 | sressler ([Sketchfab](https://sketchfab.com/3d-models/curious-george-vintage-1970s-stuffed-animal-47fae6ca9ff64f1b823682799da54b82)) |

Khronos model license details: see each model's `metadata.json` / `LICENSE.md` in the glTF-Sample-Assets repository.
