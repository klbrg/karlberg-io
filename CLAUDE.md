# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static portfolio website for Rickard Karlberg (karlberg.io) — an Infrastructure Engineer. Single-page site built with vanilla HTML, CSS, and JavaScript. No frameworks, no build tools, zero npm dependencies.

## Development

No build process. All source files live in `src/` and are served directly.

```bash
# Local development - serve from src/
python -m http.server 8000
# or
npx http-server src/
```

There are no linters, formatters, or test suites configured.

## Deployment

- Hosted on **Azure Static Web Apps**
- CI/CD via GitHub Actions (`.github/workflows/azure-static-web-apps-victorious-glacier-025bec503.yml`)
- Push to `main` triggers automatic deployment
- The `src/` directory is deployed directly (no build output)
- PRs get automatic staging environments

## Architecture

Everything is in a single HTML page (`src/index.html`) with inline JavaScript and a separate stylesheet (`src/styles.css`).

**Page sections** (anchor-linked navigation): Hero (#home), About (#about), Skills (#skills), Projects (#projects), Contact (#contact).

**Interactive terminal demo** in the hero section simulates an ArgoCD application sync. The JS handles typing animation (`typeChar()`), sync simulation (`applyConfiguration()`), and reset (`resetToCode()`). The execute button toggles between code view and sync output.

**Scroll animations** use Intersection Observer to add a `.visible` class for fade-in effects.

**CSS** uses custom properties for theming (colors, shadows). Responsive breakpoints at 768px and 480px.

**Dark mode** is implemented using `[data-theme="dark"]` CSS selector. Theme toggle button in navigation switches between light/dark modes. Preference is saved in localStorage and respects system `prefers-color-scheme` setting. The `initTheme()`, `toggleTheme()`, and `updateThemeIcon()` functions handle theme management.

**External dependencies** (CDN only): Font Awesome 6.5.0, Google Fonts (Inter, JetBrains Mono).

## Azure SWA Configuration

Two config files handle routing:
- `staticwebapp.config.json` (root) — 404 error page override
- `src/staticwebapp.config.json` — navigation fallback routing
- `src/routes.json` — asset routing exclusions

## SEO

The site includes structured data (JSON-LD Person schema), Open Graph meta tags, `robots.txt`, and `sitemap.xml`.
