# img2ascii

Convert any image to high-fidelity Braille text art — entirely in the browser, zero dependencies, no server.

---

## Overview

`img2ascii` is a single-file, client-side tool that reads pixel luminance from the HTML5 Canvas API and maps it to a high-fidelity Unicode Braille grid in real time.

No build step. No package manager. No backend. The entire application lives in one `index.html`.

---

## Features

| Feature | Detail |
|---|---|
| **Braille rendering** | Groups 2×4 pixel blocks into a single Unicode Braille codepoint (U+2800–U+28FF), producing ~4× effective resolution |
| **Multilingual (I18n)** | Full support for English (LTR) and Arabic (RTL) dynamically switchable |
| **Edge Sharpening** | Custom convolution matrix to enhance outlines and crispness |
| **Gamma Thresholding** | Dynamic gamma curve adjustments for precise contrast control |
| **Floyd-Steinberg Dithering** | Smooths out gradients and eliminates banding in the output |
| **Resolution & Zoom** | Width slider from 50 to 400 characters, with independent display zoom controls |
| **Invert matrix** | Flips the brightness logic — useful when switching between dark and light backgrounds |
| **Drag & drop / paste** | Drop image files onto the upload zone or paste from clipboard |
| **Copy to clipboard** | Writes output to clipboard with a robust fallback for older browsers |
| **Save as `.txt`** | Downloads the current output via `Blob` + object URL |

---

## Local Development

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

---

## Architecture

### Project structure

```
img2ascii/
└── index.html    # Entire application — markup, styles, fonts, and logic in one file
```

All CSS (Tailwind utility classes + custom UI elements), HTML, and JavaScript are contained in `index.html`.

### Rendering pipeline

```
Image source (File / Drop / Clipboard)
          │
          ▼
  FileReader.readAsDataURL()
  → new Image() → img.onload
          │
          ▼
  Intermediate Canvas (Scaling & Sharpening)
  — applies Custom Sharpen Convolution Matrix —
          │
          ▼
  Final Rendering Canvas (Exact Pixel Grid)
  — ctx.getImageData() → Uint8ClampedArray (RGBA)
          │
          ▼
  Gamma Curve & Threshold Calculation
          │
          ▼
  Floyd-Steinberg Dithering (Optional)
          │
          ▼
  Braille Assembly
  — Grouping 2x4 pixel blocks into Unicode Braille
          │
          ▼
  Output injected to DOM
```

**Braille High-Fidelity Rendering** — eight pixels per character cell:

Each 2×4 pixel block maps to a Braille dot number via the standard Unicode Braille bit layout:

```
Pixel (col, row)  →  Braille dot bit
(0,0) → bit 1 (value   1)    (1,0) → bit 4 (value   8)
(0,1) → bit 2 (value   2)    (1,1) → bit 5 (value  16)
(0,2) → bit 3 (value   4)    (1,2) → bit 6 (value  32)
(0,3) → bit 7 (value  64)    (1,3) → bit 8 (value 128)
```

The rendering engine measures the exact font aspect ratio to ensure pixel-perfect scaling. Each pixel's luminance is calculated, normalized, passed through a gamma curve, and optionally dithered.

### Multilingual & UI System

The application uses a lightweight I18n engine (`translations` dictionary) to switch between English and Arabic. When the language changes, it dynamically updates `document.documentElement.dir` to handle text direction.

Sliders implement a dynamic CSS variable `--slider-dir` to gracefully invert fill directions based on the active language direction.

---

## Performance

The main cost is `ctx.getImageData()` — a GPU-to-CPU pixel readback — alongside the new Sharpening Matrix and Dithering algorithms. The canvas context is created with `{ willReadFrequently: true }`.

Practical limits:

- Up to ~300 character width renders in ~200 ms on modern hardware.
- The slider caps at 400 characters wide. Beyond this, performance degrades noticeably on large source images.
- All processing runs on the main thread. Very large images at maximum resolution will produce a brief freeze. A Web Worker offload is on the roadmap.

---

## Browser Compatibility

Requires: Canvas API (`getImageData`), `FileReader`, `DataTransfer`, `Clipboard API`.

| Browser | Minimum version | Notes |
|---|---|---|
| Chrome / Edge | 90+ | Full support |
| Firefox | 88+ | Full support |
| Safari | 14+ | Clipboard paste requires a user gesture; `navigator.clipboard` needs explicit permission |
| Opera | 76+ | Full support |

The clipboard write fallback (`document.execCommand('copy')`) is used with an invisible `<textarea>` when `navigator.clipboard.writeText` is unavailable or insecure contexts block it.

---

## Contributing

1. Fork the repository and branch from `main`.
2. Make your changes. Keep the zero-dependency, single-file constraint unless there is a strong case for an exception.
3. Test in at least Chrome and Firefox before opening a PR.
4. Open a pull request with a clear description of what changed and why.

For bug reports: include browser version, OS, and the preset/settings state when the issue occurred. A small test image that reproduces the problem is helpful.

---

## License

MIT — see [`LICENSE`](LICENSE) for the full text.
