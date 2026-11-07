# Home Designer v3 — 2D + 3D (Visualisation only)

Live: https://vijayxprty.github.io/home-design-studio/

Free, no login, no backend. Draw a building from basement to rooftop in 2D and see it in 3D automatically. Feet and inches only, everywhere.

## Start

- The app starts **empty**. Set your plot size (Ft + In), then draw.
- One-tap templates: **My Shop 10'6 × 35'**, **Staircase test case**, **Sample home 30 × 40**.

## What it does

- Plot (rectangular, Ft/In) + floors: Basement, Ground, First, Second, Rooftop — add / rename / duplicate / hide / delete, each with its own elevation, slab thickness and wall height. "Show floor below" faint reference overlay.
- 2D tools: Select, Wall (connected), Room, Door, Window, Vent/Gate, Stairs, Furniture, Pencil sketch (never becomes a wall until you convert it), Eraser (a wall deletes only that segment, with confirm), Dimension, Label. Snap 6 in, grid 1 ft. Undo/redo (50 steps), duplicate, copy/paste.
- Stairs: Straight / L / U / Spiral-simplified, from/to floors, steps, tread, riser auto-calc, landings, direction + UP arrow, slab opening on the arrival floor. Geometry warnings only (headroom, reach, overlap) — not a building-code check.
- Staircase test case: basement with its own front entrance, ground floor with its own front entrance, upper floors via a separate rear-right gate into an enclosed stairwell, flights that turn and differ per level up to the rooftop. Camera preset "Rear entrance (5'6\" eye)" puts you just inside that gate.
- Furniture (13): bed, sofa, chair, dining table, wardrobe, kitchen counter, wall cabinet, sink, toilet, basin, shower, fan (ceiling), wall painting. Colours/materials editable.
- 3D: Three.js, orbit/pan/zoom, perspective + orthographic, presets (Exterior, Front, Rear entrance, Inside stairwell, Top, Isometric), hide walls / roof / ceilings, cutaway, show-only-current-floor, reset camera. Walls have real openings (see-through, with lintels). Click a wall / furniture / stair in 3D to edit it in Properties.
- Export: PNG of the current 2D plan or 3D view, with dimensions/labels optional, 1080p / 2K / 4K. Clean — no handles or toolbars.
- Save: autosaves in this browser (status shown). Download / open a project `.json` file — that file is your portable backup, because browser data can be cleared. New project asks first.

## Architecture (brief)

One shared versioned JSON model (`project`, version 3) holds plot, floors, walls, rooms, openings, stairs, furniture, sketches and dimensions in feet. The 2D canvas and the Three.js 3D scene are both rendered from that same model, so an edit in either view updates the other. Single self-contained `index.html` (only CDN is Three.js r160 via unpkg).

## Files

- `index.html` — v3 (this version)
- `v2.html` — the previous simplified v2, preserved unchanged

## Honest limitations

- Spiral stairs are simplified curved steps, not a true helical stringer.
- No curved-wall 3D — curves stay as 2D sketches/guides.
- No plumbing, electrical, or services modelling.
- No building-code compliance check — warnings are geometry only.
- 3D editing is select + Properties only (no 3D dragging).
- Desktop-first; small-screen editing is cramped.
- Video / walkthrough export is out of scope.
- **Visualisation only — not certified architectural or structural documentation.**
