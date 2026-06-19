# Cash Flow Check

## Purpose

Flag whether the business has the cash available to support a planned spend or investment without creating a cash flow problem. Revenue and profitability are different from cash on hand. This check prevents a client from committing to ad spend that will strain operations before the first sale comes back in.

## Used By

- CFO Agent (primary)
- Marketing Director (reviewed before approving spend)

## Trigger

Use before committing to a significant ad spend, launching a new campaign, hiring a contractor, or purchasing a major tool or software. Also use when a client says they want to "scale" but the financial picture is unclear.

## Inputs Needed

- Monthly revenue (current month or 3-month average) - required
- Monthly expenses (current) - required
- Cash on hand or available budget - required
- Proposed new spend and timing - required
- Time delay between spend and expected revenue return - required

## Process

**Step 1: Calculate the current monthly surplus**

```
Monthly revenue: $[X]
Monthly expenses: $[X]
Monthly surplus: Revenue - Expenses = $[X]
```

If expenses are greater than revenue: the business is cash-flow negative. Any new spend makes the situation worse. Flag immediately.

**Step 2: Account for the timing gap**

Ad spend goes out immediately. Revenue comes back on a delay. For most service businesses, the lag is:

- Lead gen: spend today, first payment in 2-6 weeks (depending on sales cycle)
- E-commerce: spend today, revenue in days, but ad spend is prepaid and revenue takes 3-7 days to clear
- High-ticket services: spend today, first close in 4-8 weeks

Calculate how much cash goes out before the first dollar returns:

```
Proposed daily spend: $[X]
Lag weeks before first revenue: [N] weeks
Cash required upfront: Daily spend x (N weeks x 7 days) = $[X]
```

**Step 3: Assess available cash coverage**

```
Cash on hand: $[X]
Required upfront spend: $[X]
Remaining cash after commitment: $[X]
Monthly expenses still to cover: $[X]
```

How many months of operating expenses does remaining cash cover?
```
Runway after commitment: Remaining cash / Monthly expenses = [N] months
```

**Step 4: Assign a risk level**

| Condition | Risk Level |
|-----------|-----------|
| Runway 3+ months after commitment | Low |
| Runway 1-3 months after commitment | Medium |
| Runway under 1 month after commitment | High |
| Cash on hand does not cover upfront spend | Critical |

**Step 5: Write the recommendation**

- **Low risk**: Proceed. Note the approved spend amount.
- **Medium risk**: Proceed with a budget cap. Identify what triggers a pause (e.g., "if we do not see qualified leads in 3 weeks, pause and reassess").
- **High risk**: Do not proceed at the proposed budget. Recommend a reduced budget the business can sustain for 60 days, or recommend building cash reserves first.
- **Critical**: Hard stop. The business cannot financially support this spend. Recommend alternative (organic, referral, or smaller test with available cash).

## Output Format

```
CASH FLOW CHECK - [Client] - [Date]

PROPOSED SPEND: $[X]/[day or month]
TIMING: [Campaign start date and estimated duration]

---

CURRENT FINANCIAL POSITION:
Monthly revenue: $[X]
Monthly expenses: $[X]
Monthly surplus: $[X]
Cash on hand: $[X]

---

TIMING ANALYSIS:
Expected lag (spend to first revenue): [N] weeks
Upfront cash required: $[X]
Remaining cash after commitment: $[X]
Runway remaining: [N] months

---

RISK LEVEL: [Low / Medium / High / Critical]

RECOMMENDATION: [Proceed / Proceed with cap of $[X] / Do not proceed at this amount / Hard stop]

RATIONALE:
[One paragraph explaining the decision in plain language]

CONDITIONS (if Medium or High risk):
- Trigger to pause: [Specific metric or timeline]
- Max spend before reassessment: $[X]
- What would need to be true to increase budget: [Condition]
```

## Quality Check

- [ ] Current monthly surplus is calculated, not assumed
- [ ] Timing gap between spend and revenue is accounted for
- [ ] Risk level is assigned with a clear rationale
- [ ] Recommendation is specific and actionable
- [ ] If Medium or High risk, conditions for pause are defined

## Status

Phase 3 complete.
