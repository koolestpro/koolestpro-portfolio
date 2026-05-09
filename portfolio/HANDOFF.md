# Portfolio Handoff Summary

## Project

Portfolio site folder:

`/Users/mac/Downloads/replo-rebuilds/portfolio`

Main file:

`/Users/mac/Downloads/replo-rebuilds/portfolio/index.html`

## Major Changes Completed

- Fixed Lenis smooth scroll conflicts and modal/drawer scrolling.
- Made the work drawer scrollable with mouse/touch.
- Added project drawer structure with cover, video, full-page experience preview, mobile highlights, tools, decisions, and outcome sections.
- Added local iframe embeds for KURA concept pages.
- Added desktop/mobile toggle for embedded project previews.
- Switched embedded previews to a laptop-style scaled desktop viewport.
- Removed outbound "View the build" buttons from all project popups.
- Added new work items:
  - Ishu
  - Jellys Glamour
  - Captain & Skipper
  - Titanium
- Updated covers, videos, and mobile assets per project.
- Made hover preview show real cover images/videos.
- Updated About image to `images/exports/ridwan-crop.png`.
- Improved tools marquee:
  - removed Webflow, Framer, and Linear
  - added icons under `images/exports/icons`
  - improved marquee pacing and styling
- Added curved section exit dividers.
- Updated social/payment areas:
  - social: LinkedIn, Twitter/X, Instagram
  - payments: PayPal, Wise, Payoneer, Wire transfer

## Recent Media Rules

- Mobile highlights now show full images with `object-fit: contain`.
- If a project has no cover image, the drawer cover falls back to video.
- Champion Biotics:
  - laptop video used for cover/hover/full-page experience
  - mobile video used for mobile highlights
- Ishu:
  - uses `images/exports/ishu-experience.mp4`
- Mother of Macros:
  - only cover plus written content shown until more assets are available
- KURA advertorial/home/listicle:
  - embedded local pages
  - preview screenshots generated and used as cover/hover
  - mobile highlights hidden where no real mobile media exists

## Key Commits

- `25e9b47` Build Ridwan portfolio updates
- `f72cb56` Improve project preview experience
- `0d9df3d` Embed local KURA concept pages
- `1d46d38` Use desktop laptop project embeds
- `2ea18be` Update portfolio work showcase
- `65832f9` Refine portfolio media previews
- `10a507e` Update drawer media behavior

## Known Git Status

There are still unstaged deleted/unused assets intentionally left untouched, mostly old long filenames and replaced images:

- `_Users_mac_Downloads...` export files
- `captain-skippers-mobile.png`
- `pastwork-laptop-mobile-1.png`

There are also unused untracked assets:

- `Frame 427318741.png`
- `Frame 427318751.png`
- `Scene_20251116110429.gif`
- petticoat files
- `tapandrate-pdp-cover.avif`

## GitHub

The local git repo is initialized and committed. GitHub push was blocked because `gh` is not installed and HTTPS GitHub auth failed on this machine.
