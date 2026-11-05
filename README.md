# Home & Shop Design Studio

Draw in 2D, see it in 3D — free, no sign-up, no backend, no login.

## What it is

A single-file static web app (`index.html`) that lets anyone design a home or shop:

- **2D floor-plan editor** — grid in feet (1 square = 1 ft), draw walls, add rooms, drag-and-drop furniture
- **3D view** — the same plan rendered in Three.js, with orbit / zoom
- **Floors** — Basement, Ground Floor, First Floor, Second Floor, Rooftop, plus Add Floor (up to 6) and Rename Floor; optional "Show all floors stacked"
- **Camera views** — Top, Front, Back, Left Side, Right Side, Bottom / Ceiling, 3D Perspective, Isometric
- **Asset library (39 items)** — Living/Drawing Room, Bedroom, Kitchen, Washroom/Bathroom, Study, Shop, General: sofa, beds, wardrobe/almirah, kitchen counter, stove, sink, fridge, dining table, toilet, basin, shower, bathtub, study table, bookshelf, billing counter, cash counter, display shelf, wall shelf, rack/storage, chairs, tables, stool, ceiling fan, wall painting, cupboard, almirah, storage box, stairs (straight + L), door, window, plant
- **Downloads (client-side, per user)**
  - *Download PNG — this view*: the current 3D view as a PNG
  - *Download all angles (7 PNGs)*: Top, Front, Back, Left, Right, Ceiling/Bottom, Perspective for the current floor, named `<project>-<floor>-<view>.png`
  - *Record video tour*: records the 3D canvas with MediaRecorder while the camera orbits 360° for ~12 seconds, downloads a `.webm` video (Chrome/Edge recommended; a clear message is shown if the browser cannot record)
  - *Save design (.json)* / *Open design (.json)*: the whole project as a file
  - *Save / Load*: also saved in the visitor's own browser (localStorage) under the project name — every user gets their own designs
- **Measurements** — plot width/depth inputs, floor area in sq ft, selected room area
- **Pre-loaded template** — "My Shop 10'6 x 35'": basement storage, ground-floor shop (front entrance, billing + cash counter near front-left, shelves along both side walls, central display blocks, rear stairs, rear washroom), first and second floors, rooftop. Blank "New Home (30 × 40 ft)" and blank "New Shop" templates are also one tap away.
- **Undo / redo, rotate, duplicate, delete, resize** (drag the orange corner of a selected item)

## How to use

1. Open `index.html` in a browser (double-click it), or publish it on GitHub Pages (below).
2. Pick a floor tab at the top.
3. Tap an asset in the left library, then tap the 2D plan to place it — or drag it onto the plan.
4. Click an item to select it, drag to move it, drag its orange corner to resize, use Rotate / Duplicate / Delete above the plan.
5. Use the camera buttons (Top / Front / Back / Left / Right / Bottom-Ceiling / Perspective / Isometric) to inspect the 3D view. Drag the 3D view to orbit, scroll to zoom.
6. Download PNGs, all 7 angles, or record a video tour. Save the project in the browser, or download the `.json` to keep / share it.

## Publish on GitHub Pages

This repo/folder is one static file, so no build step is needed:

1. Create a GitHub repo (e.g. `home-design-studio`) and upload `index.html` (and this `README.md`) to it.
2. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`, Save.
3. Open the published URL, e.g. `https://<your-username>.github.io/home-design-studio/`

Internet is needed at first load for the Three.js CDN (`unpkg.com/three@0.160.0`); the design itself never leaves the user's browser.

## Limits (honest)

- Layout planning only — walls are 10 ft high / 9 in thick in 3D, but this is **not** a structural, building-code or approval drawing and does not do load calculations.
- 3D assets are simple coloured shapes with labels, not photoreal furniture models.
- Video tour is `.webm` (MediaRecorder); multiple PNG downloads may ask the browser for permission to download several files at once.
- Designs save in the browser they were made in (localStorage) unless the user downloads the `.json` file.
