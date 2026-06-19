# Optimization Review

## Purpose

Conduct a structured review of active campaign performance and produce specific optimization actions. Not a data report - a set of decisions. Every review ends with a numbered action list where each item names what to change, why, and who executes it.

## Used By

- Paid Ads Agent (primary - runs and acts on the review)
- Analytics Agent (provides the data, receives recommendations)
- Marketing Director (receives the action list)

## Trigger

Use weekly for any active campaign spending more than $100/day. Use immediately when CPL spikes 20%+ week-over-week, when conversion volume drops significantly, or when a metric falls outside target range.

## Inputs Needed

- Last 7 days of campaign data from the ad platform - required
- Prior 7-day data for comparison - required
- Target CPL or ROAS from the CFO Agent budget plan - required
- Creative testing plan (to understand what is currently being tested) - helpful
- CRM conversion data (lead-to-booked rate, close rate) - helpful

## Process

**Step 1: Read the metrics in the right order**
Do not jump to "CPL is up, what do I do?" Diagnose by reading metrics in sequence:

1. Impressions/Reach: Is the campaign delivering? If not, budget, bid, or audience size issue.
2. Frequency: Is the audience burning out? Over 3.5 in 7 days = fatigue.
3. CTR: Are people interested? Under 0.5% = hook or creative problem.
4. CPC: Is the cost per click in range? CPC rising with falling CTR = fatigue.
5. Landing page CVR: Are clickers converting? Low CVR = landing page or message mismatch.
6. CPL: Is the cost per lead in range? CPL = CPC / Landing page CVR. Fix the upstream cause, not the symptom.
7. Lead quality (from CRM): Are leads converting to calls and sales? If not, targeting or offer problem.

**Step 2: Identify the primary issue**

One primary issue per review. If multiple things are wrong, prioritize the one with the biggest impact on the final outcome metric (CPL or ROAS).

Common patterns:
- High CPL + low CTR + rising frequency → Creative fatigue. Rotate new creatives.
- High CPL + good CTR + low landing page CVR → Landing page issue. Alert Funnel Agent.
- High CPL + good CTR + good landing page CVR + low close rate → Offer or targeting mismatch. Alert Offer Agent.
- Good CPL + low volume → Budget too low, audience too narrow, or bid too restrictive.
- CPC rising without CTR dropping → Auction competition increasing. Check competitor activity or test new audiences.

**Step 3: Make specific decisions**

For each issue identified, make a specific decision:
- Kill: Turn off underperforming ad sets or ads (with the kill threshold from the creative testing plan)
- Scale: Increase budget on winning ad sets (horizontal or vertical depending on the strategy)
- Rotate: Pause fatigued creative, launch fresh creative from the testing queue
- Test: Introduce a new variable from the creative testing plan
- Escalate: If the issue is not in the ad account (landing page, offer, follow-up), route to the correct agent

**Step 4: Document the decisions**

Format every decision as:
"[Kill / Scale / Rotate / Test / Escalate] [specific element] because [metric evidence]. [What happens next and when]."

Example: "Kill Ad 1B (Pain-Static-Hook2) because it has spent $180 with 0 conversions. Frequency is 2.3, so audience is not burned out - the creative is not working. Pause immediately and launch Ad 1D (Pain-Static-Hook3) from the testing queue."

## Output Format

```
OPTIMIZATION REVIEW - [Client/Campaign] - [Date]

REVIEW PERIOD: [Date range]
TOTAL SPEND: $[X]
LEADS GENERATED: [N]
CPL (this period): $[X]
CPL TARGET: $[X]
CPL TREND: [Up X% / Down X% / Stable vs prior period]

---

METRIC DIAGNOSTICS:

Impressions: [N] → [Normal / Low - possible delivery issue]
Frequency: [X] → [Under 2.0: OK / 2.0-3.5: Monitor / Over 3.5: Fatigue signal]
CTR: [X]% → [Over 1%: Strong / 0.5-1%: Acceptable / Under 0.5%: Hook/creative issue]
CPC: $[X] → [Trending: up/down/stable]
Landing page CVR: [X]% → [Over 25%: Good / 15-25%: Watch / Under 15%: Flag to Funnel Agent]
CPL: $[X] vs target $[X] → [On target / X% above target / X% below target]
Lead quality (if available): Lead-to-booked rate [X]% → [benchmark]

PRIMARY ISSUE IDENTIFIED:
[One sentence: what is wrong and what type of problem it is]

---

DECISIONS:

1. [Kill / Scale / Rotate / Test / Escalate]: [Specific element]
   Reason: [Metric evidence]
   Action: [What exactly to do]
   Who: [Paid Ads Agent / Copywriter / Funnel Agent / etc.]
   When: [Immediately / Before next review / etc.]

2. [Same format]

3. [Same format]

---

METRICS TO WATCH NEXT PERIOD:
- [Metric]: currently [X], expected to [improve/hold/be watched]

NEXT REVIEW DATE: [Date]
```

## Quality Check

- [ ] Metrics read in the correct order (not jumping straight to CPL)
- [ ] One primary issue identified before listing actions
- [ ] Every decision is specific: names the exact element, the metric evidence, and the next step
- [ ] Actions that belong to other agents (Funnel, Copywriter, Offer) are escalated with specific context
- [ ] Next review date is set
- [ ] Report routes to Marketing Director and Analytics Agent

## Status

Phase 3 complete.
