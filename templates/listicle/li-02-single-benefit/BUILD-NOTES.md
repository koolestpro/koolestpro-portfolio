# li-02-single-benefit — Build Brief

Template type: Listicle / Single-Product Benefit
Status: Built — 2026-05-05
Source: No source file — built from scratch (Case C)
Reference: Live Replo marketplace templates (Outway, Everist, Portland Pet Food)

---

## What This Template Is

A configurable single-product benefit listicle. 3–5 numbered "reasons" to use
one specific product — no competitor comparison, no editorial publication framing.
The product is the only subject. It builds desire through stacked benefit copy,
social proof, and controlled CTA placement before converting.

Best for warm-to-hot paid traffic (retargeting, Meta, TikTok) where the buyer
knows the category but hasn't committed to the brand. Also works for cold traffic
when the product has a strong visual hero.

---

## Design Research

Three live Replo marketplace templates analyzed before building:

**Outway — "3 Reasons To Upgrade Your Socks"**
- Typography-only hero (no image) — stars + bold headline on warm cream
- 3 alternating reasons (text left / image right, then flipped)
- Per-reason CTA links ("Shop [X]" inline links)
- 3 review cards with avatar photo, stars, quote, "Verified Buyer" badge
- No buy box, no urgency strip — relies entirely on inline CTAs

**Everist — "5 Reasons Why Everist Is the Best Shampoo"**
- Full-bleed image hero with headline overlay + eyebrow badge
- 5 reasons, same-side layout (image always left, text always right)
- Reason 2 has an embedded "Ours vs Theirs" comparison image
- Reason 5 has a Before/After image
- Post-reasons offer panel (split: product image + "20% OFF" + CTA)
- Testimonial carousel with extended quotes

**Portland Pet Food — "3 Reasons to Try Portland Pet Food Company Today"**
- Split hero: lifestyle image left / dark brand-story panel right
- Trust bar: scrolling CSS marquee with icons + text
- Offer bar: discount code (TRIAL25) + CTA above the reasons
- 3 reasons with full embedded mini-PDP after the reasons
- Mid-page large pull quote on dark background
- Reviews carousel (3 cards with arrows)
- "Meet the McCarrons" founder story section (dark bg, image left, copy right)

---

## Design Decisions

**01. Alternating reason layout (not same-side)**
Everist uses same-side — image always left. This creates visual monotony over 5
reasons. Our template alternates (odd = image right, even = image left) to pull
the eye down the page rhythmically. Outway uses the same approach. On mobile,
all images stack above their text (consistent, predictable).

**02. Config-driven optional sections**
Different product types need different conversion paths. A premium skincare brand
needs education before purchase — no in-page buy box. A consumable product
(supplements, food, pet) benefits from in-page purchasing. Solution: every
non-essential section is marked OPTIONAL with a clear comment. Remove what you
don't need. The page still converts without any optional section.

**03. Inline CTA after Reason 02 — not Reason 01**
One reason isn't enough social proof. After two differentiated benefits, the
reader has formed initial preference. The inline CTA strip is low-pressure
(a horizontal strip, not a modal or full-screen takeover) — it's an invitation,
not a hard interrupt. Placed between reasons, not before them.

**04. Comparison as standalone optional section (not embedded in a reason)**
Everist embeds the comparison inside Reason 2. This is hard to remove cleanly
when competitive messaging isn't needed. Our template keeps it as a standalone
section after the reasons, which makes it trivial to remove. It also hits at
maximum persuasion moment — after all reasons have been stacked.

**05. Pull quote before review cards**
A single large Cormorant Garamond quote breaks the pace after the reasons stack.
It reads as editorial endorsement rather than a grid of star ratings. The review
cards that follow deliver volume proof. Trust is built in two layers: quality
first (pull quote), then quantity (three-card grid).

---

## Section Map

| Section | ID | Purpose | Optional? |
|---|---|---|---|
| Hero | S1 | Headline + stars + subhead + hero image | No |
| Trust Bar | S2 | Scrolling trust signals marquee | Yes |
| Reason 01 | S3.1 | First benefit — image right | No |
| Reason 02 | S3.2 | Second benefit — image left | No |
| Inline CTA Strip | S4 | Mid-list conversion moment | Yes |
| Reason 03 | S3.3 | Third benefit — image right | No |
| Reason 04 | S3.4 | Fourth benefit — image left | Yes (3-reason layout) |
| Reason 05 | S3.5 | Fifth benefit — image right | Yes (3-reason layout) |
| Pull Quote | S5 | Single large editorial testimonial | No |
| Comparison | S6 | Ours vs Theirs 6-feature table | Yes |
| Offer Strip | S7 | Discount code + urgency | Yes |
| Embedded Buy Box | S8 | In-page mini-PDP | Yes |
| Review Cards | S9 | 3-card social proof grid | No |
| Brand Story | S10 | Founder/brand narrative | Yes |
| Final CTA | S11 | Strong close + guarantee | No |
| FAQ | S12 | 5 accordion questions | No |
| Footer | S13 | Minimal footer | No |

