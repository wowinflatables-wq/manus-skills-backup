---
name: package-prize
description: Build irresistible, ready-to-sell rental packages from any party-rental company's inventory — priced right and paired with a dynamic, eye-catching ad. Use this skill whenever the user wants to create a package, bundle, deal, special, or combo; set or rethink pricing for a bundle; build a themed, seasonal, or holiday offer; capitalize on a trend or event; or make a promo ad / flyer / social post for a rental offer — e.g. "make me a summer birthday package," "build a trunk-or-treat bundle," "price this combo," "create a deal for graduation season," "design an ad for my new package." It reads inventory and branding from a profile, so it's fully portable and shareable with other providers. Trigger it whenever packaging, bundling, pricing a deal, or promo-ad creation comes up — even if the skill isn't named.
---

# Package Prize — Rental Package Builder & Ad Maker

Turns a party-rental company's loose inventory into named, themed, **ready-to-sell packages** with a smart price and a finished, eye-catching ad. Built to be **shared with any provider**: nothing about a specific business is hardcoded — it all comes from a profile the provider fills in once.

## Principles
1. **Portable by design.** Read all business-specific data (inventory, prices, branding, contact) from a `business_profile`. Never assume a particular company's items. If the profile is missing, ask the operator to provide it before building.
2. **Cohesive, not random.** A package should tell one story — an event, a theme, an audience — and every item should support it.
3. **Priced to sell, grounded in cost.** Use the pricing method below to produce a recommended price *with the math shown*, then remind the provider to validate it against their real costs, margins, and local market. Pricing guidance is a starting point, not a guarantee.
4. **Trends are live, not frozen.** Search for current themes/colors/popular styles at run time rather than relying on a fixed list, so the skill stays fresh for everyone who uses it.
5. **The ad is a finished asset.** Produce real, branded ad copy and visual(s) sized for where they'll be posted — not just a description.
6. **Real images only.** Ad visuals MUST use actual product photos sourced from the operator's website, gallery, or inventory system — never generic stock photos or AI-generated stand-in images of equipment the business doesn't own. Download real product images from the operator's site and incorporate them into the ad compositions. If no usable product images can be found, ask the operator to provide them before generating visuals.
7. **Theme-driven ad design.** The current holiday, season, or pop culture moment MUST visually influence the ad — not just the copy. Color palettes, graphic accents, background mood, and design motifs should all reflect the chosen angle (e.g., fireworks + red/white/blue for July 4th; toy-box primary colors + star/rocket accents for a toy-themed craze; neon glow for a summer night theme). The ad should *feel* like the moment, not just mention it.
8. **Minimize inventory repetition across packages.** When building multiple packages, avoid reusing the same inflatable unit across different packages unless it is genuinely the best thematic fit for that specific angle. Variety sells — customers who see the same unit in every package assume limited inventory. If a unit truly is the best match for multiple themes (e.g., a patriotic slide for both a July 4th package AND a military appreciation package), it may be reused, but document why. Default behavior: each package should showcase different hero units from the operator's catalog.

---

## First-run setup — the `business_profile` (any provider fills this in)

Collect once and reuse. If connected to a reservation system, pull what you can; otherwise ask:

- **Identity & branding:** business name, logo, brand colors, brand voice (playful / upscale / family-friendly), tagline.
- **Contact & CTA:** phone, website, booking link, service area, social handles.
- **Inventory:** every rentable item with its **à-la-carte price** and a short note on size/theme/best use (bounce houses, combos, water slides, obstacle courses, tents, tables/chairs, concessions, games, décor, add-ons like generators or attendants).
- **Operating economics (for pricing):** delivery/setup fee or cost, typical labor/fuel/consumable cost per job, target margin, peak vs. off-peak days, any standard discounts.
- **Constraints:** items that can't combine (space/power), delivery limits, blackout/peak dates.

> Keep the profile as a separate input from this skill so the SKILL.md itself stays generic and shareable.

---

## Step 1 — Choose the package angle
Pick the organizing idea. If the user named one (e.g., "graduation package"), use it. Otherwise propose **2–3 timely angles** based on today's date, the service area's season, and a quick live trend search, then confirm. Angle options:
- **Event:** birthday, graduation, school carnival, church festival/VBS, corporate family day, grand opening, wedding/shower, block/HOA party, fundraiser.
- **Holiday/season:** summer kickoff, back-to-school, fall festival / trunk-or-treat, winter/holiday, spring/Easter, July 4th.
- **Theme:** princess, superhero, luau/tropical, glow/neon, sports, safari, candy/sweets, "winter wonderland," etc.
- **Audience:** toddlers, big kids, teens, all-ages community, adults/corporate.

## Step 2 — Research current trends (live)
Search for what's trending **now** for that angle: popular themes, color palettes, décor styles, and the kinds of packages competitors and event pages are featuring this season. Use it to inform theme, naming, and the ad look — don't copy anyone. Note 2–3 trend cues you'll lean on.

## Step 3 — Build the package from real inventory
Select complementary items from the profile into one cohesive offer. Check they physically combine (space/power) and are the right fit for the audience. **Avoid reusing the same inflatable unit that appeared in a recent/prior package** unless it is the single best thematic match for this angle — rotate through the operator's catalog to showcase variety. Then optionally structure it as **three tiers** so there's an entry point and an upsell:
- **Essential** (anchor unit + basics) · **Crowd-Pleaser** (mark "Most Popular") · **Showstopper** (premium/most complete).
Add **2–4 add-ons** (concessions, extra seating, attendant, themed décor, generator) as upsells. Keep tiers genuinely different in value, not just price.

