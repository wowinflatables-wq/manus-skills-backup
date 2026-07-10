---
name: damage-deposit-adjudicator
description: Turn post-event return photos into a fair, documented damage assessment plus two finished documents — an internal repair ticket and a professional customer-facing damage notice that justifies any deposit deduction. Use this skill whenever a unit comes back dirty, torn, wet, stained, or damaged; whenever the user is deciding whether to keep or refund a deposit, needs to charge for cleaning/repair, or is bracing for a dispute or chargeback; or when the user says "the unit came back trashed," "do I charge them," "write up the damage," "justify the deposit," or "they're disputing the charge." It reads pricing, deposit terms, and policy from a profile, so it's fully portable across providers. Trigger it any time post-rental damage, cleaning fees, deposit deductions, or damage disputes come up — even if the skill isn't named.
---

# Damage & Deposit Adjudicator — Fair, Documented, Dispute-Proof

Cuts chargebacks and arguments by replacing the angry text with **documentation**. Drop in return photos and it logs the damage, estimates a defensible repair/cleaning cost, and produces two finished assets: an **internal repair ticket** (so the unit gets fixed and tracked) and a **customer-facing damage notice** (worded like a pro, tied to your policy, itemized). Built to be **shared with any provider** — costs, deposit terms, and policy come from a profile.

## Principles
1. **Portable by design.** Read repair costs, deposit terms, and policy language from a `business_profile`. Nothing company-specific is hardcoded. If missing, ask before adjudicating.
2. **Fair and evidence-based.** Charge for genuine damage and abnormal cleaning — not normal wear. When photos are ambiguous, say so and recommend the conservative call. Overcharging invites chargebacks; this skill's job is to make deductions *stick*, which means making them *fair*.
3. **Two audiences, two documents.** The internal ticket is blunt and operational; the customer notice is calm, factual, policy-anchored, and free of blame language.
4. **Grounded in real numbers.** Estimates come from the operator's actual repair/cleaning/replacement costs, not made-up figures. Show the itemization.
5. **Policy is the anchor.** Every customer-facing charge references the signed rental agreement / deposit terms from the profile. No policy on file → flag it and recommend adding one before charging.
6. **De-escalate by default.** The tone should make a reasonable customer nod, not fight. Offer a resolution path (repair receipt on request, partial goodwill option) where it protects the relationship without eating real losses.

---

## First-run setup — the `business_profile`

Collect once and reuse:

- **Deposit & policy:** deposit amount(s), what the signed agreement says about damage/cleaning/late/lost items, refund timeline, dispute/chargeback process, who signs and how.
- **Cost basis:** typical **cleaning** cost (light vs. deep/biohazard), common **repair** costs (patch/seam/blower/stitching), **replacement** cost or depreciated value per unit class, labor rate, and any minimum service fee.
- **Identity & contact:** business name, contact, payment processor (for refund/partial-refund mechanics), brand voice for customer messaging.
- **Thresholds:** what counts as normal wear (no charge) vs. chargeable, and any goodwill allowance the operator is comfortable extending.

> Keep the profile separate from this SKILL.md so the skill stays generic and shareable.

---

## Step 1 — Intake the return
Gather: the **unit(s)**, the **booking/customer**, the **deposit held**, **return photos** (and pre-rental condition photos if available), and any notes from the crew. If pre-rental photos exist, compare against them — a before/after pair is the strongest evidence and dramatically reduces disputes.

## Step 2 — Assess each issue from the photos
For each visible problem, classify it:
- **Type:** tear/puncture · seam/stitch failure · stain (grass, mud, food, gum, ink) · biohazard (vomit/urine/blood → deep-clean protocol) · water/mildew from improper drying · burn/scorch · missing/broken part · normal wear.
- **Severity:** cosmetic / functional / safety-critical.
- **Attribution:** consistent with misuse/neglect (chargeable) vs. normal use (not chargeable) vs. **ambiguous** (flag, recommend conservative call).
- **Cleanable vs. repairable vs. replace:** the remediation path.

Be explicit when a photo doesn't clearly support a charge — that honesty is what makes the defensible charges hold up.

