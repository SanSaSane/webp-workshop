# WebP Workshop

A fast, lightweight image editor that runs entirely in your browser. No installation, no dependencies, no build step — the whole application is a single HTML file, and your images never leave your machine.

![Format](https://img.shields.io/badge/format-WebP%20%C2%B7%20PNG%20%C2%B7%20JPEG-blue) ![License](https://img.shields.io/badge/license-MIT-green) ![Size](https://img.shields.io/badge/size-single%20file-lightgrey)

## Features

- **Formats** — opens and saves WebP, PNG, and JPEG
- **Layers** — add any image as a layer; per-layer visibility, opacity, and nine blend modes (multiply, screen, overlay, soft light, …); rename, duplicate, reorder, merge down, and delete; drag on canvas or use arrow keys to position
- **Background removal** — automatic background detection: samples the layer edges, flood-fills the connected background with a live magenta preview, adjustable tolerance and edge softening; magic wand (contiguous or global); soft eraser brush; restore brush that paints the original pixels back. Exports keep transparency (WebP/PNG); JPEG flattens onto white
- **Presets** — one-click looks: Original, Vivid, Warm, Cool, Noir, Sepia, Vintage, Faded, Punch, Chrome, Matte, Cinema
- **Adjustments** — brightness, contrast, saturation, temperature, tint, hue, blur, grayscale, sepia, invert
- **Effects** — sharpen (convolution), vignette, film grain, pixelate
- **Transform** — rotate, flip, free crop with aspect locks (1:1, 4:3, 16:9) and rule-of-thirds guides; transforms apply to the whole layer stack
- **Resize** — pixel-accurate with aspect lock and quick presets
- **Apply edits to the next image** — optionally carry the current adjustments/effects and/or canvas size (center-crop + scale) onto the next image you open, for repeatable one-image-at-a-time workflows; settings persist between sessions
- **Export** — quality slider with live file-size estimate and source-size comparison
- **Workflow** — full undo/redo, reset to original, hold-to-compare against the unedited composite, zoom (fit / 1:1 / free)

All adjustments are non-destructive: sliders re-render live from the layer composite at full resolution on export. Destructive operations (crop, resize, rotate, flip) are baked with undo history.

## Usage

Open `index.html` in any modern browser (Chrome, Edge, or Firefox 96+ recommended for full WebP encoding support), or serve it from any static host. Drag an image into the window to begin.

### Keyboard shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl+O` | Open image (replaces the current document) |
| `Ctrl+Z` / `Ctrl+Shift+Z` | Undo / redo |
| `Ctrl+Y` | Redo |
| `Ctrl+S` | Export / download |
| `C` (hold) | View unedited composite |
| `W` / `E` / `R` | Magic wand / eraser / restore tool |
| `[` / `]` | Decrease / increase brush size |
| `Esc` | Cancel crop or background preview |
| Arrow keys / `Shift`+arrows | Move active layer by 1 px / 10 px |
| `Delete` | Remove active layer |
| Drag on canvas | Move active layer |
| Double-click a layer name | Rename layer |
| Double-click a slider | Reset that slider |
| Double-click the canvas | Toggle fit / 1:1 zoom |

With a document open, dropping a file into the window adds it as a new layer; the Open button replaces the document.

## Technical notes

- Decoding and encoding use the browser's native canvas codec; the preview buffer is capped at 1600 px on the long edge for responsiveness, while export always renders at full resolution.
- If a browser cannot encode WebP, the option is disabled automatically and PNG becomes the default.
- The "carry edits to next image" toggles and last canvas size are stored in `localStorage` on your machine; nothing is uploaded.
- No network requests, analytics, or external assets.

## Trademark notice

"WebP" is used solely to describe file-format compatibility (nominative fair use). This project is an independent tool and is not affiliated with, sponsored by, or endorsed by Google LLC or any other party. All product names and formats are property of their respective owners.

## License

[MIT](LICENSE)
