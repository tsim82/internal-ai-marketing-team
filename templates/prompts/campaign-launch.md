# Prompt: Campaign Launch

Use this prompt when you're ready to build and launch a new paid ad campaign. Paste it into Claude Code and fill in the bracketed fields.

---

## When to Use

When the strategy brief is approved and you're ready to move into the build phase for a paid campaign.

---

## Pre-Conditions

Before running this prompt, confirm:
- [ ] Strategy brief is complete and approved
- [ ] Client intake form is filled in
- [ ] Offer is documented in knowledge-base/offers/
- [ ] Budget is approved
- [ ] Ad account access is confirmed

---

## The Prompt

```
@marketing-director

Campaign launch for [Client name]. Here are the details:

Campaign goal: [Leads / Booked calls / Sales]
Offer: [Offer name and price]
Audience: [Brief description of who we're targeting]
Platform: [Meta / Google / Both]
Monthly budget: $[X]
Target CPL: $[X]
Landing page: [URL of existing page or "needs to be built"]
Launch date target: [Date]

The campaign brief is [attached / pasted below / in templates/briefs/campaign-brief.md].

[Paste or reference the completed campaign brief]

Please coordinate the full build:
1. Paid Ads Agent: Campaign structure and targeting plan
2. Copywriter: Ad copy (primary text and headlines) and landing page copy if needed
3. Creative Design Agent: Ad creative brief for [number] variations
4. Funnel Agent: Landing page [build / review] and thank-you page
5. n8n Automation Agent: Speed-to-lead automation and follow-up sequence
6. CRM Follow-Up Agent: Pipeline setup and CRM configuration
7. CFO Agent: Confirm budget math works at target CPL
8. QA Agent: Pre-launch check before anything goes live

Route each task to the right agent and tell me the order of operations and what you need from me at each step.
```

---

## What Happens Next

The Marketing Director will:
1. Confirm all pre-conditions are met
2. Route each build task to the appropriate agent
3. Set the order of operations (copy and brief must come before creative; funnel before automation)
4. Flag anything missing before the build can start

---

## Notes

- Nothing gets launched until the QA Agent completes the pre-launch checklist
- Do not increase budgets by more than 20% in a 7-day window after launch
- First optimization review is 7 days after launch
