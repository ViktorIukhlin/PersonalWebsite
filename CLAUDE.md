# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

## Commands

```sh
npm run dev      # Start dev server at localhost:4321/PersonalWebsite
npm run build    # Build for production to ./dist/
npm run preview  # Preview production build locally
```

## Architecture

Single-page portfolio site built with **Astro 5** (static output).

```
src/
├── components/
│   ├── BackgroundLayer.astro  # Fixed background with photo and blur effect
│   ├── Navigation.astro       # Fixed bottom navigation with sliding indicator
│   ├── ThemeToggle.astro      # Light/dark theme toggle button
│   ├── Hero.astro             # Hero section with name, role, contacts
│   ├── Summary.astro          # About me section
│   ├── Experience.astro       # Work experience timeline
│   ├── Skills.astro           # Skills grid + languages
│   ├── Education.astro        # Education section
│   ├── Links.astro            # Social links
│   └── Footer.astro           # Page footer
├── data/
│   └── profile.ts             # All personal data (centralized)
├── layouts/
│   └── Layout.astro           # Base HTML layout + global CSS + section animations
└── pages/
    └── index.astro            # Main page composition
```

## Key Files

| File | Purpose |
|------|---------|
| `astro.config.mjs` | Site and base URL for GitHub Pages |
| `src/data/profile.ts` | All content data |
| `public/ViktorIukhlinResume.pdf` | Downloadable resume |
| `public/hero-photo.png` | Hero background photo |

## Styling

- **Themes:** Dark (default) and Light
- **Accent colors:** Golden (`rgb(255, 184, 0)`) for dark, Blue (`#4a9fd4`) for light
- **CSS Variables:** Defined in `Layout.astro`
- **Font:** Inter (Google Fonts)
- **Responsive:** Breakpoints at 480px, 768px, 1024px, 1280px

## Deployment

GitHub Actions auto-deploys to GitHub Pages on push to `main`.

**Live:** https://viktoriukhlin.github.io/PersonalWebsite/
