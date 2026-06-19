# SMS Follow-Up

## Purpose

Design and document the full SMS follow-up sequence for a lead. The SMS sequence covers the messages sent across the first 7 days after a lead opts in, including content direction, timing, message length rules, and the conditions under which each message fires and stops. The output is the sequence plan the Copywriter uses to write the messages and the n8n Automation Agent uses to build the automation.

## Used By

- CRM Follow-Up Agent (primary)
- Copywriter (writes the final message content)
- n8n Automation Agent (builds the sequence automation)

## Trigger

Use when setting up a new SMS follow-up sequence, when reply rates to SMS are low, or when the current sequence does not have a documented structure.

## Inputs Needed

- Lead source (paid traffic, organic, referral) - required
- CRM platform (GHL assumed) - required
- Offer and main value proposition - required
- Audience profile - required
- Whether a sales call is the goal or direct purchase - required

## Process

**Step 1: Confirm SMS compliance requirements**

Before writing any SMS, confirm:
- Lead must have opted in to receive SMS (documented at form level)
- Each message must include an opt-out option: "Reply STOP to opt out"
- Messages must not fire between 9pm and 8am local time (TCPA compliance)
- First message should be sent within context of the form submission (timing matters for compliance)

**Step 2: Plan the 7-day sequence**

Standard SMS sequence for a call-booking funnel:

| Touch | Day | Timing | Goal |
|-------|-----|--------|------|
| Touch 1 | Day 1 | Within 5 min of opt-in | First contact, create dialogue |
| Touch 2 | Day 1 | 2 hours after Touch 1 (if no reply) | Check-in |
| Touch 3 | Day 2 | Morning (9-11am local) | Value message |
| Touch 4 | Day 3 | Mid-morning | Social proof |
| Touch 5 | Day 5 | Morning | Soft CTA |
| Touch 6 | Day 7 | Morning | Last reach / opt-out offer |

**Step 3: Write content direction for each touch**

For each SMS touch:
- The goal of the message (what response are we hoping for?)
- The angle or type of content
- Any specific element to include (first name, specific offer, specific proof)
- Character limit: 160 characters per segment. Aim for under 160 total if possible. Over 160 splits into two messages.
- No links in Touch 1 (reduces deliverability). Links OK from Touch 2 onward.

**Step 4: Define the stop conditions**

The sequence must stop when:
- Lead replies at any point (conversation takes over)
- Lead books a call (no longer needs nurturing)
- Lead opts out (STOP reply)
- Lead is marked Disqualified

If any of these conditions occur, all remaining touches in the sequence must be cancelled.

**Step 5: Note the transition from automated to human**

After the sequence completes without a reply:
- Move to Long-term Nurture stage
- Flag for the CRM Follow-Up Agent's manual review

## Output Format

```
SMS FOLLOW-UP SEQUENCE - [Client/Offer] - [Date]

OFFER: [Name]
GOAL: [Book a call / Direct purchase / Application]
CRM: GoHighLevel
COMPLIANCE: Opt-in confirmed at form level

---

SEQUENCE MAP:

TOUCH 1 - Day 1, Minute 1-5 (Speed-to-lead)
  Goal: First contact, generate a reply
  Angle: Friendly intro, simple question
  Content direction: "Hey [First Name], this is [Name] from [Company]. You just [opted in / showed interest in / downloaded] [thing]. Just wanted to make sure you got it - did everything come through okay?"
  Character limit: Under 160 chars
  No links
  Stop if: [Lead replies]

TOUCH 2 - Day 1, Hour 2 (if no reply to Touch 1)
  Goal: Check-in, second attempt to start dialogue
  Angle: Brief, friendly, not pushy
  Content direction: "Hey [First Name], just circling back on my message earlier. Happy to answer any questions about [topic] when you're ready."
  Character limit: Under 160 chars

TOUCH 3 - Day 2, 9-11am local
  Goal: Deliver value, establish credibility
  Angle: One useful insight or tip related to the offer
  Content direction: "[One specific tip or insight the audience would find helpful] - [First Name], if you'd like to know more about how this applies to your situation, reply and I'll share more."
  Can include link from this touch onward

TOUCH 4 - Day 3, 9-11am local
  Goal: Social proof, build trust
  Angle: Quick client result
  Content direction: "Thought you'd find this helpful: [Client first name] was dealing with [problem] and here's what happened: [result]. If you want to see how we did it, reply YES."
  No hard sell

TOUCH 5 - Day 5, 9-11am local
  Goal: Soft CTA, invite them to take next step
  Angle: Direct but not pushy
  Content direction: "Hey [First Name], wanted to reach out one more time. If [problem they have] is still something you want to solve, I have [X time slots / availability] this week. Reply to grab one or here's the link: [Link]"

TOUCH 6 - Day 7, 9-11am local
  Goal: Last reach, clean the list
  Angle: Last chance, give them an easy out
  Content direction: "Hey [First Name], I'll stop reaching out after this - I don't want to bother you. If you ever want to talk about [topic], I'm here. Otherwise, reply STOP and I'll remove you. Take care!"
  Must include opt-out language

---

STOP CONDITIONS:

| Event | Action |
|-------|--------|
| Lead replies | Cancel all remaining touches, CRM Follow-Up Agent takes over |
| Lead books a call | Cancel all remaining touches, move to pre-call sequence |
| Lead replies STOP | Opt out, cancel all sequences, update GHL opt-in status |
| Lead disqualified | Cancel all remaining touches |

---

COPY BRIEF FOR COPYWRITER:
Tone: [Warm and conversational / Friendly and direct]
Voice: [First person - from sales rep / from company]
Sender name: [Who the messages appear to come from]
Include in every message: First name personalization
Opt-out language required: Touch 6 must include opt-out offer, all messages should note STOP option in GHL compliance footer
```

## Quality Check

- [ ] 6-touch, 7-day sequence is documented
- [ ] Opt-in and TCPA compliance confirmed before sequence is built
- [ ] No links in Touch 1
- [ ] Each touch has a goal, angle, and content direction
- [ ] Stop conditions cover all scenarios (reply, booking, opt-out, disqualified)
- [ ] Touch 6 includes an explicit opt-out offer
- [ ] Character limits noted (under 160 per touch)

## Status

Phase 3 complete.
