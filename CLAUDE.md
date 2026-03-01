# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is **cs.johnsonlee.io** — a "Programming for Kids" interactive slide presentation deployed to GitHub Pages via the custom domain `cs.johnsonlee.io`.

Slides are authored as Markdown files in `src/en/` (English) and `src/zh/` (Chinese), rendered by the Slides framework (`slides.johnsonlee.io`) which wraps reveal.js.

## Development

No build step required. Serve with any static HTTP server:

```bash
npx serve .
# or
python3 -m http.server
```

Then open `http://localhost:8000` (or the appropriate port).

## Architecture

- **`index.html`** — Single entry point. Loads `slides.css` and `slides.js` from `slides.johnsonlee.io`, configures chapters via `Slides.init()`, and includes MathJax3 for LaTeX rendering plus Google Analytics.
- **`src/en/`** and **`src/zh/`** — Parallel directories of Markdown slide content (English and Chinese). Every chapter file must exist in both directories.
- **`assets/`** — Images (PNG, SVG, PSD) and videos (MP4) referenced by slides.
- **`CNAME`** — GitHub Pages custom domain configuration.

### Slides.init() Configuration

The `Slides.init()` call in `index.html` declares the presentation structure:

```js
Slides.init({
  title: 'Programming for Kids',
  chapters: ['cover', 'preface', 'outline', 'chapter-1.0', ...],
  langs: { en: 'EN', zh: '中文' }
});
```

- **`chapters`** — Ordered list of Markdown filenames (without `.md`). Each maps to `src/{lang}/{name}.md`.
- **`langs`** — Available languages. Keys are language codes used in the `?lang=` query parameter; values are display labels for the language toggle UI.

### Adding a New Chapter

1. Create `src/en/{name}.md` and `src/zh/{name}.md` with matching content structure.
2. Add `'{name}'` to the `chapters` array in `index.html` at the desired position.

## i18n (Internationalization)

- Language is controlled by the `?lang=` URL query parameter (defaults to `en`).
- A language toggle button switches between configured languages.
- The Slides framework rewrites chapter paths to `src/{lang}/{name}.md` at page load.

## Slide Content Conventions

- Math formulas use LaTeX via MathJax3 (e.g., `$2^{10}$`).
- Code blocks use reveal.js line highlighting syntax: `` ```text[1-3|5-7] ``.
- Step-by-step reveals use `.element: class="fragment"` annotations.
- Horizontal slide separators: `---` (between top-level chapters).
- Vertical slide separators: `----` (between sub-slides within a chapter).
- Asset paths in markdown use `assets/...` (relative to `index.html` root).
- Center slides use `<!-- .slide: class="center" -->` directive.
