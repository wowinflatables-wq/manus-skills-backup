---
name: permit-coi-concierge
description: Research the permit, insurance, power, and anchoring rules for any specific delivery address before an event — then generate the certificate-of-insurance (COI) request and a venue-ready compliance packet. Use this skill whenever the user is booking or prepping a delivery to a park, school, church, HOA, city property, fairground, or unfamiliar venue and needs to know "are we allowed to set up here, and what do they require"; whenever a customer or venue asks for a COI / additional-insured cert / permit; or whenever the user says things like "does this park allow bounce houses," "do we need a permit for," "they're asking for insurance," "what are the rules at," or "can we stake at." It reads business and insurance details from a profile, so it's fully portable across providers. Trigger it any time a delivery location's legal, insurance, or setup requirements are in question — even if the skill isn't named.
---

# Permit & COI Concierge — Venue Compliance Before You Roll

Kills the "we showed up and they wouldn't let us set up" nightmare. For any specific delivery address, this skill autonomously researches the venue's permit rules, power/generator restrictions, anchoring/staking requirements, and insurance demands, then produces the two things that actually prevent a cancelled setup: a ready-to-send **COI request** for your carrier and a **venue compliance packet** for the customer. Built to be **shared with any provider** — nothing is hardcoded; it all comes from a profile.

## Principles
1. **Portable by design.** Read all business/insurance data from a `business_profile`. Never assume a specific company's carrier, coverage, or units. If the profile is missing, ask before researching.
2. **Address-specific, not generic.** Rules change block to block — a city park, a school, and an HOA clubhouse have different owners and different requirements. Research the *actual* location, not "parks in general."
3. **Live research, cited.** Browse the venue's, city's, and parks department's real pages at run time and note where each requirement came from, with the date checked. Rules change; a stale answer is a cancelled job.
4. **Flag the deal-breakers loudly.** Stake bans on turf/pavement, no-generator zones, weight limits, hard permit lead times — surface these first and clearly, because they change what you can even deliver.
5. **Finished documents, not advice.** Output the COI request and the compliance packet as paste-ready assets, not a summary of what to do.
6. **Not legal advice.** This narrows and drafts; the operator and their agent confirm coverage and legality before committing.

---

## First-run setup — the `business_profile`

Collect once and reuse. Pull from a connected system if possible; otherwise ask:

- **Identity:** business name, contact, service area, booking/website link.
- **Insurance:** carrier name, agent name + email/phone, policy number, general liability limits (per-occurrence / aggregate), whether the policy allows adding an **additional insured** and **waiver of subrogation**, typical turnaround time for a COI, participant/medical coverage if any.
- **Equipment realities:** which units are **stake-anchored** vs. **sandbag/weight-anchored**, generator inventory and wattage, power needs per unit, footprint/weight of largest units.
- **Operating limits:** max delivery radius, blackout dates, lead time you need to pull a permit or COI.

> Keep the profile separate from this SKILL.md so the skill stays generic and shareable.

---

## Step 1 — Capture the job
Get: **delivery address**, **venue type** (public park / school / church / HOA / city facility / fairground / private residence / commercial lot), **event date & times**, the **specific units** being delivered, and **who's asking** (customer only, or a venue/facility contact with requirements). If it's a private backyard with no third party involved, say so — most of this skill won't apply, and skip to a short anchoring/power sanity check.

## Step 2 — Identify the authority
Determine who actually controls the site and its rules: city parks & rec department, county, school district facility-use office, HOA/property manager, church office, fairground authority, or a private venue coordinator. This is the single most important step — the requirements live with the owner, not the map pin.

## Step 3 — Research requirements (live, cited)
Browse the relevant official pages and gather, for this specific location:
- **Permit / reservation:** is one required for inflatables or amplified events? What's the **lead time**, cost, and who files it (operator vs. renter)? Application link.
- **Insurance:** required limits, whether the venue must be named **additional insured**, whether a **COI** or hold-harmless is required, and where to send it.
- **Anchoring:** stakes allowed? Depth limits? Utility-locate (811) needed? Any **no-stake** surfaces (turf fields, pavement, irrigation zones) that force **water/sandbag weights** instead?
- **Power:** are outlets available/permitted, or are **generators required**? Any generator bans, noise limits, or fuel restrictions?
- **Logistics constraints:** access/gate hours, vehicle-on-grass rules, setup windows, attendant requirements, capacity/occupancy caps, alcohol or food-truck interactions that affect permitting.

