# Listicle Templates

Listicle templates are editorial-style pages — either ranking multiple products or stacking reasons to buy one. They are copy-led and persuasion-architected, disguising sales intent behind a journalistic or educational format. Both formats convert at the end of a natural reading journey.

Three distinct formats available:
- **Comparison listicle** (`li-01`): Brand vs. competitors. Cold traffic who is still deciding. Category education first.
- **Single-product benefit listicle** (`li-02`): One brand, stacked reasons. Warm/retargeting traffic who needs conviction, not category education.
- **Problem-solution listicle** (`li-03`): Pain-first. Names the reader's problems, then resolves each one with the product. Cold-to-warm traffic who is pain-aware but not product-aware.

---

## Status Table

| Template ID | Status | Source | Best For | Notes |
|---|---|---|---|---|
| `li-01-top5-comparison` | Built — 2026-05-05 | New (Case C — built from scratch) | Any product in a competitive category | 10 sections, 3-CTA placement, mobile-first, all tokens, zero emoji, IntersectionObserver animations |
| `li-02-single-benefit` | Built — 2026-05-05 | New (Case C — built from scratch) | Single-product warm/retargeting traffic | 13 sections, 6 optional sections, 3 hero variants, 3–5 reason count, embedded buy box, trust bar marquee |
| `li-03-problem-solution` | Built — 2026-05-05 | New (Case C — built from scratch) | Cold-warm pain-aware traffic; retargeting audiences who've tried and failed | 10 sections, dual-phase problem/fix blocks, transformation strip, problem-mapped reviews, 3–5 problem count |

---

## How To Use `li-01-top5-comparison`

Use this template when the traffic is cold and unfamiliar with the brand. The article format earns trust before pitching. The argument structure is:

1. Frame why this category choice matters (stakes-setting intro).
2. Show the full competitive landscape (summary table — builds credibility).
3. Review #5 to #2 honestly — include real cons. This is what makes the page feel editorial.
4. Present #1 (your brand) with expanded detail, a featured review, and a CTA.
5. Summarize why #1 wins in one clear paragraph.
6. Educate the buyer with a Buyers Guide (builds trust, handles pre-purchase anxiety).
7. Close with a verdict and final CTA.
8. Answer common objections via FAQ.

