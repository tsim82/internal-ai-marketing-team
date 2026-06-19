# Budget Planning

## Purpose

Build a realistic ad and marketing budget tied to a specific revenue goal. Works backward from the revenue target to determine what needs to be spent, at what CPL and close rate, to hit the number. The output is a budget plan the CFO Agent and Marketing Director use to approve or adjust spend before a campaign launches.

## Used By

- CFO Agent (primary)
- Paid Ads Agent (executes against this budget)
- Marketing Director (reviews for strategic alignment)

## Trigger

Use when starting a new campaign, planning a launch, reviewing monthly spend allocation, or when a client asks "how much should I spend on ads?"

## Inputs Needed

- Revenue goal for the campaign or period - required
- Offer price - required
- Expected close rate (booked call to closed) - required or estimated
- Expected show rate (booked to showed) - required or estimated
- Expected lead-to-booked rate - required or estimated
- Historical CPL if available - helpful (otherwise estimate from market benchmarks)
- Platform(s) being used - required

## Process

**Step 1: Work backward from the revenue goal**

Start with the revenue goal and reverse-engineer every step of the funnel.

```
Revenue goal: $[X]
Offer price: $[X]
Customers needed: Revenue goal / Offer price = [N] customers

Close rate (showed-to-closed): [X]%
Calls showed needed: Customers / Close rate = [N] showed calls

Show rate (booked-to-showed): [X]%
Calls booked needed: Showed calls / Show rate = [N] booked calls

Lead-to-booked rate: [X]%
Leads needed: Booked calls / Lead-to-booked rate = [N] leads
```

**Step 2: Calculate the required budget**

```
Leads needed: [N]
Target CPL: $[X] (from historical data or platform benchmark)
Required spend: Leads needed x Target CPL = $[X]

If no historical CPL: use these starting benchmarks by niche
- Service business / coaching: $15-60 CPL for Meta
- Home services: $25-80 CPL for Meta / Google
- B2B lead gen: $40-120 CPL for Meta, $80-200 for Google
- E-commerce: ROAS-based, not CPL
```

**Step 3: Sanity check the math**

Does the math work at these inputs? Calculate the blended ROAS:

```
Revenue generated: $[X]
Total ad spend: $[X]
ROAS: Revenue / Ad spend = [X]x
```

For most service businesses, a minimum viable ROAS is 3x (spend $1, make $3). If the math does not hit 3x at the target CPL and close rate, either the price needs to increase, the close rate needs to increase, or the CPL target needs to come down.

**Step 4: Set the minimum test budget**

Meaningful test data requires hitting statistical significance. A test period needs enough leads to identify patterns.

Minimum test budget calculation:
```
Minimum leads to test: 20-30 leads per significant variable
Minimum spend: 20 x Target CPL = $[X]
Minimum test period: 7-14 days at this spend level
```

Do not cut a campaign that has spent less than 2x the target CPL. It has not had enough data.

**Step 5: Build the phased budget**

Phase the spend to match the campaign stage:

- **Week 1-2 (Learning)**: Start at $[X]/day. Goal is data, not ROAS. Do not optimize yet.
- **Week 3-4 (Optimizing)**: Cut non-performers, scale early winners. Budget may stay flat or increase slightly.
- **Month 2+ (Scaling)**: Once CPL is stable below target, scale by 20% per week maximum. Scaling too fast resets the algorithm.

## Output Format

```
BUDGET PLAN - [Client/Campaign] - [Date]

REVENUE GOAL: $[X] ([Period: month / launch / quarter])
OFFER PRICE: $[X]
FUNNEL ASSUMPTIONS:
  Lead-to-booked rate: [X]%
  Show rate: [X]%
  Close rate: [X]%

---

LEADS NEEDED TO HIT GOAL: [N] leads

REVERSE-ENGINEERED FUNNEL:
  Customers needed: [N]
  Calls showed needed: [N]
  Calls booked needed: [N]
  Leads needed: [N]

---

BUDGET CALCULATION:
  Target CPL: $[X] ([Historical / Benchmark estimate])
  Required spend: $[X] total / $[X] per day over [N] days
  Platform split:
    Meta: $[X]/day ([X]%)
    Google: $[X]/day ([X]%)
    Other: $[X]/day ([X]%)

---

PROJECTED ROAS: [X]x
MIN VIABLE ROAS: 3x
Status: [Viable / Needs adjustment - see notes]

---

MINIMUM TEST BUDGET: $[X] over [N] days
Reasoning: [X] leads at $[X] CPL = sufficient to identify pattern

---

PHASED SPEND PLAN:
  Week 1-2: $[X]/day (Learning phase - do not optimize)
  Week 3-4: $[X]/day (Optimization phase)
  Month 2+: $[X]/day (Scaling phase - 20% weekly increase max)

---

NOTES:
[Any assumptions, risks, or conditions that would change this plan]
```

## Quality Check

- [ ] Revenue goal is specific (not "grow revenue," but "$30,000 in May")
- [ ] Math is shown, not just the final number
- [ ] CPL assumption is sourced (historical data or named benchmark)
- [ ] ROAS sanity check is performed
- [ ] Minimum test budget is documented
- [ ] Phased plan is included so the team knows not to over-optimize in week 1

## Status

Phase 3 complete.
