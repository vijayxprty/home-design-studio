# Home & Shop Design Studio — v2 (simple)

Draw in 2D, see it in 3D — free, no sign-up, no backend, no login.

v2 is a redesign of v1 after the user said v1 felt confusing and cluttered. Same working engine and same saved-design format (v1 designs still open), much simpler screen: 3 steps at the top (1 Draw • 2 Add furniture • 3 See in 3D), one view at a time with two big buttons (✏️ Draw plan / 🏠 See in 3D), stories as the hero list, 3 drawing tools, 6 furniture categories, 4 views in 3D, and one ⬇️ Download menu + one ••• More menu for everything else.

## What it is

A single-file static web app (`index.html`) that lets anyone design a home or shop — a building with stories (floors):

- **Stories first** — Basement, Ground Floor, First Floor, Second Floor, Rooftop, plus "+ Add story" (up to 6) and rename; in 3D, "See the whole building stacked" (under ••• More) shows all stories together
- **Draw (2D)** — grid in feet (1 square = 1 ft); only 3 tools: Draw Wall, Add Room, Erase. Tap a furniture item, tap the plan to place it, drag to move it
- **Furniture in 6 big categories** — 🛋️ Living, 🛏️ Bedroom, 🍳 Kitchen, 🚿 Bathroom, 📚 Study, 🏪 Shop — 39 items total: sofa, beds, wardrobe/almirah, kitchen counter, stove, sink, fridge, dining table, toilet, basin, shower, bathtub, study table, bookshelf, billing counter, cash counter, display shelf, wall shelf, rack/storage, chairs, tables, stool, ceiling fan, wall painting, cupboard, almirah, storage box, stairs (straight + L), door, window, plant
- **See in 3D** — the same plan rendered in Three.js (warm cream, soft light), drag to look around, scroll to zoom; only 4 view buttons: Top, Front, 3D, Around (slow spin). Back / Left / Right / Ceiling / Isometric are still available inside the Download menu's "Photos of all angles"
- **Downloads (client-side, per user)** — all under one ⬇️ Download button:
  - *Photo of this view*: the current 3D view as a PNG
  - *Photos of all angles (7 PNGs)*: Top, Front, Back, Left, Right, Ceiling/Bottom, Perspective for the current floor, named `<project>-<floor>-<view>.png`
  - *Video tour*: records the 3D canvas with MediaRecorder while the camera orbits 360° for ~12 seconds, downloads a `.webm` video (Chrome/Edge recommended; a clear message is shown if the browser cannot record)
  - *Save my design (file)*: the whole project as `.json`; open it later from ••• More → Open a design file
  - *Save in this browser*: also saved in the visitor's own browser (localStorage) under the project name — every user gets their own designs; the design autosaves in the browser as you work
- **Hidden under ••• More** — Save, Open saved, New project, templates, Undo/Redo, Rename story, whole-building stacked view, plot size, measurements
- **Pre-loaded template** — "My Shop 10'6 x 35'": basement storage, ground-floor shop (front entrance, billing + cash counter near front-left, shelves along both side walls, central display blocks, rear stairs, rear washroom), first and second floors, rooftop. Blank "New Home (30 × 40 ft)" and blank "New Shop" templates are also in ••• More.
- **Selected items** — drag to move, drag the orange corner to resize, Rotate or Delete from the small pop-up bar

## How to use

1. Open `index.html` in a browser (double-click it), or publish it on GitHub Pages (below).
2. Tap a story (Basement, Ground Floor, 1st Floor, 2nd Floor, Rooftop).
3. Tap a furniture category, tap an item, then tap the plan to place it. Or tap Draw Wall / Add Room and draw.
4. Tap "🏠 See in 3D" to see it in 3D. Try Top, Front, 3D, Around.
5. Tap "⬇️ Download" for a photo, all 7 angles, or a video tour. Your work autosaves in this browser.

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