**CRO principle:** Never place a CTA before the reader has been educated. The 3 CTA placements are timed to natural decision moments — after the mid-list (after #3), inside the #1 entry, and at the final verdict.

---

## Image Requirements

| Image | Dimensions | Use |
|---|---|---|
| `hero.jpg` | 1200 × 525 | Article hero image — editorial product or category photo |
| `winner-hero.jpg` | 1200 × 514 | #1 entry hero — clean product hero or lifestyle |
| `product-2.jpg` | 800 × 450 | #2 entry card |
| `product-3.jpg` | 800 × 450 | #3 entry card |
| `product-4.jpg` | 800 × 450 | #4 entry card |
| `product-5.jpg` | 800 × 450 | #5 entry card |

---

## Token Quick Reference

Search `index.html` for any `[TOKEN]` placeholder to replace with real content.

| Find | Replace with |
|---|---|
| `[BRAND NAME]` | Your brand name |
| `[PRODUCT NAME]` | Your product name |
| `[PRODUCT URL]` | Your product/checkout URL |
| `[PRICE]` | Display price |
| `[TAGLINE]` | Short product tagline |
| `[PUBLICATION NAME]` | Fake editorial site name |
| `[CATEGORY]` | Product category |
| `[ARTICLE HEADLINE]` | Listicle headline |
| `[AUTHOR NAME]` | Fake author name |
| `[DATE]` | Publish date |
| `[READ TIME]` | Estimated read time |
| `[PRODUCT #2–5 NAME]` | Competitor names |

Full token list in `li-01-top5-comparison/BUILD-NOTES.md`.

---

## How To Use `li-02-single-benefit`

Use this template when the traffic already knows your category and just needs reasons to commit. The format stacks benefits as numbered reasons, building desire through repetition and proof. The argument structure is:

1. Hook with a bold headline and star aggregate above the fold.
2. Optional trust bar immediately below — establishes credibility before any scrolling.
3. Stack reasons 1 through N — each with an image, headline, body, and inline CTA link.
4. Drop a mid-list CTA strip after reason 2 — low pressure, timed to first-formed preference.
5. Break momentum with a single pull quote — editorial trust before the close.
6. Optional comparison table — useful when competitive messaging is needed.
7. Optional offer strip — adds urgency for discount-driven campaigns.
8. Optional embedded buy box — closes in-page for consumable/repeat-purchase products.
9. Three review cards — social proof volume after the buy box.
10. Optional brand/founder story — adds brand trust for higher-consideration products.
11. Final CTA with guarantee — risk reversal at the decision moment.
12. FAQ — handles last-mile objections before the reader bounces.

**Hero variants** (set by CSS class on the `<section>` element):
- `hero--image` (default): Full-bleed lifestyle image with overlay. Best for warm traffic.
- `hero--text-only`: Clean cream background, no image dependency. Best for cold traffic.
- `hero--split`: Image left, brand content right. Best for founder-story brands.

**CRO principle:** Reasons come first, CTA comes second. Never pitch before the reader has been educated. The inline CTA strip after reason 2 is intentionally low-pressure — a horizontal strip, not a takeover.

---

## Image Requirements — `li-02-single-benefit`

| Image | Dimensions | Use |
|---|---|---|
| `hero.jpg` | 1440 × 680 | Hero background (image hero variant) |
| `reason-1.jpg` | 800 × 600 | Reason 01 image |
| `reason-2.jpg` | 800 × 600 | Reason 02 image |
| `reason-3.jpg` | 800 × 600 | Reason 03 image |
| `reason-4.jpg` | 800 × 600 | Reason 04 (optional — 4 or 5 reason layout) |
| `reason-5.jpg` | 800 × 600 | Reason 05 (optional — 5 reason layout) |
| `product.jpg` | 600 × 600 | Embedded buy box product image |
| `founder.jpg` | 600 × 700 | Brand story / founder image (optional) |
| `review-1.jpg` | 80 × 80 | Reviewer avatar, circular crop |
| `review-2.jpg` | 80 × 80 | Reviewer avatar, circular crop |
| `review-3.jpg` | 80 × 80 | Reviewer avatar, circular crop |

---

## Token Quick Reference — `li-02-single-benefit`

Search `index.html` for any `[TOKEN]` placeholder to replace with real content.

| Find | Replace with |
|---|---|
| `[BRAND NAME]` | Your brand name |
| `[PRODUCT NAME]` | Your product name |
| `[PRODUCT URL]` | Checkout or PDP URL |
| `[PRICE]` / `[COMPARE PRICE]` | Price + strikethrough price |
| `[HERO EYEBROW]` | e.g. "Over 50,000 Sold" |
| `[ARTICLE HEADLINE]` | e.g. "Why Thousands Are Switching to [Product]" |
| `[ARTICLE SUBHEADLINE]` | Supporting subheadline |
| `[REASON COUNT]` | "3", "4", or "5" |
| `[REASON N HEADLINE]` | Reason title (N = 1–5) |
| `[REASON N BODY]` | Reason copy (N = 1–5) |
| `[REASON N CTA]` | Per-reason link text (N = 1–5) |
| `[PULL QUOTE]` | Single large testimonial |
| `[DISCOUNT CODE]` | e.g. "FIRST20" |
| `[HERO CTA TEXT]` | CTA button text |
| `[GUARANTEE TEXT]` | e.g. "30-Day Risk-Free Guarantee" |

Full token list in `li-02-single-benefit/BUILD-NOTES.md`.

---

## How To Use `li-03-problem-solution`

Use this template when the traffic is pain-aware but not yet product-aware — they know they have a problem, they may have tried other solutions, but they haven't committed to a brand. This template leads with empathy before selling. The argument structure is:

1. Hook with a pain-framing headline above the fold (stars appear after the hook, not before — this is intentional for cold traffic).
2. Optional trust bar — credibility signals before the first problem block.
3. Stack 3–5 problem-solution blocks. Each block has two distinct phases: **THE PROBLEM** (named pain, reader's voice) → divider arrow → **THE FIX** (product mechanism, first or second sentence names the product by name).
4. Drop a mid-list CTA strip after block 2 — timed to first recognition moment.
5. Transformation strip — before/after in plain language on a dark background. Not competitive, personal.
6. Three review cards, each tagged with the specific problem it resolves. Proof maps to pain.
7. Optional guarantee block — risk reversal at maximum conviction.
8. Final CTA — strong close, not just a button.
9. FAQ — 5 questions framed around problem resolution, not generic product questions.

**CRO principle:** The recognition effect. Named pain = trust. The reader thinks "they get it" before they're ever pitched. The divider between the problem and fix blocks creates a deliberate beat — the reader processes the pain before receiving the solution. Reviews tagged to specific problems are significantly more persuasive than generic five-star grids.

**Problem count:** 3, 4, or 5. Inline CTA strip always goes after block 2. For 3-problem layouts, remove S3.4 and S3.5 entirely. See the CONFIG GUIDE comment at the top of `index.html`.

---

## Image Requirements — `li-03-problem-solution`

| Image | Dimensions | Section |
|---|---|---|
| `hero.jpg` | 1440 × 680 | S1 Hero background |
| `solution-1.jpg` | 800 × 600 | S3.1 — Problem 01 block (shows the resolution state, not the problem) |
| `solution-2.jpg` | 800 × 600 | S3.2 — Problem 02 block |
| `solution-3.jpg` | 800 × 600 | S3.3 — Problem 03 block |
| `solution-4.jpg` | 800 × 600 | S3.4 — Problem 04 (optional) |
| `solution-5.jpg` | 800 × 600 | S3.5 — Problem 05 (optional) |
| `review-1.jpg` | 80 × 80 | S6 Review Card 1 avatar |
| `review-2.jpg` | 80 × 80 | S6 Review Card 2 avatar |
| `review-3.jpg` | 80 × 80 | S6 Review Card 3 avatar |

Note: Solution images should show the **resolution state** (product in use, positive outcome). The pain is carried by the copy — keep the imagery aspirational throughout.

---

## Token Quick Reference — `li-03-problem-solution`

Search `index.html` for any `[TOKEN]` placeholder to replace with real content.

| Find | Replace with |
|---|---|
| `[BRAND NAME]` | Your brand name |
| `[PRODUCT NAME]` | Your product name |
| `[PRODUCT URL]` | Checkout or PDP URL |
| `[HERO EYEBROW]` | Pain-framing eyebrow e.g. "For people who are done with wasted mornings" |
| `[ARTICLE HEADLINE]` | e.g. "5 [Audience] Problems That [Product] Finally Fixes" |
| `[ARTICLE SUBHEADLINE]` | Supporting subheadline |
| `[STAR COUNT]` | e.g. "4.9" |
| `[REVIEW COUNT]` | e.g. "3,200+ reviews" |
| `[PROBLEM COUNT]` | "3", "4", or "5" |
| `[HERO CTA TEXT]` | CTA button text |
| `[TRUST SIGNAL N]` | Trust bar text (N = 1–5) |
| `[PROBLEM N LABEL]` | Short badge text e.g. "Wasted time" (N = 1–5) |
| `[PROBLEM N HEADLINE]` | Pain-framing headline — reader's situation (N = 1–5) |
| `[PROBLEM N BODY]` | 2–3 sentences in reader's voice, "you" language, specific failure scenario |
| `[FIX N HEADLINE]` | Solution headline (N = 1–5) |
| `[FIX N BODY]` | 2–3 sentences — name the product, explain the mechanism (N = 1–5) |
| `[FIX N CTA]` | Per-problem CTA link text (N = 1–5) |
| `[TRANSFORM HEADLINE]` | Transformation strip section heading |
| `[THEN N]` | Before-state line (6–8 words, plain language) (N = 1–3) |
| `[NOW N]` | After-state line (6–8 words, parallel structure) (N = 1–3) |
| `[PROBLEM SOLVED N]` | Short label above review card e.g. "Fixed: wasted mornings" (N = 1–3) |
| `[REVIEW TITLE N]` | Review card title (N = 1–3) |
| `[REVIEW BODY N]` | Review card body (N = 1–3) |
| `[REVIEWER NAME N]` | Reviewer name (N = 1–3) |
| `[GUARANTEE HEADLINE]` | Guarantee section heading |
| `[GUARANTEE BODY]` | 2–3 sentences of guarantee copy |
| `[GUARANTEE TEXT]` | Short guarantee label e.g. "30-Day Risk-Free Guarantee" |
| `[FINAL CTA HEADLINE]` | Close headline |
| `[FINAL CTA SUBHEAD]` | Close subheadline |
| `[FAQ Q N]` / `[FAQ A N]` | FAQ content — frame questions around problem resolution (N = 1–5) |

Full token list in `li-03-problem-solution/BUILD-NOTES.md`.
