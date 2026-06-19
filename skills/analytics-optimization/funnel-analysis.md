# Funnel Analysis

## Purpose

Identify where leads are dropping out of the funnel and diagnose why. A funnel analysis pinpoints the specific conversion point that is underperforming, confirms it with data, and produces a prioritized fix list. The output tells the team exactly where to focus, not a general sense that "the funnel could be better."

## Used By

- Analytics Agent (primary)
- Marketing Director (prioritizes fixes based on the output)
- Paid Ads, Copywriter, Funnel Agent, or CRM Follow-Up Agent (acts on specific fixes)

## Trigger

Use when a revenue target is being missed, when conversion rates have declined week over week, when CPL is acceptable but closed clients are not resulting, or monthly as a standard health check.

## Inputs Needed

- CRM data for the review period (leads by stage) - required
- Benchmarks for each stage conversion rate - required
- Date range - required
- Any changes made to the funnel during this period - helpful

## Process

**Step 1: Map the funnel and calculate conversion rates**

Pull data for the period and calculate each stage-to-stage conversion rate.

Benchmark conversion rates for a call-booking service funnel:

| Stage transition | Good | Needs attention | Broken |
|----------------|------|----------------|--------|
| Lead to Contacted (within 24h) | 80%+ | 60-80% | Under 60% |
| Contacted to Qualified | 40-60% | 25-40% | Under 25% |
| Qualified to Call Booked | 50-70% | 30-50% | Under 30% |
| Call Booked to Showed | 70-80% | 50-70% | Under 50% |
| Showed to Closed/Won | 20-30% | 10-20% | Under 10% |

**Step 2: Identify the biggest drop-off point**

The biggest drop-off is the highest-priority fix. Calculate absolute volume lost at each stage, not just rate. A 50% drop on 100 leads loses 50. A 70% drop on 10 leads loses 7. Fix the bigger volume leak first.

**Step 3: Diagnose the cause of the biggest drop-off**

Common causes by stage:

| Biggest drop-off at | Most common causes |
|--------------------|-------------------|
| Lead to Contacted | Slow speed-to-lead / bad phone numbers / wrong contact info |
| Contacted to Qualified | Targeting wrong audience / qualification criteria misaligned |
| Qualified to Booked | Booking friction / link broken / not following up after qualifying |
| Booked to Showed | No reminder sequence / calls scheduled too far out |
| Showed to Closed | Pitch issues / offer mismatch / pricing misaligned / no guarantee |

**Step 4: Check for compounding issues**

Sometimes two stages are off. Note all stages below benchmark, not just the worst one.

**Step 5: Produce the prioritized fix list**

For each underperforming stage:
- What is broken (with data)
- Most likely cause
- Recommended fix
- Agent who handles the fix
- Expected revenue impact if fixed

## Output Format

```
FUNNEL ANALYSIS - [Client] - [Date Range]
Prepared by: Analytics Agent

---

FUNNEL DATA:

| Stage | In | Out | CVR | Benchmark | Status |
|-------|---|-----|-----|-----------|--------|
| Total Leads | [N] | - | - | - | - |
| Contacted | [N] | [N] | [X%] | 80%+ | [Good / Attention / Broken] |
| Qualified | [N] | [N] | [X%] | 40-60% | [...] |
| Call Booked | [N] | [N] | [X%] | 50-70% | [...] |
| Showed | [N] | [N] | [X%] | 70-80% | [...] |
| Closed/Won | [N] | [N] | [X%] | 20-30% | [...] |

Revenue this period: $[X]
Revenue at benchmark rates (if funnel were healthy): $[X]
Revenue gap from funnel underperformance: $[X]

---

BIGGEST DROP-OFF POINT:

Stage: [Stage name]
Actual CVR: [X%]
Benchmark: [X%]
Volume lost: [N leads that should have converted, did not]
Revenue impact: $[X] (volume lost x average close value)

---

DIAGNOSIS:

Most likely cause: [Single most probable explanation with supporting evidence]
Contributing factors: [Any secondary causes]

Evidence:
- [Data point that supports the diagnosis]
- [Data point]

---

ALL STAGES BELOW BENCHMARK:

| Stage | CVR | Gap | Priority |
|-------|-----|-----|---------|
| [Stage] | [X%] | [-X%] | [1st / 2nd / 3rd fix] |

---

PRIORITIZED FIX LIST:

Fix 1 - [Stage]
  Problem: [What is broken with data]
  Cause: [Most likely reason]
  Recommended fix: [Specific action]
  Owner: [Which agent]
  Expected impact: [If fixed, CVR should improve to X%, adding N leads and $X revenue]

Fix 2 - [Stage]
  [Same format]

---

NOTES:
[Contextual factors - recent funnel changes, seasonal effects, data gaps]
```

## Quality Check

- [ ] Revenue impact of the biggest drop-off is calculated in dollars
- [ ] Every underperforming stage is listed, not just the worst one
- [ ] Diagnosis includes supporting evidence
- [ ] Every fix has an owner
- [ ] Expected impact is estimated for each fix

## Status

Phase 3 complete.
