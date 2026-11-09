# Home Designer v4.3 — 2D + 3D (Visualisation only)

Live: https://vijayxprty.github.io/home-design-studio/

Free, no login, no backend. Planner 5D style: a big empty canvas first, a thin top bar with a 2D / 3D pill in the middle, a small icon rail on the left, floating cards only when you open them.

## What's new in v4.3

Stairs you can drive: set a stair's direction (up or down), its length in feet and inches, add landings and turns, and choose its floors from the selection. The **Building — all floors** toggle shows every floor together, the roof has an opening where the stairs arrive, and the **Walk** button puts a walk character into the 3D view so you can stroll through the plan.

## Start

- The app starts **empty** — blank grid, nothing pre-loaded.
- Tap **Build** (house icon, left rail) → **Draw Walls** or **Rooms**, or tap **My Shop — 10'6" × 35'** for Vijay's shop template (exactly 10.5 × 35 ft = 367.5 sq ft).

## Drawing (fixed in v4.1)

- **Draw Walls:** click corner to corner. Press **Esc** (or double-click, or tap Draw Walls again) to finish — the walls stay. Click back near the first corner to close a room: it fills with wood and shows its size.
- **Rooms:** drag a rectangle. **Pillar:** tap anywhere for a 9" × 9" column. **Stairs:** drag a rectangle, then set its direction (up or down), length in feet and inches, floors, landings and turns in the pill below.
- **Doors / Windows:** pick a type in the Build card, then tap a wall — it snaps to the nearest wall. Or select a wall and tap **+ Door** / **+ Window** in the pill below to add one in the middle automatically.
- **Doors:** Single 3'×7', Double 5'×7', Sliding 4'×7', Main entrance 4'×8', Bathroom 2'6"×7', Balcony 3'×7', Shop shutter 8'×9'.
- **Windows:** Standard 4'×4', Large 6'×5', Small 2'×2', Sliding 5'×4', Ventilator 1'6"×1'6" — each with its own sill height.

## Selecting things

- Click anything to select it — a pill appears at the bottom with its controls.
- **Wall:** drag it to move it (the room follows and resizes); drag the green dots at its ends to move one corner. Set its **thickness in inches** (default 9") and **height in feet** — the pill tells you where the roof sits ("10' 0" high — roof sits at 10' 0"").
- **Room:** type its **Width and Depth in feet and inches** (e.g. 10 ft 6 in), rename it, hide it.
- **Pillar:** drag it, set its size in inches.
- **Hide / Show:** every selected thing has a Hide button (hidden = faint dashed outline in 2D, gone in 3D). Export card → **Show all** brings everything back.
- **Floors card:** set each floor's wall height (default 10').

## 3D — move like Blender

- Tap the green **3D** pill. Drag to orbit, right-drag to pan, scroll to zoom.
- **WASD** moves the camera. **Q / E** go down / up. Camera presets top-right: Angle, Top, Front, Inside, **Eye 5'6"** (stand inside at human eye height).
- Toggles: **Building — all floors**, Walls, Roof, Furniture — turn the roof or walls off to see what's behind or below.
- A flat **roof slab** sits on top of the highest floor, so you can see exactly where the roof will sit. Turn it off with the Roof toggle to look inside.
- 2D also moves freely: drag empty space to pan, mouse wheel zooms to the cursor, ⟲ ⟳ buttons rotate the view.

## Furniture — 22 pieces

Bed, Sofa, Chair, Dining table, Wardrobe, Kitchen counter, Toilet, Basin, Shower, Ceiling fan, plus TV unit, Study desk, Bookshelf, Plant, Rug, Floor lamp, Fridge, Bathtub, Washing machine, Shoe rack, Side table, Dining chair. Tap a tile, tap the plan to place it, drag to move, double-tap to turn it.

## Save and export

- Autosaves in this browser (key `home-designer-v4-project` — v4 saves still load).
- **Export** (top right): download a PNG of the current view, download the project as a `.json` file, or open a `.json` project file. The `.json` file is your portable backup — browser data can be cleared.

## Architecture (brief)

One shared versioned JSON model (`project`, version 4) holds plot, floors, walls, rooms, openings, stairs, pillars and furniture in feet. The 2D canvas and the Three.js 3D scene are both rendered from that same model. Single self-contained `index.html` (only CDN is Three.js r160 via unpkg).

## Files

- `index.html` — v4.3 (this version)
- `v4.2.html` — the previous v4.2, preserved unchanged
- `v4.1.html` — the previous v4.1, preserved unchanged
- `v4.html` — the previous v4, preserved unchanged
- `v3.html` — the full-spec v3, preserved unchanged
- `v2.html` — the earlier simplified v2, preserved unchanged

## Honest limitations

- No curved walls, no plumbing/electrical modelling.
- 3D needs internet for the Three.js CDN; if it can't load, 2D still works and 3D shows a message.
- Desktop-first; small-screen editing is cramped.
- **Visualisation only — not certified architectural or structural documentation.**
