# Pricing Analysis

## Purpose

Determine whether an offer is priced correctly for the market, the buyer, and the revenue goal. The output is a pricing recommendation with a rationale, a competitor price comparison, and clear criteria for when the price should go up, down, or stay the same.

## Used By

- CFO Agent (primary)
- Offer Agent (uses this to set or adjust the offer price)
- Copywriter (knows the anchor and frame to use in copy)
- Marketing Director (reviews before any price change goes to market)

## Trigger

Use when setting a price for a new offer, reviewing an existing offer that is not converting, or when a client is considering raising or lowering prices.

## Inputs Needed

- Product or service description - required
- Cost to deliver - required
- Revenue goal - required
- Competitor price range (from competitor research or client knowledge) - required
- Target audience income or budget range (from audience research) - helpful
- Current conversion rate if the offer is live - helpful
- Any prior prices tested and results - helpful

## Process

**Step 1: Calculate the price floor**

The price floor is the minimum price that makes the offer profitable at the target margin.

```
Cost to deliver: $[X]
Target gross margin: [X]% (typically 60-80% for digital/service)
Price floor: Delivery cost / (1 - Target margin) = $[X]
```

If the current price is below the price floor, the offer cannot be run at this price profitably at any conversion rate.

**Step 2: Map the competitor price range**

Pull 3-5 competitor prices for similar offers. Organize into:

| Competitor | Price | What is included | Notes |
|-----------|-------|-----------------|-------|
| [Name / Description] | $[X] | [Brief] | [Differentiator or weakness] |
| [...] | [...] | [...] | [...] |

Identify three zones:
- **Bottom of market**: discounted or budget options
- **Mid market**: most common price range
- **Premium**: top 20% price range and what justifies it

**Step 3: Identify the right price position**

Where should this offer sit in the market?

- **Bottom**: Only if competing on price is the strategy and delivery cost supports it. Not recommended for most service businesses.
- **Mid market**: Safe. Easier to position. Works when differentiation is moderate.
- **Premium**: Requires clear reason-to-charge-more: speed, guarantee, outcome specificity, proof, access level. Converts better at lower volume. Cannot be premium without proof.

**Step 4: Assess the price-to-value gap**

Perceived value must be higher than the price for the sale to happen. Check both sides:

Value side:
- What is the outcome worth to the buyer in dollars, time, or risk avoidance?
- What is the cost of the problem if unsolved?
- What is the cost of alternatives (hiring in-house, doing it themselves, competitor)?

Price side:
- Where does the price land relative to those alternatives?
- Does the price signal the quality of the outcome?

If the price is higher than perceived value: the offer needs to either have its value demonstrated better (copy and proof), or the price needs to come down.

If the price is much lower than perceived value: the offer is underpriced. Raising price may improve conversions if the market reads low price as low quality.

**Step 5: Make a recommendation**

State a specific price or price range and a clear rationale. Include:
- The recommended price
- Where it sits in the market (position)
- What makes it defensible (differentiation or proof)
- What would need to be true to change the recommendation

## Output Format

```
PRICING ANALYSIS - [Client/Offer] - [Date]

OFFER: [Name and brief description]
COST TO DELIVER: $[X]
REVENUE GOAL: $[X] per [month / launch / quarter]

---

PRICE FLOOR ANALYSIS:
Delivery cost: $[X]
Target margin: [X]%
Price floor (minimum to be profitable): $[X]

---

COMPETITOR PRICING:

| Competitor | Price | Included | Notes |
|-----------|-------|----------|-------|
| [Name] | $[X] | [Brief] | [...] |
| [Name] | $[X] | [Brief] | [...] |
| [Name] | $[X] | [Brief] | [...] |

Market zones:
  Budget: $[X range]
  Mid market: $[X range]
  Premium: $[X range]

---

VALUE-TO-PRICE ASSESSMENT:
Outcome value to buyer: [Qualitative + estimated dollar value if possible]
Cost of the problem unsolved: $[X estimate]
Best alternative cost: $[X]
Price-to-value verdict: [Underpriced / Well-positioned / Overpriced]

---

RECOMMENDED PRICE: $[X]

Position: [Bottom / Mid market / Premium]
Rationale: [One paragraph - why this price, why this position]
Defensibility: [What makes this price credible and justified]

WHAT WOULD CHANGE THE RECOMMENDATION:
- [Condition that would push price up]
- [Condition that would push price down]

---

COPY NOTE FOR COPYWRITER:
Price anchor to use: $[X] (what to compare the price against)
Anchor rationale: [Why this comparison is valid]
```

## Quality Check

- [ ] Price floor is calculated (not assumed)
- [ ] At least 3 competitor prices documented
- [ ] Value-to-price gap is assessed from the buyer's perspective
- [ ] Recommendation names a specific price, not a range
- [ ] Rationale explains why the price is defensible
- [ ] Copy anchor is provided for the Copywriter

## Status

Phase 3 complete.
