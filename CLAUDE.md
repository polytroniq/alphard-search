# Alphard Tracker

## Project
A React-based car search tracker for Toyota Alphard 20-series imports. Single-page app in `index.html` using React 18 via CDN + Babel transpilation. Data stored as JSON files per car. Hosted on GitHub Pages from the `claude/alphard-tracker-app-vkpzX` branch.

## Repo Structure
```
index.html              — Main app (React, all components + styles inline)
data/config.json        — Global questions + target spec
cars/car01/data.json    — Per-car data (specs, questions, notes)
cars/car01/photos/      — Car images
cars/car02/...
```

## Key Details
- **Default branch**: `claude/alphard-tracker-app-vkpzX` (GitHub Pages deploys from here)
- **Tabs**: Cars Considered | Outstanding Questions | Specs | Trims | Target Spec
- Each car has: core stats (always visible), extra stats (behind toggle), inline questions with status cycling, photo gallery with lightbox
- SPECS tab: Alphard variants across 4 generations (AH10–AH40), embedded as `ALPHARD_SPECS` JS constant
- Trims tab: AH20 model codes & feature matrix infographic, embedded as `TRIMS_HTML`/`TRIMS_CSS` constants rendered via `dangerouslySetInnerHTML`
- GitHub save feature: PAT stored in localStorage, writes car data back to repo via GitHub API
- Car data auto-saves to localStorage; "Reset to original data" clears it

## Conventions
- Auto-commit and push after every change
- Car folders are sequential: `car01`, `car02`, etc.
- New fields added to car JSON should have `"TBC"` as default
- Questions use status cycle: `to_ask` → `awaiting` → `resolved`
- Verdicts cycle: `pass` → `investigating` → `shortlisted`
- Beige/cream interior is acceptable (no warning styling)
- Photos go in `cars/carNN/photos/`; the app discovers them via GitHub API

## Current Cars
1. car01 — Algys import option
2. car02 — Algys import option
3. car03 — South Coast Jap Autos
4. car04 — Alphard 350S, £12,990, AutoTrader (UK stock)
5. car05 — Alphard 350G L-Package Business Edition, £14,495, Japanese MPV Motors
