---
name: search-and-destroy
description: Find and pursue B2B rental opportunities for an inflatables / party-rental business. Use this skill whenever the operator wants to generate leads, prospect, fill open calendar dates, find events or organizations to rent to, or run outreach — e.g. "find me churches doing VBS," "who's having fall festivals near me," "fill my June weekends," "find rental opportunities," "drum up business," or any request touching seasonal demand, local events, or cold outreach. It scans for time-of-year and location-based opportunities (VBS, school carnivals, trunk-or-treat, festivals, grand openings, corporate picnics, etc.) inside the business's service radius, qualifies leads, finds public points of contact, and drafts approval-gated email + ad outreach. Always run this when the user mentions prospecting, leads, marketing outreach, or finding events — even if they don't name the skill.
---

# Search and Destroy — Rental Opportunity Prospector

This skill turns "I need more bookings" into a reviewed list of real, local, time-appropriate organizations to pitch, with personalized outreach drafted and ready. It is a **prospecting and outreach assistant for an inflatables / party-rental business**, not a mass-spam tool. Email is the automated channel; social messages are drafted for the operator to send by hand.

## Operating principles (read first — non-negotiable)

1. **Human approval gate.** Never send, post, or DM anything automatically. Produce drafts + a lead sheet, then STOP and wait for the operator's explicit "approved, send these" before any outbound contact.
2. **Email follows CAN-SPAM.** Every email must have a truthful "from" and subject, the business's real postal address, a clear opt-out link/line, and honor opt-outs immediately. (Add CASL handling if any recipient is in Canada.)
3. **No automated social DMs.** Do not auto-message via Facebook/Instagram Messenger, etc. — it violates platform terms and gets accounts banned. For social, draft the message and hand it to the operator to send manually from their own account/Page.
4. **Public business contacts only.** Use publicly listed organizational contacts (role inboxes, "contact us" pages, staff directories). Do not scrape or guess private personal data. Maintain and respect a suppression / do-not-contact list.
5. **Only pitch what you can fulfill.** Check the business's own availability for the target date before pitching it (don't sell a date you're already booked solid).
6. **Personalize, don't blast.** Reference the org's specific event and date. Cap contacts per organization and rate-limit sends to protect sender reputation and stay out of spam folders.
7. **No duplicate leads.** Never present the same organization twice — across the current run OR across previous runs. Deduplicate by normalized org name (case-insensitive, ignore punctuation/"the"/"inc"/"llc"). If the same org has multiple events, merge into one row with both events listed. Before finalizing the Lead Sheet, cross-check against the contact log from prior runs (if available) and drop any org already contacted within the last 90 days.

---

## Inputs the skill needs (gather once; reuse every run)

If any are missing, ask the operator or read from a saved `business_profile`:

- **Business identity:** name, logo, website, booking link, phone, **physical mailing address** (required for CAN-SPAM), reply-to email, sender name.
- **Service area:** home base address/ZIP and **radius** (default 30 miles).
- **Inventory & pricing:** what's available to rent (bounce houses, combos, water slides, obstacle courses, concessions, tents/tables/chairs), unit names, "from $X" prices, any items that pair well with specific events.
- **Availability:** open dates / blackout dates (pull from the reservation system if connected; otherwise ask).
- **Brand voice:** friendly / professional / playful — and any do's/don'ts.
- **Channels approved:** email (default), and which social accounts exist for *manual* sends.
- **Suppression list:** orgs/contacts already opted out or off-limits.
- **Offer/hook (optional):** discount, package, or "book early" incentive to include.

---

## The Opportunity Calendar (the "time of year + who" intelligence)

Pick the opportunity types whose **planning window is open now** — i.e., the event is **30–60 days out** (sweet spot to pitch). Lead times skew earlier for big church/school events. Adjust for the business's region/climate; outdoor inflatables slow in deep winter, so lean indoor then.

