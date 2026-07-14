# Fresh Seal — Store Setup Guide

Crosson base theme + 8 custom Fresh Seal sections, wired into the homepage and product
page per the Fresh Seal layout guide. Everything is editable in
**Online Store → Themes → Customize** — no code needed.

## Page structure (already wired up)

**Homepage** (`templates/index.json`), top to bottom per the layout guide:
1. Announcement bar — navy, "🇿🇦 Ships from South Africa · Free shipping over R700 · 30-day guarantee" (part of the header group; edit under Header)
2. Fresh Seal — Hero (headline "Keep food fresh 5× longer.", R599 offer, CTA, 3 trust ticks)
3. Fresh Seal — Trust strip (Ships SA · Free shipping R700+ · 30-day · 12-month, cream bg)
4. Fresh Seal — Tabbed comparison (Why Fresh Seal? / Us vs Them / What's Included / Benefits)
5. Fresh Seal — Carousel (bundles, arrows + swipe, ~1 card mobile / 1.5–2 desktop)
6. Fresh Seal — Social proof (2×2: three green stats + one testimonial card)
7. Fresh Seal — 4-in-1 modes (Vacuum & Seal / Seal Only / Pulse / Jar & Container)
8. Fresh Seal — Bundle offer (R599 starter + R149 bump = R748 → unlocks free shipping)
9. Fresh Seal — FAQ (accordion, one open at a time)

**Product page** (`templates/product.json`): product gallery/buy box on top, then the same
Fresh Seal flow (trust → tabs → modes → bundle → social proof → carousel → FAQ).

## The 10-minute launch checklist

1. **Bundle offer** → pick your real products: *Bundle product* (machine+51 bags) and
   *Bump product* (50 bags). Set the cents fields: R599 → `59900`, R149 → `14900`,
   threshold R700 → `70000`. The live total and "unlock FREE SHIPPING" logic then run
   themselves.
2. **Carousel** → each card has a *Product* picker (pulls image/price/link). The
   "What's in the bundle" field uses `Qty | Item` lines (e.g. `51 | Vacuum Bags`) to show
   numbered chips.
3. **Hero** → upload your before/after image (freezer burn vs sealed).
4. **Social proof** → replace the placeholder stats and the placeholder testimonial with
   your real numbers and a real review (per the brief, no fake reviews are pre-filled).
5. **Us vs Them tab** → optionally upload your logo for the column header; rows are
   `Feature | You | Them` lines (`yes`/`no` → green tick / red cross). Defaults compare
   R599 vs R690+, any-bag compatibility, 4-in-1 modes, warranty, SA shipping.
6. **Header** → replace the logo, and set free shipping to R700 in
   Shopify Settings → Shipping.

## Section files

| File | Section |
|---|---|
| `sections/fresh-seal-hero.liquid` | Hero (image + offer) |
| `sections/fresh-seal-trust-strip.liquid` | Trust strip |
| `sections/fresh-seal-tabbed-comparison.liquid` | Tabbed comparison |
| `sections/fresh-seal-carousel.liquid` | Bundle carousel |
| `sections/fresh-seal-social-proof.liquid` | Stats + testimonial grid |
| `sections/fresh-seal-modes.liquid` | 4-in-1 modes |
| `sections/fresh-seal-bundle-offer.liquid` | Bundle + order bump |
| `sections/fresh-seal-faq.liquid` | FAQ accordion |

All sections: scoped inline CSS/JS, mobile-first (375px+), 48px+ touch targets, lazy
srcset images, flat design (no gradients), colours per brand spec — white/cream
(#FFFFFF/#F5F5F5), green #2D9D78 (hover #1e7d5f), navy #1A1A1A, grey #555555/#DDDDDD.
Every colour is also a theme-editor setting if you want to tweak.
