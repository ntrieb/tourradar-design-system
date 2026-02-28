# CLAUDE.md

## Project Overview

TourRadar SCOUT Design System - A comprehensive HTML component library implementing every component from TourRadar's design system.

## Commands

```bash
npm start        # Start dev server on port 3003
```

## Architecture

Static HTML site, no build step:

```
public/
  index.html     # Complete component showcase (single file)
  assets/        # Logo and static assets
```

- Vanilla CSS with custom properties (no Tailwind)
- Vanilla JS for interactive components
- Deployed to Vercel as static site: https://tourradar-design-system.vercel.app

## Design Tokens

All tokens defined as CSS custom properties in `:root` of `index.html`. Source of truth is the SCOUT Design System Figma file and the live TourRadar website.

## Figma Source

https://www.figma.com/design/xbrz3u2rdry1LmCOz12dTh/SCOUT-Design-System
