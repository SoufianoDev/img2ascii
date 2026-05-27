# img2ascii

```
⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⡟⠛⢻⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡟⠛⠛⠛⠛⠛⠛⣿⣿⣿⣿⣿⣿⣿⣿⠟⠛⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⡇⠀⢸⡟⠛⠿⠛⠛⠿⠟⠛⠻⣿⡿⠟⠛⠛⠻⣿⣿⠟⠛⠻⠛⢻⣿⡿⠛⠛⠻⢿⣿⣿⣷⠀⢰⣿⣿⠿⠛⠛⠻⢿⣿⣿⡟⠀⡀⠘⣿⣿⡿⠟⠛⠛⠿⣿⡿⠟
⣿⣿⣿⣿⣿⣿⡇⠀⢸⡇⠀⣴⣷⠀⠀⣾⣧⠀⢸⣷⠶⠛⠃⠀⢹⠃⢀⣾⣷⠀⢸⡏⠀⠰⠿⠂⠀⣿⣿⣿⠀⢸⣿⡏⠀⣴⣿⡆⠀⣿⡿⠁⢰⣷⡀⠸⣿⣇⠀⠻⠷⢤⣿⠁⢠
⣿⣿⣿⣿⣿⣿⡇⠀⢸⡇⠀⣿⣿⠀⠀⣿⣿⠀⢸⠁⠀⣾⠇⠀⢸⡄⠈⢿��⠀⢸⣇⠀⠰⣶⠶⢶⣿⣿⣿⠀⢸⣿⣇⠀⠻⡿⠇⠀⣿⠃⢀⣤⣤⣀⠀⢹⡛⠳⣶⡦⠀⣹⡀⠘
⣿⣿⣿⣿⣿⣿⣧⣤⣼⣧⣤⣿⣿⣤⣤⣿⣿⣤⣼⣷⣤⣤⣶⣤⣼⣿⢦⣤⡴⠀⢸⣿⣷⣦⣤⣤⣾⣿⣿⣿⣤⣼⣿⣿⣷⣤⣤⣴⣾⣧⣤⣼⣿⣿⣿⣤⣤⣷⣦⣤⣤⣶⣿⣿⣦
⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣤⣀⣠⣤⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿
```

Convert any image to high-fidelity Braille text art — entirely in the browser, zero dependencies, no server.

**[Live Demo](https://soufianodev.github.io/img2ascii)** · **[Repository](https://github.com/SoufianoDev/img2ascii)** · **[Report a Bug](https://github.com/SoufianoDev/img2ascii/issues)**

---

## Overview

`img2ascii` is a single-file, client-side tool that converts images into Unicode Braille text art in real time. Your images stay in your browser — no uploads, no tracking, no servers.

No build step. No package manager. No backend. The entire application lives in one `index.html`.

---

## Features

| Feature | Detail |
|---|---|
| **Braille rendering** | High-fidelity Unicode Braille output with ~4× effective resolution |
| **Multilingual (I18n)** | Full support for English (LTR) and Arabic (RTL) dynamically switchable |
| **Edge Sharpening** | Enhance outlines for crisp, clear text art |
| **Gamma Thresholding** | Precise contrast and brightness control |
| **Floyd-Steinberg Dithering** | Smooth gradients without banding |
| **Resolution & Zoom** | Width slider (50–400 characters), independent display zoom |
| **Invert matrix** | Toggle brightness logic for dark/light backgrounds |
| **Drag & drop / paste** | Load images via drag-and-drop, file browser, or clipboard (`Ctrl+V` / `Cmd+V`) |
| **Copy to clipboard** | One-click export with fallback for older browsers |
| **Save as `.txt`** | Download output as a text file |

---

## Why This Exists

Most online converters upload your image to a remote server, require an account, or add noise with ads and friction. `img2ascii` does none of that. The image never leaves your browser — all processing happens locally using the Canvas API.

The Braille mode is a specific design choice: each Unicode Braille character encodes a 2×4 dot matrix (8 binary pixels per cell), which gives substantially more spatial information per character than ASCII alone.

---

## Getting Started

### Local Development

The project has no build toolchain. Clone and open.

```bash
git clone https://github.com/SoufianoDev/img2ascii.git
cd img2ascii
```

**Option A — open directly**

```bash
open index.html
```

Works for most use cases. Note: clipboard paste (`Clipboard API`) is blocked on `file://` origins in some browsers. Use option B if paste doesn't work.

**Option B — local HTTP server**

```bash
# Python
python3 -m http.server 8080
# Node (no install needed)
npx serve .
```

Then open `http://localhost:8080`.

No `.env`, no dependencies, no configuration required.

### Usage

1. **Load an image** — drop onto the zone, click to browse, or paste (`Ctrl+V` / `Cmd+V`)
2. **Adjust size** — use the **Width** slider (50–400 characters); height scales automatically
3. **Fine-tune details**:
   - **Edge Sharpening** — enhance outlines
   - **Threshold (Gamma)** — control contrast
   - **Smooth Dithering** — smooth gradients
4. **Toggle options**:
   - **Invert Matrix** — flip brightness (useful for light backgrounds)
   - **Display Zoom** — scale font size without changing resolution
5. **Export** — copy to clipboard or save as `.txt`

---

## Privacy & Security

All image processing is local. The application:

- Makes no network requests after initial page load
- Does not send your image anywhere
- Stores only theme and language preference in `localStorage`
- Contains no analytics, telemetry, or third-party tracking scripts
- Only accesses the clipboard on explicit user action

---

## Accessibility

- **Theme toggle** — responds to `prefers-color-scheme` on first load
- **RTL support** — Arabic language provides full interface mirroring
- **Keyboard accessible** — all controls are standard HTML elements
- **Monospace font** — `Fira Code` / `Courier New` for consistent spacing

**Known limitation:** Braille output is visual art and not meaningfully interpretable by screen readers. If sharing output publicly, include a text description of the source image.

---

## Browser Support

| Browser | Min Version | Notes |
|---|---|---|
| Chrome / Edge | 90+ | Full support |
| Firefox | 88+ | Full support |
| Safari | 14+ | Clipboard paste requires user gesture |
| Opera | 76+ | Full support |

---

## Contributing

1. Fork the repository and branch from `main`
2. Make your changes. Keep the zero-dependency, single-file constraint unless there is a strong case for an exception
3. Test in at least Chrome and Firefox before opening a PR
4. Open a pull request with a clear description of what changed and why

**Bug reports:** include browser version, OS, the settings state when the issue occurred, and a small test image that reproduces the problem.

---

## License

MIT — see [`LICENSE`](LICENSE) for the full text.
