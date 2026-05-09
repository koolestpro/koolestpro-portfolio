# Build Workflow — 6-Phase Pipeline

Every product goes through this exact sequence, in this exact order.
Do not skip phases. Do not jump ahead. Each phase output feeds the next.

---

## PHASE 0 — Product Intake

**Trigger:** You share a product with Cowork.

**You provide:**
- Product name (or working title)
- 1–3 product images (from the dropship platform)
- Short product description (can be the supplier copy, unpolished is fine)
- Page type you want to build (PDP / Homepage / Landing Page / Advertorial / Listicle)
- Template preference (optional — Cowork will suggest the best fit if not specified)

**Cowork does:**
- Confirms the product, page type, and template selection
- Suggests the most suitable template ID with reasoning
- Confirms before moving to Phase 1

**Output:** Confirmed product brief + template selection

---

## PHASE 1 — Brand Identity

**Trigger:** Product brief confirmed.

**Cowork generates:** `[brand]-identity.html`

This single HTML file contains:

```
01 — Brand Overview
     Brand name (invented, ownable, memorable)
     Hero product name
     Tagline
     Positioning statement

02 — Target Customer
     3 buyer personas with names, ages, pain points

03 — Color System
     5-color palette with hex codes and usage roles
     Color rationale paragraph

04 — Typography
     Display / Serif / Body / Mono font stack
     Usage rules per typeface

05 — Voice & Tone
     Do / Don't table
     2 side-by-side copy examples (off-brand vs on-brand)
     Brand voice in one line

06 — Product Line Naming
     Hero SKU + 4 potential extension products

07 — Shopify / Replo Store Guidelines
     Logo rules, button style, image direction,
     template colour mapping, review strategy, SEO

08 — AI Image Prompts
     6 prompts covering every page type use case:
       - Hero product shot
       - Lifestyle in-use shot
       - Villain/problem shot
       - Flat lay / specs shot
       - Social proof / person shot
       - Detail / close-up shot
     + Universal style modifier to append to all prompts
     Each prompt has a Copy button

09 — Page Copy (varies by page type)
     Full copy for every section of the chosen page type,
     written in the brand voice, in collapsible accordions.
     Sections map 1:1 to the selected template.
```

**File saved to:** `brands/[brand-name]/[brand]-identity.html`

**You review:** Check brand name, colors, voice. Request any changes before moving on.

**Output:** Approved brand identity HTML file

---

## PHASE 2 — Image Generation

**Trigger:** Brand identity approved.

**You do:**
- Open `[brand]-identity.html` → Section 08
- Copy each prompt into your AI image tool (Midjourney / DALL·E / Ideogram)
- Generate images
- Share generated images back in the Cowork chat

**Cowork does:**
- Reviews each image against the brand brief
- Gives specific feedback per image (usable / needs re-gen / minor fix)
- Confirms which images map to which page sections
- Names and organises the images for you:

```
brands/[brand-name]/assets/images/
  hero.png          ← Primary product, dark background
  lifestyle.png     ← Active use, warm kitchen/lifestyle setting
  villain.png       ← Problem/before image
  sizes.png         ← Flat lay / size lineup
  person.png        ← Person holding / using product
  detail.png        ← Close-up / feature detail shot
```

**Output:** Approved image set, named and placed in assets folder

---

## PHASE 3 — Page Build

**Trigger:** Images approved and placed.

**Cowork generates:** `[brand]-[type]-[template-id]/index.html`

Build standards (non-negotiable):
- Mobile-first responsive (375px → 768px → 1280px breakpoints)
- All images referenced from `./images/` folder (relative paths)
- Inline SVG for all icons — zero icon font dependencies
- No external JS libraries — vanilla JS only
- Google Fonts via `<link rel="preconnect">` + display=swap
- CSS custom properties (design tokens) in `:root` — all brand colors there
- `<!-- EDIT: -->` comments on every editable text block
- `<!-- IMAGE: -->` comments on every image src
- Sections separated by clear comments: `<!-- ═══ SECTION NAME ═══ -->`
- Scroll fade-in animations on sections (IntersectionObserver)
- Working interactions: gallery thumbnails, FAQ accordion, variant selector, ATC button

**Template sections (map to page type):**

> See `CLAUDE.md` → Section: Template Section Maps for the full section list per page type.

**Performance checklist before delivery:**
- [ ] Passes mobile layout at 375px
- [ ] Sticky elements don't overlap content
- [ ] All images display (no broken paths)
- [ ] All JS interactions work
- [ ] No horizontal scroll on mobile
- [ ] Fonts load (check with slow connection simulation)

**Files saved to:**
```
brands/[brand-name]/pages/[brand]-[type]-[template-id]/
  index.html
  images/
    hero.png
    lifestyle.png
    (etc — copied from assets/images/)
```

**Output:** Delivered `index.html` + image folder, ready to open in browser

---

## PHASE 4 — Review & Polish

**Trigger:** Page delivered.

**You do:**
- Open `index.html` in browser
- Check all three breakpoints (mobile, tablet, desktop)
- List any fixes or copy changes needed

**Cowork does:**
- Applies all requested changes via targeted `str_replace` edits
- No full rewrites unless the structure changes
- Re-delivers only changed sections if minor

**Output:** Final approved `index.html`

---

## PHASE 5 — Case Study

**Trigger:** Page approved and final.

**Cowork generates (2 files):**

### `[brand]-case-study.html`
A Behance-style single-page case study document. Agency quality.

Structure:
```
Cover                  — Brand name, project type, hero image
01 The Brief           — Product, target customer, business goal
02 Brand Strategy      — Name rationale, positioning, color choices
03 Visual Identity     — Color palette, typography specimens, logo
04 Image Direction     — Prompt approach, mood board grid
05 The Build           — Page type, template used, key design decisions
06 Section Walkthrough — Annotated screenshots of key page sections
07 Results / Outcome   — What was built, portfolio use, learnings
08 Next Steps          — What this brand could scale to
```

Design direction:
- Dark/editorial aesthetic (slate background, cream text, copper accents)
- Full-bleed section headers
- Page screenshots as embedded images or mockup frames
- Section numbers in large display type
- Tight, professional layout — looks like an agency deliverable

### Social content brief (inside the case study file or separate):
```
LinkedIn post copy    ← Professional announcement
Instagram caption     ← Shorter, visual-led
Twitter/X thread      ← 3-5 tweet breakdown of the build
Video script outline  ← For personal walkthrough video
```

**File saved to:** `brands/[brand-name]/case-study/`

**Output:** Case study HTML + social content brief

---

## PHASE 6 — Archive & Next Product

**Trigger:** Case study complete.

**Cowork does:**
- Updates the brand entry in `README.md` → Current Brands table
- Confirms all files are in the right folders
- Suggests the next page type to build for this brand (e.g., if a PDP was built, suggest the homepage or a landing page variant)
- Clears context for the next product

**Output:** Updated README, clean slate for next build

---

## Quick Reference — Phase Summary

| Phase | Who | What | Output |
|---|---|---|---|
| 0 — Intake | You | Share product + page type | Confirmed brief |
| 1 — Brand Identity | Cowork | Generate identity HTML | `[brand]-identity.html` |
| 2 — Images | You + Cowork | Generate & review AI images | Named image set in assets/ |
| 3 — Page Build | Cowork | Build responsive HTML page | `index.html` + images/ |
| 4 — Polish | You + Cowork | Review, fix, approve | Final `index.html` |
| 5 — Case Study | Cowork | Build case study doc | Case study HTML + social brief |
| 6 — Archive | Cowork | Update README, prep next | Clean system |
