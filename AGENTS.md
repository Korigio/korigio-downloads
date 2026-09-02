# AGENTS.md

## Cursor Cloud specific instructions

This repository is a **single static HTML download page** for the Korigio desktop app
(the actual application source lives in a separate private repo, `Korigio/korigio-desktop-app`).
It is published via GitHub Pages. There is **no build system, package manager, backend, or
dependencies** — the entire site is `index.html` plus a `.nojekyll` marker.

### Services

There are no long-running services required. The only "service" is a static file server used
to preview the page locally (GitHub Pages serves it in production).

### Run / preview locally

There is no defined dev script. Serve the repo root with any static file server, e.g.:

```bash
python3 -m http.server 8000   # then open http://localhost:8000/
```

### Lint / test / build

There is **no lint, test, or build step** in this repo — it is a hand-written static page with
inline CSS and no JavaScript. Changes to `index.html` are verified by opening the page in a
browser and confirming it renders correctly.

### Notes

- Download cards link directly to GitHub Release assets
  (`https://github.com/Korigio/korigio-downloads/releases/download/<tag>/<file>`), so clicking a
  download triggers a real download from GitHub, not from the local server.
- `.nojekyll` disables Jekyll processing on GitHub Pages; keep it in place.
