---
name: event-opportunity-radar
description: Scan local calendars — festivals, school and church events, grand openings, HOA and community schedules — inside a rental company's service radius and surface a ranked list of date-anchored booking opportunities, each with a suggested outreach angle and timing. Use this skill whenever the user wants to find new bookings, events, or leads by date/location; asks "what's happening in my area," "where can I find events to book," "what festivals/fundraisers/grand openings are coming up," "who should I pitch this month," or wants demand-driven prospecting instead of cold company lists. It reads the service area, inventory, and voice from a profile, so it's fully portable across providers. Trigger it any time local-event prospecting, seasonal demand hunting, or date-anchored outreach comes up — even if the skill isn't named.
---

# Event Opportunity Radar — Date-Anchored Demand, Not Cold Lists

Feeds the growth loop with **real upcoming events that need what you rent**, ranked and timed, instead of a generic list of businesses to cold-call. It scans public local calendars inside your service radius, surfaces the festivals, school/church events, grand openings, and community gatherings most likely to book inflatables, and hands you a **ranked opportunity list with an outreach angle and the right time to reach out for each.** Built to be **shared with any provider** — service area, inventory, and voice come from a profile.

## Principles
1. **Portable by design.** Read service area, inventory, and brand voice from a `business_profile`. Nothing company-specific is hardcoded. If missing, ask before scanning.
2. **Demand-anchored.** Every opportunity ties to a **real date and place** with a plausible need for units — not a speculative company list. A date creates urgency and a natural reason to reach out.
3. **Public sources only.** Use public event calendars, community pages, chamber/tourism listings, school and church public calendars, permit/festival announcements, and public social posts. No logins, no scraping behind access controls.
4. **Ranked by winnability, not just size.** Score on fit (does it need inflatables?), timing (enough lead time?), reachability (is there a public contact?), and value (repeatable? multi-unit?). Surface the best bets first.
5. **Outreach-ready.** Each opportunity comes with a suggested angle, the right contact type, the ideal outreach window, and a drafted opener — not just "here's an event."
6. **Respectful outreach.** Warm, relevant, non-spammy. Pitch a genuine fit; honor do-not-contact and public-record norms.

---

## First-run setup — the `business_profile`

Collect once and reuse:

