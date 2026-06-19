# Weekly Report

## Purpose

Produce the weekly performance report that summarizes what happened across all active channels in the past 7 days. The weekly report is not a data dump - it is a narrative summary of what the numbers mean, what changed, and what the team should do about it. The output is a client-ready or director-ready document that requires no additional interpretation.

## Used By

- Analytics Agent (primary)
- Marketing Director (reviews before distribution)

## Trigger

Use every Monday morning (or the defined weekly reporting day) to cover the prior 7-day period.

## Inputs Needed

- All active channel performance data for the week (Meta Ads, Google Ads, email, CRM) - required
- Targets or benchmarks for each metric - required
- Prior week data for comparison - required
- Any campaign changes or events during the week - helpful

## Process

**Step 1: Pull the data**

Data sources to pull before writing:
- Meta Ads Manager: Impressions, Reach, CPM, CTR, CPC, Leads, CPL, Amount Spent
- Google Ads (if active): Impressions, Clicks, CTR, CPC, Conversions, CPA, Spend
- GHL CRM: Leads by stage, Booked, Showed, Closed, Revenue
- Email (if active): Open rate, Click rate, Unsubscribes, Conversions

Pull 7-day rolling window, same window from the prior week.

**Step 2: Complete the metrics table**

For each metric, show: this week, last week, and the target.

**Step 3: Write the findings**

Each finding must follow a four-part format:
[Metric] [direction] [magnitude] [probable cause]

Example: "CPL increased 23% week over week, from $18 to $22, likely due to creative fatigue on the top-performing ad set which has now exceeded 3.5x frequency."

Do not write findings that are just data. "CPL was $22" is not a finding.

**Step 4: Write the risk flags**

What could go wrong in the next 7 days if nothing changes? These are early warnings, not confirmed problems.

**Step 5: Write the recommended actions**

For each finding that warrants action, write one recommendation with:
- What to do
- Who handles it (which agent or team member)
- By when

## Output Format

```
WEEKLY PERFORMANCE REPORT - [Client] - Week of [Date Range]
Prepared by: Analytics Agent

---

EXECUTIVE SUMMARY (2-3 sentences):
[What happened this week in plain language. Lead with the most important thing.]

---

METRICS SNAPSHOT:

PAID ADVERTISING:
| Metric | This Week | Last Week | Change | Target | Status |
|--------|---------|---------|--------|--------|--------|
| Ad Spend | $[X] | $[X] | [+/-X%] | $[X] | [On track / Over / Under] |
| Impressions | [X] | [X] | [+/-X%] | - | - |
| CTR | [X%] | [X%] | [+/-X%] | 2%+ | [Above / Below target] |
| CPL | $[X] | $[X] | [+/-X%] | $[X] | [Above / Below target] |
| Leads | [X] | [X] | [+/-X%] | [X] | [On track / Off] |

FUNNEL:
| Stage | This Week | Last Week | Change | Target Rate | Status |
|-------|---------|---------|--------|------------|--------|
| Leads | [X] | [X] | [+/-X] | - | - |
| Booked | [X] | [X] | [+/-X] | 60%+ of leads | [...] |
| Showed | [X] | [X] | [+/-X] | 70-80% of booked | [...] |
| Closed | [X] | [X] | [+/-X] | 20-30% of showed | [...] |
| Revenue | $[X] | $[X] | [+/-X%] | $[X] | [...] |

---

FINDINGS:

1. [Metric] [direction] [magnitude] [cause]

2. [Metric] [direction] [magnitude] [cause]

3. [Continue for all notable changes, positive and negative]

---

RISK FLAGS FOR NEXT 7 DAYS:

- [Specific risk] - if [condition], expect [outcome]

---

RECOMMENDED ACTIONS:

| Priority | Action | Owner | Due |
|---------|--------|-------|-----|
| High | [Specific action] | [Agent/Person] | [Date] |
| Medium | [Action] | [Agent/Person] | [Date] |

---

CONTEXT / NOTES:
[Any campaign changes, external factors, or client communications that affected this week's data]
```

## Quality Check

- [ ] Every finding has all four parts (metric, direction, magnitude, cause)
- [ ] Metrics table shows this week, last week, and target
- [ ] Recommended actions each have an owner and a due date
- [ ] Executive summary leads with the most important thing
- [ ] Risk flags are forward-looking

## Status

Phase 3 complete.
