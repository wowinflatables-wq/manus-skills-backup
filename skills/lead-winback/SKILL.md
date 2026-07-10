---
name: lead-winback
description: Recover quotes that never converted with a timed, personalized multi-touch win-back sequence (text + email) that handles objections and offers a re-quote or a small sweetener. Use this skill whenever the user has quotes, leads, or inquiries that went cold or "ghosted"; wants to follow up on, revive, chase, or "win back" a lead; asks "how do I get this quote to convert," "they never replied," "follow up on my open quotes," or "recover lost bookings"; or wants to turn a list of un-booked quotes into outreach. It reads the operator's offers, tone, and booking link from a profile, so it's fully portable across providers. This is for people who got a quote and didn't book — distinct from re-engaging past customers. Trigger it any time cold quotes, un-converted leads, ghosted inquiries, or follow-up sequences come up — even if the skill isn't named.
---

# Lead Win-Back — Recover the Quotes That Ghosted

The single highest-ROI automation most operators aren't running. People who **got a quote and didn't book** already wanted what you sell — they got distracted, price-shopped, or froze. This skill runs a **timed, personalized, multi-touch sequence** that handles the real objection, offers a re-quote or a small sweetener, and closes the date. Built to be **shared with any provider** — offers, voice, and links come from a profile.

> **Scope note:** This is for **un-converted quotes/leads** (got a price, never booked). Re-engaging *past customers* for repeat business is a different motion — hand that to the rebooking skill.

## Principles
1. **Portable by design.** Read offers, brand voice, booking link, and sweetener rules from a `business_profile`. Nothing company-specific is hardcoded. If missing, ask before sending.
2. **Personal, not blast.** Each touch references *their* event, date, and unit. Generic "just following up" gets ignored; "still holding {{date}} for your {{event}}?" gets a reply.
3. **Objection-first.** Most ghosts have a reason — price, date uncertainty, comparison shopping, decision-maker delay. Diagnose the likely one and speak to it.
4. **Timed and finite.** A short sequence (typically 3–4 touches over ~7–10 days), then a clean stop. No pestering — persistence with a deadline, not harassment.
5. **Protect margin on sweeteners.** Sweeteners come from a profile-set list (free delivery within radius, a small add-on, a modest % off) with a floor. Never discount below the operator's guardrail; prefer added value over price cuts.
6. **Compliant and respectful.** Honor opt-outs immediately, keep texting within reasonable hours, include identification, and stop the sequence the instant they reply or book. Follow local SMS/email consent norms.

---

## First-run setup — the `business_profile`

Collect once and reuse:

- **Voice & identity:** business name, brand voice (playful/warm/pro), signature, phone, **booking link**, service area.
- **Offer levers / sweeteners:** the approved list and limits — e.g., free delivery within X miles, a free upgrade or small add-on, up to Y% off, weekday incentive. Include the **margin floor** below which nothing goes.
- **Objection playbook inputs:** typical price band, top differentiators (clean units, insured, reliable, reviews), booking/deposit terms, cancellation policy, availability pressure (how fast weekends fill).
- **Channels & rules:** SMS and/or email available, allowed contact hours, opt-out handling, how many touches max.

> Keep the profile separate from this SKILL.md so the skill stays generic and shareable.

---

## Step 1 — Load the cold quotes
Take the list of un-converted quotes/leads with, ideally: name, contact + channel, **event type**, **requested date**, **unit(s) quoted**, **quoted price**, **date quoted / last contact**, and any notes on why they hesitated. If a reservation system is connected, pull open/expired quotes automatically. If a lead is missing key fields, note the gap rather than guessing.

## Step 2 — Segment & diagnose
Sort leads and infer the **likely objection** for each from the notes and pattern:
- **Price-sensitive** (asked about cost, compared) → lead with value + a sweetener.
- **Date-uncertain** (event date soft) → offer a courtesy hold / flexible booking.
- **Comparison-shopping** (multi-quoting) → lead with differentiators + availability pressure.
- **Decision-delay** (waiting on a spouse/committee) → make it easy to forward + a soft deadline.
- **Went quiet, no signal** → friendly re-open, low pressure.
Also flag **stale** leads whose event date has already passed → route to a *future-event* or rebooking angle instead.

