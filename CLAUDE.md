# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Landing page for **רגעים אמיתיים** — a Hebrew-language wedding photography business. Single-file HTML/CSS/JS, no build system or dependencies.

## Development

Open `index.html` directly in a browser — no server needed. All code lives in one file.

## Architecture

`index.html` is fully self-contained:
- **Fonts**: Google Fonts CDN — Frank Ruhl Libre (display/headings) + Heebo (body)
- **CSS**: Embedded `<style>` block with CSS custom properties for the color palette
- **JS**: Inline `<script>` at bottom — IntersectionObserver for scroll reveals, navbar scroll state, parallax, form feedback
- **No framework, no build step, no dependencies**

## Design System

All colors are defined as CSS variables on `:root`:
- `--bg` / `--bg2`: near-black backgrounds
- `--cream` / `--cream2`: warm ivory text
- `--gold` / `--gold2`: warm bronze accent (#c4954a / #9e7038)
- `--border`: subtle gold border (`rgba(196,149,74,0.2)`)

Typography scale uses `clamp()` for responsive sizing. All text and layout are RTL (`dir="rtl"`, `lang="he"`).

## Sections (in order)

1. **Nav** — fixed, becomes opaque+blur on scroll
2. **Hero** — full-viewport, animated title with outlined text effect
3. **About** — two-column: photo placeholder + text with pull quote
4. **Gallery** — 12-column CSS grid with 7 editorial-layout cells
5. **Services** — 3 pricing cards (basic / featured / premium)
6. **Testimonials** — 3-column cards with star ratings
7. **Contact** — two-column: info details + form
8. **Footer**

## Content to Replace

Gallery cells use gradient placeholders (`ph1`–`ph7`). Replace `.photo-inner` backgrounds with real `background-image: url(...)` or `<img>` tags.

Contact details (phone, email, Instagram) are placeholders — update before launch.
