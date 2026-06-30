# Color Palette Generator

A browser-based color palette tool with real color-theory harmony — no build step, no dependencies, no server. Open `index.html` and start designing.

![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Zero dependencies](https://img.shields.io/badge/dependencies-zero-brightgreen?style=flat)

---

## Features

### Palette Generation
- Generates **2–8 color swatches** that fill the entire viewport
- Five palette **modes**, each backed by real color theory (HSL color space):

  | Mode | Strategy | Saturation | Lightness |
  |------|----------|-----------|-----------|
  | **Random** | Analogous, Complementary, Triadic, or Split-Comp | 45–82% | 32–72% |
  | **Pastel** | Analogous | 18–52% | 72–92% |
  | **Vibrant** | Complementary, Triadic, or Split-Comp | 76–100% | 42–60% |
  | **Monochrome** | Single hue, stepped lightness | 28–65% | 14–84% |
  | **Dark** | Analogous | 35–78% | 7–35% |

- Press `Space` or click **Generate** to create a new palette
- Smooth background-color transitions on every generation

### Color Count Control
- `−` / `+` stepper adjusts the palette between **2 and 8 colors**
- Adding colors: new blocks grow in with a fade animation and are filled harmoniously
- Removing colors: departing blocks shrink out while remaining blocks expand to fill the space

### Lock Colors
- Click the **lock icon** on any color block to pin it
- Locked colors survive Generate, mode switches, and count adjustments
- Lock icon is always visible while locked; appears on hover otherwise

### Copy Hex Codes
- Hover a color block to reveal its **HEX code** and a copy button
- Clicking copies to clipboard and briefly shows a checkmark confirmation
- A toast notification confirms the copied value

### Save & Manage Palettes
- **Save** stores the current palette to `localStorage` with an auto-generated name and timestamp
- Saved palettes appear in the **My Palettes** sidebar as interactive swatch previews
- Click swatches or **Load** to restore any saved palette (color count adjusts automatically)
- **Rename** palettes inline by clicking the palette name
- **Delete** removes individual palettes

### UI & Accessibility
- Light and dark mode toggle — preference is persisted across sessions
- Fully **responsive** — on small screens, color blocks stack vertically with always-visible controls
- No external fonts, third-party APIs, or network requests of any kind

---

## Getting Started

No installation required.

```bash
# Clone the repo
git clone https://github.com/your-username/color-palette-generator.git

# Open in browser
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Or simply drag `index.html` into any modern browser. Everything runs locally.

---

## Keyboard Shortcut

| Key | Action |
|-----|--------|
| `Space` | Generate a new palette |

> The shortcut is disabled when focus is inside an input, select, button, or textarea.

---

## How It Works

The harmony engine operates in three steps:

1. **Mode selection** — each mode defines allowed harmony strategies and HSL saturation/lightness ranges.
2. **Hue generation** — `buildHues()` picks a base hue at random and derives the palette's other hues using the selected strategy (analogous spread, complementary offset, triadic 120° split, etc.).
3. **Color assembly** — `genColors()` maps each hue to a final HEX color using `hslToHex()`. Locked slots bypass this step and return their pinned value unchanged.

Text contrast (lock/copy icons, hex labels) is determined using the **WCAG relative luminance formula**, switching automatically between light and dark foreground colors per block.

Palettes are persisted as JSON in `localStorage` under the key `cpg_v1`.

---

## Project Structure

```
color-palette-generator/
└── index.html    # Entire application — HTML, CSS, and JavaScript in one file
```

---

## Browser Support

Works in all modern browsers (Chrome, Firefox, Safari, Edge). Falls back to `document.execCommand('copy')` when the Clipboard API is unavailable.

---

## License

MIT
