# WebP Workshop

A fast, lightweight image editor that runs entirely in your browser. No installation, no dependencies, no build step — the whole application is a single HTML file, and your images never leave your machine.

![Format](https://img.shields.io/badge/format-WebP%20%C2%B7%20PNG%20%C2%B7%20JPEG-blue) ![License](https://img.shields.io/badge/license-MIT-green) ![Size](https://img.shields.io/badge/size-single%20file-lightgrey)

## Features

- **Formats** — opens and saves WebP, PNG, and JPEG
- **Presets** — one-click looks: Original, Vivid, Warm, Cool, Noir, Sepia, Vintage, Faded, Punch, Chrome, Matte, Cinema
- **Adjustments** — brightness, contrast, saturation, temperature, tint, hue, blur, grayscale, sepia, invert
- **Effects** — sharpen (convolution), vignette, film grain, pixelate
- **Transform** — rotate, flip, free crop with aspect locks (1:1, 4:3, 16:9) and rule-of-thirds guides
- **Resize** — pixel-accurate with aspect lock and quick presets
- **Export** — quality slider with live file-size estimate and source-size comparison
- **Workflow** — full undo/redo, reset to original, hold-to-compare against the source image, zoom (fit / 1:1 / free)

All adjustments are non-destructive: sliders re-render live from the source image at full resolution on export. Destructive operations (crop, resize, rotate, flip) are baked with undo history.

## Usage

Open `index.html` in any modern browser (Chrome, Edge, or Firefox 96+ recommended for full WebP encoding support), or serve it from any static host. Drag an image into the window to begin.

### Keyboard shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl+O` | Open image |
| `Ctrl+Z` / `Ctrl+Shift+Z` | Undo / redo |
| `Ctrl+Y` | Redo |
| `Ctrl+S` | Export / download |
| `C` (hold) | View original |
| `Esc` | Cancel crop |
| Double-click a slider | Reset that slider |
| Double-click the canvas | Toggle fit / 1:1 zoom |

## Technical notes

- Decoding and encoding use the browser's native canvas codec; the preview buffer is capped at 1600 px on the long edge for responsiveness, while export always renders at full resolution.
- If a browser cannot encode WebP, the option is disabled automatically and PNG becomes the default.
- No network requests, analytics, or external assets.

## Trademark notice

"WebP" is used solely to describe file-format compatibility (nominative fair use). This project is an independent tool and is not affiliated with, sponsored by, or endorsed by Google LLC or any other party. All product names and formats are property of their respective owners.

## License

[MIT](LICENSE)
