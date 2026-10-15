# Fairplug

**Get paid when your AI agent recommends something, and tell your users so.**

Fairplug is one MCP tool that turns your agent's product, SaaS and travel recommendations into tracked affiliate links, each with a disclosure label your users can see. Many programs, one payout. Early pilot: we're onboarding 5 agent builders by hand.

> Fairplug is an early pilot, not a finished product. There are no users or revenue yet, and nothing here should be read as a claim that there are.

---

## How it works

1. **Your agent searches offers.** When a user has decided what they want ("a hotel in Kyoto under $150", "a CRM for a 5-person team"), your agent calls `search_offers` with the category, location and budget. Matching is deterministic (category, geo, price, availability), not ad copy written by an LLM.
2. **It gets a tracked link plus a disclosure label.** `get_tracked_link` returns a signed tracked link and a short disclosure label (for example *"Paid link: we may earn a commission"*) to show next to the recommendation. Your agent still decides what to recommend. Fairplug only makes the link pay.
3. **You get one payout.** Fairplug tracks validated commissions across the affiliate programs and networks behind the offers, and pays you once a month. You get one statement instead of a dozen dashboards.

```text
search_offers(query, category, geo, budget)  ->  offers[]
get_tracked_link(offer_id, placement)        ->  { url, disclosure_label, expires_at }
```

---

## The pricing promise: Open-book 10%

> **We keep 10% of what you earn, plus payout fees at cost. Never more than 15% in total.**

- **10% of validated commissions.** We only earn when you do: after the merchant or network confirms the sale or lead.
- **Fees at cost.** Payment-rail fees (for example Stripe Connect payout fees) are passed through at cost and itemised on every statement.
- **15% all-in cap.** Our fee plus the pass-through fees never exceeds 15% of your commission.
- **Small print, said plainly.** There is a US$0.50 minimum platform fee per validated conversion, still subject to the 15% cap. Payouts go out monthly once you're above US$50. We pay when we've been paid: we don't front money we haven't received. New publishers have a 10% reserve held for 90 days to cover clawbacks.

---

## Disclosure-first, by design

Trust is the product. If users stop trusting agent recommendations, everyone loses.

- **Every link carries a disclosure.** Each tracked link comes with a disclosure label and render templates. No disclosure shown, no payout.
- **Your agent picks, we don't.** Offers are data, never instructions. Fairplug never injects text into your agent's answer or tells it what to recommend.
- **No LLM-written ads.** Matching is deterministic and explainable.
- **Open statements.** Every commission, fee and payout appears on a statement you can check line by line.
- **Sensible exclusions.** Regulated categories (health, credit and financial products, political) are out of scope for the pilot.

---

## FAQ

**Is this live?**
It's an early pilot. The MCP tool and payouts are being built and tested with a small group of builders. Expect rough edges. I'll do the integration with you myself and fix what breaks.

**Which programs and categories are covered?**
The pilot focuses on travel (hotels, tours, flights, eSIM, car hire), B2B SaaS (trials and signups) and retail shopping, through existing affiliate networks and programs. Coverage grows with pilot needs. Tell us which merchants your users ask for.

**Do I have to change what my agent recommends?**
No. Your agent keeps choosing on merit. Fairplug only returns a tracked link and a disclosure for the choice your agent already made, if a matching offer exists.

**How and when do I get paid?**
Monthly, once your validated balance is above US$50, after the merchant or network has paid us. Commissions are validated first. Returns, cancellations and fraud can reverse a commission, and that's normal in affiliate.

**Why should I trust the fee?**
Because it's open-book: 10%, fees at cost, a 15% cap, and an itemised statement. If the numbers don't add up, you'll be able to see it.

---

## Join the pilot

We're looking for **5 independent agent builders** (shopping, travel or SaaS-recommendation agents and MCP servers) who want to try disclosed commissions in a real product.

**What you get:** hands-on integration help from the founder, direct input on the tool design and disclosure spec, and the Open-book 10% pricing locked in for pilot partners.

**[Join the pilot](mailto:fairplughq@gmail.com?subject=Fairplug%20pilot)**: email us with your agent's name and what it recommends.

Or reach out directly: Kunal Adhia, founder. X: [@FairPlugHQ](https://x.com/FairPlugHQ) · Email: [fairplughq@gmail.com](mailto:fairplughq@gmail.com) · GitHub: [github.com/fairplug](https://github.com/fairplug)

---

<sub>Fairplug is an early-stage project. Nothing here is a financial, legal or tax offer. Affiliate programs set their own terms, and merchants and networks can reverse commissions.</sub>
