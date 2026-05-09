# pdp-01-story-arc — Source Audit & Build Brief

Source file: `_source-forestcamps.html`
Template status: Source only. Do not use directly. Build `index.html` using this audit.

---

## What This Template Is

A 13-section product detail page following the villain/hero/proof narrative structure.
Sections: Hero + Buy Box → Why Us → Villain → Hero Solution → Before/After → Steps →
Social Proof → Stats → Comparison → Comparison Reviews → FAQs → Trust Pillars → Footer.

This is the correct structural foundation for `pdp-01-story-arc`. All issues below
must be resolved when building the clean `index.html` version of this template.

---

## Troubleshooting Report — 30 Issues Found

Cowork: when building `index.html` from this source, check for and fix every item below.

---

### CRITICAL — Content & Structure

**01. Wrong product content throughout**
Everything below the buy box is hair product content (Full Hair Club, fibers, thinning hair).
The section headings, step descriptions, review copy, FAQ answers, trust section, and comparison
table rows all reference a hair product. Every content block must be replaced with
brand-neutral placeholder copy using `[BRAND]`, `[PRODUCT]`, `[BENEFIT]` tokens.

**02. External Shopify CDN image paths**
All `src` values point to `cdn.shopify.com/...` which will 404 outside Shopify.
The `onerror` fallback to `placehold.co` is acceptable in source only.
In `index.html`: replace ALL `src` values with relative paths `./images/placeholder-[name].jpg`
and add `<!-- IMAGE: description of what goes here -->` comments above every `<img>` tag.

**03. Hardcoded brand names with no edit markers**
"forestcamps" appears in the logo, footer, and page title.
"Full Hair Club" appears in the comparison table header and step copy.
Neither has `<!-- EDIT: -->` comments. In `index.html`: replace with `[BRAND NAME]` tokens
and add `<!-- EDIT: Brand name — replace [BRAND NAME] with actual brand -->` above each.

**04. No section separator comments**
HTML comments exist but are inconsistent. In `index.html`: every section must open with
`<!-- ═══ SECTION [N]: [NAME] ══════════════════════════════════ -->`.

**05. `<div class="product-hero">` not in a `<section>`**
All other content blocks use `<section>`. The hero uses a `<div>`. Fix for semantic consistency.

---

### CRITICAL — Emojis (Zero Tolerance Rule)

**06. Emoji in benefit cards**
`.benefit-emoji` class (line 118) uses `font-size: 28px` emoji as the icon.
Replace with inline SVG. Each benefit gets its own SVG icon.

**07. Emoji in villain section**
`.villain-icon` (line 107) is a `font-size: 40px` emoji.
Replace with an inline SVG wrapped in the orange circle container.

**08. Emoji in step icons**
`.step-icon` circles (lines 488, 493, 498) contain emoji: 💨, 🧂, 💈.
Replace each with an appropriate inline SVG inside the existing circle container.

**09. Emoji in trust section**
`.trust-icon` containers (lines 703, 708, 713) contain emoji: 🌿, 💬, 🪞.
Replace each with an inline SVG.

**10. Emoji in comparison table rows**
Row labels contain inline emoji: ⏳️, 👌, 💦, 🌟, 💪 (lines 596–619).
Remove all emoji. Text labels only.

**11. Emoji in section title**
`WHY CHOOSE US OVER OTHERS? 👀` (line 588). Remove the emoji.

---

### CRITICAL — Mobile-First Responsive

**12. Desktop-first CSS architecture**
All base styles are written for desktop. The single `@media (max-width: 768px)` block
at line 215 overrides for mobile. This is backwards.
In `index.html`: rewrite base styles for 375px mobile layout.
Use `@media (min-width: 768px)` for tablet and `@media (min-width: 1280px)` for desktop.
This means: grid starts as `grid-template-columns: 1fr` in base, then promotes to 2-col at 768px+.

**13. Only one breakpoint — no tablet (768px) treatment**
The responsive block handles 768px collapse but nothing in between.
Add `@media (min-width: 768px)` and `@media (min-width: 1280px)` breakpoints.

**14. `.sp-top` flex layout breaks on mobile**
`.sp-top` uses `display: flex` with a hardcoded `260px × 180px` image (`.sp-banner-img img`).
This hardcoded size does not stack correctly on mobile.
In `index.html`: base style stacks vertically (`flex-direction: column`), promotes to row at 768px+.
Image width should be `100%` in base, `260px` at 768px+.

**15. `.gallery` mobile behaviour needs refinement**
At mobile, gallery goes `flex-direction: column-reverse` which puts thumbs below the main image — correct.
But the `.thumbs` row needs `scrollbar-width: none` and `-ms-overflow-style: none`
with matching `::webkit-scrollbar { display: none; }` for a clean horizontal scroll on mobile.

---

### ABOVE THE FOLD — Performance

**16. No `loading="eager"` on the hero main image**
The main product image (`.main-img img`) needs `loading="eager"` to load immediately.
All other images need `loading="lazy"`.

