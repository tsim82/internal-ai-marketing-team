# Lead Quality Review

## Purpose

Assess whether the leads coming in are good leads. A lead quality review separates the CPL problem (traffic and conversion) from the lead quality problem (are these the right people?). If CPL is on target but close rates are low, the leads are likely wrong. The output is a lead quality score and specific recommendations for improving targeting, copy, or qualification criteria.

## Used By

- Analytics Agent (primary)
- Paid Ads Agent (adjusts targeting and creative based on findings)
- CRM Follow-Up Agent (adjusts qualification criteria)
- Marketing Director (escalates if lead quality is a strategic problem)

## Trigger

Use when close rates are below target despite acceptable CPL, when sales is complaining about lead quality, when show rates drop below 65%, or monthly as part of the standard analytics cycle.

## Inputs Needed

- CRM data for the period (all leads with stage history) - required
- Lead source breakdown (which campaigns generated which leads) - required
- Qualification data from form level - helpful
- Sales call outcomes (closed, not closed, stated reasons) - helpful
- Booked/showed/closed rates by lead source - required

## Process

**Step 1: Calculate lead quality by source**

Break down conversion rates per source (campaign, ad set, or form):

| Source | Leads | Booked% | Show% | Close% | Revenue | CPA |
|--------|-------|---------|-------|--------|---------|-----|
| [Source A] | [N] | [X%] | [X%] | [X%] | $[X] | $[X] |

A source with high lead count but low close rate is generating unqualified leads. A source with fewer leads but high close rate is worth scaling.

**Step 2: Review qualification data**

If the form captures qualification data:
- What % of leads met the qualification threshold?
- Which form questions are being answered in disqualifying ways?
- Is there a pattern in the disqualifying responses?

**Step 3: Check for audience-copy mismatch**

Signs that copy is attracting the wrong people:
- Common stated reason for not buying: "I thought this was for [X] not [Y]"
- High no-show rates from a specific source (means they did not really want the call)
- Short call durations

**Step 4: Score lead quality overall**

- **Strong (Green)**: Booked 60%+, Showed 70%+, Closed 20%+
- **Moderate (Yellow)**: Any stage 10-20% below benchmark
- **Weak (Red)**: Any stage 20%+ below benchmark
- **Broken (Critical)**: Multiple stages 20%+ below or CPA exceeds gross profit

**Step 5: Write source-specific recommendations**

For each source producing low-quality leads:
- Specific quality problem
- Most likely cause
- Recommended change
- Owner

## Output Format

```
LEAD QUALITY REVIEW - [Client] - [Date Range]
Prepared by: Analytics Agent

TOTAL LEADS REVIEWED: [N]

---

LEAD QUALITY SCORE: [Strong / Moderate / Weak / Broken]

Evidence:
  Booked rate: [X%] (Benchmark: 60%+)
  Show rate: [X%] (Benchmark: 70-80%)
  Close rate: [X%] (Benchmark: 20-30%)

---

PERFORMANCE BY SOURCE:

| Source | Leads | Booked% | Show% | Close% | Revenue | CPA | Rating |
|--------|-------|---------|-------|--------|---------|-----|--------|
| [Source] | [N] | [X%] | [X%] | [X%] | $[X] | $[X] | [Strong/Weak] |

Best source: [Name] - [Why]
Worst source: [Name] - [Why]

---

QUALIFICATION DATA (if available):

% of leads meeting full BANT criteria: [X%]
Most common disqualifying issue: [Budget / Authority / Need / Timeline]
Form questions showing high disqualification rates:
  - "[Question]": [X%] gave disqualifying answer of type "[Answer type]"

---

AUDIENCE-COPY MATCH CHECK:

Evidence of mismatch: [Yes / No]
Signs observed: [List any evidence]
Most likely copy issue: [What is the ad promising that is attracting the wrong people?]

---

SOURCE-SPECIFIC RECOMMENDATIONS:

SOURCE: [Name]
  Quality problem: [What is wrong with leads from this source]
  Likely cause: [Targeting / Copy / Form / Offer mismatch]
  Recommended change: [Specific action]
  Owner: [Paid Ads Agent / CRM Follow-Up Agent / Copywriter]

---

QUALIFICATION ADJUSTMENTS (if needed):

Current threshold: [What qualifies a lead today]
Recommended new threshold: [Change]
Rationale: [Why this improves quality]
Owner: CRM Follow-Up Agent - update lead-qualification.md
```

## Quality Check

- [ ] Lead quality is broken down by source (not just overall averages)
- [ ] All three downstream rates checked (booked, showed, closed)
- [ ] Lead quality score is given
- [ ] Audience-copy mismatch check is included
- [ ] Every source-specific recommendation has an owner
- [ ] Qualification criteria change is specific if recommended

## Status

Phase 3 complete.
