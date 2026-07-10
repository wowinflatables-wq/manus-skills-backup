---
name: competitor-watchtower
description: Run a recurring sweep of a rental company's named local competitors — pricing, unit availability, new inventory, and active promos — and report the gaps and moves worth making. Use this skill whenever the user wants to check on, track, compare against, or "keep an eye on" competitors; asks "what are my competitors charging / offering / running," "am I priced right vs. the market," "what units do they have that I don't," "who's running a promo," or "should I raise/drop my price on X"; or wants a periodic competitive pulse instead of a one-time study. It reads the operator's own inventory/pricing and the competitor list from a profile, so it's fully portable across providers. Trigger it any time competitive pricing, positioning, inventory gaps, or rival promotions come up — even if the skill isn't named.
---

# Competitor Watchtower — Recurring Competitive Pulse

Turns a one-time competitive analysis into a **repeatable radar**. Point it at your named local competitors and it sweeps their public info for pricing, availability, new inventory, and promos, then tells you the three things that make money: **where you're underpriced, what units they have that you don't, and where to undercut or hold.** Built to be **shared with any provider** — the competitor list and your own numbers come from a profile.

## Principles
1. **Portable by design.** Read the operator's inventory/pricing and the competitor set from a `business_profile`. Nothing company-specific is hardcoded. If missing, ask before sweeping.
2. **Public sources only.** Use public websites, booking pages, public social posts, and public listings. Never scrape behind logins, fake a booking, or attempt to defeat access controls. If a price is only visible via a real quote flow, note it as "quote-gated," don't fabricate it.
3. **Gaps over gossip.** The output is decisions — reprice, add inventory, launch a counter-promo — not a wall of competitor facts.
4. **Grounded in your own economics.** Compare against the operator's real prices and costs from the profile, and remind them to protect margin, not just match a number.
5. **Recurring by default.** Designed to run on a cadence and report **what changed since last time**, so it's a pulse, not a snapshot.
6. **Play clean.** Compete on price, inventory, and service — never advise deception, review manipulation, or disparaging competitors publicly.

---

## First-run setup — the `business_profile`

Collect once and reuse:

- **Your side:** business name, service area, your full inventory with **your à-la-carte prices**, your delivery/setup fees, target margin, current promos, peak vs. off-peak days.
- **Competitor set:** 3–8 named local competitors with their website and public social links. Note each one's rough positioning if known (budget / mid / premium).
- **What to watch:** the units/categories you care most about (e.g., water slides, big combos, obstacle courses, concessions), and your must-win keywords/service towns.
- **Cadence:** how often to sweep (weekly, biweekly, monthly, or seasonal spike).

> Keep the profile separate from this SKILL.md so the skill stays generic and shareable.

---

## Step 1 — Confirm scope
Confirm the competitor set, the categories to watch, and whether this is a **baseline** run (first time) or a **delta** run (compare to the last sweep). If it's the first run, say so — there's nothing to diff against yet, so it becomes the baseline.

## Step 2 — Sweep each competitor (live, public)
For each competitor, gather from public pages:
- **Pricing** on comparable units (match by type/size, not just name); note quote-gated items.
- **Inventory:** units they list — flag anything they carry that the operator's profile doesn't.
- **Availability signals:** "booked/unavailable" markers, seasonal units live now, sold-out dates if shown.
- **Promos/offers:** active discounts, bundles, seasonal specials, delivery-fee deals, referral offers.
- **Positioning cues:** delivery area, minimums, add-ons, guarantees, anything they lead with.

Record source + date for each so the next run can diff it.

## Step 3 — Compare to the operator
Line each comparable unit up against the operator's own price and inventory:
- **Price position:** for each watched unit, is the operator **below / at / above** the market, and by how much?
- **Inventory gaps:** units competitors have that the operator doesn't (demand the operator may be turning away).
- **Inventory advantages:** units the operator has that competitors lack (lean into these in marketing).
- **Promo exposure:** where a competitor's active offer could pull the operator's bookings.

## Step 4 — Turn it into moves
Produce a short, ranked action list, each with a one-line rationale grounded in the numbers:
- **Reprice:** raise where the operator is leaving money on the table; hold or sharpen where a competitor undercuts; note the margin implication.
- **Add inventory:** the 1–3 gap units most worth acquiring, with the demand signal behind each.
- **Counter-promo:** a specific response to a live competitor offer (match, beat, or differentiate on service/inclusions instead of price).
- **Message:** advantages to feature in listings/ads right now.

Every pricing move carries the reminder: *validate against your real costs and margin before changing published prices.*

## Step 5 — Report deltas (on recurring runs)
On a delta run, lead with **what changed** since last sweep: new units, price moves, new/expired promos, availability shifts — then the updated action list. Keep the full data underneath for reference.

## Step 6 — Deliver & schedule
Output the report, then offer to set the next sweep on the profile's cadence (if scheduling is available) and to draft any repricing update or counter-promo copy (hand off to the package skill for a full promo build).

---

## Output format

**Watchtower Report — {{date}}** ({{baseline / delta since {{last date}}}})

**Headline moves (ranked)**
1. {{move}} — {{one-line rationale + $ impact}}
2. …

**Price position** (per watched unit)
- {{Unit}}: You {{$}} vs. market {{low–high}} → {{below/at/above}} → {{action}}

**Inventory gaps & advantages**
- Gaps to consider adding: {{units}} — {{demand signal}}
- Your advantages to feature: {{units}}

**Active competitor promos**
- {{Competitor}}: {{offer}} → {{suggested response}}

**What changed since last sweep** (delta runs only)
- {{new units / price moves / promo changes}}

*Sources & dates checked listed under each item. Validate pricing against your costs before publishing.*

---

## Templates

### Per-unit comparison row
```
Unit: {{type/size}}
  You: {{$}} ({{margin note}})
  {{Comp A}}: {{$ or quote-gated}}  |  {{Comp B}}: {{$}}  |  {{Comp C}}: {{$}}
  Market range: {{low}}–{{high}}
  Position: {{below/at/above}} by {{$/%}}
  → Action: {{raise to $X / hold / sharpen / feature}}  ({{rationale}})
```

### Counter-promo brief (hand to package skill to finish)
```
Trigger: {{Competitor}} is running {{offer}} until {{date}}.
Our response: {{match / beat / differentiate on inclusions}}
Offer: {{what we put out}}
Guardrail: keeps us above {{cost floor}} — margin ~{{%}}.
Push to: {{audience/segment}} · {{channel}}
```

---

## Illustrative examples (pattern only — build from the operator's real list & live data)
- **Underpriced water slide** — operator at $X, market $X+40 → recommend raise, ~$40/job upside on a high-volume unit.
- **Gap: 40-ft obstacle course** — two competitors list one, operator doesn't; steady inquiries suggest a real acquisition case.
- **Competitor free-delivery weekend** — recommend a differentiated counter (bundle a concession instead of eating delivery margin).
- **Delta run** — competitor quietly dropped combo prices 10% and added a foam unit; flagged both with responses.

---

## Sharing this skill
Self-contained and provider-agnostic — share as-is (or as a `.skill` file / via the Manus skills library / GitHub import). Each provider supplies their own inventory and competitor set; the sweep logic and reporting are identical for everyone. (Great live demo for teaching new operators — everybody wants this one.)

## Optional bundled resources (add later)
- `references/unit_matching.md` — how to match comparable units across differently-named catalogs.
- `references/pricing_position_guide.md` — when to raise vs. hold vs. differentiate.
- `assets/report_template.md` — reusable report layout for baseline and delta runs.
