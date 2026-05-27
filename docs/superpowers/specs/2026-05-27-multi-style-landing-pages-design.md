# Multi-Style Landing Pages Design

## Overview

Create three distinct visual styles for the Milan Chinese Christian Church landing page, all sharing the same content structure but with different layouts, color schemes, and typographic choices. Deploy as a single GitHub Pages site with subdirectory routing.

## Architecture

### Directory Structure

```
MilanChiesa/
├── index.html        ← Root: style selector page with links to v1/v2/v3
├── v1/
│   └── index.html    ← Current style: Navy blue modern
├── v2/
│   └── index.html    ← Warm elegant style
├── v3/
│   └── index.html    ← Bold contemporary style
├── CLAUDE.md
├── Logo.js           ← SVG logo reference (inline in HTML)
├── Mark.js           ← SVG mark reference (inline in HTML)
└── docs/
```

### Deployment

- GitHub Pages serves from repo root on `master` branch
- Each version accessible at `username.github.io/MilanChiesa/v1/`, `/v2/`, `/v3/`
- Root `index.html` is a simple style selector with three cards linking to each version
- No build tools, no framework — pure HTML/CSS/JS per version
- User will preview locally before pushing to GitHub

### Branch Strategy

- `v2-style` branch: create v2 directory and files
- `v3-style` branch: create v3 directory and files
- Merge both into `master`
- Do NOT push until user approves local preview

## Shared Content (All Versions)

All three versions share the same content structure:

1. **Hero**: Church name + tagline "在米兰，一起认识爱" + dual CTA
2. **About Us**: Church description + 4 value cards (敬拜、团契、宣教、服事)
3. **History**: 6 timeline milestones (2005-2022)
4. **Vision**: Quote block with Isaiah 60:1
5. **Team**: 1 leader + 6 workers
6. **Fellowship**: 12 fellowship group cards
7. **Newcomer**: Guide + contact form
8. **Footer**: Address, schedule, contact info

SVG logos (navbar logo + hero mark) are shared across all versions via inline SVG.

## Style Definitions

### v1: Modern Fresh (Current)

- **Colors**: Navy `#2c3e50`, sky blue `#3498db`, white cards
- **Font**: Source Han Sans SC throughout
- **Hero**: Blue gradient, centered text, white CTA buttons
- **Cards**: White background, subtle shadow, rounded corners
- **Layout**: Vertical timeline, horizontal scroll carousel for fellowship
- **Navbar**: Dark navy with white text

### v2: Warm Elegant

- **Colors**:
  - Background: Cream `#FDF6EC`
  - Primary: Wine red `#8B3A3A`
  - Accent: Gold `#C9A84C`
  - Text: Dark brown `#3D2B1F`
  - Card bg: Warm white `#FFF9F0`
- **Font**: Noto Serif SC for headings, Noto Sans SC for body
- **Hero**: Warm gradient (cream to light gold), serif title, wine-red CTA
- **Layout differences**:
  - About section: left-text/right-image magazine style (image placeholder)
  - History: horizontal timeline with gold line
  - Fellowship: grid cards with wine-red left border accent
  - Vision: cream background with gold quote border
- **Navbar**: Semi-transparent cream with dark text
- **Footer**: Deep wine red `#5A1A1A` background, gold accents

### v3: Bold Contemporary

- **Colors**:
  - Background: Deep charcoal `#0F0F1A`
  - Primary: Coral `#FF6B6B`
  - Accent: Teal `#4ECDC4`
  - Text: Light gray `#E8E8E8`
  - Card bg: Dark `#1A1A2E`
- **Font**: System sans-serif, bold weights, large sizes, tight line-height
- **Hero**: Full-screen dark, huge centered title (60px+), coral glowing CTA buttons
- **Layout differences**:
  - About: cards with gradient borders, hover scale effect
  - History: vertical but with neon-accent timeline dots
  - Fellowship: large horizontal cards (80% viewport width), story-card style scroll
  - Vision: full-screen dark + giant quote text, pure typographic impact
- **Navbar**: Transparent dark, becomes solid on scroll
- **Footer**: Minimal single-row with social icons

## Root Index Page

Simple style selector with three cards:
- Each card shows style name + brief description + color preview
- Links to `/v1/`, `/v2/`, `/v3/`
- Clean design, centered layout

## Implementation Order

1. Move current `index.html` into `v1/index.html`, update relative paths
2. Create root `index.html` (style selector)
3. Create `v2/index.html` on `v2-style` branch
4. Create `v3/index.html` on `v3-style` branch
5. Merge both branches into `master`
6. User local preview
7. Push when approved

## Constraints

- No push to GitHub until user approves local preview
- Auto-commit after each approved change
- All versions are self-contained single HTML files (inline CSS/JS)
- Responsive design (mobile-first) for all versions
- SVG logos embedded inline in all versions
