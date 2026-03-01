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

## Slide Layout Rules

There are three types of slides, each with different layout and markdown conventions:

1. **Cover / Title page** — Centered layout. Uses `<!-- .slide: class="center" -->` directive. Contains `# H1` title, subtitle, author info. Example: `cover.md`.

2. **Chapter title page** — Centered layout. Uses `<!-- .slide: class="center" -->` directive. Contains `## H2` chapter number and name, plus an italic tagline. This is the first slide in each chapter file. Example:
   ```
   <!-- .slide: class="center" -->

   ## 2.1. What is a Programming Language?

   *From human language to computer language*
   ```

3. **Title + Content page** — Top-aligned flex layout (default, no directive needed). Contains `## H2` title followed by body content (bullet points, blockquotes, tables, code blocks, etc.). Content should fit on one screen — if it overflows, split into multiple slides. Example:
   ```
   ## Variables = Labeled Boxes

   A **variable** is like a labeled box.

   * You give the box a **name** (label)
   * You put a **value** inside

   > In Java, you also need to say what **type** of thing goes in the box.
   ```

Slides within a chapter are separated by `----` (vertical separator). The `<!-- .slide: class="center" -->` directive must appear as the very first line of the slide (immediately after `----`).

## Slide Content Conventions

- Math formulas use LaTeX via MathJax3 (e.g., `$2^{10}$`).
- Code blocks use `` ```java `` for Java syntax highlighting; `` ```text `` for plain output.
- Code blocks use reveal.js line highlighting syntax: `` ```text[1-3|5-7] ``.
- Step-by-step reveals use `<!-- .element: class="fragment" -->` annotations.
- Horizontal slide separators: `---` (between top-level chapters).
- Vertical slide separators: `----` (between sub-slides within a chapter).
- Asset paths in markdown use `assets/...` (relative to `index.html` root).
- Center slides use `<!-- .slide: class="center" -->` directive.

## Slide Writing Rules

- **One idea per slide.** If a slide's content overflows the screen, split it into multiple slides.
- **Keep programs complete.** Always show complete, runnable Java code (including `class` and `main` boilerplate). Never omit the boilerplate — it misleads kids into thinking partial code is valid.
- **Explain boilerplate with analogy.** Use the "house & room" analogy: `class` = the house (gives the program a name), `main` = the front door (where the program starts). Don't gloss over boilerplate — explain it once, then remind kids it's always there.
- **Match register to context.** Use casual, conversational language for explanations and analogies. Use proper technical terms for concepts and definitions.
- **Introduce before using.** Never use a term without first explaining what it is. New concepts must be introduced on the same slide or an earlier slide before being referenced.
- **Forward references need annotation.** If a term must appear before its dedicated introduction slide, add an inline note such as "（后面会详细介绍）" / "(we'll learn about this later)".

## Narrative Rules

- **Progressive depth.** Arrange slides from shallow to deep: analogy/metaphor → mechanism → code example → insight/blockquote. Never jump to code before the intuition is established.
- **Prerequisites before payoff.** A concept that depends on another concept must come after it. For example, arrays should come after loops (so readers can loop through arrays), not before.
- **Smooth transitions.** When moving from one topic to another, make the connection explicit. End each sub-chapter with a lead-in to the next topic.
- **End-of-chapter summary.** The last sub-chapter should include a summary slide that connects what was learned to what comes next.

## Quotation Mark Rules

- **Chinese slides (`src/zh/`)**: Always use `“”` as the quotation mark pair. Never use ASCII straight quotes `"` in Chinese content. HTML attributes (e.g., `class="center"`) remain unchanged.
- **English slides (`src/en/`)**: Use ASCII straight quotes `"`.

## CJK Bold Parsing Rule

- The `marked` Markdown parser used by Reveal.js does not correctly parse `**bold**` when the closing `**` is immediately followed by a CJK character or fullwidth punctuation (U+3000–U+303F, U+FF00–U+FFEF, U+2000–U+206F, U+4E00–U+9FFF).
- **Fix**: Always insert a space between the closing `**` and any adjacent CJK character or fullwidth punctuation mark. Example: `**方向** （` instead of `**方向**（`.
