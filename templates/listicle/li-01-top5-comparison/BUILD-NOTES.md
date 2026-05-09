# li-01-top5-comparison — Build Brief

Template type: Listicle / Top-5 Comparison Editorial
Status: Built — 2026-05-05
Source: No source file — built from scratch (Case C)

---

## What This Template Is

A 10-section editorial listicle page. Disguised as editorial journalism, it ranks
5 products in a category with the brand's own product as the clear #1. It educates
the buyer, handles objections through the ranking copy, and drives traffic to the
product's PDP or checkout.

This is the go-to template for top-of-funnel paid traffic (Facebook/Google/TikTok)
where a cold audience needs category education before they're ready to buy.

Sections: Editorial Header → Introduction → Quick Summary Table → #5 to #2 Entries →
#1 Entry (Brand) → Why #1 Wins → Buyers Guide → Final Verdict → Inline CTAs → FAQ

---

## Design Decisions

**01. Editorial typography over display typography**
The template uses a serif (Libre Baskerville) for article body text to feel like
genuine editorial content, not a sales page. Display font (Bebas Neue) is reserved
for rank numbers and the #1 entry title only. This creates trust before the pitch.

**02. Progressive CTA placement (CRO-led)**
CTAs appear at three controlled friction points: mid-list (after #3), at the #1 entry,
and in the Final Verdict. No CTA before the reader has been educated. This respects
the O/CO framework — deliver value, handle objections through ranking copy, then convert.

**03. #1 entry visually breaks the grid**
All #5–#2 entries use an identical compact card format. The #1 entry breaks into a
wider, feature-rich section with multiple benefit details, a quote, and a prominent CTA.
Visual differentiation drives attention without saying "buy this one" directly.

**04. Rank badges use color psychology**
#5–#4 = slate; #3 = muted; #2 = warm gray; #1 = accent (copper/brand color).
Readers unconsciously associate the warmest color with the winner before reading.

**05. Summary table anchors the reader early**
The quick-comparison table appears after the intro — before the detailed entries.
CRO research shows readers scan tables first on listicle pages. The table pre-loads
the key proof that the brand's product is #1 before the long-form copy.

---

## Section Map

| Section | Template ID | Purpose |
|---------|-------------|---------|
| S1 | Editorial Header | Publication name + category + headline + author + date |
| S2 | Introduction | Why this list, criteria, 2 paragraphs |
| S3 | Quick Summary Table | 5 products, specs, price, rating — brand = #1 |
| S4 | Entries #5 to #2 | Each: rank + name + image + pros + cons + verdict |
| S5 | #1 Entry (Brand) | Expanded: benefits, image, detail copy, first CTA |
| S6 | Why #1 Wins | Summary comparison paragraph |
| S7 | Buyers Guide | What to look for — educational, builds trust |
| S8 | Final Verdict | Strong close + CTA |
| S9 | Inline CTAs | 2 mid-article CTAs (after #3 and in #1 entry) |
| S10 | FAQ | 5 questions relevant to the category |

---

## Token System

| Token | Replace with |
|---|---|
| `[BRAND NAME]` | Your brand name |
| `[PRODUCT NAME]` | Your product name |
| `[PRODUCT URL]` | Your product URL or "#" |
| `[PRICE]` | Your product price |
| `[TAGLINE]` | Short tagline |
| `[PUBLICATION NAME]` | Fake editorial site name |
| `[CATEGORY]` | Product category (e.g. "cutting boards") |
| `[ARTICLE HEADLINE]` | The listicle headline |
| `[AUTHOR NAME]` | Fake author name |
| `[DATE]` | Publish date |
| `[READ TIME]` | Estimated read time |
| `[INTRO PARA 1]` | Why this category matters paragraph |
| `[INTRO PARA 2]` | Criteria explanation paragraph |
| `[PRODUCT #2–5 NAME]` | Competitor or generic product names |
| `[PRODUCT #2–5 PRICE]` | Competitor prices |
| `[PRODUCT #2–5 PRO 1–3]` | Pros for each |
| `[PRODUCT #2–5 CON 1–2]` | Cons for each |
| `[PRODUCT #2–5 VERDICT]` | One-sentence verdict |
| `[BENEFIT 1–6]` | Brand product benefit labels |
| `[FEATURE PARA 1–3]` | Brand product feature paragraphs |
| `[BUYERS GUIDE PARA]` | Educational buyers guide content |
| `[VERDICT PARA]` | Final verdict paragraph |
| `[FAQ Q1–5]` / `[FAQ A1–5]` | FAQ content |
| `[REVIEW TITLE]` / `[REVIEW BODY]` / `[REVIEWER NAME]` | #1 entry review |
| `[STAT 1]` / `[STAT 2]` / `[STAT 3]` | Comparison table specs |

---

## CRO Design Principles Applied

- **Value first, pitch second**: Buyers Guide section educates before asking for the sale
- **O/CO framework**: Cons on competitor entries pre-empt objections; brand entry only has pros
- **Progressive disclosure**: Detail increases as reader nears #1 — reward their scroll
- **Trust signals**: Author name, date, publication format all increase editorial credibility
- **Friction point CTAs**: CTAs only at 3 specific high-intent moments, never in intro
- **Specificity over vagueness**: Table uses specific numbers, not round estimates
- **Social proof at decision point**: Featured review card appears directly inside #1 entry

---

## Design Tokens Applied

```css
:root {
  --color-primary:   #2B3445;   /* [PRIMARY COLOR] */
  --color-accent:    #C47A3A;   /* [ACCENT / CTA COLOR] */
  --color-bg:        #F8F6F2;   /* [BACKGROUND COLOR] */
  --color-surface:   #FFFFFF;   /* card/article surface */
  --color-text:      #181820;   /* [BODY TEXT COLOR] */
  --color-muted:     #6B7280;   /* [MUTED / SECONDARY TEXT] */
  --color-border:    #E5E7EB;   /* [BORDER COLOR] */
  --color-rank-1:    #C47A3A;   /* #1 rank badge */
  --color-rank-2:    #78716C;   /* #2 rank badge */
  --color-rank-low:  #9CA3AF;   /* #3–5 rank badges */
}
```

---

## Responsive Strategy

- Mobile (375px): Single column. Table scrolls horizontally. Entry cards stack.
- Tablet (768px): Table fits, entry cards go 2-col in pros/cons lists.
- Desktop (1280px): Max-width 800px article container centered. Sticky sidebar CTA optional.

---

## Audit Checklist (Pre-Delivery)

- [x] Zero emoji in HTML content
- [x] Zero emoji in CSS content values
- [x] All icons are inline SVG with viewBox, width, height, aria-hidden
- [x] All colors in :root — no hardcoded hex in component CSS
- [x] Mobile-first CSS (min-width queries only)
- [x] hero/header image has loading="eager"
- [x] IntersectionObserver scroll animations on all sections
- [x] All editable nodes have <!-- EDIT: --> comments
- [x] All image src values have <!-- IMAGE: --> comments
- [x] All sections have ═══ SECTION separator comments
- [x] CTA buttons have click feedback
- [x] FAQ accordion works (one open at a time)
- [x] No external JS libraries
- [x] No !important declarations
- [x] Star ratings have aria-label and role="img"
- [x] All images have descriptive alt text
- [x] Comparison table scrolls on mobile without breaking layout
- [x] Token placeholders on all brand-specific content
