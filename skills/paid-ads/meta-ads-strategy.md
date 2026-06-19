# Meta Ads Strategy

## Purpose

Produce the full strategic plan for a Meta (Facebook/Instagram) advertising campaign: campaign type, budget structure, audience strategy, funnel stage alignment, and bid strategy. The output is the plan the Paid Ads Agent uses to set up and run the campaign. It is not a checklist - it is a documented strategic rationale with specific decisions made.

## Used By

- Paid Ads Agent (primary)
- Marketing Director (reviews for alignment with campaign goals)
- CFO Agent (reviews budget allocation)

## Trigger

Use when launching a new Meta campaign, when restructuring an underperforming campaign, or when scaling a campaign that is working.

## Inputs Needed

- Offer name, price, and goal (lead gen, purchase, application) - required
- Budget (daily or monthly) - required
- Audience data: any custom audiences, lookalikes, or only interest targeting - required
- Funnel stage: TOF (new cold traffic), MOF (warm), or BOF (retargeting) - required
- Prior campaign data (if restructuring) - helpful
- Copy and creative ready to launch or in progress - helpful

## Process

**Step 1: Decide campaign type**
- Lead gen campaign: Use Leads objective if going to Meta's native lead form. Use Conversions (Lead event) if going to an external landing page. Never use Traffic objective for lead gen campaigns.
- Purchase campaign: Use Purchases objective with full pixel and Conversions API setup.
- Application / call booking: Use Leads or Conversions depending on where the form lives.

**Step 2: Decide CBO vs ABO**
- Start new campaigns in CBO (Campaign Budget Optimization) with 1-3 ad sets containing 3-5 ads each.
- Use ABO only when testing specific ad sets against each other with controlled budgets, or when scaling proven ad sets.
- Standard starting structure: 1 campaign / 3 ad sets / 3-5 ads per ad set.

**Step 3: Build the audience strategy**

Cold traffic (TOF):
- Broad: no interests, no lookalikes. Age and gender only (if relevant). Let the pixel and creative do the targeting. Works well with budgets above $100/day and strong creative.
- Interest stacking: 1-2 broad interests per ad set, not 10 narrow ones. Wider audiences give the algorithm more room.
- Lookalikes: 1-3% LAL of buyers or best customers. Do not use leads as the source - use buyers or the top 20% of leads by LTV.

Warm traffic (MOF):
- Video viewers (50%+): retarget people who watched more than half of a video ad
- Engagement retargeting: people who interacted with the page, IG profile, or lead form
- Website traffic: pixel-based audiences from landing page visitors (90-day window)

Retargeting (BOF):
- Website visitors who did not convert (30-day window)
- Lead list (uploaded customer/lead list)
- Cart abandoners if applicable

Exclusions: Always exclude buyers from cold traffic. Exclude opt-in page visitors from top of funnel.

**Step 4: Set the bid strategy**

Starting out or under 50 conversions/week: Highest Volume (no cost cap). Let Meta optimize.

Once getting 50+ conversions/week: Consider Cost Cap or Bid Cap.
- Cost Cap: sets the average cost you are willing to pay. More stability but may limit delivery.
- Bid Cap: hard ceiling. Reduces delivery more but maintains cost discipline.

Do not use Cost Cap or Bid Cap until the pixel has enough data. Imposing limits too early starves the algorithm.

**Step 5: Set the naming convention**
Every element must be named consistently so the team can read reports without decoding.

```
Campaign: [Client]-[Offer]-[Objective]-[Date] 
  Example: Acme-LeadGen-Leads-2026-06

Ad Set: [Audience Type]-[Audience Description]-[Placement]
  Example: TOF-Broad-30M-Feed | MOF-VideoViewers50pct | BOF-Retarget30d

Ad: [Hook]-[Format]-[Angle]
  Example: Pain-Static-AgencyFail | Proof-Video-Client47Leads
```

**Step 6: Plan the budget allocation by funnel stage**

Standard starting allocation:
- TOF: 70% of budget
- MOF: 20% of budget
- BOF: 10% of budget

As retargeting audience builds and quality leads accumulate, shift more to MOF and BOF.

## Output Format

```
META ADS STRATEGY - [Client/Offer] - [Date]

CAMPAIGN GOAL: [Lead gen / Purchase / Application]
TOTAL BUDGET: $[X]/day or $[X]/month
FUNNEL STAGE FOCUS: [TOF / MOF / BOF / All]

---

CAMPAIGN STRUCTURE:

Campaign: [Name per convention]
  Objective: [Leads / Conversions / etc.]
  Budget type: [CBO]
  Daily budget: $[X]

Ad Set 1: [Name per convention]
  Audience: [Description]
  Size: ~[X]M people
  Placement: [Automatic / Manual - specify]
  
Ad Set 2: [Name per convention]
  [Same format]

Ad Set 3: [Name per convention]
  [Same format]

---

AUDIENCE PLAN:

TOF Audiences:
  Ad Set 1: [Broad / Interest stack - description]
  Ad Set 2: [LAL - source and percentage]

MOF Audiences (if applicable):
  [Video viewers / Engagement / Website visitors]

BOF Audiences (if applicable):
  [Retargeting - window and source]

Exclusions:
  All cold: Exclude [buyers, opt-in visitors]
  [Other relevant exclusions]

---

BID STRATEGY: [Highest Volume / Cost Cap $[X] / Bid Cap $[X]]
Rationale: [Why this bid strategy for this stage]

---

BUDGET SPLIT:
  TOF: $[X]/day ([X]%)
  MOF: $[X]/day ([X]%)
  BOF: $[X]/day ([X]%)

---

NAMING CONVENTION:
  Campaign: [Example]
  Ad Set: [Example]
  Ad: [Example]

---

NOTES:
  Pixel status: [Confirmed working / Needs verification]
  Custom conversions needed: [List]
  Minimum conversion threshold before cost cap: [50 events/week]
  Creative status: [Ready / In progress - status]
```

## Quality Check

- [ ] Campaign objective matches the conversion goal (not Traffic for lead gen)
- [ ] CBO used for new campaigns unless ABO rationale is explicit
- [ ] Audiences have estimated size noted
- [ ] Exclusions documented
- [ ] Naming convention is consistent and decodable
- [ ] Budget split documented with rationale
- [ ] Bid strategy appropriate to current conversion volume
- [ ] Creative status confirmed before launch

## Status

Phase 3 complete.
