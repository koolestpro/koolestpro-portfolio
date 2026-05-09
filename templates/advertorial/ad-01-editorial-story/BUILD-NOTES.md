# ad-01-editorial-story — Source Audit & Build Brief

Source file: `_source-forestcamps.html`
Reference screenshot: `preview-page.png`
Reference URL: `https://forestcamps.myshopify.com/apps/alchemy/element/preview?elementId=9dfdce45-f283-4418-9d81-1deb46ad8678&storeId=374a8a49-9154-4110-90ef-1305cde121c0`
Template status: Source captured and audited. Do not use the source directly. Build `index.html` only after this audit is reviewed.

---

## What This Template Is

A long-form editorial advertorial modeled after a supplement-style performance article. It uses a publication header, a discounted offer banner, a headline/subheadline/byline block, credibility counters, featured-in logos, article sections, inline CTAs, a sticky right-side CTA rail, ingredient/product proof blocks, celebrity/expert endorsement framing, a final offer block, and customer proof.

The clean rebuild should keep the persuasion architecture, not the product-specific content or Replo-generated code.

---

## Reference Structure Observed

1. Top editorial masthead: logo/publication mark, "Advertorial" label, and offer link.
2. Small placeholder/kicker row: currently "This is default text"; should become article category or disclosure.
3. Article hero: headline, subheadline, date, author, author image, and large hero visual.
4. Social authority strip: 3 counters for followers/likes/audience size.
5. Featured-in strip: label plus publication/logo placeholders.
6. Main article opening: big thesis heading and 4 paragraphs agitating the problem.
7. First image-led transition: article image, section heading, and explanatory copy.
8. Inline CTA panel: repeated product disadvantage claim + CTA.
9. Sticky right CTA card: product image, short pitch, and CTA. This must be sticky on desktop and become an inline/mobile-safe CTA on smaller screens.
10. Solution section: product category intro, product differentiation, product image.
11. Quote/testimonial card: named authority/person quote with role.
12. Product mechanism section: "How it works" heading, explanatory copy, and 3 named mechanism/blend cards.
13. Compliance/trust paragraph: e.g. caffeine-free, certified, tested, safe, clean, etc.
14. Second authority quote: named user/athlete/creator story.
15. Inline CTA repeat.
16. Ingredient/product grid: 5 small tiles for key ingredients/materials/features.
17. Endorsement/story section: why the authority/person uses or created the product.
18. Final offer block: discount/urgency copy, product image, CTA, trust badge.
19. Customer proof heading: currently appears but the review cards are absent in the captured visible text; the rebuild should include them.

---

## Troubleshooting Report — Issues Found

### Critical — Source & Dependency Issues

**01. Source is a Shopify/Replo export, not a clean template**
The actual advertorial is embedded inside a Shopify theme shell with generated Replo classes, import maps, storefront scripts, analytics, captcha scripts, cart/search modals, footer sections, and preview banner code. `index.html` must be rebuilt from scratch as one self-contained HTML/CSS/JS file.

**02. External image dependencies**
The advertorial images are hosted on `andytown-public.s3.amazonaws.com`, while the Shopify shell includes `cdn.shopify.com` assets. Every image must become a relative path under `./images/`, with `<!-- IMAGE: -->` comments.

**03. External JS dependencies**
The source loads Shopify theme modules, Replo runtime code, analytics, captcha, storefront features, and preview scripts. The clean rebuild must use no external JS libraries and only small vanilla JS for interactions.

**04. Replo preview banner must be removed**
The fixed "This is a page preview by Replo" banner is part of the preview environment, not the template.

**05. Storefront header/footer must be removed**
The Shopify header, cart drawer, search modal, email signup footer, and powered-by footer are not part of the advertorial template.

### Critical — Copy & Content Issues

**06. Product-specific content throughout**
The copy is for Alpha BRAIN and nootropics. Replace all product, founder, ingredient, endorsement, CTA, and offer copy with bracket tokens.

**07. Unusable placeholder copy**
"This is default text" appears near the top. Replace with `[ARTICLE CATEGORY / DISCLOSURE]`.

**08. Deliberate typo/misspelling copy**
The source contains many errors such as "you're flow state", "Watsapp", "teh", "alot", "dis", "Wat", "their promoted", "Wif", "halps", "CAFFIENE", and "CHECK AVALABILITY". The clean template must contain polished, brand-neutral copy tokens only.

**09. Compliance-sensitive claims**
The reference makes health/performance claims, cites studies, and uses supplement language. Future product builds must separate verified claims from placeholders. No fabricated statistics, studies, certifications, endorsements, or testimonials.

**10. Celebrity/person-specific endorsement**
Joe Rogan and other named figures are hardcoded. The clean template must use `[EXPERT / CREATOR NAME]`, `[EXPERT ROLE]`, and `[QUOTE]` tokens. Do not imply endorsement unless the product brief provides proof.

