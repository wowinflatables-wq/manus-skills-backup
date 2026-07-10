---
name: rebooking-radar
description: Win repeat bookings by automatically nudging last year's bounce house / party rental customers before their occasion comes around again. Use this skill whenever the user wants to follow up with past customers, win repeat business, reactivate old clients, find who's "due" to rebook, or remind people whose kid's birthday (or annual church/school/corporate event) is coming up again. Trigger it whenever repeat customers, rebooking, anniversaries, "who rented last year," customer retention, or reactivation come up — even if the skill isn't named. Every kid has a birthday every year; this skill makes sure last year's customer hears from you first.
---

# Rebooking Radar — Annual Repeat-Customer Reactivation

The cheapest booking is the one from a customer you already delighted. This skill scans last year's bookings, finds who's coming up on their annual occasion, and drafts a personal nudge timed to land before they book elsewhere — or forget. Portable via a shared `business_profile`.

## Principles
1. **Anniversaries are predictable revenue.** Birthdays, church festivals, school carnivals, company picnics, and HOA July-4th parties recur on roughly the same date every year. Reach out *before* that date.
2. **Warm, personal, specific.** Reference exactly what you did last year — the unit, the theme, the child's name. This isn't cold outreach; it should feel like a friend remembering.
3. **Beat the calendar.** Nudge early enough that prime dates aren't gone (default ~5–6 weeks before the anniversary).
4. **Respect the relationship.** Honor opt-outs, don't over-contact, and follow CAN-SPAM on email (real address + working unsubscribe). Review the batch before it sends.

## Inputs (from `business_profile` + booking history)
Past bookings: customer name, contact + preferred channel, **last event date**, occasion type, child name/age (if known), unit(s) + theme rented, amount spent, satisfaction/notes. Plus brand voice, booking link, business name + **postal address** (for email compliance), and any **returning-customer offer** (e.g., "10% off for coming back").

## Workflow

### 1. Build the radar
From booking history, compute each customer's **nudge date** = last year's event date − lead time (default 35–42 days; configurable). Surface everyone whose nudge date falls in the chosen window (e.g., "next 30 days").

### 2. Segment
- **VIPs / high-spend / multi-year repeats** — priority, warmest tone, best offer.
- **One-time customers** — standard nudge.
- **Lapsed** (rented two+ years ago, skipped last year) — a "we miss you" win-back angle.
- Tag occasion type so the message fits (birthday vs. annual fall festival vs. corporate picnic).

### 3. Personalize the nudge
Reference last year specifically and, for birthdays, advance the child's age ("Mia must be turning 6!"). Include the returning-customer offer if provided, the booking link, and a date-hold line. Match channel to preference (text for some, email for others).

### 4. Review, then send
Present the batch for the operator's quick approval. On approval, send through the right channel, honoring opt-outs. (Drafts only until approved.)

### 5. Follow up once
If no response after ~7 days, one friendly bump, then stop. Stop immediately on a reply, booking, or opt-out.

### 6. Track reactivation
Log nudged → responded → rebooked, and report the reactivation rate and revenue recovered. Feed opt-outs into the suppression list and hand new bookings to the reservation system.

---

## Output format
1. **Radar list** — table: customer, occasion, last year's date + unit/theme, this year's nudge date, segment, channel.
2. **Drafted nudges** — one personalized message per customer, ready on approval.
3. **Tracking note** — who's pending, reactivation rate, revenue recovered.

## Templates

### Birthday rebooking (text)
```
Hi {{name}}! Can you believe it's almost been a year since we brought the {{unit}}
for {{child}}'s birthday? 🎉 {{child}} must be turning {{age+1}}! Want me to hold
{{this year's date}} before our {{month}} weekends fill up? {{offer}} 🎈
Book here: {{booking_link}} — {{business_name}}
```

### Annual event rebooking (email)
```
Subject: Time to plan {{org/event}} again? 🎉

Hi {{name}}, this time last year we brought the {{unit}} out for your
{{event}} — it was a great one! That date tends to book early, so I wanted to
reach out before it's spoken for. {{returning_offer}} I'd love to do it again.
Reserve your date 👉 {{booking_link}}
{{business_name}} · {{phone}} · {{postal_address}} · Unsubscribe: {{optout_link}}
```

### Win-back (lapsed)
```
Hi {{name}}, we've missed bouncing with your family! It's been a bit — if you've
got a party coming up, I'd love to bring back the fun (and {{welcome-back offer}}).
{{booking_link}} 🎈 — {{business_name}}
```

## Guardrails
- Use real booking history only. • CAN-SPAM on email (address + honored opt-out). • Review batch before sending; don't over-contact; stop on reply/booking/opt-out. • Keep it warm and personal, not salesy.

## Sharing
Provider-agnostic — runs on any company's `business_profile` + booking history. Share as-is or as a `.skill`.
