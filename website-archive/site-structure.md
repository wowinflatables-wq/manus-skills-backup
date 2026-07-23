# Site Structure & Tech Stack — www.wowjumpparty.com

*Archived July 2026*

---

## Technology Stack

| Component | Platform / Service |
|---|---|
| **Website Builder** | Manus WebDev (static site) |
| **Domain** | wowjumpparty.com |
| **Booking System** | BounceBook (`bouncebook-3fimm8bf.manus.space`) |
| **Legacy Booking (old)** | Checkfront (`wowinflatables.checkfront.com`) |
| **Merch Store** | Shopify (`v5cjnf-ud.myshopify.com`) |
| **Email** | wowinflatables@gmail.com |
| **Analytics** | Google Analytics (referenced in Privacy Policy) |

---

## Page Structure

```
www.wowjumpparty.com/
├── /                        ← Homepage (hero, categories, trust section, testimonials, FAQ)
├── /about                   ← About Wow Inflatables
├── /blog/                   ← Wow News blog
│   └── /blog/what-happens-when-it-rains-on-your-bounce-house-party-...
├── /book                    ← BounceBook catalog (embedded or linked)
└── (external links)
    ├── BounceBook catalog    → bouncebook-3fimm8bf.manus.space/catalog
    ├── BounceBook rentals    → bouncebook-3fimm8bf.manus.space/rentals
    ├── Shopify merch store   → v5cjnf-ud.myshopify.com
    └── Checkfront (legacy)  → wowinflatables.checkfront.com
```

---

## Key CTAs and Booking Flow

1. Customer lands on `www.wowjumpparty.com`
2. Clicks "Book Online", "Select", or a category button
3. Redirected to BounceBook catalog at `bouncebook-3fimm8bf.manus.space/rentals`
4. Customer selects unit, checks availability, pays deposit
5. BounceBook sends automated confirmation, waiver, and follow-up sequence

---

## Recommended Updates

The following legacy Checkfront links still appear in some sections of the site and should be updated to point to BounceBook:

| Current URL | Should Be |
|---|---|
| `https://wowinflatables.checkfront.com/reserve/` | `https://bouncebook-3fimm8bf.manus.space/rentals` |

---

## SEO & Agentic Search Notes

- The `/book` URL should be submitted to Google Search Console as the canonical booking entry point.
- All landing pages and category pages should be optimized for agentic search (AI-driven discovery).
- Category deep-links (`/book?category=bounce-houses`, etc.) improve both SEO and user experience.