**11. CTA destination is hardcoded**
CTA links point to an S3 placeholder or Onnit-style affiliate URL. Replace all with `#offer` or `[CTA URL]`.

### Critical — Mobile-First Responsive

**12. Replo CSS is not acceptable as project template CSS**
The source uses generated classes and mixed breakpoints such as `@media (max-width: 640px)` plus tablet ranges. Rebuild CSS mobile-first with base mobile styles and only `@media (min-width: 768px)` and `@media (min-width: 1280px)`.

**13. Sticky right CTA needs deliberate responsive behavior**
Desktop: right rail CTA should use `position: sticky; top: 96px; align-self: start;`.
Tablet/mobile: rail must become an inline CTA after the first article section or a bottom non-overlapping CTA bar if chosen during build. It must never cover article text.

**14. Article measure needs control**
The clean article column should use a comfortable editorial measure: roughly `680px` for body copy and `900px-1100px` for media sections, with a desktop layout grid for article + sticky rail.

### Above The Fold — Performance

**15. Hero images are eager but not cleanly preloaded**
The source has multiple `loading="eager"` images. In the rebuild, preload exactly the primary hero image with `<link rel="preload" as="image" href="./images/hero.jpg">`; hero image uses `loading="eager"`, all others `loading="lazy"`.

**16. Fonts are imported in source CSS**
The source uses an `@import` for Montserrat/Gilda/Nunito. Rebuild with required Google Fonts preconnect links in `<head>` and the project font variable pattern.

### CSS Quality

**17. Colors are hardcoded throughout generated CSS**
Examples include dark navy `#17242C`, blue `#0077CC`, white, black, and multiple inline color spans. Rebuild with all colors in `:root` tokens.

**18. Many inline `style=""` attributes**
The Shopify/Replo output relies on inline variables and style attributes. Clean `index.html` should use authored classes and edit comments.

**19. Generated class names are not maintainable**
Classes like `r-102t4hh`, `r-k6or2c`, and similar generated names cannot be used. Rebuild with semantic classes such as `.masthead`, `.article-hero`, `.article-shell`, `.sticky-offer`, `.proof-strip`, `.ingredient-grid`, `.quote-card`.

**20. `!important` and framework resets must not carry over**
The Replo reset and Shopify theme CSS should not be copied. The rebuild should use scoped, simple CSS.

### Icon & Image Audit

**21. Logo strips are image-based**
The featured-in logos are external image assets. For a brand-neutral template, use text logo placeholders or local placeholder images. If icons are needed, use inline SVG only.

**22. Missing image alt text**
Many source images lack alt text. Every image in the rebuild needs descriptive alt text plus edit comments.

### JavaScript & Interaction Audit

**23. No project-standard scroll fade-in**
The clean template needs `IntersectionObserver` fade-in on all major sections.

**24. CTA feedback missing**
All CTA buttons should provide click feedback where they act as template buttons. If they are anchor links, keep navigation semantic and add focus-visible states.

**25. Customer reviews section appears incomplete**
The visible source ends with "What Alpha BRAIN Customers Are Saying" but review card copy is not present in the extracted visible text. The rebuild should include 3 customer review cards to complete the persuasion arc.

### Accessibility

**26. Editorial disclosure needs semantic placement**
The advertorial label/disclosure should be visible near the masthead and readable by screen readers.

**27. Author metadata should use semantic elements**
Use `<article>`, `<header>`, `<time datetime="">`, and accessible author/image markup.

**28. CTAs need accessible labels**
Repeated CTAs can share visible copy, but each should have context through nearby text or `aria-label`.

---

## Product Inputs Required For Any Future Advertorial

Before writing copy for a product using this template, gather:

1. Product name and brand name.
2. Product category in plain language.
3. Primary buyer and traffic context: ad click, cold social, native ad, email, or retargeting.
4. One central problem the article agitates.
5. The old way or common failed solution.
6. The product's unique mechanism: material, ingredient blend, design, workflow, ritual, sensor, formula, etc.
7. 3-5 proof points that are true: reviews, certifications, test results, founder story, before/after evidence, guarantee, press mentions.
8. Any compliance boundaries: health, medical, financial, safety, or legal claims that must be avoided.
9. Offer details: price, discount, bundle, guarantee, shipping, urgency window.
10. Required images: publication/logo mark, hero/editorial image, problem image, product cutout, lifestyle image, detail/mechanism image, person/quote image, final offer product image, customer/review images.
11. Expert/creator/testimonial details only if real and approved.
12. Citation/source inputs if the article references research, statistics, or studies.

---

## Clean Template Section Map

The rebuild should use these 15 sections:

S1 Masthead / Offer Bar: publication logo, advertorial label, disclosure, offer link.
S2 Article Header: category, headline, subheadline, author, date, hero image.
S3 Social Authority: 3 audience/proof counters plus featured-in row.
S4 Opening Hook: thesis heading and problem-agitation paragraphs.
S5 Problem Deep Dive: image, subheading, science/context explanation, source callout.
S6 Inline CTA 1: short disadvantage/urgency claim and CTA.
S7 Solution Introduction: product category context, product image, product differentiation.
S8 Expert Quote: named expert/creator/user quote card.
S9 Mechanism: "How [PRODUCT] Works" plus 3 mechanism cards.
S10 Trust / Safety / Compliance: clean formula/material/testing/guarantee proof.
S11 Use Case Story: second authority/customer story with image.
S12 Inline CTA 2: repeated CTA after proof.
S13 Ingredient / Feature Grid: 5 key ingredients, materials, specs, or features.
S14 Final Offer: product packshot, discount/guarantee/urgency, CTA, secure transaction note.
S15 Customer Proof: 3 review cards and small closing CTA.

Desktop layout requirement: S4-S13 should sit inside an `.article-layout` grid with the main article column and `.sticky-offer` right rail. The sticky rail starts after the hero/proof strip and remains sticky through the article body.

---

## Copywriting Rules For This Template

1. The article must read like editorial content, not a product page.
2. Every section advances one argument: problem, stakes, failed old way, mechanism, proof, offer.
3. Use specific buyer pain language instead of generic claims.
4. Avoid unsupported numbers. If a stat is not supplied, use a token like `[SOURCE-BACKED STAT]`.
5. Do not fabricate press logos, expert quotes, certifications, studies, or customer reviews.
6. Avoid overclaiming. Health, wellness, safety, financial, and performance claims need softer compliant language unless verified.
7. CTA copy should be product-specific: `Check Availability`, `See Today's Offer`, `Get [PRODUCT]`, or `Claim The Bundle`.
8. The sticky CTA should summarize the offer, not introduce new claims.

---

## Token Requirements For `index.html`

Use these additional advertorial-specific tokens alongside the global template tokens:

| Token | Purpose |
|---|---|
| `[PUBLICATION NAME]` | Fake editorial publication name |
| `[ADVERTORIAL DISCLOSURE]` | Short sponsored/disclosure label |
| `[ARTICLE CATEGORY]` | Category label above headline |
| `[ARTICLE HEADLINE]` | Main editorial headline |
| `[ARTICLE SUBHEADLINE]` | One-sentence promise/problem hook |
| `[AUTHOR NAME]` | Article byline |
| `[PUBLISH DATE]` | Visible article date |
| `[READ TIME]` | Optional read time |
| `[PROBLEM THESIS]` | Opening section thesis |
| `[PAIN PARAGRAPH 1]` etc. | Article body paragraphs |
| `[SOURCE NOTE 1]` etc. | Citation notes if supplied |
| `[MECHANISM 1 TITLE]` | Mechanism/ingredient/feature card title |
| `[MECHANISM 1 BODY]` | Mechanism/ingredient/feature explanation |
| `[EXPERT NAME]` | Expert, founder, or reviewer name |
| `[EXPERT ROLE]` | Role/title |
| `[EXPERT QUOTE]` | Quote text |
| `[OFFER HEADLINE]` | Final offer headline |
| `[OFFER BODY]` | Final offer body copy |
| `[CTA URL]` | CTA destination |

---

## Build Order For `index.html`

1. Set up `index.html` with the required project header comment block.
2. Add Google Fonts preconnect and font link with `&display=swap`.
3. Add hero image preload for `./images/hero.jpg`.
4. Define `:root` tokens for colors, fonts, spacing, shadows, radii, and editorial measures.
5. Write mobile base CSS first.
6. Add `@media (min-width: 768px)` tablet rules.
7. Add `@media (min-width: 1280px)` desktop rules, including sticky right CTA.
8. Build semantic HTML with `<article>`, `<header>`, `<aside>`, `<section>`, `<figure>`, and `<time>`.
9. Add `<!-- EDIT: -->` comments before every editable text node.
10. Add `<!-- IMAGE: -->` comments before every image.
11. Use relative images only: `./images/hero.jpg`, `./images/problem.jpg`, `./images/product.png`, `./images/lifestyle.jpg`, `./images/detail.jpg`, `./images/person.jpg`, `./images/offer.png`.
12. Add inline SVG icons for lock/check/arrow/source/trust marks.
13. Add IntersectionObserver section fade-ins.
14. Add one-open-at-a-time FAQ/customer-proof accordion only if the final design includes collapsible proof; otherwise keep review cards visible.
15. Test no horizontal scroll at 375px, tablet layout at 768px, and sticky rail at 1280px.

---

## Recommended Visual Direction

Use a credible editorial style: white or warm off-white article background, dark masthead, restrained blue or copper links, readable serif/display headline pairing, and clean product CTA cards. The page should feel like a premium magazine article with a commerce rail, not like a loud direct-response landing page.
