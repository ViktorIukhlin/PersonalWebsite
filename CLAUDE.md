# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```sh
npm run dev      # Start dev server at localhost:4321/PersonalWebSite
npm run build    # Build for production to ./dist/
npm run preview  # Preview production build locally
```

## Architecture

Single-page portfolio site built with **Astro 5** (static output).

```
src/
├── components/          # Reusable UI components
│   ├── Hero.astro       # Hero section with photo, contacts, navigation
│   ├── Summary.astro    # About me text with blockquote
│   ├── Experience.astro # Work experience timeline
│   ├── Skills.astro     # Skills grid + languages
│   ├── Education.astro  # Education section
│   ├── Links.astro      # Social links (GitHub, LinkedIn, Telegram, etc.)
│   └── Footer.astro     # Page footer
├── data/
│   └── profile.ts       # All personal data (contacts, experience, skills)
├── layouts/
│   └── Layout.astro     # Base HTML layout + global CSS variables
└── pages/
    └── index.astro      # Main page - imports and composes components
```

## Data Management

All personal information is centralized in `src/data/profile.ts`:
- Contact info (email, phone, social links)
- Work experience with highlights
- Skills by category
- Education
- Projects

Components import and use this data directly.

## Styling

- **Theme:** Dark background (#000) with golden accent (#d4a84b)
- **CSS Variables:** Defined in `Layout.astro` (--color-accent, --color-text-muted, etc.)
- **Scoped CSS:** Each component has its own `<style>` block
- **Font:** Inter (Google Fonts)
- **Responsive:** Mobile-first with breakpoints at 768px and 1024px

## Deployment

GitHub Actions (`.github/workflows/deploy.yml`) auto-deploys to GitHub Pages on push to `main`.

**Site URL:** https://viktoriukhlin.github.io/PersonalWebSite/

## Key Files

| File | Purpose |
|------|---------|
| `astro.config.mjs` | Sets `site` and `base` for GitHub Pages |
| `src/data/profile.ts` | Central data source for all content |
| `public/Viktor_Iukhlin_CV.pdf` | Downloadable CV |
| `public/favicon.svg` | Site favicon |

## Adding Content

- **New experience:** Add to `profile.experience[]` in `profile.ts`
- **New skills:** Add to appropriate category in `profile.skills`
- **Photo:** Add PNG with transparent background to `public/`, update `Hero.astro`
- **Social links:** Update URLs in `profile.ts`
