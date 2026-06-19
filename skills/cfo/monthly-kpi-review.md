# Monthly KPI Review

## Purpose

Review the key financial and marketing performance metrics for the month. Compare against targets set at the start of the period. Flag what changed, what is off-track, and what decisions need to be made in the next 30 days. The output is a monthly performance summary the Marketing Director and client use for strategic decisions.

## Used By

- CFO Agent (primary)
- Analytics Agent (provides the data, Analytics Agent owns ad metrics, CFO Agent owns financial)
- Marketing Director (receives and reviews)

## Trigger

Use at the end of each month for any active client or campaign. Should be produced within the first 3 business days of the new month.

## Inputs Needed

- Revenue for the month - required
- Ad spend for the month - required
- Lead volume (total and by source) - required
- Lead-to-booked rate - required
- Booked-to-showed rate - required
- Close rate (showed-to-closed) - required
- Monthly targets set at the start of the period - required
- Prior month data for comparison - required

## Process

**Step 1: Confirm all data is in before writing**

Do not write the review with incomplete data. The findings section is meaningless if ad spend or conversion rates are still being counted. Confirm that revenue is finalized for the period and all leads are attributed.

**Step 2: Build the KPI table**

Compare each metric against:
1. The target set for the month
2. The prior month's actual

| Metric | Target | Actual | vs Target | vs Prior Month |
|--------|--------|--------|-----------|---------------|
| Revenue | $[X] | $[X] | [+X% / -X%] | [+X% / -X%] |
| Ad spend | $[X] | $[X] | [on target / over / under] | [comparison] |
| ROAS | [X]x | [X]x | [...] | [...] |
| Leads | [N] | [N] | [...] | [...] |
| CPL | $[X] | $[X] | [...] | [...] |
| Lead-to-booked rate | [X]% | [X]% | [...] | [...] |
| Show rate | [X]% | [X]% | [...] | [...] |
| Close rate | [X]% | [X]% | [...] | [...] |
| Customers acquired | [N] | [N] | [...] | [...] |
| CPA (cost per customer) | $[X] | $[X] | [...] | [...] |

**Step 3: Identify the top 3 findings**

A finding is: metric + direction + magnitude + cause.

Example finding (good): "Revenue came in at $47,200, up 18% vs the prior month. The increase is tied directly to the new nurture sequence deployed in week 3 - booked call rate from the email list went from 12% to 19%."

Example finding (bad): "Revenue was good this month." (Not a finding - no direction, no cause)

One finding per metric does not make sense. Look for what was meaningful: what moved the needle positively, what was a warning sign, and what was surprising.

**Step 4: Flag risks for the next 30 days**

Based on the current data, what could go wrong next month if nothing changes? Examples:
- "Ad creative is showing frequency above 3.0 in the retargeting audiences. If new creative is not added by [date], CPL will rise."
- "The close rate dropped 4 points this month. If the sales conversation is not reviewed, this will affect next month's revenue."
- "Current cash position covers only 5 weeks of ad spend at this rate. Budget review needed before scaling further."

**Step 5: Write the recommended actions**

Each action must name who does it and by when. Unassigned action items do not get done.

## Output Format

```
MONTHLY KPI REVIEW - [Client] - [Month/Year]

REVIEW PERIOD: [Month] [Year]
PREPARED BY: CFO Agent
DATE: [Date]

---

PERFORMANCE SUMMARY:

Revenue: $[X] vs target $[X] ([+/-X%]) | vs prior month: [+/-X%]
[One sentence summary: "Hit target / Missed by X / Beat by X - context sentence"]

---

KPI TABLE:

| Metric | Target | Actual | vs Target | vs Prior Month |
|--------|--------|--------|-----------|---------------|
| Revenue | $[X] | $[X] | [X%] | [X%] |
| Ad spend | $[X] | $[X] | [on target/over/under] | [X%] |
| ROAS | [X]x | [X]x | [...] | [...] |
| Total leads | [N] | [N] | [...] | [...] |
| CPL | $[X] | $[X] | [...] | [...] |
| Lead-to-booked | [X]% | [X]% | [...] | [...] |
| Show rate | [X]% | [X]% | [...] | [...] |
| Close rate | [X]% | [X]% | [...] | [...] |
| Customers | [N] | [N] | [...] | [...] |
| CPA | $[X] | $[X] | [...] | [...] |

---

TOP 3 FINDINGS:

1. [Metric + direction + magnitude + cause]

2. [Metric + direction + magnitude + cause]

3. [Metric + direction + magnitude + cause]

---

RISK FLAGS FOR NEXT 30 DAYS:

1. [Risk: what could go wrong, why, and timeline]

2. [Risk: same format]

---

RECOMMENDED ACTIONS:

1. [Action] | Owner: [Agent or person] | Due: [Date]

2. [Action] | Owner: [Agent or person] | Due: [Date]

3. [Action] | Owner: [Agent or person] | Due: [Date]

---

NOTES:
[Anything else the team needs to know: data quality issues, external factors, caveats]
```

## Quality Check

- [ ] All data points are confirmed final before writing
- [ ] Every metric has a target to compare against (not just prior month)
- [ ] Each finding includes metric + direction + magnitude + cause (all four)
- [ ] At least one risk flag for the next 30 days
- [ ] Every recommended action has an owner and a due date
- [ ] Review is produced within first 3 business days of the new month

## Status

Phase 3 complete.
