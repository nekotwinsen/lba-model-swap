# lba-model-swap

A model viewer and converter for the 3D models (bodies) of **Little Big Adventure 1**, **Little Big Adventure 2** and the **LBA2 demo**, in a single web page.

Open `index.html` in a browser (Edge, Chrome, Firefox). Everything runs locally in the browser: you pick the files from your own game folder, nothing is uploaded, and the page contains no game data. You need your own copy of the games.

## What it does

- Reads `BODY.HQR` (or any HQR with bodies) and the palette from `RESS.HQR`; LBA1, LBA2 and the LBA2 demo formats are detected automatically.
- Lists all models with thumbnails and shows them in 3D (orbit, zoom, wireframe, bones, flat/smooth shading).
- Exports a model as **GLB** (glTF with a skeleton: one joint per bone, vertex colours - riggable in Blender) or as **OBJ + MTL**.
- **Converts** a model between the LBA1, LBA2 and LBA2-demo body formats, with the colours mapped to the target game's palette: download it as a raw body, or let the page write a **new copy** of an HQR with one entry replaced (your original file is never changed).

## Notes

- A converted model keeps the bones of its source. The target game's animations only fit when the skeletons match (same bones, same order and parents - the page shows them).
- LBA2 textures are not converted (they become flat or gouraud colours).
- The 3D view loads three.js from cdn.jsdelivr.net, so it needs an internet connection; listing, export and conversion also work without it.

## Credits and license

The file formats are ported from the `twine` engine of [ScummVM](https://www.scummvm.org/) (the HQR container, the LBA1/LBA2/demo body parsers and the LBA2-to-LBA1 colour mapping). Like ScummVM, this project is licensed under the **GNU General Public License v3** (see `LICENSE`).

Little Big Adventure is © Adeline Software / [2.21]. This project contains no game files.
