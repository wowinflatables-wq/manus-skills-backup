---
name: content-cannon
description: Generate a full month of themed, ready-to-post social media content for a bounce house / party rental business — captions, hooks, hashtags, a posting calendar, and visual direction. Use this skill whenever the user wants social media posts, a content calendar, captions, Instagram/Facebook/TikTok ideas, a month of content, or help marketing online. Trigger it whenever social content, posting schedules, captions, hashtags, reels, or "what should I post this month" come up — even if the skill isn't named. It builds a balanced month of posts at once, tied to local events, holidays, and current trends, all in the business's brand voice.
---

# Content Cannon — A Month of Posts, One Shot

Most rental operators post sporadically or not at all. This skill loads a full month of varied, on-brand, ready-to-schedule content tied to the season, local events, and current trends — so the calendar is never empty. Portable via a shared `business_profile`.

## Principles
1. **Balanced mix, not all "book now."** A feed that only sells gets ignored. Blend promotion with value, proof, personality, and community.
2. **Timely and local.** Tie posts to the month's holidays, local events (VBS, back-to-school, fall festivals), and **current trends pulled live** — not a stale evergreen list.
3. **Every post earns its CTA.** Clear next step where it fits (book, DM, comment, save, share) without being pushy on every single one.
4. **Ready to schedule.** Each post ships with caption, hashtags, visual direction, format, and best post time — paste-and-go.

## Inputs (from `business_profile`)
Business name, brand voice, inventory + signature units/themes, service area, booking link, brand colors/logo, social handles, current packages/promos (can pull from Package Prize), and any known top-performing past content. Target platforms (IG / FB / TikTok) and goal for the month (bookings / awareness / engagement).

## Workflow

### 1. Set the month
Confirm the month, platforms, posting frequency (default 3–4×/week ≈ 12–16 posts), and primary goal. Pull the month's holidays + local events for the service area, and run a quick live trend scan (themes, audio/format trends, popular party styles).

### 2. Plan the content mix
Distribute posts across proven categories so the feed stays fresh:
- **Promotional** — a package/offer (hand visual-heavy ones to Package Prize).
- **Seasonal / holiday** — tie-ins to the month's occasions.
- **Educational / tips** — "how many kids fit in a 15×15?", planning checklists, safety basics, choosing a theme.
- **Social proof** — review screenshots, party photos, customer shout-outs.
- **Behind-the-scenes** — setup, cleaning standards, meet-the-owner.
- **Engagement / fun** — polls, "this or that," caption-this, theme brackets.
- **UGC prompt** — ask customers to tag photos.
- **Community / local** — local events, school/church shout-outs, giving back.
- **Urgency** — "summer Saturdays are booking up."

### 3. Build the calendar
Lay posts on a dated calendar with an easy recurring rhythm (e.g., Tip Tuesday → educational; Feature Friday → unit spotlight; weekend → social proof / promo). Front-load booking-driving posts ahead of the area's peak demand windows.

### 4. Write each post
For every slot produce: a scroll-stopping **hook/caption** in brand voice, the **CTA**, **5–10 hashtags** (mix local + theme + niche), **visual direction** (photo to take or AI-graphic brief), **format** (feed / story / reel / carousel), and **best day + time** to post. For reels, suggest a hook line and a trending-audio-style direction.

### 5. Deliver & optionally generate visuals
Output the full calendar + all post content. Optionally generate key graphics (Manus image/design) or hand promo posts to Package Prize. Offer a quick "remix" for any post.

---

## Output format
1. **Monthly calendar** — table: date, category, platform/format, topic, CTA, post time.
2. **Full post content** — for each slot: caption + hashtags + visual direction + format + timing.
3. Optional: generated graphics or design briefs for the hero posts.

## Templates

### Post block
```
{{Date}} · {{Platform/Format}} · {{Category}}
Hook: {{scroll-stopping first line}}
Caption: {{2–4 lines, brand voice, value or story}}
CTA: {{book / DM / comment / save / tag}}
Visual: {{photo to take OR AI graphic brief}}
Hashtags: #{{Local}}Parties #BounceHouse{{City}} #{{Theme}} #PartyRentals #{{niche}} ...
Best time: {{day, time}}
```

### Recurring formats to reuse
```
• "Unit of the Week" spotlight (specs + who it's perfect for + book link)
• "Party Tip" carousel (planning/safety/space)
• "Real Party" social-proof post (photo + review quote)
• "This or That" engagement poll (theme A vs theme B)
• "Booking Now" urgency post (open dates this month)
```

## Guardrails
- Pull trends/holidays live so content stays current. • Keep claims truthful; don't fake reviews or results. • Get photo/UGC permission before reposting customer images. • Balance the mix — not every post is a sales pitch.

## Sharing
Provider-agnostic — runs on any company's `business_profile`. Share as-is or as a `.skill`.
