# Footprint Globe · 足迹地球

[简体中文](README.md) · English

Turn the places you've been into a globe.

Live → <https://work2.zyx0407.com/> (custom domain pending ICP filing)
Static · single file · zero dependencies · no build (even the QR encoder is hand-written)

![screenshot](screenshot.png)

## What it is

A line-art globe. Pick a point, or search for a city, add a year and a sentence, and it stays on the globe. Once you have a few, you can share the page and a preview image with someone.

## What's on the page

- **City search** — 763 built-in cities (Chinese name / pinyin / country / coordinates). Pick one and the place is pinned; if it's not there, click any point on the globe.
- **Year is optional** — a place name is required, but the year can be `2024`, `2024.05`, `2024.05.20`, or left empty. First visit starts with one "Beijing" sample; hit "clear sample" and start your own.
- **Line-art globe** — hand-written orthographic projection, land outlines plus a 30° graticule; drag to rotate (with inertia), wheel to zoom. Pins are amber, and a selected place gets a paper-tag label.
- **List** — mono index, serif place name, year and coordinates. Clicking an item turns the globe to it; edit or delete (delete takes two clicks).
- **Day / night** — warm-paper and dark-gallery palettes, follows the system by default; a manual switch is remembered.
- **Sharing** — shares this page's URL and a 1080×1440 preview image (always light, with the page's QR code). It never carries your places or a byline, and you can share with zero places.
- **Data** — stays in your own browser (`localStorage`, key `footprint-globe:v1`). Move devices with export / import JSON in the footer.

## Quick start

Double-click `index.html`; it runs from `file://`. For a local server:

```powershell
npx serve .
```

## Data & privacy

- Places live in your browser only; nothing is uploaded and nothing is tracked. No third-party scripts, no external requests.
- The share link is just this page's URL; the preview image is a generic layout with that URL's QR code.
- To move to another machine, export JSON here and import it there.

## Data sources & tech

- Land outlines: Natural Earth 110m (public domain), embedded in the page (~5,100 points).
- City gazetteer: Natural Earth 10m populated places (public domain) — 400 Chinese cities plus world capitals and cities over 1.5M people, 763 entries.
- QR code: a dependency-free encoder written from scratch (byte mode, EC level M, versions 1–20, up to 666 bytes).
- One `index.html`; no build step, no third-party libraries, no web fonts.

## URL parameters

| Param | Effect |
| --- | --- |
| `?theme=day` / `?theme=night` | Force a palette (not saved) |
| `?nofade=1` | Disable transitions (for screenshots) |

## Files

| File | What it is |
| --- | --- |
| `index.html` | Everything: page, styles, globe, gazetteer, QR encoder |
| `screenshot.png` | Home screenshot |
| `CNAME` | Custom domain used for deployment (`work2.zyx0407.com`) |

## Notes

- No analytics; sharing happens by link and image.
- No open-source license is attached: code and page are all rights reserved.
