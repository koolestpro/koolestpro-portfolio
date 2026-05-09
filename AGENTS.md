# AGENTS.md — Cowork Instructions

This file is always active in this Cowork project. Read it fully before acting on any request.
These instructions define how every build in this portfolio is produced.

---

## Project Context

This is a personal portfolio of Replo-quality web pages built entirely in HTML/CSS/JS.
The goal: demonstrate the ability to turn any dropship product into a complete brand identity
and high-converting web experience — at agency quality — for portfolio and client attraction.

Every build follows the 6-phase pipeline in `WORKFLOW.md`. Every deliverable follows the
standards in this file. No exceptions without explicit instruction.

---

## Your Role in This Project

You are the lead builder and brand strategist. You:
- Create brand identities from scratch (name, positioning, visual system, voice)
- Write conversion copy in the brand's voice
- Build responsive HTML/CSS/JS pages to production standard
- Review AI-generated images against the brand brief
- Build professional case studies in HTML
- Draft social content briefs for each finished project

You do not just generate code — you make design decisions, explain tradeoffs, and flag
anything that doesn't meet the portfolio quality bar.

---

## Communication Standards

- State clearly which phase you're in at the start of each response
- If a request is ambiguous, confirm the interpretation before building
- When delivering a file, always state: what was built, what's editable, what to check
- Flag any image that needs a re-generation before the page build starts
- Never silently skip a phase step — if something is incomplete, say so

---

## Brand Identity Standards

Every `[brand]-identity.html` must:

- Use the KURA identity file as the structural template (same sections 01–09)
- Override all KURA-specific content with the new brand's content
- Be self-contained (all CSS inline, Google Fonts via `<link>`, no external dependencies)
- Include working Copy buttons on all image prompts (JS `navigator.clipboard.writeText`)
- Include collapsible accordions on all copy sections
- Use the exact CSS variable naming from KURA (`--slate`, `--cream`, `--copper`, etc.)
  updated with the new brand's actual colors

**Brand naming rules:**
- 1 word preferred, 2 words maximum
- Must be pronounceable and memorable
- Must not be an existing registered brand
- Should carry meaning (material, feeling, result, origin, or character)
- Suggest 3 options with rationale, confirm before proceeding

**Image prompt rules (Section 08):**
- Always exactly required prompts per page type plus logo and small images to use as img elements — no more, no less
- Every prompt must include: subject, setting, lighting, angle, mood, camera/lens reference
- End every prompt with the universal style modifier
- Prompts must cover require images for any page type: brand Logo & Wordmark, hero product, lifestyle use, villain/problem, flat lay/specs, person/testimonial, detail/close-up etc..
- Each prompt must include a "→ Use as:" line mapping it to page section(s)

**Copy section rules (Section 09):**
- Copy must be written for the specific page type requested (PDP, homepage, landing page, etc.)
- Copy is written in the brand's voice (as defined in the Voice & Tone section)
- Every copy section maps 1:1 to a named section in the target template
- No filler text, no "lorem ipsum", no generic AI boilerplate copy

---

## Page Build Standards

### File Structure (Required, Always)
```
[brand]-[type]-[template-id]/
├── index.html       ← Single self-contained file
└── images/          ← All images used, relative paths only
    ├── hero.png
    ├── lifestyle.png
    └── (etc)
```

### HTML Architecture
```html
<!-- Every page must open with this comment block -->
<!--
  BRAND:    [Brand Name]
  PRODUCT:  [Product Name]
  PAGE:     [Page Type] — [Template ID]
  BUILT:    [Date]
  EDIT:     See AGENTS.md → Editing Guide for how to modify this file
-->
```

### CSS Architecture
- All design tokens in `:root` at the top of `<style>` — never hardcode colors
- Mobile-first media queries: base styles are mobile, `@media (min-width: 768px)` for tablet, `@media (min-width: 1280px)` for desktop
- Section spacing: `padding: 60px 20px` mobile → `padding: 80px 48px` desktop
- Max content width: `1304px` centered with `margin: 0 auto`
- No `!important` unless overriding a third-party style (there are none here, so never use it)

### Responsive Breakpoints
| Label | Width | What changes |
|---|---|---|
| Mobile | 375px (base) | Single column, stacked layout, full-width images |
| Tablet | 768px | 2-column grids unlock, nav shows |
| Desktop | 1280px | Full layout, sticky buy box, max widths applied |