**17. No `<link rel="preload">` for the hero image**
Add `<link rel="preload" as="image" href="./images/hero.jpg">` in `<head>`.

**18. No Google Fonts — system font stack only**
`:root --font: 'Helvetica Neue', Arial, sans-serif` means no web font loads.
In `index.html`: the font stack is replaced by the brand's fonts from the brand identity.
Add `<link rel="preconnect">` and the Google Fonts `<link>` in `<head>`.
Default placeholder: Bebas Neue (display) + DM Sans (body) until brand is applied.

**19. `font-weight: 800` used with a font that doesn't support it**
`.section-title` (line 87), `.ba-quote` (line 130), `.sp-headline` (line 149) all use `font-weight: 800`.
Helvetica Neue only reliably renders 400 and 700. 800 renders as 700 anyway.
Replace with 700 for system fonts. When Google Fonts with 800 support are loaded, this is fine.

---

### CSS QUALITY

**20. Hardcoded color values outside `:root`**
The following colors are hardcoded and not in `:root`:
- `#22c55e` (check mark green, line 176) → add `--color-yes: #22c55e;`
- `#ef4444` (cross red, line 177) → add `--color-no: #ef4444;`
- `rgba(0,0,0,.05)`, `rgba(0,0,0,.06)` in box shadows → add `--shadow-card`
- `#ddd` used as placeholder background (lines 50, 111, 121) → add `--color-placeholder`
All must be in `:root`.

**21. Inconsistent border-radius values**
`12px`, `14px`, `8px`, `20px` are used across different components with no system.
Add `--radius-sm: 6px`, `--radius-md: 10px`, `--radius-lg: 14px` to `:root`
and apply consistently.

**22. Inline `style=""` attributes on 15+ HTML elements**
Lines 483, 484, 516, 520, 549–553, 562–563, 584–588, 641–643, 654, 699, 733 all have
`style=""` attributes. All must be converted to CSS classes. Zero inline styles in `index.html`.

**23. `badge::before { content: '✓' }` is CSS-generated text, not SVG**
The checkmark badges use `::before` with a Unicode character (line 60). Replace with
a proper inline SVG checkmark inside `.badge` instead of a pseudo-element.

**24. Inconsistent max-width**
`.product-hero` uses `max-width: 1200px` while `.section-inner` uses `max-width: 1100px`.
Pick one. Use `--max-width: 1280px` in `:root` and apply consistently.

**25. No CSS variable for section padding**
`section { padding: 64px 24px }` is hardcoded. Add `--section-padding-v: 64px` to `:root`
so it can be adjusted globally. Mobile base should be `padding: 48px 20px`.

---

### JAVASCRIPT

**26. Gallery JS doesn't set `active` class on click correctly**
Line 752–758: the script removes `.active` from all thumbs, then sets `.active` on the
clicked thumb. The `src` copy via `mainImg.src = thumb.querySelector('img').src` works
but there is no fade transition. Add `opacity: 0` → setTimeout → set src → `opacity: 1`
transition as in the KURA build.

**27. No scroll fade-in animations**
The source has zero scroll-triggered animations. `index.html` must implement
`IntersectionObserver` fade-in on all `<section>` elements.

**28. FAQs use native `<details>/<summary>` — no JS control**
This is fine for accessibility. Keep `<details>/<summary>` in this template.
But ensure `summary::after` close animation works on all browsers (it does currently).
Consistency note: if the brand build uses JS accordion, switch to JS accordion at that stage.

---

### ACCESSIBILITY & SEMANTICS

**29. Star ratings are pure text characters `★★★★★`**
These are not accessible — no `aria-label` for screen readers.
Wrap in `<span aria-label="5 out of 5 stars" role="img">★★★★★</span>`.

**30. Missing `alt` text on several images**
Several `<img>` tags have generic or empty alt text. Every image in `index.html`
must have a descriptive `alt` attribute with a `<!-- EDIT: alt text -->` comment.

---

## Build Order for `index.html`

When Cowork builds the clean template from this source, work in this order:

1. Set up `<head>`: viewport, preconnect, Google Fonts (placeholder stack), preload hero image
2. Write `:root` with ALL tokens: colors, fonts, radii, shadows, spacing, max-widths
3. Write base (mobile) CSS first — no media queries yet
4. Add `@media (min-width: 768px)` tablet layer
5. Add `@media (min-width: 1280px)` desktop layer
6. Replace all emoji with inline SVG
7. Remove all inline `style=""` attributes — convert to classes
8. Replace all content with `[BRAND]`/`[PRODUCT]`/`[BENEFIT]` tokens
9. Replace all external image paths with `./images/` relative paths + `<!-- IMAGE: -->` comments
10. Add `<!-- EDIT: -->` comments on every editable text node
11. Add `<!-- ═══ SECTION N: NAME ═══ -->` separators
12. Add `loading="eager"` to hero, `loading="lazy"` to all others
13. Implement IntersectionObserver scroll fade-in
14. Add gallery fade transition
15. Fix star rating aria-labels
16. Test at 375px, 768px, 1280px before marking complete
