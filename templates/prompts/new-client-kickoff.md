# Prompt: New Client Kickoff

Use this prompt when onboarding a new client. Paste it into Claude Code and fill in the bracketed fields before sending.

---

## When to Use

When a new client has signed and you're ready to begin the onboarding process.

---

## The Prompt

```
@marketing-director

New client onboarding. Here are the details:

Client name: [Name]
Business: [What they do in 1-2 sentences]
Target audience: [Who they serve]
Primary offer: [What they sell and the price]
Revenue goal: [Monthly revenue target]
Ad budget: [Monthly ad spend they are starting with]
Platforms: [Meta / Google / Both / Organic only]
CRM: [GHL or other]
Contract start date: [Date]

The client intake form is [complete / not yet complete - we will wait / pasted below].

[Paste intake form responses here if available]

Please:
1. Review the intake information and identify any gaps before we can begin strategy
2. Create a strategy brief using the client details above
3. Route to the relevant agents to begin the onboarding checklist (skills/knowledge-base/sop/client-onboarding.md)
4. Tell me what you need from me and from the client before we can move to the build phase
```

---

## What Happens Next

The Marketing Director will:
1. Identify any missing information needed before strategy can be built
2. Create the strategy brief
3. Route research tasks to the Market Research Agent
4. Route offer documentation to the Offer Agent
5. Route budget planning to the CFO Agent
6. Tell you what is needed before the build phase starts

---

## Notes

- Do not start the build (copy, creative, funnel) until the strategy brief is complete and you have confirmed it
- If the client intake form is not yet complete, send `templates/intake/client-intake.md` to the client first and wait for it before running this prompt
