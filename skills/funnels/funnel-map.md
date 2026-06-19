# Funnel Map

## Purpose

Document the complete customer journey from traffic source to conversion. The funnel map defines every page, step, and decision point in the funnel and how they connect. It is the blueprint the Funnel Agent uses to plan builds, the Copywriter uses to write each page, and the Analytics Agent uses to track drop-off points.

## Used By

- Funnel Agent (primary)
- Copywriter (writes copy for each page mapped here)
- Analytics Agent (sets up tracking against each step)
- n8n Automation Agent (builds automations triggered at each funnel step)

## Trigger

Use when launching a new funnel, auditing an existing one, or when the team is unclear about what the funnel actually looks like and what happens at each step.

## Inputs Needed

- Offer and goal (lead gen, application, direct purchase, webinar) - required
- Traffic source(s) (paid Meta, Google, organic, email) - required
- Tech stack or tools in use (ClickFunnels, GHL, Webflow, Kajabi, Shopify, etc.) - required
- Audience awareness level - helpful
- Any existing funnel in place to audit - helpful

## Process

**Step 1: Define the funnel type**

Match the funnel type to the offer and traffic:

| Funnel Type | Best for | Structure |
|------------|---------|-----------|
| Lead gen / opt-in | Building a list, free offer | Ad → Landing page → Thank you page → Email sequence |
| Application | High-ticket services | Ad → VSL or landing page → Application form → Confirmation → Call booking |
| Webinar | Complex offers, skeptical audiences | Ad → Registration page → Confirmation → Reminder sequence → Webinar → Sales page |
| Direct purchase | Low-to-mid ticket, warm audiences | Ad → Sales page → Checkout → Order confirmation → Upsell |
| Book-a-call | Service businesses | Ad → Landing page → Calendar booking → Confirmation → Pre-call sequence |

**Step 2: Map every page and step in sequence**

Draw the full path from first touch to conversion. Be explicit about what happens at each step and what triggers the next step.

```
TRAFFIC SOURCE → PAGE 1 → [action] → PAGE 2 → [action] → PAGE 3 → [automation] → NEXT STEP
```

Include:
- Each page and its single goal
- The action that moves the user forward
- What happens if they do NOT take the action (exit intent? retargeting?)
- Any automations that fire at each step

**Step 3: Identify the measurement points**

For each step, name what metric is tracked:
- Step 1 → Step 2: Click-through rate
- Step 2 → Step 3: Opt-in conversion rate
- Step 3 completion: Lead event fires

**Step 4: Identify the failure modes**

Where do people exit? What happens to them? Document the exits:
- Page 1 visitor who does not click through → retargeting audience or lost
- Visitor who opts in but does not book → CRM follow-up sequence
- Visitor who starts application but does not submit → abandoned form email

**Step 5: Note the tech requirements at each step**

What tool or integration is needed for each step to work? Flag any dependencies.

## Output Format

```
FUNNEL MAP - [Client/Offer] - [Date]

FUNNEL TYPE: [Lead gen / Application / Webinar / Direct purchase / Book-a-call]
TRAFFIC SOURCE(S): [Meta / Google / Organic / Email]
TECH STACK: [Tools involved]
GOAL: [What a successful conversion looks like]

---

FULL FUNNEL PATH:

STEP 1: [Traffic source]
  Action: User sees ad/post/email
  URL: n/a
  Goal: Click through
  Metric tracked: CTR
  If no action: [Retargeting audience / Lost]

STEP 2: [Page name - e.g., Landing Page]
  URL: [domain.com/page]
  Page goal: [One thing this page needs to do]
  Primary CTA: [What the visitor clicks or does]
  Metric tracked: [Conversion rate / Opt-in rate / etc.]
  Required elements: [Headline, form, video, etc.]
  Tech: [Tool building this page]
  If no action: [Exit intent popup / retargeting / lost]
  Automation fires: [What triggers when they complete this step]

STEP 3: [Page name - e.g., Thank You Page]
  URL: [domain.com/thank-you]
  Page goal: [Confirm opt-in + next step]
  Required elements: [Confirmation message, next step CTA, etc.]
  Tech: [Tool]
  Automation fires: [Email sequence starts, CRM contact created, etc.]

[Continue for every step]

---

MEASUREMENT POINTS:

| Step | Metric | Benchmark |
|------|--------|-----------|
| Ad → Landing page | CTR | 1-3% |
| Landing page → Opt-in | Conversion rate | 25-40% |
| [Step] → [Step] | [Metric] | [Good/Watch/Broken benchmarks] |

---

EXIT HANDLING:

| Exit point | What happens | Owner |
|-----------|-------------|-------|
| Landing page without opt-in | [Retargeting audience / pixel event] | Paid Ads Agent |
| Opted-in, did not book | CRM follow-up sequence starts | CRM Follow-Up Agent |

---

TECH REQUIREMENTS:

| Step | Tool | Integration needed |
|------|------|------------------|
| Landing page | [Tool] | [Pixel / CRM webhook / etc.] |
| Booking confirmation | [Tool] | [Calendar / CRM / etc.] |
```

## Quality Check

- [ ] Every page has a single, documented goal
- [ ] Every step has a named metric being tracked
- [ ] Exit handling is documented at each major step
- [ ] Tech requirements are listed so the build can start without additional clarification
- [ ] Automations that fire at each step are named
- [ ] Funnel type matches the offer and audience awareness level

## Status

Phase 3 complete.
