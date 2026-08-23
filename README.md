# Ascent — A Parallax Journey

A single-page scroll experience that climbs through five atmospheric zones — forest trailhead, foothills, cloud canopy, stratosphere, and orbit — using layered, speed-differentiated parallax to create a real sense of depth and altitude.

**[Live demo](#)** _(https://cute-crumble-1060e0.netlify.app/)_

## Concept

Rather than a generic "background moves slower than foreground" demo, the whole page is framed as a single ascent narrative. Every design decision ties back to that:

- **5 zones, 3–4 hand-drawn SVG layers each** — hills, ridgelines, clouds, stars, and a planet, all drawn as inline vector shapes (no image assets, so the page loads instantly).
- **Per-layer scroll speed** — each layer has a `data-speed` value; some are negative, so a few elements (like the birds in the foothills) drift *against* the scroll direction for a stronger depth illusion.
- **Live altitude HUD** — a readout in the top-right climbs from `000 M` to `400,000 M` as you scroll, plus a side flight-path marker showing which zone you're in.
- **Global sky-color interpolation** — the entire background gradient smoothly blends through 5 color stops (warm dawn → golden hour → daylight blue → deep blue → near-black space) computed live in JavaScript, not just swapped per section.

## Tech

- Plain HTML / CSS / vanilla JavaScript — no build step, no framework
- Inline SVG for all illustration (mountains, clouds, stars, planet)
- Google Fonts: [Fraunces](https://fonts.google.com/specimen/Fraunces) (display), [Inter](https://fonts.google.com/specimen/Inter) (body), [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (HUD/labels)
- Parallax driven by `requestAnimationFrame` + `getBoundingClientRect()`, throttled with a scroll-tick flag
- Respects `prefers-reduced-motion`

## Run locally

No dependencies or build step — just open the file:

```bash
git clone <your-repo-url>
cd <repo-folder>
open index.html   # or double-click the file / drag into a browser
```




## Deploy

Works on any static host — GitHub Pages, Netlify, or Vercel, since it's a single self-contained `index.html`.

**GitHub Pages:**
1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to your default branch, root folder
4. Your live URL will appear at https://github.com/shreyakulk2771-beep/Interactive-Parallax-Scrolling-Page

## Project structure

```
.
├── index.html   # everything — markup, styles, and script in one file
└── README.md
```

## Credits

Built as a parallax scrolling study — all illustration is original inline SVG, no external image assets.

