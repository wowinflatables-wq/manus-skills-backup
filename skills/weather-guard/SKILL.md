---
name: weather-guard
description: Watch the weather for every upcoming booked bounce house / inflatable event and manage wind/rain risk before it becomes a problem. Use this skill whenever the user wants to check the forecast for upcoming rentals, assess whether events are safe to run, decide on reschedules/refunds for weather, or draft a heads-up message to a customer about wind or rain. Trigger it whenever weather, wind, rain, storms, "is it safe to set up," or reschedule/refund-for-weather comes up — even if the skill isn't named. Inflatables are wind-sensitive and a unit in high wind is a serious safety and liability risk, so this skill leads with safety and defers to the manufacturer's rating, ASTM F2374, and local regulations.
---

# Weather Guard — Forecast Watch & Reschedule Manager

Wind and rain are the #1 operational risk for inflatables. This skill watches the forecast for every booked event, flags risk early, and drafts the proactive customer message — protecting safety, revenue, and reputation in one move. Portable via a shared `business_profile`.

## Safety first — the rules this skill enforces
Per **ASTM F2374** and CPSC guidance for inflatable amusement devices:
- **Never operate above the manufacturer's posted maximum wind speed.** If no manufacturer limit is given, ASTM's default is a **15 mph sustained** shutdown threshold. Manufacturer ratings typically fall between **15 and 25 mph**.
- **Above 25 mph (including gusts) it is dangerous to operate any inflatable — evacuate and deflate immediately.** 25 mph is a *design* threshold, not an operating green light; the real operating limit is lower.
- Wind is measured as **sustained speed and gusts**; monitor both. Rain/lightning means stop, evacuate, and deflate.
- These are minimums. **The manufacturer's rating, ASTM F2374, and your state/local regulations are the final authority** — when they differ, follow the strictest. This skill flags risk and drafts comms; the trained on-site operator makes the go/no-go call.

## Inputs (from `business_profile`)
Per-unit manufacturer wind ratings (default to 15 mph sustained if unknown); your written **weather policy** (reschedule window, rain-check credit, refund terms, decision deadline); brand voice; business contact. Plus **upcoming bookings**: date, time, location, unit(s), customer name + contact.

## Workflow

### 1. Pull the forecast per event
For each event in the watch window (default next 5–7 days), get the location- and time-specific forecast: **sustained wind, gusts**, precipitation probability/timing, thunderstorm/lightning risk, and temperature. Use live weather data at run time.

### 2. Classify risk (per unit's rating)
- 🟢 **Green** — winds and weather comfortably below the unit's limit; no action.
- 🟡 **Yellow / Watch** — forecast wind approaching the limit, gusty, or rain possible. Monitor; prepare the customer for a possible change; re-check 24–48 h out.
- 🔴 **Red / No-Go** — forecast sustained wind or gusts at/above the limit (or ≥25 mph), or storms/lightning. Plan to reschedule or cancel per policy; do not set up.

### 3. Build the daily watch list
A table of every upcoming event with risk level, the key numbers (sustained/gust/precip), the unit's limit, and a recommended action. Re-run daily; forecasts firm up as the date nears, so escalate Yellow→Red or relax →Green as needed.

### 4. Draft proactive customer comms
For Yellow/Red events, write an on-brand, **safety-first** message that: states you're monitoring the forecast for their date, explains the wind/rain concern plainly, and offers the options your policy allows (monitor & decide by {{deadline}}, reschedule to an open date, rain-check credit, or refund). Lead with their kids' safety, not your liability. Never pressure them to proceed in unsafe conditions.

### 5. Day-of guidance
For events happening that day in Yellow/Red, remind the operator: measure on-site wind (anemometer / Beaufort scale), follow the unit's rating, and have the evacuation/deflate plan ready. If conditions exceed the limit, do not operate.

---

## Output format
1. **Watch list** — table: event, date/time, unit + limit, sustained/gust/precip, risk 🟢🟡🔴, recommended action.
2. **Draft messages** — one per Yellow/Red event, ready to send.
3. **Day-of no-go alerts** — clear, if any event crosses the threshold.

## Templates

### Weather heads-up (Yellow)
```
Hi {{name}}! We're keeping a close eye on the forecast for your {{event_date}}
event. Right now it shows {{wind/rain detail}}, which is borderline for safe
inflatable operation. Nothing to do yet — we'll make the final call by
{{deadline}}. If we need to move it, your options are {{reschedule / credit /
refund per policy}}. Your family's safety comes first. — {{business_name}}
```

### Reschedule / no-go (Red)
```
Hi {{name}}, the forecast for {{event_date}} now shows {{winds/storms}}, which is
above the safe limit for our equipment — for everyone's safety we can't set up in
those conditions. Let's protect your party: I can {{move it to an open date /
issue a rain-check credit / refund}} per our policy. Which works best? So sorry
for the weather curveball — we'll make it great. — {{business_name}}
```

## Guardrails
- Forecasts are predictions, not guarantees — always re-check and defer to **on-site measurement** and the **manufacturer/ASTM/local** limits. • Never advise operating above a unit's rating. • Lead every customer message with safety. • This skill informs decisions; the trained operator on site decides go/no-go.

## Sharing
Provider-agnostic. Each company supplies its own unit ratings and weather policy in the `business_profile`. Share as-is or as a `.skill`.
