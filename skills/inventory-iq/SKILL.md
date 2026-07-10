---
name: inventory-iq
description: Analyze a bounce house / party rental company's bookings to recommend which unit to buy (or retire) next, with ROI and payback math. Use this skill whenever the user wants to know what to invest in, which inflatable to buy next, whether a unit is worth it, how their inventory is performing, what they're missing, or how to spend a growth budget. Trigger it whenever purchasing decisions, inventory analysis, utilization, ROI/payback, "what should I buy," turned-away demand, or retiring underperformers come up — even if the skill isn't named. It turns booking data into a ranked buy-next recommendation grounded in the company's own numbers.
---

# Inventory IQ — Buy the Right Unit Next

Capital is your scarcest resource; this skill spends it wisely. It reads your booking history, scores every unit you own, finds the demand you're leaving on the table, and produces a ranked "buy next" recommendation with payback math. Portable via a shared `business_profile`.

## Principles
1. **Decide from data, not gut.** Recommendations come from the company's actual bookings, revenue, and demand signals.
2. **Lost demand is the loudest signal.** A unit that's booked solid every Saturday — with requests you had to turn away — is screaming "buy another." Track turn-aways relentlessly.
3. **Payback drives the ranking.** Rank candidates by how fast they pay for themselves, adjusted for strategic fit and seasonality.
4. **Honest estimates.** Projections depend on real local demand and costs; present them as informed recommendations to validate, not guarantees.

## Inputs (from `business_profile` + booking data)
Booking history (units, dates, revenue, occasion); current inventory with acquisition cost, operating/maintenance cost, and footprint; **turn-away / unmet-request log** if kept (dates a unit was fully booked or a non-owned item was requested); growth budget; target payback period; seasonality of the market. Accepts a **CSV export** from the reservation system if available.

## Workflow

### 1. Score the current fleet (utilization)
Per unit, compute: bookings count, total revenue, **revenue per unit**, **utilization rate** (booked days ÷ available days, weighted to peak weekends), and trend over time. Rank workhorses vs. idle units. Flag chronic underperformers as retire/sell candidates (free up cash and storage).

### 2. Find the unmet demand
Quantify lost bookings: dates a popular unit was fully booked with additional requests, and **requests for items you don't own** (themes/sizes/categories customers asked for). Convert to estimated **lost revenue** ("~14 turned-away castle requests on summer Saturdays ≈ $X"). This is the strongest buy signal.

### 3. Gap & trend analysis
Compare your lineup to demand and seasonal patterns — common gaps: a second copy of a sold-out workhorse, water slides for summer, combo units, toddler/soft-play for the under-5 crowd, obstacle courses, interactive games, concessions. Note seasonality so the recommendation accounts for when the unit earns.

### 4. Model ROI / payback per candidate
For each buy candidate: `annual contribution = expected annual bookings × avg price − annual operating cost`; `payback (months) = unit cost ÷ (annual contribution ÷ 12)`. Base the bookings estimate on observed demand (turn-aways, comparable-unit utilization). State assumptions plainly.

### 5. Recommend
Output a **ranked buy-next list**: unit, why (the demand evidence), estimated payback, expected utilization, **best time to buy** (before its peak season), and rough budget fit. Note any underperformers to retire. End with: *"Projections use your historical demand — validate against current quotes and local market before purchasing."*

### 6. Sharpen future analysis
If turn-aways aren't being tracked, recommend logging them going forward (date, requested unit, reason) — it makes the next analysis far more accurate. (Quote Rocket can capture these.)

---

## Output format
1. **Fleet performance table** — unit, bookings, revenue, revenue/unit, utilization, rank.
2. **Unmet-demand summary** — turn-aways + non-owned requests → estimated lost revenue.
3. **Buy-next recommendation** — ranked, with payback math, timing, and budget fit.
4. **Retire/sell flags** — underperformers, with reasoning.

## Example output shape
```
FLEET (last 12 mo)
Unit                 Bookings  Revenue  Util%  Rank
Castle Bounce A         48      $7,200   86%    ★ workhorse (often sold out)
Combo Slide             31      $6,975   61%    strong
Toddler Soft Play        6      $  540   11%    underperformer → consider retiring

UNMET DEMAND
• Castle: ~14 turned-away requests on summer Saturdays ≈ $2,100 lost
• Water slide: 22 requests, 0 owned ≈ $4,000+ lost in Jun–Aug

BUY NEXT
1. 2nd Castle Bounce — payback ~5 mo — buy before May. Demand proven, sells out.
2. Water Slide (dual-lane) — payback ~7 mo — buy by April for summer.
Retire: Toddler Soft Play (11% util) — sell, redeploy cash.
```

## Guardrails
- Recommendations are data-informed, not guaranteed; depend on real demand, costs, and local market. • This is business analysis, not financial advice — the operator owns the decision. • Be explicit about assumptions.

## Sharing
Provider-agnostic — analyzes any company's `business_profile` + booking data (CSV or connected system). Share as-is or as a `.skill`.
