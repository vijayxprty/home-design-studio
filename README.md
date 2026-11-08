# Home Designer v4 — 2D + 3D (Visualisation only)

Live: https://vijayxprty.github.io/home-design-studio/

Free, no login, no backend. Built from scratch in the Planner 5D style Vijay picked: a big empty canvas first, a thin top bar with a 2D / 3D pill in the middle, a small icon rail on the left, and floating cards only when you open them.

## Start

- The app starts **empty** — blank grid, nothing pre-loaded.
- Tap **Build** (house icon, left rail) → **Draw Walls** or **Rooms**, or tap **My Shop — 10'6" × 35'** for Vijay's shop template (exactly 10.5 × 35 ft = 367.5 sq ft).

## How it feels

- Draw walls click-by-click: the wall you're drawing is bright green, corners are green dots, "Press Esc to finish draw" while drawing.
- When a room closes, it fills with wood floor and labels itself, e.g. "Shop — 367.5 sq ft", with side dimensions in feet and inches.
- Tap **3D** in the top pill and the same plan becomes a dollhouse — no roof, brick outside, white inside, wood floors. Orbit, pan, zoom; camera presets Angle / Top / Front / Inside.
- Floors: Ground, Basement, First, Second, Rooftop — add a floor from the floor selector, up to 6 floors.
- Doors and windows cut real openings in 2D and 3D. Stairs link floors, with an enclosed-staircase test-case template (basement front entrance, ground front entrance, rear-right gate into an enclosed stairwell, differing flights to the rooftop).
- Furniture: big tiles (Bed, Sofa, Chair, Table, Wardrobe, Kitchen counter, Toilet, Basin, Shower, Fan). Click a tile, click in the plan to place, drag to move.
- Bottom-left pill shows total area in sq ft and undo/redo. Bottom-right is zoom.

## Save and export

- Autosaves in this browser (new key `home-designer-v4-project`, so it starts empty and does not inherit v2/v3 saves).
- **Export** (top right): download a PNG of the current view, download the project as a `.json` file, or open a `.json` project file. The `.json` file is your portable backup — browser data can be cleared.

## Architecture (brief)

One shared versioned JSON model (`project`, version 4) holds plot, floors, walls, rooms, openings, stairs and furniture in feet. The 2D canvas and the Three.js 3D scene are both rendered from that same model. Single self-contained `index.html` (only CDN is Three.js r160 via unpkg).

## Files

- `index.html` — v4 (this version)
- `v3.html` — the previous full-spec v3, preserved unchanged
- `v2.html` — the earlier simplified v2, preserved unchanged

## Honest limitations

- Stairs are straight runs in 3D (L/U types are labelled but drawn as a straight run).
- No curved walls, no plumbing/electrical modelling.
- 3D needs internet for the Three.js CDN; if it can't load, 2D still works and 3D shows a message.
- Desktop-first; small-screen editing is cramped.
- **Visualisation only — not certified architectural or structural documentation.**