## Step 4 — Name it
Give the package (and each tier) a catchy, themed, on-brand name — short, benefit- or theme-forward. Match the brand voice. Avoid clichés where a fresher line fits.

## Step 5 — Price it
Use this method and **show the math**:

1. **Component value (S):** sum the à-la-carte prices of everything included.
2. **Cost floor (C):** delivery/setup + labor/fuel + consumables + reasonable wear allowance. The price must clear `C + target margin`.
3. **Pick a pricing posture:**
   - **Value bundle** → price at `S × (1 − discount)` (default 10–15% off à-la-carte) so the bundle is obviously cheaper than booking separately. Drives bigger orders. Best for price-sensitive events.
   - **Experience bundle** → price at `S + service premium` when the package adds convenience/exclusivity (full setup, themed décor, attendant). Best for upscale/corporate/wedding.
4. **Demand adjustment:** hold firm or add a small premium for peak weekends/holidays; discount deeper off-peak or for weekday/last-minute fills.
5. **Make it attractive:** round to a clean psychological price (ends in 9 or 5), and frame the value — e.g., **"$420 value — yours for $349"** or **"Save $71 vs. booking separately."** For tiers, anchor with the Showstopper so the middle looks like the smart buy.
6. **Output** the recommended price for each tier, the value-framing line, and a one-line rationale. Add: *"Validate against your actual costs, margin target, and local rates before publishing."*

## Step 6 — Create the ad (finished asset)
Generate **both copy and visual(s)**, fully branded from the profile.

**Copy:** a benefit-driven headline/hook, the package name, a short "what's included" list, the price/offer line, a strong CTA ("Reserve your date — weekends fill fast"), and the business name + contact + booking link.

**Visual:** Scrape/download the operator's actual product images from their website or gallery. Use these real photos of their real equipment in the ad compositions — composited into an eye-catching, on-brand graphic with the package name, price/offer, CTA, logo, and brand colors. NEVER use generic stock photos or AI-generated images of equipment — only the operator's own product photos. Produce these sizes by default (ask if they want others):
- **1080×1080** square (Instagram/Facebook feed)
- **1080×1920** vertical (Stories/Reels/TikTok)
- **1200×628** banner (Facebook link / website)
- **8.5×11** printable flyer (community boards, schools, churches)

*If image generation isn't available in the environment, output a complete, paste-ready design brief (layout, colors, exact text, image direction) plus the copy, ready to drop into Canva or hand to a designer.*

**Caption:** a ready-to-post social caption matching the brand voice, with a clear CTA and 5–10 relevant, local + theme hashtags, plus a suggested best time/day to post.

## Step 7 — Deliver & iterate
Output the Package Brief + the ad assets + the caption, then offer revisions ("want a cheaper tier, a different theme, or other ad sizes?").

---

## Output format

**Package Brief**
- **Name / tiers:** …
- **Angle & theme:** event/holiday/theme + 2–3 trend cues used
- **Best for / season:** who it's for, when to push it
- **What's included** (per tier) + **add-ons/upsells**
- **Recommended price** (per tier) + **value framing** + **pricing rationale** + the validate-against-costs note

**Ad assets:** the generated visual(s) by size (or the design brief), the ad copy, and the social caption + hashtags + suggested post time.

---

## Templates

### Ad copy block
```
{{HOOK HEADLINE}}
Introducing the {{Package Name}} from {{Business Name}}!

Includes:
• {{item 1}}
• {{item 2}}
• {{item 3}}
{{+ add-on teaser}}

{{Price / offer line — e.g., "From $349 — a $420 value"}}
📅 {{CTA — Reserve your date, weekends fill fast}}
{{Phone}} · {{Booking link}} · Serving {{service area}}
```

### Social caption
```
{{Themed one-liner with personality}} 🎉
The {{Package Name}} is here — {{one benefit}}. {{Price/offer}}.
Book your date 👉 {{booking link}}
#{{LocalCity}}Parties #BounceHouse{{City}} #{{Theme}}Party #PartyRentals #{{relevant} #{{relevant}}
```

---

## Illustrative examples (pattern only — build from each provider's real inventory & live trends)
- **"Backyard Birthday Bash"** — themed bounce house + tables/chairs + concession machine; value bundle, ~12% off à-la-carte; bright kid-party ad.
- **"Trunk-or-Treat Takeover"** (church/school, Oct) — large combo + obstacle course + popcorn; experience bundle with setup; spooky-but-friendly ad.
- **"Grad Glow Party"** (May–Jun, teens) — glow/neon theme, slide + games + sound add-on; premium tier anchored; neon ad.
- **"Corporate Family Fun Day"** — multiple units + tents + attendant; experience pricing; clean, upscale ad.

---

## Sharing this skill
This SKILL.md is self-contained and provider-agnostic — share it as-is (or packaged as a `.skill` file / via the Manus skills library / GitHub import). Each new provider just supplies their own `business_profile`; the skill logic, pricing method, and ad workflow are identical for everyone.

## Optional bundled resources (add later)
- `references/theme_library.md` — expanded theme + color-palette ideas per event.
- `references/pricing_examples.md` — worked pricing examples by package type.
- `assets/ad_layouts.md` — reusable ad layout briefs per format.
