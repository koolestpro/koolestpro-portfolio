# BUILD-NOTES — hp-01-brand-story
**Template Type:** Homepage  
**Template ID:** hp-01-brand-story  
**Built For:** KURA (stainless steel cutting board brand)  
**Build Date:** 2026-05-06  
**Status:** In Progress

---

## Build Brief

This is the first homepage template in the system. It was built template-first using KURA's real brand content — then sections will be extracted into the `_sections/` library afterward.

**Why this template exists:**  
Homepage serves organic/direct traffic. Cold traffic goes → Advertorial → PDP. Warm traffic goes → Listicle → PDP. The homepage handles brand discovery, direct navigation, and return visitors.

**Page philosophy:** Story-first. Visitor arrives without context — the page builds brand trust before pushing product. Emotion → Proof → Action.

---

## Section Map

| # | Section | Copy Source | Image |
|---|---------|-------------|-------|
| S1 | Sticky Nav | Brand guidelines | KURA wordmark (CSS text) |
| S2 | Hero | Brand identity copy | images/lifestyle.jpg |
| S3 | Trust Bar | Brand pillars | SVG icons (inline) |
| S4 | Brand Story | Positioning statement | images/brand-story.jpg |
| S5 | Featured Product | S1 hero copy | images/product.png |
| S6 | Use Cases (3 cards) | Persona copy | images/hero.jpg, lifestyle.jpg, person.jpg |
| S7 | Social Proof | Review copy S7 | images/person.jpg |
| S8 | Brand Pillars | Voice & tone | SVG icons (inline) |
| S9 | Lifestyle Full-Bleed | CTA copy | images/lifestyle.jpg |
| S10 | Email Signup | Brand voice | None |
| S11 | Footer | Brand overview | KURA wordmark (CSS text) |

---

## Design Decisions

1. **Hero layout:** Split — text left, lifestyle image right on desktop. Collapses to single column on mobile. Image takes full width below the buy box. This is Hero B in the section library.

2. **Background rhythm:** Alternating Cream / White / Slate to give sections visual breathing room. No two adjacent sections share the same background.

3. **Hero image choice:** `lifestyle.jpg` (hands chopping on the board in a warm kitchen) — shows the product in active use rather than a studio shot. More emotional hook for brand-discovery traffic.

4. **Use cases instead of product collection:** KURA is single-SKU for now. Three use case cards (Daily Chef, Family Kitchen, Premium Gift) replace a product grid — matches the three buyer personas from the identity doc.

5. **No sticky CTA bar:** Homepage visitors are in discovery mode. The sticky CTA bar is reserved for the PDP where purchase intent is higher.

---

## Image Map

| File | Used In | Source |
|------|---------|--------|
| images/lifestyle.jpg | S2 Hero (right), S9 Lifestyle | brands/kura/assets/images/ai-gen/ |
| images/hero.jpg | S6 Use Case 1 card | brands/kura/assets/images/ai-gen/ |
| images/person.jpg | S6 Use Case 3, S7 Reviews | brands/kura/assets/images/ai-gen/ |
| images/product.png | S5 Featured Product | brands/kura/assets/images/ai-gen/ |
| images/brand-story.jpg | S4 Brand Story | brands/kura/assets/images/ai-gen/ |
| images/offer.png | S6 Use Case 2 | brands/kura/assets/images/ai-gen/ |

---

## Token Reference (for future templatization)

When extracting this to a brand-neutral template, replace:

| Content | Token |
|---------|-------|
| KURA | [BRAND NAME] |
| The KURA Board | [PRODUCT NAME] |
| Clean Surface. Clear Mind. | [TAGLINE] |
| $48.00 | [PRICE] |
| #2B3445 | [PRIMARY COLOR] |
| #C47A3A | [ACCENT COLOR] |
| #F6EFE2 | [BACKGROUND COLOR] |
| All review names/text | [REVIEW TITLE], [REVIEW BODY], [REVIEWER NAME] |

---

## Audit Notes (Pre-Build)

This is a Type C build (described in chat — built from scratch). No source file to audit. Standards checklist applied proactively:

- [x] Mobile-first CSS (min-width queries only)
- [x] No emoji anywhere in HTML or CSS
- [x] All icons inline SVG with viewBox + aria-hidden
- [x] Hero image loading="eager" + preload link in head
- [x] All colors in :root CSS variables
- [x] IntersectionObserver scroll animations on all sections
- [x] Google Fonts via preconnect + display=swap
- [x] No external JS libraries
- [x] EDIT comments on all editable elements
- [x] IMAGE comments on all image elements
- [x] Section separator comments on every section
- [x] ATC button click feedback
- [x] focus-visible outline styles
- [x] scroll-behavior: smooth on html
