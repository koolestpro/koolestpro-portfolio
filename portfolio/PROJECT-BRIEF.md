# KOOLESTPRO Portfolio — Project Brief
> Paste this into any new chat to instantly pick up the project.

---

## What We're Building
A dark-themed, single-page portfolio for **Ridwan Adekunle (@koolestpro)** — Shopify CRO & UX Designer based in Ibadan, Nigeria. The page is designed to be shared as a cold outreach link and answers 7 recruiter/client questions in order: **Who → What → Work → Process → Results → Tools → Hire**.

**Primary file:** `/Users/mac/Downloads/replo-rebuilds/portfolio/index.html`

---

## Person Details
- **Name:** Ridwan Adekunle
- **Handle:** @koolestpro
- **Role:** Shopify CRO & UX Designer
- **Location:** Ibadan, Nigeria
- **Calendly:** https://calendly.com/sirridwan721/30min
- **Email:** sirridwan721@gmail.com
- **Platforms:** Fiverr · Contra · LinkedIn (koolestpro) · Instagram · Twitter/X
- **Real clients:** tapandrate.co.uk · championbiotics.com · motherofmacros.com
- **Stats:** 100+ Projects · 6+ Years · 5-Star Rated · Replo Expert

---

## Brand System
- **Display font:** Syne 800 (Google Fonts)
- **Body/labels font:** DM Mono 400 (Google Fonts)
- **Body text font:** DM Sans 400/500 (Google Fonts)
- **Colors:**
  - `--bg: #0a0a0a` — page background
  - `--surface: #141414` — card/section backgrounds
  - `--surface-2: #1b1f23` — elevated surfaces
  - `--text: #f0ede8` — primary text
  - `--orange: #FF9500`
  - `--pink: #E040A0`
  - `--purple: #7B2FBE`
  - `--gradient: linear-gradient(90deg, #FF9500, #E040A0, #7B2FBE)` — brand gradient
- **Custom easing:** `cubic-bezier(0.16, 1, 0.3, 1)` on ALL transitions (expo-out)
- **Gradient text rule:** Use CSS `background-clip: text` for HTML headings; SVG `<linearGradient>` for exported/print graphics
- **No emoji — ever.** Every icon = inline SVG

---

## Page Architecture (8 Sections)

| # | ID | Section | Key Content |
|---|-----|---------|-------------|
| NAV | nav | Navigation | Logo (gradient) · Work/Services/Process/Contact links · "Let's work →" CTA · Transparent → solid on scroll |
| S1 | hero | Hero | Availability badge · "Shopify pages that convert." headline · subline · 4 stats · 2 CTAs |
| S2 | services | Services | "WHAT I DO" label · "From Figma to first sale." · 6 service cards in 3-column grid |
| S3 | work | Work | "WORK" label · "100+ builds. Every one custom." · Vertical hover-reveal list · Cursor-following preview card · Click opens drawer |
| S4 | process | Process | "HOW IT WORKS" · 5 numbered steps |
| S5 | results | Results | 3 stats + 3 testimonial cards |
| S6 | stack | Stack | "TOOLS" · Two-row CSS marquee (opposite directions) |
| S7 | about | About | Single para positioning + credentials row + photo frame |
| S8 | hire | Hire | "Ready when you are." · Calendly CTA · Payment icons · Social links |
| FTR | footer | Footer | Copyright + availability status dot |

---

## Key Interactions / Signature Moments

### 1. Cursor-Following Work Preview
- Work section has a `#work-preview` div: `position: fixed`, 280×180px
- Follows cursor inside `.work-list` using `requestAnimationFrame` + `lerp(a, b, 0.12)`
- Each project has a unique `gradient` in the PROJECTS array → applied as preview bg
- Shows big project number (ghost) + brand name + type
- Only appears on desktop (`@media (hover: none)` hides it on touch devices)
- Transition: `opacity 0.3s var(--ease), transform 0.3s var(--ease)` (scale + slight rotate)

