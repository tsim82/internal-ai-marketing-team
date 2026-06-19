# Offer Profitability

## Purpose

Calculate whether an offer is profitable at the current price, delivery cost, and acquisition cost. Identify the break-even point and minimum viable conversion rate or ROAS required to make the numbers work. The output tells the team whether to run ads against this offer and at what budget, or whether the price or delivery cost needs to adjust first.

## Used By

- CFO Agent (primary)
- Paid Ads Agent (sets CPL and ROAS targets from this analysis)
- Offer Agent (uses this to inform pricing decisions)
- Marketing Director (reviews before committing to a campaign budget)

## Trigger

Use before launching any paid campaign, before setting a budget, or when a campaign is running but profitability is unclear.

## Inputs Needed

- Offer price - required
- Cost to deliver or fulfill the offer - required
- Average CPL or CPA from ads (historical or estimated) - required
- Expected conversion rate (lead to customer) - required
- Refund rate (if known from prior offers or niche benchmarks) - helpful
- Any upsells or LTV considerations - helpful

## Process

**Step 1: Calculate gross margin per unit**

```
Offer price: $[X]
Cost to deliver: $[X]
Gross profit per sale: Price - Delivery cost = $[X]
Gross margin %: Gross profit / Price = [X]%
```

Delivery cost includes: contractor time, platform costs, software, fulfillment, and any direct variable costs. It does not include fixed overhead like general software subscriptions or office costs.

**Step 2: Calculate the maximum allowable CPA**

The maximum allowable CPA is the most the business can spend to acquire a customer and still make a profit. This sets the ceiling for ad spend targets.

```
Gross profit per sale: $[X]
Target net margin: [X]% (typically 20-40% for service businesses)
Target net profit per customer: Gross profit x Target margin = $[X]
Maximum allowable CPA: Gross profit - Target net profit = $[X]
```

Example: Gross profit is $2,000. Target net margin is 30%, so target net profit is $600. Max CPA is $2,000 - $600 = $1,400.

**Step 3: Calculate the break-even conversion rate**

If the CPA from ads is known or estimated, what conversion rate (lead to customer) is needed to break even?

```
Max allowable CPA: $[X]
Estimated CPL: $[X]
Leads needed per customer (break-even): Max CPA / CPL = [N]
Break-even conversion rate: 1 / (Max CPA / CPL) = [X]%
```

**Step 4: Calculate minimum viable ROAS**

For purchase campaigns or e-commerce, the same math applies but expressed as ROAS:

```
Revenue per customer: $[X]
Maximum allowable spend per customer (CPA): $[X]
Minimum viable ROAS: Revenue / Max CPA = [X]x
```

**Step 5: Account for refunds and churn**

```
Expected refund rate: [X]%
Effective revenue per customer: Price x (1 - Refund rate) = $[X]
Recalculate gross profit and max CPA using effective revenue
```

**Step 6: Layer in upsell/LTV if relevant**

If the business has a backend offer or recurring revenue, the economics can support a higher CPA:

```
Average LTV: $[X]
Average time to LTV: [N] months
Max CPA adjusted for LTV: [X]% of LTV (typically 30-50%)
```

Only use LTV to expand CPA targets if LTV is documented from real data, not a projection.

**Step 7: Write the verdict**

Is this offer profitable at the current metrics? What needs to be true for it to work?

## Output Format

```
OFFER PROFITABILITY ANALYSIS - [Client/Offer] - [Date]

OFFER PRICE: $[X]
DELIVERY COST: $[X]
GROSS PROFIT PER SALE: $[X] ([X]% margin)

---

ACQUISITION COST ANALYSIS:

Estimated CPL: $[X] ([Historical / Benchmark estimate])
Expected funnel conversion rate (lead to customer): [X]%
Implied CPA: CPL / Conversion rate = $[X]

Maximum allowable CPA at [X]% target margin: $[X]

---

BREAK-EVEN ANALYSIS:

Break-even conversion rate needed at estimated CPL: [X]%
Current expected conversion rate: [X]%
Status: [Above break-even / At break-even / Below break-even]

Minimum viable ROAS: [X]x
Expected ROAS at current metrics: [X]x

---

REFUND / CHURN ADJUSTMENT (if applicable):
Refund rate: [X]%
Effective revenue per customer: $[X]
Adjusted max CPA: $[X]

---

LTV CONSIDERATION (if applicable):
Estimated LTV: $[X]
LTV-adjusted max CPA: $[X]

---

VERDICT: [Profitable at current metrics / Marginally profitable - monitor closely / Not profitable - see recommendations]

RECOMMENDATIONS:
1. [Specific: what needs to change - price, delivery cost, conversion rate, or CPL target]
2. [If multiple issues: prioritize the one with the biggest impact]
```

## Quality Check

- [ ] Gross margin calculated with actual delivery costs, not estimates
- [ ] Max allowable CPA documented
- [ ] Break-even conversion rate is documented
- [ ] Refund rate is addressed (even if assumed at 0%)
- [ ] Verdict is clear: profitable, marginal, or not profitable
- [ ] Recommendations are specific, not vague

## Status

Phase 3 complete.