| Window (event month) | Opportunity | Who organizes it | Contact role to find | Why inflatables fit |
|---|---|---|---|---|
| Mar–Apr | Easter egg hunts, spring festivals | Churches, parks & rec, communities | Children's ministry / events coordinator | Family draw, kid zones |
| Apr–May | School field days / fun days | Elementary schools | PTA/PTO president, school events coord. | Core field-day attraction |
| May | End-of-school carnivals, teacher appreciation | Schools, PTAs | PTA president, principal's office | Carnival centerpiece |
| May–Jun | Graduation & end-of-season sports parties | Families, leagues, schools | League president, booster club | Backyard / park parties |
| **Jun–Jul** | **Vacation Bible School (VBS)** | **Churches** | **VBS director / children's ministry dir.** | **Daily kids' energy outlet** |
| Jun–Aug | Summer day camps, library reading finales | Camps, libraries, rec centers | Camp director, programs coordinator | Weekly rotating fun |
| Jun–Jul | July 4th / community & HOA parties | Cities, HOAs, neighborhoods | HOA manager, social committee chair | Big community draw |
| Jun–Aug | Corporate family days / picnics | Employers, HR | HR / office manager, events coord. | Family attraction |
| Jul–Aug | Back-to-school bashes | Churches, schools, apartments | Outreach pastor, property manager | Welcome-event magnet |
| Sep–Oct | Fall / harvest festivals | Churches, schools, farms | Events coordinator | Festival centerpiece |
| **Oct** | **Trunk-or-Treat / Halloween events** | **Churches, schools** | **Events / outreach coordinator** | **Huge inflatable demand** |
| Oct–Nov | Fall fundraisers & carnivals | PTAs, nonprofits | Fundraising chair | Ticketed attraction |
| Nov–Dec | Holiday / "Breakfast with Santa," winter festivals | Churches, malls, communities | Events coordinator | Indoor inflatable / photo draw |
| Dec–Feb | Lock-ins, daddy-daughter dances, indoor events | Churches, schools | Youth pastor, PTA | Indoor units in slow season |
| Year-round (peak Apr–Oct) | Birthday parties, grand openings | Families, businesses | Parent / marketing manager | Direct rentals (different channel) |

> Use this as a starting map, not a limit. If the operator names a target (e.g., "find VBS churches"), go straight to that row. Otherwise propose the 2–4 most timely opportunities for the current date and location and confirm before searching.

---

## Workflow

### Step 1 — Set the frame
Determine today's date and the business location/radius. List the opportunity types whose pitch window is open (event ~30–60 days out). Confirm the target(s) with the operator (or proceed if they already specified one).

### Step 2 — Search for live opportunities
For each target opportunity, run focused web searches to find **specific organizations actively advertising the event with a date**, within radius. Search patterns (substitute town/region names from the service area):
- `"vacation bible school" [town/county] 2026 dates`
- `[town] church "trunk or treat" OR "fall festival" [year]`
- `[town] elementary "field day" OR "fall carnival"`
- `[county] community calendar [month] events`
- Check church/school websites, Facebook Events, Eventbrite, Nextdoor/community calendars, parks & rec pages, and local news roundups.
Capture: org name, event name, **event date**, location, and the source URL.

### Step 3 — Qualify & Deduplicate
Keep a lead only if: within radius • event date is **≥30 days out** • not on the suppression list • not already contacted recently • the business has the right inventory free for that date. Drop or flag anything that fails.

**Deduplication rules (mandatory):**
1. **Within-run dedup:** Normalize each org name (lowercase, strip "the", "inc", "llc", punctuation). If two results share the same normalized name, merge them into one lead row listing all their events.
2. **Cross-run dedup:** Before finalizing, check the contact log / "already contacted" list from prior runs. Any org contacted within the last 90 days is dropped unless the operator explicitly re-targets them.
3. **Same-event dedup:** If the same event appears under multiple names or sources (e.g., "City Fun Day" found on both Facebook and the Chamber calendar), keep only one entry with the richest data.
4. **Address/location dedup:** If two orgs share the same physical address and event date, flag as possible duplicate for operator review.

