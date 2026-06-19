# Prompt: Weekly Performance Review

Use this prompt every week to run the full performance review across active clients and campaigns.

---

## When to Use

At the start of each week (typically Monday) to review the prior week's performance.

---

## The Prompt (Single Client)

```
@analytics-agent

Weekly performance review for [Client name]. Week ending [Date].

Data available:
- Meta Ads: [Paste key metrics or say "pull directly from the ad account"]
- GHL pipeline: [Paste stage counts or say "pull directly from GHL"]
- Google Analytics: [Paste LP conversion rate or say "pull directly from GA"]

Targets for this client:
- CPL target: $[X]
- Show rate target: [X]%
- Close rate target: [X]%
- Monthly revenue target: $[X]

Please:
1. Run the weekly report (skills/analytics-optimization/weekly-report.md)
2. Run the ad performance review (skills/analytics-optimization/ad-performance-review.md) with a Scale/Keep/Iterate/Kill decision for each active ad
3. Identify any risk flags for next week
4. Output the completed weekly report using templates/reports/weekly-report.md
5. List the recommended actions with owner and due date
```

---

## The Prompt (Multiple Clients)

```
@marketing-director

Weekly review for all active clients. Week ending [Date].

Active clients:
- [Client 1]
- [Client 2]
- [Client 3]

Please route the weekly review to the Analytics Agent for each client and then compile a summary of:
1. Which clients are on target, which are off
2. The top priority action across all clients this week
3. Any accounts that need immediate attention
```

---

## What Happens Next

The Analytics Agent will:
1. Pull all required data
2. Apply the metrics read order (Impressions → Frequency → CTR → CPC → LP CVR → CPL → Lead quality)
3. Make Scale/Keep/Iterate/Kill decisions on every active ad
4. Complete the weekly report template
5. Flag risks and list recommended actions

---

## Notes

- If data is not available via MCP tools, paste the relevant metrics into the prompt
- Do not make budget changes without reviewing the CFO Agent's budget planning first
- All Scale decisions increase budget by 20% maximum
- All Kill decisions trigger a new creative brief request to the Creative Design Agent
