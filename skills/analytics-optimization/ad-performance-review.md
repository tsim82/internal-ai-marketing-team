# Ad Performance Review

## Purpose

Diagnose ad performance at the campaign, ad set, and ad level and produce specific decisions (scale, kill, iterate, or test) for every active element. The output is a decision table that the Paid Ads Agent executes without needing to re-analyze the data.

## Used By

- Analytics Agent (primary - reads data and produces the review)
- Paid Ads Agent (executes the decisions)

## Trigger

Use weekly as part of the regular reporting cycle, or immediately when CPL spikes, spend efficiency drops, or a campaign is underperforming versus target.

## Inputs Needed

- Meta Ads Manager data (last 7 days or the review period) - required
- Campaign structure (campaigns, ad sets, ads) - required
- Target CPL, Target CPA, and monthly budget - required
- Historical data for comparison (prior week minimum) - required

## Process

**Step 1: Read metrics in the correct order**

Do not jump to CPL first. Read in this order:

1. **Impressions**: Is the campaign getting delivery? Low impressions = budget, audience, or bid issue.
2. **Frequency**: Is frequency above 3.5 in 7 days? If yes, creative fatigue is likely regardless of other metrics.
3. **CTR**: Is CTR above 1%? Under 0.5% = creative or hook problem.
4. **CPC**: Is CPC within range? High CPC with low CTR = creative. High CPC with good CTR = audience competition.
5. **LP CVR**: Is the landing page converting at 25-40%? Below 20% = page problem, not ad problem.
6. **CPL**: Is CPL above or below target?
7. **Lead quality**: Are leads converting downstream (booked, showed, closed)?

**Step 2: Diagnose each underperforming element**

Common pattern table:

| Pattern | Diagnosis | Fix |
|---------|----------|-----|
| High CPL + Low CTR | Creative fatigue or wrong hook | Rotate creative, new hooks |
| High CPL + Good CTR + Low LP CVR | Landing page problem | Fix page, check mobile load speed |
| High CPL + Good CTR + Good LP CVR + Poor lead quality | Targeting wrong audience | Tighten audience or adjust copy |
| Good CPL + Low scale | Budget constrained or audience too small | Increase budget or broaden audience |
| Good CTR + High CPC | Competitive auction | Adjust bid strategy or shift placement |

**Step 3: Make a decision for each ad**

Each active ad gets one of five decisions:
- **SCALE**: CPL below target, leads are quality. Increase budget 20%.
- **KEEP**: On target. Do not change.
- **ITERATE**: Within 20% of target, under 7 days. Small change to one variable.
- **KILL**: CPL 2x+ target with no conversions after sufficient spend (at least 5x CPL in budget), OR CTR under 0.3% after 3 days.
- **TEST**: New creative concept needed. Pull the creative brief.

**Step 4: Make campaign and ad-set level decisions**

After ad-level decisions, step up:
- If all ads in an ad set are being killed, kill the ad set
- If one ad is scaling, consider duplicating the ad set to scale further
- Redistribute budget toward top-performing campaigns

## Output Format

```
AD PERFORMANCE REVIEW - [Client] - [Date Range]
Prepared by: Analytics Agent

ACCOUNT OVERVIEW:
  Total Spend: $[X]
  Total Leads: [X]
  Overall CPL: $[X] vs. Target: $[X]
  Overall Status: [On track / Needs attention / Off track]

---

CAMPAIGN BREAKDOWN:

CAMPAIGN: [Campaign Name]
  Type: [Lead gen / Retargeting / TOF / MOF / BOF]
  Spend: $[X] | Leads: [X] | CPL: $[X] | Target: $[X]
  Status: [On track / Needs attention / Off track]

  AD SET: [Ad Set Name]
    Audience: [Brief description]
    Frequency: [X] - [OK / WARNING: fatigue]
    CTR: [X%] | CPC: $[X] | LP CVR: [X%] | CPL: $[X]

    AD DECISIONS:

    | Ad Name | CPL | CTR | Frequency | Lead Quality | Decision | Action |
    |---------|-----|-----|-----------|-------------|---------|--------|
    | [Ad 1] | $[X] | [X%] | [X] | [Good/Low] | SCALE | Increase budget 20% |
    | [Ad 2] | $[X] | [X%] | [X] | [Good/Low] | KILL | Pause today |
    | [Ad 3] | $[X] | [X%] | [X] | [Good/Low] | ITERATE | Test new hook |
    | [Ad 4] | $[X] | [X%] | [X] | [Good/Low] | KEEP | No change |

    Diagnosis: [Pattern from diagnosis table - what is the main issue?]

[Repeat for each ad set and campaign]

---

ACCOUNT-LEVEL DECISIONS:

| Decision | Element | Action | Owner | Due |
|---------|---------|--------|-------|-----|
| SCALE | [Ad name] | Increase budget 20% on [ad set] | Paid Ads Agent | [Date] |
| KILL | [Ad name] | Pause today | Paid Ads Agent | Today |
| TEST | [Ad set] | New creative brief needed - [concept direction] | Creative Design Agent | [Date] |

---

CREATIVE BRIEF REQUESTS:

Brief 1: [Concept direction for replacement creative]
Hand to Creative Design Agent via ad-creative-brief.md

---

NOTES:
[Budget pacing notes, account-level patterns, anything the Paid Ads Agent needs to know]
```

## Quality Check

- [ ] Metrics were read in order (Impressions through Lead quality)
- [ ] Every active ad has a decision
- [ ] Kill decisions include the specific reason
- [ ] Scale decisions are capped at 20% budget increase
- [ ] Creative brief requests are noted for every killed ad
- [ ] Frequency above 3.5 is flagged even if CPL is still acceptable

## Status

Phase 3 complete.
