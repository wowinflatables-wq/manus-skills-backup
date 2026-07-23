# BounceBook Embed Configuration

This document records how BounceBook is embedded and linked from the Wow Inflatables website (`www.wowjumpparty.com`).

## Live Booking URLs

| Purpose | URL |
|---|---|
| Main Catalog / Rentals | `https://bouncebook-3fimm8bf.manus.space/rentals` |
| Booking Catalog | `https://bouncebook-3fimm8bf.manus.space/catalog` |

## Website Integration Points

The following locations on `www.wowjumpparty.com` link directly to BounceBook:

| Page Section | Link Text | Destination |
|---|---|---|
| Hero / Header CTA | "Book Online" | `/rentals` |
| Bounce Houses section | "Select" | `/rentals` |
| Wet & Dry Slides section | "Select" | `/rentals` |
| Interactives section | "Select" | `/rentals` |
| Amusements section | "Book Now" button | `/rentals` |
| Footer | "Book Online" | `/rentals` |
| Navigation (top) | "Inflatables" | `/catalog` |

## Category-Specific Deep Links (Recommended)

For improved SEO and user experience, use these category-filtered deep links in navigation dropdowns:

```
/book?category=bounce-houses       → Bounce Houses
/book?category=water-slides        → Wet & Dry Slides
/book?category=interactive-games   → Interactive Games
/book?category=amusements          → Amusements
/book?category=concessions         → Concessions
```

## Previous Booking System

Prior to BounceBook, Wow Inflatables used **Checkfront** as its reservation system. Legacy Checkfront links (`https://wowinflatables.checkfront.com/reserve/`) still appear in some older sections of the website and should be updated to point to BounceBook URLs.

| Old Checkfront URL | Replace With |
|---|---|
| `https://wowinflatables.checkfront.com/reserve/` | `https://bouncebook-3fimm8bf.manus.space/rentals` |
| Back Office: `https://wowinflatables.checkfront.com/` | BounceBook operator dashboard |
