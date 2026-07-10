---
name: bounce-safe
description: Generate and maintain safety, cleaning, and standard-operating-procedure documents for a bounce house / inflatable rental business. Use this skill whenever the user wants inspection checklists, setup/anchoring or teardown SOPs, cleaning and maintenance logs, posted safety rules for a unit, attendant training, or an incident report form. Trigger it whenever safety, inspections, anchoring, cleaning, maintenance logs, SOPs, posted rules, attendant training, liability, or "how do I set this up safely / stay compliant" comes up — even if the skill isn't named. It produces ready-to-use documents grounded in ASTM F2374 and CPSC guidance, and always defers to the manufacturer's manual and local regulations.
---

# Bounce Safe — Safety, Cleaning & SOP Keeper

The skill most specific to inflatables and the one that protects you legally. It generates and maintains your inspection checklists, setup/anchoring and teardown SOPs, cleaning/maintenance logs, posted rules, attendant training, and incident forms — reducing liability, extending unit life, and letting you train a helper in an afternoon. Portable via a shared `business_profile`.

## The authority chain (state this on every document)
These materials are grounded in **ASTM F2374** (the U.S. standard for inflatable amusement devices) and **CPSC** guidance, but they are **templates**. The order of authority is: **(1) the unit's manufacturer manual → (2) ASTM F2374 → (3) your state/local regulations and your insurer's requirements → (4) these templates.** When they conflict, follow the strictest. The operator is responsible for compliance; this skill does not replace the manufacturer's instructions, professional inspection, or legal/insurance advice.

## Key safety facts these documents enforce (per ASTM F2374 / CPSC)
- **Wind:** never operate above the manufacturer's posted maximum. If none is given, ASTM default is **15 mph sustained** shutdown; **25 mph (incl. gusts) = evacuate and deflate any inflatable.** Monitor sustained + gusts; trained attendant uses an anemometer/Beaufort scale. (See Weather Guard.)
- **Anchoring:** use **every manufacturer anchor point, every time** — minimum **4**. Each point should resist ~**1,600 N (360 lbf)**. **Stakes** on grass: min ~**1" diameter × 18" long, driven vertically** (angling loses 40–60% of holding force). **Weights/ballast** on concrete/asphalt: commercial guidance is ~**200–450 lb per anchor point** (small sandbags are not sufficient on their own).
- **Power:** blower on a dedicated **GFCI**-protected circuit; secure cords; generator if no outlet within range.
- **Site:** clear overhead lines/branches, level ground, debris cleared, safety perimeter, entrance/exit mats.
- **Supervision:** a **trained attendant** while inflated; **permanent info plate** at the entrance with capacity, age/height limits, and wind limit.
- **Operating rules:** enforce occupancy and age/height separation; no shoes, glasses, food, gum, sharp objects; no flips/roughhousing; evacuate on power loss or weather.

## Inputs (from `business_profile`)
Unit list with types/specs and (if available) manufacturer wind ratings, anchor counts, and occupancy; surfaces typically worked; state/local regs or permitting if known; insurer requirements; business name/branding for headers.

## What this skill produces (pick what's asked, or generate the full set)

1. **Pre-rental inspection checklist** — blower & airflow, seams/stitching, anchor points/D-rings, netting/mesh, no tears/punctures, clean & dry, info plate legible, GFCI tested.
2. **Setup SOP (by surface)** — site survey (overhead clearance, slope, debris, footprint + perimeter), anchoring method per surface with the specs above, blower/GFCI setup, entrance mat, attendant briefing.
3. **Posted safety rules card** (for the unit entrance) — occupancy, age/height separation, prohibited items/behavior, supervision, weather/power evacuation.
4. **Teardown SOP** — power down, evacuate, deflate, inspect, **clean & fully dry before storage**, log condition.
5. **Cleaning & maintenance log (per unit)** — date, cleaned/disinfected, damage found, repair done, next service due.
6. **Attendant training one-pager** — wind monitoring, occupancy enforcement, emergency/evacuation steps, what to never allow.
7. **Incident report form** — date/time/location, unit, what happened, injuries, witnesses, weather/wind reading, photos, actions taken — formatted for insurer/authority reporting.

## Workflow
1. Confirm which document(s) the operator needs (or offer the full safety binder).
2. Pull unit specs from the profile; for any unknown manufacturer limit, apply the conservative ASTM defaults above and label them as defaults to verify against the manual.
3. Generate the document(s) with the business header and the authority-chain note. Offer them as clean, printable files (checklists/logs as fillable, rules card as a postable sheet).
4. For logs, set up a reusable per-unit format the operator can keep updating; remind on maintenance cadence.

## Output format
The requested document(s), business-branded, print-ready, each carrying the authority-chain disclaimer. When asked for "the works," deliver the full binder: inspection + setup SOP + rules card + teardown SOP + maintenance log + training sheet + incident form.

## Guardrails
- Always defer to manufacturer manual, ASTM F2374, and local law/insurer. • Present unknown limits as conservative defaults to verify, never as the final word. • This is operational documentation, not legal advice. • Never soften a safety threshold to make setup easier.

## Sharing
Provider-agnostic — works from any company's `business_profile`. Share as-is or as a `.skill`. Each operator must still reconcile output with their own units' manuals and local regulations.
