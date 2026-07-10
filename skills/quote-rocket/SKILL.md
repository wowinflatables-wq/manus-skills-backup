---
name: quote-rocket
description: Turn any incoming rental inquiry into a fast, accurate, ready-to-send quote for a bounce house / party rental business. Use this skill whenever the user pastes or forwards a customer inquiry, asks to "quote this," "reply to this lead," "price this party," "how much would I charge for…," or wants a fast response to someone asking about availability, units, or cost — even a vague one like "do you have a princess castle for the 14th?" It parses the request, checks availability, recommends the right unit(s), calculates delivery + add-ons + deposit, and writes a polished customer-ready message. Speed-to-lead wins bookings, so trigger this on any inbound inquiry or quoting request, even if the skill isn't named.
---

# Quote Rocket — Inquiry-to-Quote in Minutes

Whoever replies first with an accurate, friendly quote usually wins the booking. This skill takes a raw inquiry and produces a polished, ready-to-send quote plus a quick internal cheat-sheet for the operator. Portable: all business specifics come from a shared `business_profile`.

## Principles
1. **Fast beats perfect.** Always produce a usable reply now; if a detail is missing, give a clear ballpark and ask one or two quick questions rather than stalling.
2. **Accurate and honest.** Quotes are estimates pending availability confirmation. Never promise a unit you can't verify is free, and never hide fees — itemize them.
3. **Right-size the unit.** Match the recommendation to guest count, ages, space, power, and surface — safety and fit, not just upselling.
4. **Always be closing (gently).** End every quote with the deposit/booking link and a date-hold nudge.

## Inputs (from `business_profile`)
Inventory with à-la-carte prices, capacities, ages, footprint (L×W×H) and power needs; delivery-fee rule (flat or per-mile + free radius); deposit terms; tax/surcharges (stairs, long carry, generator, park permit, attendant, overnight); service area; min order; booking link; brand voice; business name + contact. Availability source (reservation system if connected, otherwise flag "verify date").

## Workflow

### 1. Parse the inquiry
Extract: event date(s) + time, location/ZIP, indoor/outdoor, **surface** (grass / concrete / asphalt / indoor), **power access** (outlet within ~100 ft? else generator), guest count + age range, requested unit/theme, and any constraints (gate width, stairs, HOA/park). Note what's missing.

### 2. Fill the gaps
If a **critical** detail is missing (date, location, surface/power), still give a ballpark and ask up to **two** crisp questions to finalize. Don't interrogate — a quote with one open variable beats a delayed perfect one.

### 3. Check availability
Confirm the requested date against the calendar (or mark "pending availability — I'll confirm your date the moment you're ready"). Never quote a unit as guaranteed without this.

### 4. Recommend the right unit(s)
Pick the best fit by guest count, ages, space, surface, and power. Note the footprint vs. their space, the anchoring method (stakes on grass / weights on hard surface), and flag if a generator is needed. Suggest **one** sensible add-on/upsell (concession, extra unit, attendant) — not a pile.

### 5. Price it (show the line items)
`Rental(s)` + `Delivery fee` (by distance rule) + `Add-ons` + `Surcharges` (stairs/generator/permit) + `Tax` = **Total**. Then `Deposit due to book` (per terms) and `Balance due before/at delivery`. Round cleanly; never bury a fee.

### 6. Write the reply
Produce a warm, on-brand customer message (email or text per how they contacted) with: a quick thank-you, the recommended unit and why it fits, an itemized price, what's included (delivery, setup, takedown), the deposit + booking link, a date-hold line, and an easy CTA. Keep it skimmable on a phone.

### 7. Hand the operator a cheat-sheet
A 4–6 line internal summary: parsed details, date availability to confirm, recommended unit + alternative, distance/fee math, upsell suggested, and anything to verify (surface/power/access).

---

## Output format
1. **Customer-ready quote** (email or text).
2. **Internal cheat-sheet** (availability to confirm, math, flags, upsell).
3. If info was missing: the **1–2 questions** to ask, already worked into the message.

## Templates

### Email quote
```
Subject: Your {{event_date}} party quote from {{business_name}} 🎉

Hi {{name}}, thanks for reaching out!

For ~{{guest_count}} kids ages {{ages}} on {{event_date}}, I'd recommend our
{{unit}} — {{one-line why it fits}}. It needs about {{footprint}} of {{surface}}
and an outlet within ~100 ft ({{generator note if needed}}).

Here's your quote:
• {{unit}} (full-day rental) ............ ${{x}}
• Delivery, setup & takedown ........... ${{y}}
{{• Add-on / surcharge ................. ${{z}}}}
• Tax .................................. ${{t}}
  Total ............................... ${{total}}

A ${{deposit}} deposit holds your date; balance due {{terms}}.
Reserve here 👉 {{booking_link}}

Dates for {{month}} are filling up — want me to hold {{event_date}} for you?

{{sender_name}} · {{business_name}} · {{phone}}
```

### Text quote
```
Hi {{name}}! For {{event_date}}, the {{unit}} would be perfect for {{guest_count}}
kids. All-in it's ${{total}} (delivery + setup included). ${{deposit}} holds the
date: {{booking_link}}. Want me to lock it in? — {{business_name}}
```

### No-response follow-up (send ~24–48h later)
```
Hi {{name}}, just making sure you got the quote for {{event_date}}! Happy to
adjust the unit or answer questions. The date's still open if you'd like it. 🎈
```

## Guardrails
- Estimates only until the date is confirmed in the calendar. • Itemize every fee. • Flag surface/power/space so there are no setup surprises (a unit that won't fit or can't be anchored is a safety issue, not just an inconvenience). • Don't over-upsell.

## Sharing
Self-contained and provider-agnostic — share as-is or as a `.skill`. Each provider supplies their own `business_profile`.
