# CLAUDE.md — drewbefree.github.io

## Project Overview
Personal GitHub Pages site for Andrew Webb (Atlanta, GA). Serves as a command center / portfolio linking to business sites and hosting small utility apps.

## Owner
Andrew Webb · drewbefree.github.io

## File Structure
```
/
├── index.html          # Main command center / landing page
├── CLAUDE.md           # This file
└── apps/
    └── poker/
        └── index.html  # Poker Night app (poker-timer.html in dev)
```

> Note: The poker app lives at `apps/poker/index.html` in the repo. The working/dev filename used during editing sessions has been `poker-timer.html`.

## Tech Stack
- **Pure HTML/CSS/JS** — no build tools, no frameworks, no npm
- Single-file architecture: each app is a self-contained `.html` file
- Google Fonts loaded via CDN (Playfair Display, Courier Prime, Orbitron, etc.)
- No backend, no database — everything runs client-side

## Deployment
- Hosted on **GitHub Pages** from the `main` branch
- Pushing to `main` deploys automatically
- No build step required — what's in the repo is what's live

## Sites Referenced (external, not in this repo)
| Card | URL |
|------|-----|
| Kybernet | https://kybernet.tech |
| Surf the Webb | https://surfthewebb.com |
| DW Solutions | https://dwebbsolutions.com |

## Apps
### Poker Night (`apps/poker/index.html`)
- No-Limit Hold'em cash game session manager
- Features: session timer, round tracking, buy-ins/rebuys, mid-game cashouts, end-of-night payout calculator
- Mobile responsive
- Has a `beforeunload` guard to warn before navigating away from an active session
- CSV export and print/PDF view built in
- Chip legend: White $0.50 · Red $1.00 · Blue $5.00 · Green $10.00

## Design Conventions
### index.html (Command Center)
- Dark terminal/cyberpunk aesthetic
- CSS variables in `:root` — use these, don't hardcode colors
- Card accent colors set via inline `--card-accent` and `--card-glow` CSS vars
- Staggered fade-up entrance animations via `opacity:0` + named `@keyframes fadeUp`
- New site cards go in `.site-grid`; new app cards go in `.app-grid`

### Poker Night
- Casino/felt aesthetic — deep greens, gold, cream
- CSS variables in `:root` — use these, don't hardcode colors
- Fonts: Playfair Display (headings/display), Courier Prime (mono/body)
- Mobile breakpoints at 750px and 480px

## Common Tasks
- **Add a new app card**: Edit `index.html`, copy an existing `.card` block inside `.app-grid`, update the `card-id`, icon, name, URL, desc, tags, and `href`
- **Update a site link**: Find the relevant `.card` `href` in `index.html`
- **Update version/date on a card**: Edit the `card-meta` span (e.g. `v20 · 2026-03-10`)
- **Update terminal readout**: Edit the `.terminal` div near the bottom of `index.html`
- **Push changes**: `git add . && git commit -m "message" && git push`