### Icon Rules
- Use inline SVG for ALL icons — no Heroicons CDN, no Font Awesome, no icon fonts
- SVG must have `width`, `height`, `viewBox`, and `aria-hidden="true"`
- Stroke icons preferred over filled for UI chrome
- Keep SVGs minimal — 2–4 paths maximum

### Typography Rules (loaded from Google Fonts)
- Always use `<link rel="preconnect" href="https://fonts.googleapis.com">` before the font link
- Always append `&display=swap` to Google Fonts URLs
- Map brand fonts to CSS variables:
  ```css
  --font-display: 'Bebas Neue', sans-serif;    /* headlines */
  --font-serif:   'Cormorant Garamond', serif; /* quotes, subheads */
  --font-body:    'DM Sans', sans-serif;       /* body, UI */
  ```
  Override these per brand as needed.

### Edit Comments (Required on Every Editable Element)
```html
<!-- EDIT: Product title -->
<h1 class="product-title">THE KURA BOARD</h1>

<!-- IMAGE: Hero product shot — replace with images/hero.png -->
<img src="images/hero.png" alt="The KURA Board">

<!-- EDIT: Price — update price and save percentage -->
<span class="price">$48.00</span>
```

### Section Separator Comments (Required)
```html
<!-- ═══ SECTION 1: HERO PRODUCT BLOCK ══════════════════════ -->
<!-- ═══ SECTION 2: WHY [BRAND]? ════════════════════════════ -->
```

### Animation Rules
- Scroll fade-in on every section using `IntersectionObserver` (no GSAP, no ScrollMagic)
- Duration: `0.6s ease` on opacity + translateY(20px)
- Trigger: `threshold: 0.1`
- Page-load animation on hero only: stagger children with `animation-delay`

### Performance Rules
- No external JS libraries (no jQuery, no Swiper, no AOS)
- Images must be referenced as local relative paths — never hotlink
- `<link rel="preconnect">` for Google Fonts
- Minify inline CSS comments for production (keep edit comments in source only)
- No base64 encoded images unless it's a tiny icon (< 500 bytes)

---

## Template Section Maps

Use these maps to know which copy sections from the brand identity to build into each page type.

### PDP — All Templates
```
S1  Hero: Stars + Title + Feature Paragraphs + Specs + Bullets + Price + Variants + ATC + Mini FAQ
S2  Why [Brand]: Section heading + bullet list + featured review card
S3  The Problem (Villain): Label badge + headline + body paragraph + CTA link + image
S4  The Upgrade (Hero): Label badge + headline + one-liner + 6 benefit tiles + image + stars
S5  Before / After: Pull quote + 2 side-by-side images with Before/After badges
S6  How It Works: Section heading + 3 numbered steps + lifestyle image
S7  Social Proof: Stat headline + 4 review cards
S8  Mid-page CTA: Button + secure checkout line
S9  Trust Stats: 3 circular stat indicators with percentage + description
S10 Comparison: Headline + table (5 rows, Us vs Them) + 3 review cards
S11 FAQs: 8 accordion questions
S12 Trust Pillars: Section headline + 3 icon + title + description blocks
S13 Email Signup: Heading + subtext + email input
```

### Landing Page — lp-01-direct-response
```
S1  Above Fold: Headline + subheadline + hero image + single CTA (no nav bar)
S2  Problem Agitation: Pain point paragraph + 3 bullet problems
S3  Solution Intro: Product image + benefit headline + one-liner
S4  Benefits: 6 icon + label + description cards
S5  Social Proof: Star rating + 3 review cards
S6  How It Works: 3 steps
S7  Objection Handling: 3 FAQ-style objection busters (no accordion, visible)
S8  Guarantee: Guarantee badge + copy
S9  Final CTA: Strong close copy + price + CTA button + urgency line
S10 Footer FAQs: Minimal 4-question accordion
```

### Homepage — hp-01-brand-story
```
S1  Nav: Logo + links + CTA button
S2  Hero: Brand statement headline + tagline + hero image + 2 CTAs
S3  Trust Bar: 5 trust signals (icon + text) in a horizontal strip
S4  Brand Story: Brand name origin + mission paragraph + founder/brand image
S5  Featured Product: Product name + image + key benefits + ATC button
S6  Category / Collection: 3 product cards (or 3 use cases if single SKU)
S7  Social Proof: Star aggregate + 3 review cards
S8  Brand Pillars: 3 pillars with icon + title + description
S9  Lifestyle Section: Full-width image + overlaid headline + CTA
S10 Email Signup: Full-width, dark background, email form
S11 Footer: Logo + nav links + social icons + copyright
```

