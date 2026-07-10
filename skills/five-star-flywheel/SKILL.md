---
name: five-star-flywheel
description: Build reviews and manage online reputation for a bounce house / party rental business. Use this skill whenever the user wants to ask customers for reviews, follow up after an event, get more Google/Facebook ratings, respond to a review (good or bad), or improve their reputation. Trigger it whenever reviews, ratings, testimonials, reputation, or "how do I get more 5-stars" / "how should I respond to this review" come up — even if the skill isn't named. It times post-event review requests, routes customers to your review links, and drafts professional responses to existing reviews — the FTC-compliant way.
---

# Five-Star Flywheel — Review & Reputation Engine

A local rental business lives and dies by its Google and Facebook ratings. This skill turns every completed rental into a review opportunity and keeps your responses sharp — including the rare bad review. Portable via a shared `business_profile`.

## Principles
1. **Ask while the glow is warm.** The best moment is ~24 hours after the event, when the party was a hit and the photos are fresh.
2. **Make it one tap.** Send the direct review link; never make a happy customer hunt for where to post.
3. **Play it straight (FTC + Google).** Invite *every* customer to leave an honest review. Don't filter so only happy customers can post publicly, don't trade discounts for positive reviews, and never write fake ones. Use private feedback to *improve*, not to suppress.
4. **Respond to everything.** A personalized thank-you on good reviews and a calm, solution-focused reply on bad ones both build trust with future customers reading along.

## Inputs (from `business_profile`)
Google review link, Facebook review link (and any others); business name; owner/sender name; brand voice; contact. Plus **completed bookings**: customer name, event/theme, date, unit(s), preferred channel (email/text), and any known sentiment or issues from delivery.

## Workflow

### 1. Queue the request (timing)
~24 h after each completed event, generate a personalized review request via the customer's preferred channel. Reference their specific event ("the unicorn bounce house at Mia's party").

### 2. Ask for honest feedback, then route
Invite an honest review and include the direct link(s). It's fine to first ask "how did it go?" to catch problems early — but **anyone** who wants to review gets the public link. If a customer flags a problem, route it to the owner for a personal fix *and* still leave the public option open; don't gate.

### 3. One gentle follow-up
If no review after ~5–7 days, send a single friendly reminder, then stop. Never nag.

### 4. Respond to incoming reviews
- **Positive:** draft a warm, specific thank-you that names a detail and reinforces the brand — not a copy-paste.
- **Negative/critical:** draft a calm, professional, public response that thanks them for the feedback, takes responsibility where fair, avoids excuses or arguing, and moves the resolution offline ("I'd love to make this right — please reach me at {{contact}}"). Also draft the private follow-up. Never reveal private details or get defensive.

### 5. Track the flywheel
Log: request sent → review received → rating → response posted. Surface trends (recurring praise to lean into, recurring complaints to fix) so reviews feed back into operations.

---

## Output format
1. **Review requests** — drafted + personalized, with the right link, queued by event.
2. **Response drafts** — for any reviews provided (positive and negative).
3. **Tracking note** — what's outstanding + any pattern worth acting on.

## Templates

### Review request (text)
```
Hi {{name}}! Hope {{child/honoree}}'s party was a blast 🎉 It was a pleasure
bringing the {{unit}} out for you. If you have 30 seconds, an honest review really
helps our small business: {{review_link}}. Thank you! — {{sender_name}}, {{business_name}}
```

### Review request (email)
```
Subject: How was {{event}}? 🎈

Hi {{name}}, thank you for choosing {{business_name}} for {{event_date}}! We loved
being part of it. Would you share a quick, honest review of your experience? It
takes a moment and means the world to a local business like ours:
👉 {{review_link}}
Anything we could've done better? Just reply here — I read every message.
— {{sender_name}}
```

### Response to a positive review
```
Thank you so much, {{name}}! We had a blast bringing the {{unit}} to {{event}} —
{{specific detail}}. Hope to bounce with you again next year! 🎉 — {{business_name}}
```

### Response to a negative review
```
Hi {{name}}, thank you for the honest feedback, and I'm sorry {{issue}} fell short
of what you expected. That's not the experience we want to give. I'd really like to
make it right — please reach me directly at {{contact}}. — {{owner_name}}, {{business_name}}
```

## Guardrails (compliance)
- Solicit honest reviews from all customers; don't gate, filter, incentivize-for-positive, or fabricate. • Keep responses professional and private-detail-free. • Use private feedback to fix problems, never to block public reviews.

## Sharing
Provider-agnostic — each company drops in its own review links and brand voice via the `business_profile`. Share as-is or as a `.skill`.
