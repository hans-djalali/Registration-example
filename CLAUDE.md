# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static showcase of 5 progressive versions of a mobile registration page, demonstrating iterative UI/UX improvements. Hosted on GitHub Pages at `hans-djalali/Registration-example`.

## Architecture

Each version is a **standalone, self-contained HTML file** with inline `<style>` and `<script>` — no build tools, bundlers, or external dependencies.

- `index.html` — **V1**: Bare-minimum form (plain gray, no validation, password shown as plain text intentionally)
- `v2.html` — **V2**: Adds labeled fields, required indicators, email/password validation, styled form
- `v3.html` — **V3**: Adds password strength meter, requirements checklist, confirm password, eye-toggle visibility
- `v4.html` — **V4**: Full-featured — social login buttons, gradient card design, inline field errors with red borders, terms checkbox, success overlay animation
- `v5.html` — **V5**: Fully accessible — WCAG 2.1 AA compliant with `<form>` wrapper, `aria-required`/`aria-invalid`/`aria-describedby` on all inputs, `aria-live` regions for strength meter and match indicator, focus trap on success dialog, `prefers-reduced-motion` support, 44px touch targets, semantic landmarks (`<main>`, `<nav>`, `<form>`)

All five pages share a **version navigation bar** (dot pagination + arrows) linking between them. The nav markup is duplicated in each file.

## Key Conventions

- **Mobile frame**: Fixed 375×812px container (`.mobile-frame`) simulating a phone screen
- **Color palette**: Dark warm background (`#1A0900`), amber/brown tones (`#B45309`, `#FDE68A`, `#92400E`), cream form backgrounds (`#FFFBF5`)
- **Font stack**: `-apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`
- **Toast notifications**: Each page uses a `.toast` element for form feedback messages
- **CSS classes are version-prefixed**: `.v1-*`, `.v2-*`, `.v3-*`, `.v4-*`, `.v5-*` for version-specific elements; shared classes (`.form-input`, `.form-label`, `.form-group`) are reused across V2–V5
- **Byline**: Fixed-position "made by Hans Djalali" on every page — preserve this

## Development

No build step. Open any HTML file directly in a browser, or use a local server:

```
npx serve .
```

Since this is hosted on GitHub Pages, `index.html` is the entry point (V1).
