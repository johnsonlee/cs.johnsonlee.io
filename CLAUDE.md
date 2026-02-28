# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is **cs.johnsonlee.io** — a "Programming for Kids" interactive slide presentation using **reveal.js v5.1.0 from CDN** (jsDelivr), deployed to GitHub Pages via the custom domain `cs.johnsonlee.io`.

Slides are authored as Markdown files in `src/en/` (English) and `src/zh/` (Chinese), rendered by reveal.js in a single-page HTML app (`index.html`).

## Development

No build step required. Serve with any static HTTP server:

```bash
npx serve .
# or
python3 -m http.server
```

Then open `http://localhost:8000` (or the appropriate port).

## Architecture

- **`index.html`** — Single entry point. Loads reveal.js + plugins from jsDelivr CDN. Contains all CSS styles inline, i18n logic (language detection via `?lang=` query parameter), layout adjustment JavaScript, and Google Analytics. Uses the `night` theme.
- **`src/en/`** — English Markdown slide content.
- **`src/zh/`** — Chinese Markdown slide content.
- **`assets/`** — Images and videos referenced by slides.
- **`CNAME`** — GitHub Pages custom domain configuration.

## i18n (Internationalization)

- Language is controlled by the `?lang=` URL query parameter (defaults to `en`).
- A language toggle button in the top-right corner switches between English and Chinese.
- Each `<section data-src="filename.md">` in `index.html` gets rewritten to `src/{lang}/filename.md` at page load.

## Slide Content Conventions

- Math formulas use LaTeX via MathJax3 (e.g., `$2^{10}$`).
- Code blocks use reveal.js line highlighting syntax: `` ```text[1-3|5-7] ``.
- Step-by-step reveals use `.element: class="fragment"` annotations.
- Horizontal slide separators: `---` (between top-level chapters).
- Vertical slide separators: `----` (between sub-slides within a chapter).
- Asset paths in markdown use `assets/...` (relative to `index.html` root).
- Center slides use `<!-- .slide: class="center" -->` directive.