## Step 3 — Estimate cost (itemized, from the profile)
Build a line-item estimate using the operator's real costs: cleaning tier, each repair, any part, labor, minimum fee. Total it. Then compare to the deposit held:
- If **total < deposit** → deduct the total, refund the remainder.
- If **total > deposit** → keep the deposit and note the shortfall (recommend a separate additional-charge conversation per policy).
- If **normal wear only** → recommend **full refund**, no charge.

## Step 4 — Produce the internal repair ticket
Operational and direct: unit, issues, severity, safety hold if applicable (**do not re-rent until repaired** for anything safety-critical), parts needed, estimated repair time, assigned/priority, and cost booked. This drives the actual fix and keeps a maintenance record.

## Step 5 — Produce the customer-facing damage notice
Calm, factual, and policy-anchored, in the profile's brand voice:
- Thank them for the rental, state the unit came back with issues beyond normal use.
- **Itemize** what was found and the cost of each, referencing the photos and the signed agreement clause.
- State the **deposit math** plainly (held → deducted → refunded, with dates).
- Offer a resolution path: repair receipt/photos available on request; a stated goodwill option if the operator allows one.
- Close professionally with contact for questions. No accusatory language.

## Step 6 — Deliver & prep for dispute
Output both documents plus the deposit math and a short **evidence pack** list (which photos support which charge) the operator can submit if the customer disputes with their card issuer. Offer to draft the chargeback-response summary if it comes to that.

---

## Output format

**Adjudication Summary**
- **Verdict:** full refund / partial deduction / full deposit kept / shortfall beyond deposit — one line why.
- **Deposit math:** held {{$}} → charges {{$}} → refund {{$}} (by {{date per policy}}).
- **Safety hold:** yes/no — {{unit}} out of service until repaired.

**Findings** (per issue)
- {{issue}} — {{severity}} — {{cleanable/repair/replace}} — {{$}} — {{photo ref}} — {{normal wear? Y/N}}

**Documents**
- **Internal repair ticket** (paste-ready) · **Customer damage notice** (paste-ready, brand voice).

**Evidence pack** — which photos + which policy clause support each charge.

---

## Templates

### Internal repair ticket
```
REPAIR TICKET — {{Unit}} — {{date}}
Booking: {{ref}}  ·  Crew notes: {{...}}
Safety hold: {{YES — do not re-rent / NO}}
Issues:
  - {{issue}} — {{severity}} — {{fix: patch/seam/part/clean}} — ~{{time}}
Parts/materials: {{list}}
Est. repair cost booked: {{$}}
Priority: {{high/med/low}}  ·  Assigned: {{who}}
```

### Customer damage notice
```
Hi {{Customer Name}},

Thank you for renting the {{Unit}} from {{Business Name}} on {{date}}.

During our post-event inspection, we found the following beyond normal
wear, documented in the return photos:

  • {{issue}} — {{cleaning/repair}} — {{$}}
  • {{issue}} — {{$}}
  Total: {{$}}

Per the rental agreement you signed ({{clause ref}}), these are covered
by the security deposit.

  Deposit held: {{$}}
  Applied to above: {{$}}
  Refund to you: {{$}} — processed by {{date}}

We're happy to share the repair receipt and photos on request. If you have
any questions, just reply or call {{phone}}.

Thanks again,
{{Business Name}}
```

---

## Illustrative examples (pattern only — use the operator's real costs & policy)
- **Grass + mud, no tears** — deep-clean fee only; partial deduction; refund the rest; friendly notice.
- **Seam blowout from over-occupancy** — safety hold + repair ticket; itemized repair charge; notice cites capacity clause.
- **Biohazard (vomit)** — deep-clean protocol, higher fee; calm notice, receipt offered.
- **Faint scuff, normal use** — no charge; recommend **full refund**; short thank-you note (builds a rebooking).

---

## Sharing this skill
Self-contained and provider-agnostic — share as-is (or as a `.skill` file / via the Manus skills library / GitHub import). Each provider supplies their own costs, deposit terms, and policy; the assessment logic and document templates are identical for everyone.

## Optional bundled resources (add later)
- `references/damage_taxonomy.md` — issue types, severity rubric, chargeable vs. wear.
- `references/cleaning_repair_costs.md` — worked cost examples by unit class.
- `assets/chargeback_response_template.md` — evidence-pack format for card-issuer disputes.
