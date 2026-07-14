# Fresh Seal — Theme Setup Guide

This theme is the uploaded high-converting Shopify theme, enhanced with **7 custom, fully
editable Fresh Seal sections**. The original conversion structure is untouched — everything
below is additive and editable from **Online Store → Themes → Customize** (no code needed).

## What was added

| File | Section (theme editor name) | Purpose |
|------|------------------------------|---------|
| `sections/fresh-seal-hero.liquid` | Fresh Seal — Hero | Image + offer + CTA + trust bullets |
| `sections/fresh-seal-tabbed-comparison.liquid` | Fresh Seal — Tabbed comparison | "Why Fresh Seal? / Us vs Them / What's Included / Benefits" — switches on tap, no reload |
| `sections/fresh-seal-carousel.liquid` | Fresh Seal — Carousel | Horizontal snap-scroll product/bundle cards (1.2–1.5 mobile, 3–4 desktop) |
| `sections/fresh-seal-social-proof.liquid` | Fresh Seal — Social proof | Big green stats + testimonial cards |
| `sections/fresh-seal-bundle-offer.liquid` | Fresh Seal — Bundle offer | Hero bundle + order bump that "unlocks free shipping" |
| `sections/fresh-seal-faq.liquid` | Fresh Seal — FAQ | Accordion (no JS needed) |
| `sections/fresh-seal-trust-strip.liquid` | Fresh Seal — Trust strip | Shipping / warranty / returns icons |
| `templates/product.fresh-seal.json` | — | Ready-made product page wiring all sections together |
| `templates/page.fresh-seal.json` | — | Ready-made standalone landing page |

## Install / import

The whole folder **is** a valid Shopify theme.

1. Zip the theme root (the folder containing `assets/`, `config/`, `layout/`, `sections/`,
   `snippets/`, `templates/`).
2. Shopify admin → **Online Store → Themes → Add theme → Upload zip**.
3. Or, to add only the new pieces to an existing theme, copy the 7 `sections/fresh-seal-*.liquid`
   files and the two `templates/*.fresh-seal.json` files into that theme.

Each section also appears in **Add section** on any page/product, so you can drag them in
individually.

## Assign it to a product

1. Create your product (e.g. the Fresh Seal machine bundle) in **Products**.
2. In the product page, **Theme template → `fresh-seal`** (this uses `product.fresh-seal.json`).
3. Or build a landing page: **Pages → Add page → Theme template → `fresh-seal`**.

## The two things to wire up (5 minutes)

Everything ships with sensible copy already filled in. The only wiring needed is to point the
**Bundle offer** at real products so "Add to cart" works:

1. Customize the page → click **Fresh Seal — Bundle offer**.
2. **Bundle product** → pick your machine+bags product. Set **Price in cents** to match
   (R599 → `59900`).
3. **Bump product** → pick your "50 bags" product. Set **Bump price in cents** (R149 → `14900`).
4. **Free-shipping threshold (cents)** → `70000` for R700.

That's it — the live total, the "unlock FREE shipping" message, and the two-item add-to-cart
all update automatically. If you leave the products blank, the button falls back to the
standard cart flow.

## What's editable per section (all in the theme editor)

- **Swap products** — Carousel cards and the Bundle offer use Shopify **product pickers**
  (pull live image/title/price) with optional manual overrides.
- **Change copy / CTAs** — every headline, subtitle, button label, tab, testimonial, stat,
  FAQ and trust item is a text field or block.
- **Upload images** — Hero image, carousel card images and testimonial avatars are
  `image_picker` fields (lazy-loaded, `srcset` responsive) — no redeploy needed.
- **Prices, bundles, shipping threshold** — plain fields in the Bundle offer section.
- **Colours** — every section exposes Accent (default `#2D9D78`), Text (`#1A1A1A`),
  Background (`#FFFFFF`/`#F5F5F5`) and card colours.
- **Add / remove / reorder** — tabs, cards, stats, testimonials, FAQs and trust items are
  all **blocks** — use "Add block" and drag to reorder.

### Tab & table shorthand (Tabbed comparison)
- Bullet lists: one item per line. Use `::` to bold a lead-in, e.g.
  `5× longer freshness::vacuum-seal in seconds.`
- "Us vs Them" table rows: `Feature | Fresh Seal | Them`, one per line. Type `yes` / `no`
  for green ticks / grey crosses, or any short text.

## Design notes

- Mobile-first, tested at 375 / 390 / 768 / 1440px. Single column on mobile, multi-column
  on desktop. All buttons are ≥ 44px tall (touch-friendly).
- Scoped CSS (each section's styles are namespaced by `section.id`) — no bleed into the rest
  of the theme, no external files to manage. All CSS/JS is inline in the section.
- No gradients, minimal motion (a light fade on tab switch), generous spacing — Apple/Dyson feel.
- Accent green `#2D9D78` drives CTAs, stats and highlights; hover darkens to `#248063`.