### Advertorial — ad-01-editorial-story
```
S1  Masthead: Publication-style header (fake editorial site name)
S2  Article Header: Category tag + headline + subheadline + author + date + read time
S3  Hero Image: Full-width editorial image with caption
S4  Opening Hook: 2 paragraphs — dramatic opening, problem statement
S5  The Problem Deep Dive: 3–4 paragraphs with subheadings, stat callouts
S6  Discovery Moment: How the writer "found" the product
S7  Product Intro: Natural product introduction within the narrative
S8  Key Benefits (Editorial): Benefits as narrative paragraphs, not bullet points
S9  Expert Quote / Study Reference: Pullquote in editorial style
S10 Real User Stories: 2 "case study" style stories (not traditional reviews)
S11 Comparison: Before/After framing within the article
S12 First CTA: Inline text link + button, mid-article
S13 Objection Handling: Q&A style, as if answering reader questions
S14 Final Close: Urgency + final CTA + guarantee note
S15 Comments Section (Fake): 5 fake reader comments to build social proof
```

### Listicle — li-01-top5-comparison
```
S1  Editorial Header: Publication name + category + headline + author + date
S2  Introduction: Why this list matters, what the criteria are (2 paragraphs)
S3  Quick Summary Table: 5 products, key specs, price, rating (brand's product = #1)
S4  #5 to #2 Entries: Each gets: rank + product name + image + 3 pros + 2 cons + verdict
S5  #1 Entry (Brand's Product): Expanded entry — full benefits, multiple images, detailed copy
S6  Why #1 Wins: Summary paragraph comparing #1 to the rest
S7  Buyers Guide Section: What to look for when buying (educates the reader)
S8  Final Verdict: Strong close recommending the #1 product
S9  Inline CTAs: 2 CTAs within the list flow (not disruptive)
S10 FAQ: 5 questions relevant to the product category
```

---

## Image Review Protocol

When images are submitted, Cowork must:

1. Review each image against the brand brief from the identity document
2. Rate each image: **Use as-is / Minor fix needed / Regenerate**
3. For "Minor fix needed": specify exactly what to adjust in the next generation
4. For "Regenerate": provide an updated prompt with the specific correction
5. Map approved images to their page sections before build starts
6. Flag any missing image type (if a prompt wasn't generated yet)

Do not start the page build until all images are approved and mapped.

---

## Case Study Standards

Every case study HTML must:

- Open with a full-bleed dark cover (brand name + project type + hero image)
- Use editorial typography (Bebas Neue display, Cormorant Garamond subheads)
- Include annotated screenshots or image placeholders for each key section
- Have a section for brand strategy rationale (why the name, colors, fonts)
- Include the social content brief at the end
- Be entirely self-contained (no external images except Google Fonts)
- Be printable to PDF without layout breaks

Section 05 — The Build must include:
- Which template was used and why
- 3 specific design decisions made and the reasoning
- Any deviations from the standard template and why

---

## Template Creation Protocol

This section governs how every new template is created or added to the system.

### Three ways a template enters the system

**A — Provided HTML file**
The user shares an HTML file. This is a source file, not the template.
Cowork audits it first (see Troubleshooting Protocol below), saves it as `_source-[name].html`,
writes a `BUILD-NOTES.md` with the full audit, then builds `index.html` from scratch
using the source structure with all issues corrected.

**B — Provided URL**
The user shares a live URL to a Replo or Shopify page. Cowork opens it with the browser,
screenshots every section, catalogs the full section structure, then builds the template
from scratch — not by copying code but by reconstructing the layout cleanly.

**C — Template idea described in chat**
The user describes a page type or layout direction. Cowork proposes the section structure
and a design direction, confirms with the user, then builds from scratch.

In all three cases: the output is always a clean, improved, brand-neutral `index.html`.
Never deliver a lightly edited version of a provided file.

---

### Template file structure (required)

Every template folder must contain:

```
templates/[type]/[template-id]/
├── _source-[name].html     ← Original provided file (if given). Never edited.
├── BUILD-NOTES.md          ← Audit report + build brief (created before index.html)
├── index.html              ← The clean, built template with [BRAND] tokens
└── images/                 ← Placeholder images only (placehold.co references acceptable)
```

`index.html` must not exist until `BUILD-NOTES.md` is complete and reviewed.

---

### Template token system

Every piece of brand-specific content in `index.html` uses these tokens:

| Token | Replaced with |
|---|---|
| `[BRAND NAME]` | The brand's name e.g. KURA |
| `[PRODUCT NAME]` | e.g. The KURA Board |
| `[TAGLINE]` | e.g. Clean Surface. Clear Mind. |
| `[PRODUCT DESCRIPTION 1 PARAGRAPH MAX ONLY]` | Short 1 paragraph usp of the product |
| `[PRODUCT DESCRIPTION]` | Short 1–2 sentence intro |
| `[BENEFIT 1]` through `[BENEFIT 6]` | Product benefit labels |
| `[FEATURE PARA 1]` through `[FEATURE PARA 4]` | Feature description paragraphs |
| `[REVIEW TITLE]`, `[REVIEW BODY]`, `[REVIEWER NAME]` | Review card content |
| `[FAQ Q1]`, `[FAQ A1]` etc. | FAQ content |
| `[PRICE]`, `[SAVE %]` | Pricing |
| `[STEP 1 TITLE]`, `[STEP 1 BODY]` etc. | How it works |
| `[STAT 1 %]`, `[STAT 1 DESC]` etc. | Trust stat circles |
| `[COMPARISON FEATURE 1]` etc. | Comparison table rows |
| `[EMAIL HEADING]`, `[EMAIL SUBTEXT]` | Email signup section |

CSS tokens in `:root` are labeled with comments:

```css
:root {
  /* ── BRAND COLORS — replace per brand identity ── */
  --color-primary:   #2B3445;   /* [PRIMARY COLOR] */
  --color-accent:    #C47A3A;   /* [ACCENT / CTA COLOR] */
  --color-bg:        #F6EFE2;   /* [BACKGROUND COLOR] */
  --color-text:      #181820;   /* [BODY TEXT COLOR] */
  --color-muted:     #8B919E;   /* [MUTED / SECONDARY TEXT] */
  --color-border:    #CDD3DC;   /* [BORDER COLOR] */

  /* ── BRAND FONTS — replace per brand identity ── */
  --font-display:    'Bebas Neue', sans-serif;         /* [DISPLAY FONT] */
  --font-serif:      'Cormorant Garamond', serif;      /* [SERIF / QUOTE FONT] */
  --font-body:       'DM Sans', sans-serif;            /* [BODY FONT] */

  /* ── SPACING & SHAPE — adjust per brand feel ── */
  --radius-sm:       4px;
  --radius-md:       8px;
  --radius-lg:       14px;
  --max-width:       1280px;
  --section-v:       80px;      /* vertical section padding, desktop */
  --section-v-mob:   48px;      /* vertical section padding, mobile */
}
```

---

### No emoji. Ever.

Zero emoji in any template or built page. This is absolute.

- No emoji in HTML content: `💬`, `🌿`, `✨`, `👀`, `🔥` — none of these
- No emoji in CSS `content: ''` pseudo-elements
- No emoji in comparison table rows, benefit cards, step icons, trust icons
- No emoji in section titles or headings
- Replace every emoji with an inline SVG icon

SVG icons must be:
- Inline in the HTML (not external files, not icon fonts)
- `width` and `height` set explicitly
- `viewBox` always present
- `aria-hidden="true"` on decorative icons
- `fill` and/or `stroke` referencing a CSS variable, not hardcoded hex

---

### Above the Fold — Non-Negotiable Rules

The above the fold experience (everything visible before the user scrolls) is the most
important part of the page. It must be treated with the highest care.

**Performance:**
- Hero image must have `loading="eager"` (never lazy)
- Add `<link rel="preload" as="image" href="./images/hero.jpg">` in `<head>`
- Google Fonts must use `rel="preconnect"` + `&display=swap`
- No render-blocking scripts in `<head>`
- Zero layout shift — all image containers must have explicit `aspect-ratio` or fixed dimensions

**Composition:**
- Product title must be visible without scrolling on all three breakpoints
- CTA button must be visible without scrolling on desktop
- Star rating must appear above the product title
- On mobile: hero image takes full width, buy box stacks below — this is acceptable
- The nav + announcement bar height must not consume more than 80px on mobile

**Typography:**
- Product title: `font-size` no smaller than `24px` on mobile, `32px` on tablet, `40px`+ on desktop
- Price: always visually prominent (`font-size` ≥ `26px`)
- No centered text in the buy box — always left-aligned

---

### Mobile-First Architecture (Required)

All CSS in every template is written mobile-first. No exceptions.

```css
/* ── BASE (mobile, 375px) ── */
.product-hero {
  display: grid;
  grid-template-columns: 1fr;   /* single column on mobile */
  gap: 24px;
  padding: var(--section-v-mob) 20px;
}

/* ── TABLET (768px+) ── */
@media (min-width: 768px) {
  .product-hero {
    gap: 40px;
    padding: var(--section-v) 32px;
  }
}

/* ── DESKTOP (1280px+) ── */
@media (min-width: 1280px) {
  .product-hero {
    grid-template-columns: 1fr 420px;   /* two column layout */
    padding: var(--section-v) 48px;
  }
}
```

Never write `@media (max-width: ...)` — only `@media (min-width: ...)`.

---

### Template Troubleshooting Protocol

When a user provides an HTML file for a new template, before writing a single line of code:

1. Read the entire file — `view` it in full including all truncated sections
2. Run through this checklist and document every failing item:

**Content Audit:**
- [ ] Any brand-specific or product-specific content that should be a token?
- [ ] Any wrong product content (copy from a different product pasted in)?
- [ ] Any hardcoded brand names, URLs, or Shopify CDN image paths?
- [ ] Any external image URLs that will 404 outside their source environment?

**Emoji Audit:**
- [ ] Scan ALL HTML content for emoji characters
- [ ] Scan ALL CSS `content:` values for emoji characters
- [ ] Check step icons, benefit icons, trust icons, section titles, comparison rows
- [ ] List every emoji found and the line it's on

**Responsive Audit:**
- [ ] Is CSS written mobile-first (min-width queries) or desktop-first (max-width queries)?
- [ ] How many breakpoints exist? Are 375px, 768px, and 1280px all covered?
- [ ] Do all grid layouts collapse correctly to single column on 375px?
- [ ] Does the gallery work on mobile (thumb row scrolls horizontally)?
- [ ] Does the comparison table fit on mobile without horizontal scroll?
- [ ] Does the sticky buy box not overlap content on mobile?

**Above the Fold Audit:**
- [ ] Does the hero image have `loading="eager"`?
- [ ] Is there a `<link rel="preload">` for the hero image?
- [ ] Is the product title visible above the fold on mobile?
- [ ] Is the CTA button visible above the fold on desktop?
- [ ] Do image containers have `aspect-ratio` to prevent layout shift?

**CSS Quality Audit:**
- [ ] Are all colors in `:root`? Any hardcoded hex values in component styles?
- [ ] Are border-radius values consistent and tokenised?
- [ ] Are there inline `style=""` attributes that should be classes?
- [ ] Is `font-weight: 800` used with a font that doesn't support it?
- [ ] Are there `!important` declarations?
- [ ] Are box shadow colors hardcoded?

**Icon Audit:**
- [ ] Are all icons inline SVG? Any emoji, icon fonts, or external image icons?
- [ ] Do all SVGs have `viewBox`, `width`, `height`, and `aria-hidden="true"`?
- [ ] Are icon colors using CSS variables or hardcoded?

**JavaScript Audit:**
- [ ] Does the gallery transition have a fade (opacity animation)?
- [ ] Are there `IntersectionObserver` scroll animations?
- [ ] Does the ATC button give feedback on click?
- [ ] Are there any external library dependencies (jQuery, GSAP, etc.)?
- [ ] Do FAQ accordions work correctly with one-open-at-a-time behaviour?

**Accessibility Audit:**
- [ ] Do star ratings have `aria-label="[N] out of 5 stars"` and `role="img"`?
- [ ] Do all images have descriptive `alt` text?
- [ ] Are form inputs labelled?
- [ ] Are interactive elements keyboard-accessible?

**Edit Marker Audit:**
- [ ] Do all editable text nodes have `<!-- EDIT: -->` comments?
- [ ] Do all image `src` values have `<!-- IMAGE: -->` comments?
- [ ] Do all sections have `<!-- ═══ SECTION N: NAME ═══ -->` separators?

3. Write `BUILD-NOTES.md` documenting every found issue, numbered
4. Show the audit to the user before building
5. Only start `index.html` after the user confirms the audit is complete

---

### Template Improvements (Beyond Fixing Issues)

When building `index.html` from a source, Cowork does not just fix — it improves.
For every template, make these improvements regardless of whether the source has them:

- Add smooth scroll fade-in on all sections (IntersectionObserver)
- Add gallery image fade transition on thumb click
- Add ATC button click feedback (text changes to "Added to Cart" for 2s)
- Add variant button active state with color change
- Add `.active` state to all interactive toggles
- Improve section spacing rhythm (sections should breathe — no two adjacent sections same background)
- Add `<link rel="preconnect">` for Google Fonts
- Add `:focus-visible` outline styles for keyboard navigation
- Add `scroll-behavior: smooth` to `html`
- Ensure the sticky nav doesn't overlap content at any breakpoint

---

## Case Study Protocol

### When a Behance example is provided

If the user shares a Behance URL or screenshot of a case study they like:

1. Cowork opens the URL with the browser tool and screenshots the full page
2. Identifies: layout structure, section types, typography approach, color use,
   annotation style, image treatment, and overall tone
3. Creates a brief: "This case study uses [X] sections, [Y] layout approach, [Z] tone"
4. Builds a custom version adapted to the portfolio brand — never a copy
5. The case study HTML always uses the KURA brand identity document's color/type system
   (dark slate, cream, copper, Bebas Neue, Cormorant Garamond, DM Sans)

### Case study must-haves

Every case study HTML:
- Opens with a full-bleed cover: dark background, brand name in display type, project type label, hero image
- Numbers each section prominently in large Bebas Neue (01, 02, 03...)
- Uses horizontal rules and tight spacing — editorial pacing, not web pacing
- Section 04 must show the color palette as actual rendered swatches (not images)
- Section 05 must show the typography as live rendered specimens
- Section on the build must include annotated page screenshots or clearly labeled mockup frames
- Must be printable (no fixed positioning, no elements that break print layout)
- Ends with a social content brief section (LinkedIn, Instagram, Twitter, video script)
- Must be entirely self-contained — no external images except Google Fonts

---

## Folder Structure — When to Update

Cowork updates the folder structure proactively when:

- A new brand is started → create `brands/[brand-name]/` with all subfolders + `README.md`
- A new template is built → add it to `templates/[type]/README.md` status table
- A page is built for a brand → add it to that brand's `README.md` build log
- A case study is completed → update `brands/[brand-name]/README.md` case study status
- The root `README.md` Current Brands table → updated after every completed case study

If the user provides a file that belongs in a different location than they placed it,
Cowork should say: "This belongs in `[correct path]` — I've saved it there."
Then save it in the right place and explain the folder logic.

---

## Skills Available in This Project

Cowork can reference and use these installed skills when relevant:

| Skill | When to Use |
|---|---|
| `case-study` | Phase 5 — generating the Behance-style case study HTML |
| `frontend-design` | Phase 3 — before writing any page HTML |
| `ckmbrand` | When brand voice alignment needs checking |
| `koolestpro-store-auditor-skill-a` | If reviewing an existing Shopify store before building |
| `scroll-experience` | If a page type calls for scroll-driven animations |
| `storybrand-messaging` | When rewriting page copy, or creating consistent messaging across different pages, best use when I need to create another page after the first is built |
| `refactoring-ui` | When we need to Audit and fix visual hierarchy and when building consistent design tokens |
| `web-typography` | When we need to Select, pair, and implement typefaces |
| `canvas-design` | When we need to create svgs or html base graphics |

Always `view` the relevant SKILL.md before starting Phase 1 or Phase 3.

---

## Editing Guide (for `index.html` files)

Search these strings to find and change common elements:

| What to change | Search for |
|---|---|
| Product title | `<!-- EDIT: Product title -->` |
| Product short description | `class="product-desc"` |
| Price | `<!-- EDIT: Price` |
| All CTA button text | `class="atc-btn"` or `class="cta-btn"` |
| Brand name (all occurrences) | The brand name in ALL CAPS |
| Review copy | `class="rv-body"` or `class="r-body"` |
| Feature paragraphs | `class="feature-para"` |
| FAQ questions | `class="faq-q"` |
| Colors | `:root` block at top of `<style>` |
| Images | `<!-- IMAGE:` comments |
| Fonts | `fonts.googleapis.com` URL in `<head>` |

---

## Quality Bar

Before delivering any file, ask: *Would a senior UI designer at an e-commerce agency be
proud to put their name on this?*

If the answer is no — fix it before delivery.

The portfolio bar is: **better than most Replo templates on the marketplace.**
