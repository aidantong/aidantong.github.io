# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static personal portfolio site for Aidan Tong (aidantong.github.io), hosted via GitHub Pages. There is no build system, package manager, or test suite — it's plain HTML/CSS/JS served directly from the repo.

## Development

There are no build/lint/test commands. To preview locally, just open the HTML files directly in a browser, or serve the directory with any static file server, e.g.:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000/index.html`.

## Structure

- `index.html`, `about.html`, `exp.html` — the three pages of the site (home, about me, experience). Each page has its own stylesheet in `assets/styles/` (`index.css`, `about.css`, `exp.css`) with matching filenames.
- `assets/img/` — images, including company/organization logos used on the experience page and personal photos.
- `assets/docs/resume.pdf` — resume linked from the about page.
- `assets/fonts/` — a self-hosted webfont (ITC Avant Garde Gothic Std); pages also pull in Roboto from Google Fonts via `<link>` tags in each `<head>`.
- `assets/js/carousel.js` — a photo carousel script; currently unused by any page (the photo slider markup was removed from `about.html` in a previous commit), so don't assume it's wired up without checking.
- `docs/CNAME` — custom domain config for GitHub Pages. Note that GitHub Pages actually serves from the repo root (`index.html` at top level), not from `docs/` — the `docs/CNAME` file's placement is a quirk of this repo, not a signal that `docs/` is the site root.

## Conventions

- Each page follows the same layout skeleton: a `.navbar` with a logo linking to `index.html` and nav links using `on-page`/`off-page` classes to indicate the current page, followed by page-specific `#content`/`.content`.
- Styling is plain CSS per-page (no CSS framework, no preprocessor) — keep new styles in the matching `assets/styles/*.css` file rather than introducing inline styles or a new stylesheet convention.
- No JavaScript framework is used; any interactivity is plain vanilla JS (see `carousel.js` for the existing style/pattern).
