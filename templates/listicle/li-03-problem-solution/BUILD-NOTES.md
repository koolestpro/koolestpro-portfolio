# li-03-problem-solution — Build Brief

Template type: Listicle / Problem → Solution
Status: Built — 2026-05-05
Source: No source file — built from scratch (Case C)
Reference: Replo marketplace patterns + CRO problem-agitation-solution framework

---

## What This Template Is

A pain-first listicle. 3–5 numbered problems the target reader has — each one
named, amplified, then resolved with the brand's product. Structurally different
from li-02 (benefit stacking): this template leads with empathy before selling.

The reader's experience: "They know exactly what I'm dealing with" → "And they
have the fix." This sequence builds trust faster than any benefit list can,
because it proves understanding before making a claim.

Best for cold-to-warm traffic that is pain-aware but not product-aware. Works
especially well for audiences who have tried other solutions and been let down —
because naming the failure patterns signals you understand the category deeply.

---

## How This Differs From li-01 and li-02

| Format | li-01 (Comparison) | li-02 (Benefit) | li-03 (Problem-Solution) |
|---|---|---|---|
| Lead with | Category education | Product benefits | Reader's pain |
| Structure | 5 products ranked | N reasons to buy | N problems → fixes |
| Tone | Editorial, objective | Enthusiastic | Empathetic, then confident |
| Trust mechanism | Competitor honesty | Proof stacking | Recognition effect |
| Best traffic | Cold, category-shopping | Warm, conviction-needing | Cold-warm, pain-aware |
| Hero headline | "Best X of 2025" | "N Reasons to try Y" | "N Problems Y Fixes" |

---

## Design Decisions

**01. Dual-phase sections — Problem badge then Fix badge**
Every problem-solution block has two visually distinct phases, each with a labeled
badge (red "THE PROBLEM" / green "THE FIX"). This is not cosmetic — it signals
the structural contract: you're naming pain before pitching. The visual label
makes the transition moment clear, which is where the reader's emotional state
shifts from recognition to hope. Without the labels, the copy reads like any
benefit section. With them, each block feels like a mini case study.

**02. Divider arrow between problem and fix**
A horizontal rule with a centered downward-arrow SVG separates the problem copy
from the fix copy within each section. This creates a pause — the reader processes
the pain before receiving the solution. Functionally it acts like a beat: "I hear
you. Now here's what changes." Skipping this loses the timing of the format.

**03. Pain headline before stars in the hero**
li-02 leads with eyebrow → stars → headline. li-03 leads with eyebrow (pain frame)
→ headline (problem count) → stars (social proof). Stars appear after the hook, not
before it. On cold traffic, the hook must earn the right to cite proof — the reverse
order feels like a commercial, not a conversation.

**04. Transformation Strip instead of comparison table**
The comparison table in li-02 is product-vs-competition. For li-03, the relevant
contrast is before-vs-after. The transformation strip shows the reader's life in
two states — "Then" (pain language, red tint) and "Now" (resolution language,
green tint) — on a dark background. Same emotional payload as a comparison table
but personal rather than competitive.

**05. Reviews framed as problem confirmations**
The review cards include a "Problem solved:" label above each reviewer quote. This
maps social proof directly to the pain points — the reader with Problem 2 sees a
review from someone who had Problem 2 specifically. Generic five-star reviews are
weaker than reviews that say "I had exactly this problem and here's how it changed."

---

## Section Map

| Section | ID | Purpose | Optional? |
|---|---|---|---|
| Hero | S1 | Pain-framing headline + image | No |
| Trust Bar | S2 | Scrolling trust signals | Yes |
| Problem-Solution 01 | S3.1 | Problem 1 → Fix | No |
| Problem-Solution 02 | S3.2 | Problem 2 → Fix | No |
| Inline CTA Strip | S4 | Mid-list conversion moment | Yes |
| Problem-Solution 03 | S3.3 | Problem 3 → Fix | No |
| Problem-Solution 04 | S3.4 | Problem 4 → Fix | Yes (3-problem) |
| Problem-Solution 05 | S3.5 | Problem 5 → Fix | Yes (3-problem) |
| Transformation Strip | S5 | Before / After contrast strip | No |
| Review Cards | S6 | 3 cards, each tied to a pain point | No |
| Guarantee | S7 | Risk reversal block | Yes |
| Final CTA | S8 | Strong close | No |
| FAQ | S9 | 5 objection-handling questions | No |
| Footer | S10 | Minimal | No |

---

## Problem Count Guide

| Count | Keep | Remove |
|---|---|---|
| 3 problems | S3.1, S3.2, S3.3 | Remove S3.4 and S3.5 |
| 4 problems | S3.1 through S3.4 | Remove S3.5 |
| 5 problems | All S3.1–S3.5 | Nothing (default) |

Tip: For 3-problem layouts, move the inline CTA strip after S3.2 (middle).
For 5-problem layouts, keep it after S3.2 (default).

---

## Token System

