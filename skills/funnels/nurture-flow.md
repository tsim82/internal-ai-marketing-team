# Nurture Flow

## Purpose

Design the post-opt-in nurture sequence that moves a new lead from "interested" to "ready to buy." The nurture flow is the automated email and/or SMS path a lead follows after opting in but before purchasing or booking. The output is a complete flow map with each touchpoint defined, the timing between them, and the goal of each message.

## Used By

- Funnel Agent (designs the flow)
- Copywriter (writes the messages in the flow)
- n8n Automation Agent (builds the automations)
- CRM Follow-Up Agent (manages leads in the flow within GHL)

## Trigger

Use when a new funnel is being built (the nurture flow is a required component), when leads are opting in but not converting to booked calls or purchases, or when no nurture sequence exists after the opt-in.

## Inputs Needed

- Offer being nurtured toward - required
- Audience awareness level at opt-in - required
- Traffic source (determines temperature of lead at entry) - required
- How long the typical sales cycle is - required
- Any existing email sequence in place - helpful
- CRM tool in use (for automation logic) - required

## Process

**Step 1: Define the nurture goal**

What is the sequence trying to accomplish? Pick one:
- **Book a call**: Lead opts in → sequence converts them to a booked discovery or sales call
- **Purchase a product**: Lead opts in → sequence converts them to a direct purchase
- **Attend a webinar**: Lead registers → sequence converts them to webinar attendees
- **Long-term nurture**: Lead is not ready to buy → sequence keeps them warm until they are

**Step 2: Define the sequence length and arc**

Match sequence length to price point:
- Free or low-ticket (<$100): 3-5 email sequence
- Mid-ticket ($100-2,000): 5-7 email sequence
- High-ticket ($2,000+): 7-14 emails + phone/SMS touchpoints

The sequence arc (the emotional journey the reader takes):
1. **Welcome + context**: Who sent this, what they should expect, one quick win
2. **Problem depth**: Reflect the problem back. Make them feel understood.
3. **Mechanism**: Introduce the thing that makes the offer work
4. **Proof**: Show others getting results
5. **Objection handling**: Address the main thing stopping them from acting
6. **Offer**: Present the offer with price, guarantee, and CTA
7. **Urgency/close**: Final push if deadline or capacity is real

**Step 3: Map each touchpoint**

For each message in the sequence:
- Day/timing from opt-in
- Channel (email / SMS)
- Subject line direction (for email)
- Goal of this message (what should they feel or believe after reading?)
- CTA (what do we want them to do?)

**Step 4: Define the exit conditions**

A lead should exit the nurture sequence when:
- They book a call (remove from lead sequence, enter pre-call sequence)
- They purchase (remove from all prospect sequences, enter customer sequence)
- They click an unsubscribe link

Do not continue sending the same nurture sequence after someone converts.

**Step 5: Note the handoff to the CRM Follow-Up Agent**

For leads who complete the sequence without converting, the CRM Follow-Up Agent takes over for manual or long-term follow-up.

## Output Format

```
NURTURE FLOW - [Client/Offer] - [Date]

NURTURE GOAL: [Book call / Direct purchase / Webinar attendance / Long-term]
LEAD ENTRY POINT: [Opt-in page / Webinar registration / Content lead magnet]
LEAD TEMPERATURE AT ENTRY: [Cold / Warm]
SALES CYCLE LENGTH: [Days / Weeks]

---

SEQUENCE MAP:

DAY 0 - Immediate (within 5 minutes of opt-in)
  Channel: Email
  Type: Welcome / confirmation
  Subject direction: "Here's what you just signed up for + quick note from me"
  Goal: Confirm they got it, set expectations, create goodwill
  CTA: [Read the lead magnet / watch the video / check your email]
  Automation: [n8n or GHL sequence start trigger]

DAY 1
  Channel: Email
  Type: Problem depth
  Subject direction: [One-line that mirrors their situation]
  Goal: Make them feel seen. No pitch.
  CTA: [Soft - reply, consume more content, or nothing]

DAY 2
  Channel: [Email / SMS]
  Type: Mechanism
  Subject direction: [Curiosity about the approach]
  Goal: Introduce the thing that makes this work differently
  CTA: [Watch video / Read article / Learn more]

DAY 3
  Channel: Email
  Type: Proof / Social proof
  Subject direction: [Client result or case study]
  Goal: Belief building
  CTA: [Read case study / book a call - soft]

DAY 4
  Channel: Email
  Type: Objection handling
  Subject direction: [Named objection or "I get it..."]
  Goal: Reduce the top barrier to acting
  CTA: [Book a call / Learn more]

DAY 5
  Channel: Email + SMS
  Type: Offer
  Subject direction: [Clear offer statement]
  Goal: Present the offer with context
  CTA: [Book your call / Get started - direct]

DAY 7
  Channel: Email
  Type: Urgency / Close
  Subject direction: [Last chance / final note]
  Goal: Get the undecided to act
  CTA: [Direct CTA - book a call or buy]

---

EXIT CONDITIONS:

| Event | Action |
|-------|--------|
| Lead books a call | Remove from this sequence → Enter pre-call sequence |
| Lead purchases | Remove from all prospect sequences → Enter customer onboarding |
| Lead unsubscribes | Remove from all marketing sequences |
| Sequence completes without conversion | Hand off to CRM Follow-Up Agent for long-term nurture |

---

AUTOMATION NOTES FOR n8n / GHL:
- Trigger: [Opt-in form submission / tag applied]
- Exit trigger: [Tag: Booked-Call / Tag: Customer / Unsubscribe event]
- SMS timing: confirm legal opt-in captured before sending SMS touchpoints
- Goal events to track: [Email opens, link clicks, call bookings, purchases]
```

## Quality Check

- [ ] Sequence length matches the price point and sales cycle
- [ ] Each touchpoint has a single goal (not trying to do everything in one email)
- [ ] Exit conditions are defined before the sequence is built
- [ ] Handoff to CRM Follow-Up Agent is documented for non-converters
- [ ] Sequence arc follows problem → mechanism → proof → objection → offer → urgency
- [ ] SMS touchpoints have legal opt-in confirmed

## Status

Phase 3 complete.
