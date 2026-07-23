# BounceBook — Reservation System Integration

**BounceBook** is the CRM and booking platform powering Wow Inflatables' online reservation system. It is purpose-built for bounce house and inflatable rental operators, handling everything from 24/7 online bookings and interactive quotes to automated follow-ups, driver scheduling, and payment processing — all with no transaction fees.

---

## What BounceBook Does

| Feature | Description |
|---|---|
| **Online Booking Engine** | Embeds directly on your website. Customers check availability, pick a unit, pay a deposit, and confirm — day or night, without a phone call. |
| **Lead Pipeline** | Every quote request, including half-finished bookings, lands in a visual pipeline so nothing slips through. |
| **Interactive Quotes** | Branded booking pages with photos, videos, and add-on options. Clients accept online; booking confirms instantly. |
| **Rental Agreements & Waivers** | Auto-generated from your template, personalised with booking details, and e-signed by the client. |
| **Deposits & Payments** | Online deposits and balances with zero transaction fees. Delivery fees calculate automatically by mileage. |
| **Automated Follow-Up** | Deposit reminders, weather-check nudges, delivery-day texts, post-event review requests, and upsell emails — all rule-based. |
| **Driver Portal** | Drivers get their own login to confirm jobs, routes, and load sheets. |
| **Calendar Sync** | Syncs with Google and Microsoft calendars to prevent double-booking. |
| **Financial Reporting** | Revenue by week, unit, and driver tracked in real time. |
| **Multi-Brand Support** | Run more than one brand; the right branding switches in automatically per booking. |

---

## Pricing

| Plan | Price | Users | Features |
|---|---|---|---|
| **Free** | $0/month forever | Up to 25 users | All features, unlimited bookings & inventory |
| **Pro** | $99/month | Unlimited users | All features, unlimited bookings & inventory |

No transaction fees. No card required to start. Cancel anytime.

---

## How BounceBook Is Integrated with Wow Inflatables

The live booking catalog for Wow Inflatables is embedded at:

- **Catalog / Rentals page:** `https://bouncebook-3fimm8bf.manus.space/rentals`
- **Direct booking link:** `https://bouncebook-3fimm8bf.manus.space/catalog`

These URLs are linked from `www.wowjumpparty.com` via "Book Now" and "Select" buttons throughout the site.

### Category Pre-Filtering (Advanced)

To send customers directly to a specific category (e.g., Water Slides), append a `?category=` parameter to the catalog URL and implement the following message-listener on the booking page:

```javascript
window.addEventListener("message", (event) => {
  if (event.data?.type === "SET_CATEGORY") {
    const btn = document.querySelector(`[data-category="${event.data.category}"]`);
    if (btn) btn.click();
  }
});
```

Add quick-links in your site navigation like:
- `/book?category=bounce-houses`
- `/book?category=water-slides`
- `/book?category=interactive-games`

After publishing, submit `/book` to Google Search Console (URL Inspection → Request Indexing) to ensure it is indexed as the canonical booking entry point.

---

## Booking Rules Configured for Wow Inflatables

The following business rules are active in the BounceBook configuration:

- **No same-day bookings** by customers (operators can override).
- **Rented items are blocked the following day** to allow for cleaning and inspection (operators can override).
- **Deposit options:** Customers may pay a flat deposit, the full amount, or any partial payment above the minimum deposit.
- **Timeout recovery:** If a customer is about to time out during checkout, an automated email is sent with a link to complete payment.
- **Multiple items** can be booked in a single transaction.

---

## Resources

- BounceBook Website: [https://bouncebook.com](https://bouncebook.com)
- Features Overview: [https://bouncebook.com/features](https://bouncebook.com/features)
- Pricing: [https://bouncebook.com/pricing](https://bouncebook.com/pricing)
- FAQ: [https://bouncebook.com/faq](https://bouncebook.com/faq)
- Support: hello@bouncebook.com

---

*Last updated: July 2026*