| Token | Replace with |
|---|---|
| `[BRAND NAME]` | Brand name |
| `[PRODUCT NAME]` | Product name |
| `[PRODUCT URL]` | Checkout or PDP URL |
| `[HERO EYEBROW]` | e.g. "For people who are done with X" |
| `[ARTICLE HEADLINE]` | "[N] [Audience] Problems That [Product] Finally Fixes" |
| `[ARTICLE SUBHEADLINE]` | Supporting subhead |
| `[STAR COUNT]` | e.g. "4.9" |
| `[REVIEW COUNT]` | e.g. "3,200+ reviews" |
| `[PROBLEM COUNT]` | "3", "4", or "5" |
| `[HERO CTA TEXT]` | CTA button text |
| `[TRUST SIGNAL N]` | Trust bar text (N = 1–5) |
| `[PROBLEM N LABEL]` | Short problem badge text (N = 1–5) e.g. "Wasted time" |
| `[PROBLEM N HEADLINE]` | Pain-framing headline (N = 1–5) |
| `[PROBLEM N BODY]` | Pain copy — 2–3 sentences in reader's voice (N = 1–5) |
| `[FIX N HEADLINE]` | Solution headline (N = 1–5) |
| `[FIX N BODY]` | Solution copy — 2–3 sentences mentioning product (N = 1–5) |
| `[FIX N CTA]` | Per-problem CTA link text (N = 1–5) |
| `[THEN N]` | Before-state line in transformation strip (N = 1–3) |
| `[NOW N]` | After-state line in transformation strip (N = 1–3) |
| `[TRANSFORM HEADLINE]` | Transformation strip section heading |
| `[PROBLEM SOLVED N]` | Short label above review card (N = 1–3) e.g. "Fixed: wasted mornings" |
| `[REVIEW TITLE N]` | Review card title (N = 1–3) |
| `[REVIEW BODY N]` | Review card body (N = 1–3) |
| `[REVIEWER NAME N]` | Reviewer name (N = 1–3) |
| `[GUARANTEE HEADLINE]` | Guarantee section heading |
| `[GUARANTEE BODY]` | Guarantee copy — 2–3 sentences |
| `[GUARANTEE TEXT]` | Short guarantee label (used in CTA button area) |
| `[FINAL CTA HEADLINE]` | Close headline |
| `[FINAL CTA SUBHEAD]` | Close subheadline |
| `[FAQ Q N]` / `[FAQ A N]` | FAQ content — frame around problem resolution (N = 1–5) |

---

## Copy Writing Guide

**Problem copy ([PROBLEM N BODY]):**
Write in the reader's voice. Use "you" language. Name the specific failure
scenario — not the category problem. Wrong: "Productivity tools are slow."
Right: "You open your laptop with good intentions, but an hour disappears
before you've started anything that matters."

**Fix copy ([FIX N BODY]):**
Introduce the product by name in the first or second sentence. Explain the
mechanism — not just the outcome. Wrong: "KURA changes everything." Right:
"KURA's frictionless surface clears in one sweep, so you start each session
on a clean board — no carry-over clutter from yesterday."

**Transformation strip ([THEN N] / [NOW N]):**
Keep each pair to 6–8 words. Parallel structure. The "then" is the pain in
plain language. The "now" is the resolved state. Example:
Then: "Searching for notes you can't find"
Now: "Everything in one visible place"

---

## Image Requirements

| Image | Dimensions | Section |
|---|---|---|
| `hero.jpg` | 1440 × 680 | S1 Hero background |
| `solution-1.jpg` | 800 × 600 | S3.1 — Problem 01 section |
| `solution-2.jpg` | 800 × 600 | S3.2 — Problem 02 section |
| `solution-3.jpg` | 800 × 600 | S3.3 — Problem 03 section |
| `solution-4.jpg` | 800 × 600 | S3.4 — Problem 04 (optional) |
| `solution-5.jpg` | 800 × 600 | S3.5 — Problem 05 (optional) |
| `review-1.jpg` | 80 × 80 | S6 Review Card 1 avatar |
| `review-2.jpg` | 80 × 80 | S6 Review Card 2 avatar |
| `review-3.jpg` | 80 × 80 | S6 Review Card 3 avatar |

Note: Each solution image should show the product in use (the resolution state),
not the problem state. The pain is conveyed through words, not imagery.

---

## Design Tokens Applied

```css
:root {
  --color-primary:      #1E2832;
  --color-accent:       #C47A3A;
  --color-accent-hover: #A85F25;
  --color-bg:           #FAFAF8;
  --color-surface:      #FFFFFF;
  --color-surface-2:    #F4F1EC;
  --color-text:         #181820;
  --color-muted:        #6B7280;
  --color-border:       #E5E7EB;
  --color-pro:          #16A34A;   /* Fix badge, transformation now-state */
  --color-con:          #DC2626;   /* Problem badge, transformation then-state */
  --font-display:       'Bebas Neue', sans-serif;
  --font-serif:         'Cormorant Garamond', serif;
  --font-body:          'DM Sans', sans-serif;
  --max-width:          1100px;
  --max-width-narrow:   720px;
}
```

---

## CRO Principles Applied

- **Pain-first sequence**: Reader recognises their situation before being sold to
- **Recognition effect**: Named pain = trust. Reader thinks "they get it"
- **Divider creates a beat**: Emotional pause between problem and solution
- **Transformation strip**: Concrete before/after = aspirational outcome made tangible
- **Mapped reviews**: Proof that directly matches the pain points named above
- **Guarantee after reviews**: Risk reversal when conviction is highest
- **FAQ frames around problems**: "Does it really fix X?" — not generic product questions

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
- [x] Problem count guide at top of HTML
- [x] FAQ accordion — one open at a time
- [x] No external JS libraries
- [x] No !important declarations
- [x] Star ratings have aria-label and role="img"
- [x] All images have descriptive alt text
- [x] Trust bar marquee is CSS-only
- [x] Token placeholders on all brand-specific content
- [x] Problem badge and fix badge use CSS variables for color references
