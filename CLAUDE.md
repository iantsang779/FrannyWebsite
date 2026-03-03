# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-page portfolio website for vocalist/performer Franny McGirr. Pure HTML + CSS + vanilla JS — no framework, no build tool, no dependencies beyond Google Fonts.

## Development

No build step. Open `index.html` directly in a browser:

```bash
# Quick local server if needed (avoids iframe restrictions)
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Architecture

Everything lives in `index.html`:
- **`<style>`** block — all CSS, variables defined as custom properties at `:root`
- **`<body>`** — six sections in order: `#hero`, `#about`, `#performances`, `#timeline`, `#contact`, footer
- No `<script>` block — smooth scroll handled by CSS `scroll-behavior: smooth`

**Colour palette** (CSS custom properties in `:root`):
- `--bg: #fdf6f0`, `--accent: #c9a0dc`, `--accent2: #f4a7b9`, `--text: #3a3a3a`

**Fonts:** `Cormorant Garamond` (headings) + `DM Sans` (body) via Google Fonts.

## Key URLs

| Purpose | URL |
|---|---|
| Booking form | `https://docs.google.com/forms/d/e/1FAIpQLSdbBF7EpIIW4PdhOTXle-tfB_I47f36q_tAHD41muyt7OmJLw/viewform` |
| YouTube channel | `https://www.youtube.com/@FrannyYouTube` |
| Instagram | `https://www.instagram.com/youtubefranny` |
| TikTok | `https://www.tiktok.com/@frannythebard` |
| Email | `frannymcgirr@outlook.com` |

## Headshot

The current headshot is a CSS-styled `<div>` with initials "FM". To replace with a real photo:

```html
<img src="headshot.jpg" alt="Franny McGirr" class="headshot" style="object-fit:cover;" />
```

## Git Workflow

After every change to the code:
1. Stage the relevant files (`git add <files>`)
2. Propose a clear, concise commit message
3. **Ask the user for approval before committing**
4. **Ask the user for approval before pushing**

Never commit or push without explicit user confirmation first.

## Responsive Layout

- Mobile breakpoint: `640px` (single column, stacked videos, simplified timeline cards)
- YouTube embeds use `aspect-ratio: 16/9` wrapper + absolute-positioned `<iframe>`