## Step 3 — Build the sequence per lead
Draft a finite, personalized sequence. A solid default:
- **Touch 1 (day 0–1):** warm, specific re-open. Reference their event/date/unit. "Still want me to hold {{date}}?" One clear CTA.
- **Touch 2 (day 3–4):** address the diagnosed objection directly + one differentiator or a light availability nudge.
- **Touch 3 (day 6–7):** the sweetener (from the profile's approved list, above the floor) + a soft deadline tied to real date fill.
- **Touch 4 (day 9–10, optional):** graceful last call — "closing out your quote, want me to keep the date or let it go?" Leaves the door open.
Match channel to the lead (text for speed, email for detail), keep each touch short, and end the sequence immediately on reply/booking.

## Step 4 — Arm objection responses
For each lead, provide 2–3 ready replies to the likely pushback (too expensive, still deciding, found cheaper, date changed), each in brand voice, each moving toward a booked date — with the sweetener held in reserve, not led with.

## Step 5 — Re-quote when it helps
Where the original quote is the blocker, generate a **refreshed quote** — same date if open, or the nearest available — optionally restructured as a tiered/value bundle (hand to the package skill for a full build) so the customer sees a better-fitting option, not just a nag.

## Step 6 — Deliver, schedule, and track
Output the per-lead sequences + objection replies + any re-quotes. If scheduling/sending is available, queue the touches on the timeline and **auto-stop on reply/booking/opt-out**. Provide a simple tracker (lead → stage → next touch date → outcome) and offer to report win-back results after the cycle.

---

## Output format

**Win-Back Batch — {{date}}** ({{N}} cold quotes)

**Segments**
- Price-sensitive: {{n}} · Date-uncertain: {{n}} · Shopping: {{n}} · Delay: {{n}} · Quiet: {{n}} · Stale→reroute: {{n}}

**Per lead**
- **{{Name}}** — {{event}} · {{date}} · {{unit}} · quoted {{$}} · diagnosed: {{objection}}
  - Touch 1 ({{channel, day}}): {{copy}}
  - Touch 2: {{copy}}
  - Touch 3 (+sweetener {{which, within floor}}): {{copy}}
  - Touch 4 (last call): {{copy}}
  - Objection replies: {{2–3 ready responses}}
  - Re-quote: {{if applicable}}

**Tracker** — lead → stage → next touch → outcome. **Auto-stop on reply/booking/opt-out.**

---

## Templates

### Touch 1 — warm re-open (SMS)
```
Hi {{Name}}, it's {{Business Name}} 👋 Still thinking about the {{unit}}
for your {{event}} on {{date}}? I can hold that date for you — want me to?
{{booking link}}
```

### Touch 3 — sweetener (SMS/email)
```
Hi {{Name}} — {{date}} is still open for your {{event}}, but weekends are
filling. Book by {{soft deadline}} and I'll include {{approved sweetener}}.
Lock it in here: {{booking link}} — or reply and I'll set it up.
```

### Objection reply — "found it cheaper"
```
Totally get comparing! A few things folks book us for: {{differentiator 1}},
{{differentiator 2}}, fully insured, and units that show up clean and on time.
Happy to make the value line up — want me to {{re-quote / add {{sweetener}}}}?
```

### Touch 4 — graceful last call
```
Hi {{Name}}, closing out your quote for {{date}}. Want me to keep holding it,
or release it for someone else? No worries either way — just let me know 🙂
```

---

## Illustrative examples (pattern only — use the operator's real offers & voice)
- **Price-sensitive birthday quote** — 3 touches, sweetener = free delivery within radius (above floor); books on touch 3.
- **Comparison-shopper** — lead with insured + clean-unit differentiators + "weekends filling"; no discount needed.
- **Committee/church decision-delay** — email built to forward + a soft deadline; re-quote as a value bundle.
- **Event date already passed** — rerouted to rebooking skill for their next event, not chased on the dead date.

---

## Sharing this skill
Self-contained and provider-agnostic — share as-is (or as a `.skill` file / via the Manus skills library / GitHub import). Each provider supplies their own offers, voice, and links; the sequencing, objection handling, and compliance rules are identical for everyone.

## Optional bundled resources (add later)
- `references/objection_playbook.md` — expanded responses by objection type.
- `references/sequence_timings.md` — cadence variants by event lead time and season.
- `assets/sms_email_templates.md` — full touch library per channel and segment.
