# Color Palette Generator

A single-page color palette tool built with plain HTML, CSS, and JavaScript — no build step, no dependencies, no server required. Open `index.html` in any browser and start generating.

![Color Palette Generator](https://img.shields.io/badge/built%20with-HTML%20%2F%20CSS%20%2F%20JS-informational)

## Features

**Palette generation**
- Generates 2–8 color swatches that fill the screen proportionally
- Five palette modes with real color-theory logic (HSL color space):
  - **Random** — picks a harmony strategy (analogous, complementary, triadic, split-complementary) and applies it with varied saturation and lightness
  - **Pastel** — analogous hues, high lightness (72–92%), muted saturation
  - **Vibrant** — complementary or triadic harmony, high saturation (76–100%), mid lightness
  - **Monochrome** — single hue, lightness stepped evenly from dark to light
  - **Dark** — analogous hues, low lightness (7–35%)
- Press **Space** or click **Generate** to create a new palette
- Smooth color transition animations on every generation

**Color count**
- `−` / `+` stepper in the controls bar adjusts the palette between 2 and 8 colors
- Adding colors: new blocks animate in (grow + fade) and are filled with harmonious colors
- Removing colors: departing blocks shrink out while the remaining blocks expand to fill the space

**Lock colors**
- Click the lock icon on any color block to pin it
- Locked colors survive Generate, mode changes, and count changes
- The lock icon is always visible while locked; appears on hover otherwise

**Copy hex codes**
- Hover a color block to reveal its HEX code and a copy button
- Clicking copies to clipboard and briefly shows a checkmark confirmation
- A toast notification confirms the copied value

**Save palettes**
- **Save** stores the current palette to `localStorage` with an auto-generated name and date
- Saved palettes appear in the **My Palettes** sidebar as color swatch previews
- Click swatches or **Load** to restore a saved palette (count adjusts automatically)
- Double-click a palette name to rename it inline
- **Delete** removes individual palettes

**UI**
- Light and dark mode toggle (persisted across sessions)
- Fully responsive — on small screens, color blocks stack vertically with always-visible controls
- No external fonts, APIs, or dependencies

## Usage

```
open index.html
```

Or drag the file into any browser. Everything runs locally; no internet connection needed.

## Keyboard shortcut

| Key | Action |
|-----|--------|
| `Space` | Generate new palette |
