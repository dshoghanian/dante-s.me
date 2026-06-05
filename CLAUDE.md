# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A static personal portfolio website deployed via GitHub Pages to `dante-s.me`. Built on the **Massively** theme by HTML5 UP (CCA 3.0 license). No build step, no package manager, no framework — all files are served as-is.

## Site Structure

| File | Purpose |
|------|---------|
| `index.html` | Main projects page (featured post + post grid) |
| `Awards.html` | Awards page |
| `Certifications.html` | Certifications with links to PDFs in `certificates/` |
| `interests.html` | Personal interests page |
| `generic.html` / `elements.html` | Theme boilerplate (unused in nav, kept as reference) |
| `downloads/Dante_Shoghanian_Resume.pdf` | Resume linked from nav |
| `CNAME` | GitHub Pages custom domain (`dante-s.me`) |

## Asset Pipeline

There is **no build step**. SCSS source lives in `assets/sass/` but the compiled output (`assets/css/main.css`) is committed directly. To recompile SCSS you need a Sass compiler, but editing `main.css` directly is the simpler approach for this project.

- `assets/css/main.css` — compiled stylesheet (edit this directly for style changes)
- `assets/js/main.js` — custom JS; `assets/js/*.min.js` are vendored (jQuery, scrollex, scrolly, breakpoints, browser)
- `assets/webfonts/` — FontAwesome icon fonts (vendored)

## Nav Pattern

Every page shares the same nav block. When adding a nav link, update it in **all five HTML files** (`index.html`, `Awards.html`, `Certifications.html`, `interests.html`, and any new pages). The active page sets `class="active"` on its `<li>`.

## Adding a Project Card

Project cards in `index.html` follow two layouts:

- **Featured post** (`<article class="post featured">`) — top of main, full-width
- **Grid post** (`<article>` inside `<section class="posts">`) — two-column grid

Copy an existing `<article>` block, swap the image (`images/`), title, description, and GitHub link. Add the image file to `images/`.

## Previewing Locally

Open any HTML file directly in a browser — no server needed. For a quick local server:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

## Deployment

Push to `main` — GitHub Pages serves the site automatically. The `CNAME` file handles the custom domain. No CI/CD.