Record each requirement with its source and the date checked. If the official page is unclear or missing, note it as **"confirm with [authority] — phone/email"** rather than guessing.

## Step 4 — Reconcile against your equipment
Cross-check findings against the profile: if the site bans stakes but the booked unit is stake-only, **flag the mismatch** and recommend a weight-anchored substitute or added sandbag/water-weight kit. If no power and no generator listed, flag the generator need. If permit lead time exceeds days-until-event, flag the timeline risk **now**.

## Step 5 — Generate the COI request
Draft a ready-to-send email/message to the operator's insurance agent requesting the certificate, using the template below, pre-filled from the profile and job. Include exactly what the venue asked for (additional insured wording, limits, certificate holder name/address, waiver of subrogation if required) and the date needed.

## Step 6 — Generate the venue compliance packet
Produce a clean, customer- and venue-facing document that proves you've done the homework: venue + date, the requirements found (with sources), the permit status/next step and who's responsible, the anchoring & power plan for this site, and the COI status. This is what you send the facility contact to get the green light.

## Step 7 — Deliver, flag, and set reminders
Lead with any **deal-breakers or deadlines**. Then output the packet + COI request. Offer to draft the permit application text, produce a version for a different unit, or (if scheduling is available) set reminders for permit-file-by and COI-send-by dates.

---

## Output format

**Compliance Summary (top-of-response)**
- **Verdict:** ✅ clear to set up / ⚠️ conditions to meet / ⛔ blocked or high-risk — one line why.
- **Deadlines:** permit file-by, COI send-by (with days remaining).

**Requirements Found** (each with source + date checked)
- Permit/reservation · Insurance/COI · Anchoring · Power/generator · Access & other constraints.

**Equipment Reconciliation**
- Any unit/site mismatches + recommended fix.

**Assets**
- **COI request** (paste-ready to agent) · **Venue compliance packet** (paste-ready to customer/venue).

---

## Templates

### COI request to agent
```
Subject: COI needed — {{Event Date}} — {{Venue Name}}

Hi {{Agent Name}},

Please issue a certificate of insurance for an upcoming rental:

• Policy: {{Policy #}} — {{Business Name}}
• Event date: {{Date}}, {{Times}}
• Venue / certificate holder: {{Venue legal name}}
   {{Venue address}}
• Requirements from the venue:
   - Limits: {{e.g., $1M per occurrence / $2M aggregate}}
   - Additional insured: {{Yes/No — exact wording if given}}
   - Waiver of subrogation: {{Yes/No}}
• Send certificate to: {{venue email / operator}}
• Needed by: {{Date}}

Thanks,
{{Business Name}} · {{Contact}}
```

### Venue compliance packet
```
{{BUSINESS NAME}} — Setup Compliance Packet
Venue: {{Venue Name}} · {{Address}}
Event: {{Date}} · {{Times}} · Units: {{list}}
Prepared: {{today}}

1. Authority: {{parks dept / district / HOA / venue}} — {{contact}}
2. Permit: {{required? lead time? who files? status}} — source: {{link}}
3. Insurance/COI: {{limits, additional insured, where to send, status}}
4. Anchoring plan for this site: {{stakes OR weights — why}}
5. Power plan: {{outlets OR generator — noise/fuel notes}}
6. Access & timing: {{gate hours, setup window, vehicle rules}}
7. Open items to confirm: {{anything unverified — who to call}}

Questions: {{phone}} · {{email}}
```

---

## Illustrative examples (pattern only — always research the real address)
- **City park, youth field** — turf ban on stakes → recommend water-weight kit; park permit needs a week lead time; COI must name the city as additional insured. Verdict ⚠️ with a file-by deadline.
- **Public elementary school (weekend)** — district facility-use application + $1M COI naming the district; generator required (no exterior outlets). Verdict ⚠️.
- **HOA clubhouse lawn** — property manager wants a COI + hold-harmless; stakes OK away from irrigation; no permit. Verdict ✅ once COI sent.
- **Private backyard** — no third-party authority; quick anchoring/power sanity check only. Verdict ✅.

---

## Sharing this skill
Self-contained and provider-agnostic — share as-is (or as a `.skill` file / via the Manus skills library / GitHub import). Each provider supplies their own `business_profile`; the research workflow and document templates are identical for everyone.

## Optional bundled resources (add later)
- `references/authority_lookup.md` — how to find the controlling authority by venue type.
- `references/anchoring_matrix.md` — surface type → allowed anchoring method → required weight.
- `assets/holdharmless_template.md` — reusable hold-harmless language to pair with the COI.
