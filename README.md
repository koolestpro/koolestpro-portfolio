# Replo Portfolio — Build System

A personal portfolio of Replo-quality product pages, landing pages, advertorials,
homepages, and listicles — built in pure HTML/CSS/JS, fully responsive, fast-loading,
and brand-complete. Every build is portfolio-ready and documented with a professional
agency-grade case study.

---

## What This Is

A systematic build machine that turns dropship products into full brand identities and
high-converting web experiences. Each product goes through a fixed 6-phase pipeline:

```
Product Found → Brand Identity → Image Prompts → AI Images → Page Build → Case Study
```

All builds, brands, and templates live here. This is the single source of truth.

---

## Folder Structure

```
portfolio/
│
├── README.md                      ← You are here
├── WORKFLOW.md                    ← Step-by-step pipeline (read before every build)
├── CLAUDE.md                      ← Cowork instructions (always active)
│
├── templates/                     ← Reusable page skeletons (KURA as placeholder)
│   ├── pdp/
│   │   ├── pdp-01-story-arc/      ← Villain/hero narrative, long-form proof
│   │   ├── pdp-02-social-proof/   ← Review-forward, UGC-heavy
│   │   ├── pdp-03-comparison/     ← Feature table, vs-competitors angle
│   │   ├── pdp-04-minimal/        ← Editorial, product-led, premium feel
│   │   └── pdp-05-urgency/        ← Scarcity, countdown, bold CTAs
│   ├── homepage/
│   │   ├── hp-01-brand-story/     ← Brand-first, emotional storytelling
│   │   ├── hp-02-product-hero/    ← Product above fold, single SKU
│   │   └── hp-03-collection/      ← Multi-product grid
│   ├── landing-page/
│   │   ├── lp-01-direct-response/ ← No nav, single CTA, ad traffic
│   │   ├── lp-02-vsl-style/       ← Video-first, long benefit close
│   │   └── lp-03-quiz-funnel/     ← Interactive quiz to recommendation
│   ├── advertorial/
│   │   ├── ad-01-editorial-story/ ← News/editorial third-person format
│   │   └── ad-02-personal-essay/  ← First-person transformation story
│   └── listicle/
│       ├── li-01-top5-comparison/ ← Top 5, brand product ranked #1
│       └── li-02-buyers-guide/    ← Comprehensive category guide
│
└── brands/                        ← One subfolder per product brand
    └── [brand-name]/
        ├── [brand]-identity.html  ← Full brand identity document
        ├── assets/
        │   └── images/            ← All AI-generated product images
        ├── pages/                 ← All built pages for this brand
        │   └── [brand]-[type]-[template-id]/
        │       ├── index.html     ← The built page
        │       └── images/        ← Images used in this specific page
        └── case-study/
            ├── [brand]-case-study.html
            └── assets/
```

---

## Template Naming Conventions

| Template ID | Type | Best For |
|---|---|---|
| `pdp-01-story-arc` | PDP | Everyday products with clear problem/solution. Villain → hero narrative. |
| `pdp-02-social-proof` | PDP | Beauty, wellness, lifestyle. Strong reviews and UGC. |
| `pdp-03-comparison` | PDP | Utility or tech products. Beats competitors on features. |
| `pdp-04-minimal` | PDP | Premium or design-led. Let the product and photography speak. |
| `pdp-05-urgency` | PDP | Impulse-buy or promotional products. FOMO and scarcity driven. |
| `hp-01-brand-story` | Homepage | Building brand equity. Emotional, values-led above the fold. |
| `hp-02-product-hero` | Homepage | Single-SKU brands. Product is the entire homepage hero. |
| `hp-03-collection` | Homepage | Expanding brands. Category grid, multiple products. |
| `lp-01-direct-response` | Landing Page | Paid ad traffic. No nav, one action, highest conversion focus. |
| `lp-02-vsl-style` | Landing Page | Video-first. Higher-ticket or complex products. |
| `lp-03-quiz-funnel` | Landing Page | Personalised recommendation products (supplements, skincare, etc). |
| `ad-01-editorial-story` | Advertorial | Health, kitchen, home. Written like a news feature article. |
| `ad-02-personal-essay` | Advertorial | Self-improvement, wellness. First-person before/after narrative. |
| `li-01-top5-comparison` | Listicle | SEO and cold traffic. Top 5 ranked, brand product placed #1. |
| `li-02-buyers-guide` | Listicle | Considered purchases. Comprehensive category education + recommendation. |

---

## Current Brands

| Brand | Product | Identity | Pages | Case Study |
|---|---|---|---|---|
| KURA | Stainless Steel Cutting Board | ✅ Complete | pdp-01-story-arc ✅ | 🔄 In progress |

---

## Performance Standards

Every built page must pass:
- [ ] Loads in < 2s (no external JS libraries, optimised images)
- [ ] Fully responsive (mobile-first, tested at 375px, 768px, 1280px)
- [ ] Zero layout breaks on scroll
- [ ] All interactions work (accordion, gallery, variant select)
- [ ] Prints cleanly (for case study screenshots)
- [ ] SVG icons — no icon fonts
- [ ] Google Fonts loaded async or preconnected