---

## Hero Variants

Three variants are available via CSS class on the `<section>` element:

### Default — Image Hero (`hero--image`)
Full-bleed background image with dark overlay. Headline in white. Eyebrow badge
in white border style. Best for warm traffic with a strong lifestyle image.

### Typography-Only Hero (`hero--text-only`)
Warm cream background, dark headline text. No image dependency. Use for cold
traffic or when no strong hero image is ready. Outway-style.
Change `<section class="hero hero--image">` → `<section class="hero hero--text-only">`

### Split Hero (`hero--split`)
Image left, brand content right (dark background). Portland Pet Food-style.
Use when the product image and brand story both need to be above the fold.
Change `<section class="hero hero--image">` → `<section class="hero hero--split">`

---

## Reason Count Guide

| Count | Keep | Remove |
|---|---|---|
| 3 reasons | S3.1, S3.2, S3.3 | Remove S3.4 and S3.5 blocks entirely |
| 4 reasons | S3.1 through S3.4 | Remove S3.5 block only |
| 5 reasons | All S3.1–S3.5 | Nothing (default) |

Move inline CTA strip placement based on count:
- 3 reasons: After S3.1 or S3.2 (editor's choice)
- 4–5 reasons: After S3.2 (default)

---

## Token System

| Token | Replace with |
|---|---|
| `[BRAND NAME]` | Brand name (e.g. KURA) |
| `[PRODUCT NAME]` | Product name (e.g. The KURA Board) |
| `[PRODUCT URL]` | Checkout or PDP URL |
| `[PRICE]` | Display price e.g. "$34.00" |
| `[COMPARE PRICE]` | Original/strikethrough price e.g. "$49.00" |
| `[TAGLINE]` | Brand tagline |
| `[HERO EYEBROW]` | e.g. "Over 50,000 Sold" or "20x Award-Winning" |
| `[ARTICLE HEADLINE]` | e.g. "Why [Audience] Are Switching to [PRODUCT NAME]" |
| `[ARTICLE SUBHEADLINE]` | Supporting subheadline |
| `[STAR COUNT]` | e.g. "4.9" |
| `[REVIEW COUNT]` | e.g. "2,340 reviews" |
| `[REASON COUNT]` | "3", "4", or "5" |
| `[REASON N HEADLINE]` | Reason title (N = 1–5) |
| `[REASON N BODY]` | Reason body copy — 2–3 sentences (N = 1–5) |
| `[REASON N CTA]` | Per-reason CTA link text (N = 1–5) |
| `[TRUST SIGNAL N]` | Trust bar text (N = 1–5) |
| `[PULL QUOTE]` | Single large testimonial quote — 1–2 sentences |
| `[PULL QUOTE AUTHOR]` | Attribution — name + context e.g. "Sarah M., verified buyer" |
| `[COMPARISON COL 1 LABEL]` | "Ours" column label (e.g. brand name) |
| `[COMPARISON COL 2 LABEL]` | "Theirs" column label (e.g. "The Old Way") |
| `[COMPARISON FEATURE N]` | Feature row label (N = 1–6) |
| `[OFFER HEADLINE]` | e.g. "Your First Order. Our Best Price." |
| `[DISCOUNT CODE]` | e.g. "FIRST20" |
| `[DISCOUNT AMOUNT]` | e.g. "20% OFF" |
| `[OFFER DEADLINE]` | e.g. "Offer ends tonight at midnight" |
| `[REVIEW TITLE N]` | Review card title (N = 1–3) |
| `[REVIEW BODY N]` | Review card body (N = 1–3) |
| `[REVIEWER NAME N]` | Reviewer name (N = 1–3) |
| `[BRAND STORY EYEBROW]` | e.g. "Meet the Founders" |
| `[BRAND STORY HEADLINE]` | Founder section headline |
| `[BRAND STORY BODY]` | Brand narrative — 2–3 sentences |
| `[BRAND STORY CTA]` | Founder section CTA text |
| `[FINAL CTA HEADLINE]` | Close headline |
| `[FINAL CTA SUBHEAD]` | Close subheadline |
| `[GUARANTEE TEXT]` | e.g. "30-Day Risk-Free Guarantee" |
| `[HERO CTA TEXT]` | CTA button text e.g. "Get Yours Now" |
| `[FAQ Q N]` / `[FAQ A N]` | FAQ content (N = 1–5) |

---

## Image Requirements

| Image | Dimensions | Section |
|---|---|---|
| `hero.jpg` | 1440 × 680 | S1 Hero background |
| `reason-1.jpg` | 800 × 600 | S3.1 Reason 01 |
| `reason-2.jpg` | 800 × 600 | S3.2 Reason 02 |
| `reason-3.jpg` | 800 × 600 | S3.3 Reason 03 |
| `reason-4.jpg` | 800 × 600 | S3.4 Reason 04 (optional) |
| `reason-5.jpg` | 800 × 600 | S3.5 Reason 05 (optional) |
| `product.jpg` | 600 × 600 | S8 Buy Box |
| `founder.jpg` | 600 × 700 | S10 Brand Story (optional) |
| `review-1.jpg` | 80 × 80 | S9 Review Card 1 avatar |
| `review-2.jpg` | 80 × 80 | S9 Review Card 2 avatar |
| `review-3.jpg` | 80 × 80 | S9 Review Card 3 avatar |

---

## Design Tokens Applied

```css
:root {
  --color-primary:      #1E2832;   /* dark navy */
  --color-accent:       #C47A3A;   /* copper CTA */
  --color-accent-hover: #A85F25;
  --color-bg:           #FAFAF8;   /* near white */
  --color-surface:      #FFFFFF;
  --color-surface-2:    #F4F1EC;   /* warm cream for alternating sections */
  --color-text:         #181820;
  --color-muted:        #6B7280;
  --color-border:       #E5E7EB;
  --color-pro:          #16A34A;   /* comparison checkmark */
  --color-con:          #DC2626;   /* comparison x mark */
  --font-display:       'Bebas Neue', sans-serif;
  --font-serif:         'Cormorant Garamond', serif;
  --font-body:          'DM Sans', sans-serif;
  --max-width:          1100px;
  --max-width-narrow:   760px;
}
```

---

## CRO Principles Applied

- **Stack before asking**: All reasons come before any hard CTA — buyer is educated first
- **Low-pressure inline CTA**: Strip CTA between reasons is invitational, not disruptive
- **Pull quote over star grid**: One human voice earns more trust than five-star badges
- **Optional buy box**: Not all products need in-page purchase — include only when it helps
- **Comparison at peak intent**: After all reasons, buyer is primed — comparison closes doubters
- **Guarantee at final CTA**: Risk reversal at the decision moment, not at the top

---

## Responsive Strategy

- Mobile (375px): Single column. Image above text for all reasons. Buy box stacks.
- Tablet (768px): Review cards go 3-column. Brand story goes 2-column. Buy box 2-col.
- Desktop (1024px): Reasons go 2-column with alternating image sides.

---

## Audit Checklist (Pre-Delivery)

- [x] Zero emoji in HTML content
- [x] Zero emoji in CSS content values
- [x] All icons inline SVG with viewBox, width, height, aria-hidden
- [x] All colors in :root — no hardcoded hex in component styles
- [x] Mobile-first CSS (min-width queries only)
- [x] Hero image has loading="eager" and rel="preload" in head
- [x] IntersectionObserver scroll animations on all sections
- [x] All editable nodes have <!-- EDIT: --> comments
- [x] All image src values have <!-- IMAGE: --> comments
- [x] All sections have ═══ SECTION separator comments
- [x] Optional sections have OPTIONAL SECTION begin/end markers
- [x] Configuration guide at top of HTML
- [x] ATC button has click feedback (2s "Added to Cart" state)
- [x] Buy box accordion — one-open-at-a-time
- [x] FAQ accordion — one-open-at-a-time
- [x] Quantity stepper functional
- [x] No external JS libraries
- [x] No !important declarations
- [x] Star ratings have aria-label and role="img"
- [x] All images have descriptive alt text
- [x] Trust bar marquee is CSS-only (no JS)
- [x] Token placeholders on all brand-specific content
- [x] Hero variant classes documented in comments
- [x] Reason count configuration guide at top of HTML
