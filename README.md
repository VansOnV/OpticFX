<div align="center">

# OpticFX

**Real-time camera effects in your browser. 20 presets, motion tracking, and one-tap recording.**

[![Live Demo](https://img.shields.io/badge/live-demo-ff2a1f?style=for-the-badge)](https://vansonv.github.io/OpticFX/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](LICENSE)
![HTML5](https://img.shields.io/badge/HTML5-single%20file-e34f26?style=for-the-badge&logo=html5&logoColor=white)
![Dependencies](https://img.shields.io/badge/dependencies-0-success?style=for-the-badge)
![Build](https://img.shields.io/badge/build%20step-none-lightgrey?style=for-the-badge)

[**Launch OpticFX**](https://vansonv.github.io/OpticFX/) · [Features](#features) · [Presets](#presets) · [Controls](#controls) · [Run locally](#run-locally)

</div>

---

## Overview

OpticFX turns your webcam into a live FX studio. It is a single HTML file with no dependencies, no build step, and no server. Pick a preset, see the HUD-styled result instantly, and record it straight from the page.

Everything is processed locally on a canvas. **No video ever leaves your device.**

## Features

- **20 live presets** with a unique look and HUD for each
- **Motion tracking** with a lock-on bounding box, centroid crosshair, and live readouts
- **In-page recording** to MP4 or WebM, with the HUD baked in
- **Hide UI mode** for a clean screen when you want to capture externally
- **Front and rear camera** switching on mobile
- **Adjustable intensity** slider for most effects
- **Snapshot** export to PNG
- **Responsive**: works in portrait on phones and landscape on desktop
- **Zero dependencies**: one file, runs offline once loaded

## Presets

| # | Preset | # | Preset |
|---|--------|---|--------|
| 01 | Depth Map | 11 | ASCII |
| 02 | X-Ray | 12 | Half Tone |
| 03 | Night Vision | 13 | Pixelate |
| 04 | Thermal Map | 14 | Risograph |
| 05 | Edge Detect | 15 | Kaleido |
| 06 | Posterize | 16 | Neon Edge |
| 07 | Tracking | 17 | Pixel Sort |
| 08 | Glitch RGB | 18 | Trails |
| 09 | Duotone | 19 | Mosaic Tiles |
| 10 | VHS Tape | 20 | Motion Heat |

> **Note:** Depth Map is a stylized brightness-to-depth look, not true depth sensing. Tracking is frame-difference motion detection, not face or object recognition.

## Controls

| Action | Desktop | Touch |
|--------|---------|-------|
| Next / previous preset | `→` / `←` | Swipe left / right |
| Record / stop | `Space` | Red button |
| Snapshot | `S` | **Snap** button |
| Toggle HUD | `I` | **HUD** button |
| Flip camera | `F` | **Flip** button |
| Hide / show UI | `H` | **Hide UI**, then tap the top-right corner to restore |

## Run locally

No install required.

```bash
git clone https://github.com/VansOnV/OpticFX.git
cd OpticFX
```

Browsers only allow camera access on secure origins, so serve the folder over `localhost`:

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve .
```

Then open `http://localhost:8000` and tap **Enable camera**.

## Deploy with GitHub Pages

1. Make sure the main file is named `index.html`.
2. Go to **Settings → Pages**.
3. Set the source to **Deploy from a branch**, choose `main` and `/ (root)`.
4. Your site goes live at `https://vansonv.github.io/OpticFX/`.

## Browser support

| Browser | Camera | Recording |
|---------|:------:|:---------:|
| Chrome / Edge (desktop and Android) | Yes | Yes (WebM or MP4) |
| Safari 14.1+ (macOS and iOS) | Yes | Yes (MP4) |
| Firefox | Yes | Yes (WebM) |

Performance depends on your device. Heavier presets such as Glitch RGB, VHS Tape, and ASCII use more CPU.

## Privacy

OpticFX has no backend, analytics, or network requests. Frames are read from your camera, processed on a local canvas, and displayed. Recordings are saved only to your own device.

## Roadmap

- [ ] Microphone audio in recordings
- [ ] Real face detection
- [ ] Custom preset builder
- [ ] Preset parameter panel

## Contributing

Issues and pull requests are welcome. To add a preset, append an entry to the `P` array in the main file. Each preset is a small function that receives the pixel buffer and a grayscale map.

## License

Released under the [MIT License](LICENSE).

<div align="center">

Built by [@VansOnV](https://github.com/VansOnV)

</div>