### Step 4 — Find the right public contact
For each qualified org, find the **publicly listed** best point of contact for that event: a role/person and a public email (and the org's social handle for manual follow-up). Prefer role inboxes (e.g., children's ministry, school front office, HOA management). If only a generic "info@" exists, use it. Do not fabricate or dig for private personal data.

### Step 5 — Draft outreach (per lead)
Produce, personalized to the org and event:
- a **short email** (template below) referencing their specific event and date, the relevant inventory, an offer/hook if provided, the booking link, and the compliant footer;
- a **one-line social DM** the operator can send manually;
- optional **ad/flyer copy** tailored to the event (e.g., a "VBS Week Bounce House Special").

### Step 6 — Compile the Lead Sheet and STOP
Output a single table (below) plus the drafts, and **wait for approval.** Do not send anything yet.

### Step 7 — On approval, send and log
After explicit approval, send the approved **emails** (CAN-SPAM compliant, rate-limited, one per org). Hand the operator the approved **social messages** to send manually. Log each contact (org, channel, date, message) and update the "already contacted" list.

### Step 8 — Follow-up cadence
Schedule polite follow-ups for non-responders — suggested: Day 0 email → Day 4 short bump → Day 10 final touch — each requiring the same approval gate, stopping immediately on any reply or opt-out, capped per org. Track outcomes (interested / booked / declined / opted out) and feed opt-outs into the suppression list.

---

## Output format — Lead Sheet

| # | Organization | Opportunity | Event date | Distance | Contact (role) | Channel | Inventory fit | Source | Status |
|---|---|---|---|---|---|---|---|---|---|
| 1 | First Baptist [Town] | VBS | Jul 14–18 | 12 mi | Children's Ministry Dir. (public email) | Email | 2 bounce houses, 1 combo | [url] | Draft ready |

Follow each row's draft email + social line + (optional) ad copy beneath the table, then the line: **"Ready to send on your approval — reply with the row numbers to approve, or tell me what to change."**

---

## Templates

### Email (B2B opportunity outreach)
```
Subject: Inflatables for {{org}}'s {{event_name}} on {{event_date}}?

Hi {{contact_name_or_team}},

I saw {{org}} is hosting {{event_name}} on {{event_date}} — looks like a great
time for the families coming out. I'm {{sender_name}} with {{business_name}},
a local inflatable & party rental company here in {{service_area}}.

For an event like yours, {{relevant_units}} are always a hit with kids and an
easy draw for attendance. Rentals start at {{from_price}}, and we handle delivery,
setup, and pickup so your team doesn't have to.

{{optional_offer}}

If you'd like, I can hold a unit for {{event_date}} before our summer dates fill
up. You can see everything and check availability here: {{booking_link}}.

Either way, hope {{event_name}} is a great one!

{{sender_name}}
{{business_name}} · {{phone}} · {{website}}
{{business_postal_address}}
Prefer not to hear from us? Reply "unsubscribe" or click here: {{optout_link}}
```

### Social message (operator sends manually)
```
Hi {{org}}! Saw your {{event_name}} on {{event_date}} 🎉 We're a local inflatable
rental company — happy to hold a bounce house/combo for the date if it'd help.
Details + availability: {{booking_link}}
```

### Ad / flyer copy (event-specific)
```
{{EVENT}} is coming up at {{ORG}}!
Make it unforgettable with a bounce house from {{business_name}}.
Delivery • Setup • Pickup included · From {{from_price}}
Reserve {{event_date}} → {{booking_link}} · {{phone}}
```

---

## Guardrails recap (apply on every run)
- Approval before any send. • Email = CAN-SPAM compliant (address + opt-out + honored). • No automated social DMs — draft for manual send. • Public business contacts only; honor the suppression list. • Pitch only fulfillable dates. • Personalize + rate-limit. • Log everything; stop on reply or opt-out. • **No duplicate leads** — deduplicate within each run AND across prior runs (90-day window).

## Optional bundled resources (add later if desired)
- `assets/email_templates.md`, `assets/ad_templates.md` — expanded, per-event copy.
- `references/opportunity_calendar.md` — fuller regional event lists and search queries.
- `scripts/` — a saved-leads CSV writer and follow-up scheduler.
