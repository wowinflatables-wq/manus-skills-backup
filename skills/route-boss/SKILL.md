---
name: route-boss
description: Plan and optimize a day's bounce house / party rental deliveries and pickups — route order, truck loading, and driver run sheets. Use this skill whenever the user wants to plan deliveries, sequence stops, "map out Saturday," figure out what fits on which truck, build a load list, or create a driver schedule/run sheet for rental drop-offs and pickups. Trigger it whenever delivery routing, loading, crew scheduling, or "how do I get all these out on time" comes up — even if the skill isn't named. Turns a chaotic weekend of bookings into an optimized, printable plan.
---

# Route Boss — Delivery, Load & Route Planner

Busy weekends make or lose the money. This skill takes a day's bookings and produces an optimized delivery/pickup route, a per-truck load list, and a clean driver run sheet — so nothing arrives late and nothing gets left in the warehouse. Portable via a shared `business_profile`.

## Principles
1. **Honor the windows first, then minimize miles.** Every delivery must land before its event start (with setup buffer); pickups after event end. Optimize drive time *within* those constraints.
2. **Load last-on, first-off.** Pack each truck in reverse delivery order so the first stop's gear is at the door.
3. **Nothing forgotten.** Every unit travels with its full kit — blower(s), the right anchors for the surface, cords/GFCI, mat, tarp, cleaning kit.
4. **Plan for the real world.** Build in buffer for setup, traffic, and the inevitable late customer; flag tight or impossible windows early.

## Inputs (from `business_profile`)
Warehouse/home-base address; vehicles with cargo capacity; each unit's pack specs (folded size, weight, blower count, crew needed, anchor kit). Plus **today's jobs**: per booking → address, delivery window / event start, pickup time / event end, unit(s), surface type, power situation, access notes (gate width, stairs, long carry), on-site balance due, customer name + phone.

## Workflow

### 1. Collect the day's jobs
List every delivery and pickup with address, required window, units, and special needs. Geocode addresses for distance.

### 2. Set timing rules
Delivery target = event start − setup buffer (default 60–90 min, more for big/multi-unit jobs). Pickup window = event end onward. Note overnight/next-day pickups separately.

### 3. Sequence the route
Cluster stops by geography, then order to minimize total drive time **while keeping every window**. Interleave deliveries and same-area pickups sensibly. Produce the stop order with estimated drive times and arrival times; flag any stop that can't be made on time so the operator can add a truck, shift a window, or split crews.

### 4. Assign trucks & build load lists
Assign jobs to vehicles by capacity. For each truck, output a **load list** in reverse delivery order: each unit + its blower(s), **anchors matched to the stop's surface** (stakes for grass, weights for concrete/asphalt — see Bounce Safe), extension cords + GFCI, entrance mat, tarp/dolly, and cleaning kit. Note total weight vs. capacity.

### 5. Generate the driver run sheet (per truck)
For each stop, one block: stop #, address (+ map link), arrival window, customer name + phone, unit(s), surface & **anchoring method**, power note (outlet vs. generator), access notes (gate/stairs/carry), **balance to collect on-site** (amount + method), and reminders (photo of setup, walk the safety rules with customer, get signature if needed).

### 6. Flag risks
Call out: overlapping tight windows, overcapacity trucks, long deadhead gaps, missing addresses/phones, jobs needing extra crew, and weather-sensitive stops (hand off to Weather Guard).

---

## Output format
1. **Route summary** — ordered stop list with arrival times + drive times + a map link.
2. **Per-truck load list** — units + full kit, reverse delivery order, weight check.
3. **Per-truck driver run sheet** — printable, one block per stop.
4. **Risk flags** — anything that won't work as-is, with a suggested fix.

## Templates

### Driver run sheet (per stop)
```
STOP {{n}}  |  {{DELIVER / PICKUP}}  |  Arrive by {{time}}
{{address}}   [map: {{link}}]
Customer: {{name}} — {{phone}}
Unit(s): {{units}}
Surface: {{surface}} → Anchor: {{stakes / weights}}   Power: {{outlet / generator}}
Access: {{gate width / stairs / long carry}}
COLLECT ON SITE: ${{balance}} ({{method}})
Before you leave: photo the setup • walk the rules with customer • {{signature?}}
```

### Load list (per truck)
```
TRUCK {{id}} — load last-on / first-off (reverse delivery order)
[ ] {{unit}} + {{#}} blower(s) + {{anchor kit}} + cords/GFCI + mat + tarp
[ ] ...
Cleaning kit • Dolly/hand truck • Spare stakes/weights • Patch kit
Total weight ~{{lbs}} / capacity {{cap}}
```

## Sharing
Provider-agnostic — works from any company's `business_profile` and daily job list. Share as-is or as a `.skill`.