- **Service area:** home base + delivery radius (and any towns/zips you prioritize or avoid), blackout/peak dates.
- **Inventory & fit:** what you rent and the event types each unit shines at (big combos for festivals, toddler units for church/MOPS, obstacle courses for school field days, concessions for community nights, etc.).
- **Capacity:** how many simultaneous setups you can staff on a peak day (so the radar doesn't surface more than you can serve).
- **Voice & contact:** business name, brand voice, phone, booking link, and how you prefer to reach out (email, call, message, in-person drop-by).
- **Target segments:** the event types you most want (schools, churches, HOAs, municipalities, corporate, nonprofits/fundraisers, grand openings).

> Keep the profile separate from this SKILL.md so the skill stays generic and shareable.

---

## Step 1 — Set the window & scope
Confirm the **time horizon** (next 30/60/90 days or a specific season) and the **service area** to scan. If it's a seasonal push (fall festivals, back-to-school field days, spring fundraisers, summer community nights), bias the scan toward that pattern.

## Step 2 — Scan local calendars (live, public)
Sweep public sources inside the radius for upcoming, date-anchored events:
- **Community/municipal:** city event calendars, parks & rec programs, festivals, national-night-out, holiday events, farmers-market special days.
- **Schools & PTAs:** field days, fall/spring carnivals, fun runs, teacher-appreciation, end-of-year celebrations (public school calendars/PTA pages).
- **Churches & faith orgs:** VBS, fall festivals/trunk-or-treat, harvest nights, family days.
- **HOAs & neighborhoods:** community days, pool-opening parties, seasonal gatherings.
- **Business/commercial:** grand openings, anniversary sales, chamber ribbon-cuttings, corporate family days.
- **Nonprofit/fundraiser:** galas-with-kids-areas, walks, charity fun days.

Capture for each: name, **date**, location/town, host org, event type, expected size if shown, and any **public contact** (organizer, facilities office, chamber, church office). Record source + date checked.

## Step 3 — Filter for fit
Drop events that don't plausibly need inflatables (adults-only galas, indoor lectures) or fall outside the radius/capacity. Keep those with a real family/kids/community component where a unit would land.

## Step 4 — Score & rank
Rank each surviving opportunity on:
- **Fit** — how well the event type matches inventory (which unit you'd pitch).
- **Timing** — enough lead time to reach the decision-maker before they've booked (flag anything too close).
- **Reachability** — is there a public contact or an obvious path in?
- **Value** — single vs. multi-unit, one-off vs. **repeatable annual** (recurring events are gold — winning one can lock a yearly booking).
Produce a ranked list, best bets first, sized to what the operator can actually staff.

## Step 5 — Build the outreach angle per opportunity
For each top opportunity, give:
- **Who to contact** (organizer / facilities / PTA president / church office / chamber) and the likely channel.
- **The angle** — the specific unit + why it fits *this* event ("a toddler combo for your fall festival's little-kid zone").
- **Timing** — the ideal outreach window (early enough to win, not so early it's forgotten).
- **A drafted opener** in brand voice, referencing the event by name and date.
Note where a package would fit and hand the build to the package skill.

## Step 6 — Deliver, schedule, and track
Output the ranked radar + per-opportunity outreach kits. If scheduling is available, set outreach reminders on each opportunity's ideal window and (for recurring events) a reminder to pitch again next year. Provide a simple tracker (event → contact → outreach date → status) and offer to run the radar again on a cadence.

---

## Output format

**Opportunity Radar — {{area}}, {{window}}**

**Top opportunities (ranked)**
1. **{{Event}}** — {{date}} · {{town}} · {{type}}
   - Fit: {{unit to pitch}} · Value: {{single/multi, one-off/annual}} · Lead time: {{ok/tight}}
   - Contact: {{who}} via {{channel}} · Outreach by: {{window}}
   - Opener: {{drafted message}}
2. …

**Also worth a look** — {{lower-ranked but valid events}}

**Recurring/annual flags** — {{events to lock in and re-pitch yearly}}

*Sources + dates checked under each item. Sized to {{capacity}} simultaneous setups.*

---

## Templates

### Opportunity card
```
Event: {{name}}  ·  Date: {{date}}  ·  Town: {{town}}  ·  Type: {{type}}
Host: {{org}}  ·  Est. size: {{if known}}  ·  Recurring: {{annual? Y/N}}
Pitch unit(s): {{from inventory}}  —  why it fits: {{one line}}
Contact: {{name/role}} via {{email/call/office}}  ·  Reach out by: {{window}}
Source: {{link, date checked}}
```

### Outreach opener (email)
```
Subject: {{Event Name}} on {{date}} — a fun add for the kids?

Hi {{Name}}, I saw {{Event Name}} is coming up on {{date}} in {{town}} —
looks like a great community day! I'm {{Business Name}}, local and insured,
and I think a {{unit}} would be a hit for the {{families/kids}} attending.
Happy to put together a simple option that fits your space and budget —
want me to send a quick idea? {{phone}} · {{booking link}}
```

### Outreach opener (SMS/short)
```
Hi {{Name}}! {{Business Name}} here — noticed {{Event}} on {{date}}. A {{unit}}
would be perfect for the kids. Want me to send a quick option? {{booking link}}
```

---

## Illustrative examples (pattern only — always scan the real local calendars)
- **Church fall festival, Oct** — pitch a big combo + toddler unit for the kids' zone; contact church office ~6 weeks out; likely **annual** → lock and re-pitch next year.
- **Elementary spring field day** — obstacle course + water slide; reach the PTA/athletics contact early before they book; multi-unit value.
- **Downtown grand opening** — attention-grabbing unit for foot traffic; contact the business owner/chamber; short lead time flagged.
- **HOA pool-opening party** — toddler + midsize combo; reach the property manager; recurring seasonal.

---

## Sharing this skill
Self-contained and provider-agnostic — share as-is (or as a `.skill` file / via the Manus skills library / GitHub import). Each provider supplies their own service area, inventory, and voice; the scan, scoring, and outreach logic are identical for everyone. Pairs naturally with the win-back, package, and prospecting skills to feed a full growth loop.

## Optional bundled resources (add later)
- `references/event_source_list.md` — where to find public calendars by source type.
- `references/scoring_rubric.md` — fit/timing/reachability/value weighting.
- `assets/outreach_library.md` — openers per event type and channel.
