# Hanafi Book Network

An interactive, single-file HTML tool for visualizing how the classical works of Ḥanafī fiqh relate to one another — commentaries, footnotes, summaries, and books formed by combining multiple earlier works — arranged chronologically by century (Hijrī) based on each author's death date.

**[Open the live board](https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/)** *(update this link after enabling GitHub Pages — see below)*

## Features

- **Add / rename / delete books** — click "+ Add book," double-click any book to rename it
- **Connect books** — click one book, then another, to draw a relationship:
  - **Commentary** (شرح) — arrowed line
  - **Footnote** (حاشية) — dashed line
  - **Summary** (مختصر) — dotted line
  - **Combine** — select multiple source books via "⊕ Combine books" to show them merging into a new work, marked with a star-studded line
- **Century timeline** — books are laid out in rows corresponding to the Hijrī century of the author's death, with reference gridlines down the left side
- **Manuscript flag** — mark any book still in manuscript form; it highlights in red
- **Per-book colors** — every book gets an auto-assigned color; lines take on the color of the book they originate from. Colors can be changed via the color-picker swatch or by typing a hex code / CSS color name directly
- **Zoom & pan** — Ctrl/Cmd + scroll to zoom, drag to scroll around the (very large) canvas
- **Autosaves** — your layout persists in-browser via Claude's artifact storage API when opened inside Claude; when hosted elsewhere (like GitHub Pages), autosave requires `window.storage` to be defined (see Notes below)

## Usage

Just open `index.html` in any modern browser. No build step, no dependencies except two Google Fonts (Amiri, Cairo) loaded from a CDN.

## Notes on persistence

This file was built to run inside Claude's artifact environment, which provides a `window.storage` API for autosaving. Outside that environment (e.g. plain GitHub Pages), `window.storage` won't exist, so autosave/load will silently no-op and the board will reset on every page load. If you want persistence on a static host, you have two options:
1. Swap the `loadState`/`saveState` functions to use `localStorage` instead of `window.storage`, or
2. Keep using this file inside Claude, where storage already works, and use this repo purely to publish/share the current snapshot.

## License

MIT — do whatever you'd like with it.
