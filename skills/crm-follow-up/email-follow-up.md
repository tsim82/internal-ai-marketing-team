# Email Follow-Up

## Purpose

Design the email follow-up sequence for leads who have not converted through SMS or phone contact. Email follow-up runs in parallel or in sequence with SMS, and covers a longer arc (7-21 days depending on the offer). The output is the sequence plan the Copywriter uses to write the emails and the n8n Automation Agent uses to build the automation.

## Used By

- CRM Follow-Up Agent (primary)
- Copywriter (writes the email content)
- n8n Automation Agent (builds the sequence)

## Trigger

Use when setting up a new lead follow-up email sequence, when email open rates or reply rates are below target, or when no documented email sequence exists for the current funnel.

## Inputs Needed

- Offer and funnel goal - required
- Audience awareness level and profile - required
- Current pipeline stage this email sequence supports - required
- Length of the sales cycle (determines sequence length) - required
- Tone and brand voice rules - required

## Process

**Step 1: Determine the sequence type**

There are three common email follow-up sequence types:

| Type | When to use | Length |
|------|------------|--------|
| Speed-to-lead email | Runs alongside SMS in the first 24-48 hours | 2-3 emails |
| Post-opt-in nurture | Runs after a lead magnet or free opt-in, moving toward a sale | 5-7 emails over 7-14 days |
| Post-call follow-up | Runs after a sales call where no decision was made | 3-5 emails over 5-7 days |

**Step 2: Map the email arc**

For the most common type (post-opt-in nurture toward a call booking):

| Email | Timing | Arc position | Goal |
|-------|--------|-------------|------|
| Email 1 | Immediate | Welcome + context | Confirm opt-in, set expectations |
| Email 2 | Day 1 | Problem depth | Make them feel understood |
| Email 3 | Day 2 | Mechanism / solution | Introduce the approach |
| Email 4 | Day 3 | Proof / case study | Show real results |
| Email 5 | Day 5 | Objection handling | Address main hesitation |
| Email 6 | Day 7 | Offer | Present the offer directly |
| Email 7 | Day 9 | Urgency / last chance | Final push |

**Step 3: Write content direction for each email**

For each email:
- Subject line direction (3 options minimum per email)
- Preview text direction
- Body angle and goal
- CTA (one per email)
- Whether the email is soft (value-focused) or hard (direct pitch)

**Step 4: Define the stop conditions**

The email sequence must stop when:
- Lead books a call (enters Call Booked stage)
- Lead purchases
- Lead unsubscribes
- Lead is marked Disqualified

**Step 5: Define rules for when email and SMS run simultaneously**

If both sequences run at the same time, they should not conflict:
- Email and SMS should not send within 30 minutes of each other
- On the same day, SMS in the morning and email in the afternoon (or vice versa) typically works
- The message angles should be different to avoid feeling repetitive

## Output Format

```
EMAIL FOLLOW-UP SEQUENCE - [Client/Offer] - [Date]

SEQUENCE TYPE: [Speed-to-lead / Post-opt-in nurture / Post-call follow-up]
OFFER: [Name]
PIPELINE STAGE SUPPORTED: [Stage where leads are in this sequence]
RUNNING WITH SMS: [Yes - SMS sends in morning, email in afternoon / No]

---

SEQUENCE MAP:

EMAIL 1 - Immediate (within 5 min of opt-in)
  Subject options: 
    A: "[Option 1]"
    B: "[Option 2]"
    C: "[Option 3]"
  Preview text: "[Extends the subject, adds curiosity]"
  Arc position: Welcome / Context
  Goal: Confirm opt-in, tell them what to expect, create goodwill
  Body angle: Warm welcome, 1 quick win or piece of value, what comes next
  CTA: [Low friction - read the thing / watch this / reply with X]
  Type: Soft

EMAIL 2 - Day 1 (afternoon if SMS sent morning)
  Subject options:
    A: "[Pain mirror or question]"
    B: "[...]"
    C: "[...]"
  Preview text: "[...]"
  Arc position: Problem depth
  Goal: Make them feel understood. No pitch.
  Body angle: Articulate the problem they have in their own language. Use research.
  CTA: [Soft - reply, no link needed]
  Type: Soft

EMAIL 3 - Day 2
  Subject options: [3 options]
  Arc position: Mechanism / Solution intro
  Goal: Introduce what makes this approach different
  Body angle: Name the mechanism. Why it works when other things haven't.
  CTA: [Learn more / Watch video / Soft]
  Type: Soft

EMAIL 4 - Day 3
  Arc position: Proof / Social proof
  Goal: Build belief through a specific case study
  Body angle: Before → Change → After (specific result)
  CTA: [Soft CTA toward booking or offer]
  Type: Soft-medium

EMAIL 5 - Day 5
  Arc position: Objection handling
  Goal: Address the #1 thing stopping them from acting
  Body angle: Name the objection directly and answer it
  CTA: [Medium - booking link or offer page]
  Type: Medium

EMAIL 6 - Day 7
  Arc position: Offer
  Goal: Present the offer clearly with price, value stack mention, guarantee
  Body angle: Everything they get, the price, why now
  CTA: [Direct - book your call / get started]
  Type: Hard

EMAIL 7 - Day 9
  Arc position: Last chance
  Goal: Get the fence-sitters to act
  Body angle: Final note, acknowledge they've been thinking about it, give them a reason to act today
  CTA: [Direct - same as Email 6]
  Type: Hard

---

STOP CONDITIONS:

| Event | Action |
|-------|--------|
| Lead books a call | Cancel remaining emails, enter pre-call email sequence |
| Lead purchases | Cancel all sequences, enter customer onboarding |
| Lead unsubscribes | Cancel all, update GHL email permission |
| Lead disqualified | Cancel all |

---

COPY BRIEF FOR COPYWRITER:
Tone: [Conversational / Professional / Direct]
Length: [Short: 100-200 words / Medium: 200-350 words / Long: 350-500 for proof emails]
Subject lines: 3 options per email, under 50 chars
Preview text: Extends subject, under 90 chars, never repeat subject
No em dashes in any email
```

## Quality Check

- [ ] Every email has a subject line direction with 3 options minimum
- [ ] Every email has a single CTA
- [ ] Arc builds logically from welcome → problem → mechanism → proof → objection → offer → urgency
- [ ] Stop conditions cover all scenarios
- [ ] Email and SMS coordination is noted if both run
- [ ] Copy brief is complete for Copywriter

## Status

Phase 3 complete.
