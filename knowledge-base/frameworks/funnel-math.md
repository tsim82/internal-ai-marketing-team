# Funnel Math Framework

This is the reverse-engineered budget and lead planning model used across the CFO Agent, Paid Ads Agent, and Analytics Agent. Always start from the revenue goal and work backward.

---

## The Core Formula

**Work backward from revenue to leads:**

```
Revenue Goal
÷ Average Client Value
= Clients Needed

Clients Needed
÷ Close Rate (%)
= Calls/Shows Needed

Shows Needed
÷ Show Rate (%)
= Calls Booked Needed

Calls Booked Needed
÷ Booking Rate (%)
= Qualified Leads Needed

Qualified Leads Needed
÷ Qualification Rate (%)
= Total Leads Needed

Total Leads Needed
× Target CPL
= Required Ad Budget
```

---

## Benchmark Rates

Use these when real data is not available. Replace with actuals as soon as data exists.

| Stage Transition | Conservative | Good | Strong |
|----------------|-------------|------|--------|
| Lead to Booked | 30% | 50% | 70%+ |
| Booked to Showed | 60% | 75% | 85%+ |
| Showed to Closed | 15% | 25% | 35%+ |

**CPL benchmarks by niche** (starting point only - always verify):
- Service business (local): $15-40
- Online coaching/consulting: $20-60
- B2B lead gen: $40-150
- E-commerce (lead to sale): $5-25

---

## Example Calculation

**Scenario:** $50,000/month revenue goal, $3,000 average client value, standard benchmarks.

```
$50,000 ÷ $3,000 = 17 clients/month

17 ÷ 25% close rate = 68 shows needed

68 ÷ 75% show rate = 91 booked calls needed

91 ÷ 50% booking rate = 182 qualified leads needed

182 ÷ 60% qualification rate = 303 total leads needed

303 × $35 target CPL = $10,605 monthly ad budget
```

---

## Minimum Viable Budget Rule

Do not start a campaign with less than 20 leads' worth of budget.

```
Minimum Budget = 20 × Target CPL
```

At $35 CPL target: minimum $700 to get enough data for a decision.

---

## ROAS Sanity Check

After completing the funnel math, run this check:

```
Revenue from paid leads ÷ Ad Spend = ROAS

Minimum viable ROAS = 3x for most service businesses
If ROAS < 3x at target, the math does not work at current pricing or close rates
```

---

## Scaling Rule

Never increase budget more than 20% in a 7-day window. More than that resets the learning algorithm and burns budget.

---

## Where This Framework Is Used

- `skills/cfo/budget-planning.md` - Full budget planning process
- `skills/cfo/offer-profitability.md` - Break-even and max CPA calculation
- `skills/paid-ads/meta-ads-strategy.md` - Budget split guidance
- `skills/analytics-optimization/funnel-analysis.md` - Diagnosing where leads drop

---

## Status

Active. Use in every budget planning and funnel diagnosis session.