### 2. Slide-In Case Study Drawer
- `#drawer-overlay` (full-screen dim, blur) + `#drawer` (480px right panel)
- Desktop: slides from right (`translateX(100%)` → `translateX(0)`)
- Mobile (<480px): slides from bottom (`translateY(100%)` → `translateY(0)`, 85vh, rounded top corners)
- Content populated from PROJECTS array `caseStudy` object
- Close: click overlay, click close button, or press Escape

### 3. CSS Marquee (Stack Section)
- Row 1 (left direction): Shopify · Figma · Replo · Liquid · HTML/CSS · JavaScript · Framer · Webflow · Lottie · GSAP
- Row 2 (right direction): Google Analytics · PageSpeed Insights · Klaviyo · Metafields · Instant Pages · Git · VS Code · Notion · Linear · Hotjar
- Pure CSS `@keyframes`, no JS. Items duplicated for seamless loop.

### 4. Scroll Reveals
- `IntersectionObserver` with `threshold: 0.1`
- `.reveal` class: `opacity: 0; transform: translateY(24px)` → `.visible`
- Stagger via `data-delay="1"` through `"5"` (0.1s increments)

### 5. Hero Load Animation
- `@keyframes fade-up` staggered on: badge → h1 → subline → stats → CTAs
- Delays: 0.1s, 0.2s, 0.35s, 0.45s, 0.55s

### 6. Smooth Scroll
- Lenis from CDN: `https://cdn.jsdelivr.net/npm/@studio-freight/lenis@1.0.42/dist/lenis.min.js`
- Initialized with `duration: 1.2, smoothWheel: true`
- Integrated with IntersectionObserver RAF loop

---

## PROJECTS Array Structure

```js
const PROJECTS = [
  {
    id: 'kura-pdp',
    num: '01',
    brand: 'KURA',
    title: 'KURA Board — Product Page',
    type: 'PDP',
    gradient: 'linear-gradient(135deg, #1a1a2e 0%, #c47a3a 100%)',
    url: '../brands/kura/pages/kura-pdp-01/index.html',
    status: 'concept',
    caseStudy: {
      headline: '...',
      tools: ['Replo', 'Figma', 'Custom CSS'],
      decisions: ['...', '...', '...'],
      result: '...'
    }
  },
  // tapandrate, championbiotics, motherofmacros, kura-ad, kura-hp, kura-listicle
];
```

---

## 6 Services
1. CRO Audit & Strategy
2. Shopify Store Design
3. Store Redesign / Rebuild
4. Custom Section Development
5. Static Ad Design
6. Email Template Design

---

## 5 Process Steps
1. **Request** — You send a brief or we hop on a 15-min call
2. **Estimate** — I scope the build and send a clear quote
3. **Assets** — You share brand files, copy, and references
4. **Build** — I build and send previews for your feedback
5. **Launch** — Final files delivered, ready to ship

---

## Background Texture
NOT a plain dark background. Uses:
- CSS grid lines: `repeating-linear-gradient` at 80px × 80px, 4% opacity
- Corner radial glows: orange top-left, purple bottom-right
- All via `body::before` and `body::after` pseudo-elements (both `position: fixed`)

---

## Rules (from CLAUDE.md)
- Mobile-first CSS only — `min-width` queries, never `max-width`
- No emoji anywhere — inline SVG for every icon
- No external JS except Lenis CDN
- All colors in `:root` — never hardcode hex in components
- Custom ease `cubic-bezier(0.16, 1, 0.3, 1)` on all transitions
- Section separator comments: `<!-- ═══ SECTION N: NAME ═══ -->`
- Edit comments: `<!-- EDIT: ... -->` on every editable text node

---

## What's Done / What's Next

| Item | Status |
|------|--------|
| Plan approved by user | Done |
| index.html written | In progress |
| PROJECT-BRIEF.md | Done |
| Real project thumbnails (swap placeholders) | Pending |
| Multi-page version | Pending (Phase 2) |
| Case study HTML files | Pending (Phase 3) |

---

## Files in This Project
```
portfolio/
├── index.html          ← Single-page portfolio (main deliverable)
├── PROJECT-BRIEF.md    ← This file — context for any chat
└── images/             ← Add real screenshots/thumbnails here
```
