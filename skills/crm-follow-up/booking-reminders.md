# Booking Reminders

## Purpose

Design the pre-call reminder sequence that fires after a lead books a call and before the call happens. Booking reminders reduce no-show rates by keeping the call top of mind, pre-framing the conversation, and building anticipation. A well-designed reminder sequence can increase show rates from 50-60% to 75-85%. The output is the full reminder sequence plan.

## Used By

- CRM Follow-Up Agent (primary)
- Copywriter (writes the message content)
- n8n Automation Agent (builds the automation)

## Trigger

Use when a call is booked by a lead (pipeline moves to CALL BOOKED stage), when show rates are below 70%, or when setting up a new booking system and no reminder sequence exists.

## Inputs Needed

- Call booking platform (Calendly, GHL calendar, Acuity, etc.) - required
- Typical call lead time (how many days between booking and call?) - required
- CRM platform - required
- Who the lead is meeting with (name, title, brief description) - required
- Offer and what the call is about - required

## Process

**Step 1: Map the reminder timing**

Timing should be based on when the call is, not when the booking was made. A call booked for today needs different treatment than one booked for next week.

Standard reminder sequence:

| Timing | Channel | Type |
|--------|---------|------|
| Immediately after booking | Email | Confirmation + what to expect |
| Immediately after booking | SMS | Confirmation + add-to-calendar |
| 24 hours before call | Email | Reminder + what to prepare |
| 24 hours before call | SMS | Brief reminder |
| 2 hours before call | SMS | "We're on for today" message |
| 15 minutes before call | SMS | "Joining shortly" message (optional) |

**Step 2: Write the confirmation message (fires immediately)**

The confirmation message does three things:
1. Confirms the date and time of the call (with timezone)
2. Tells them what to expect on the call
3. Gives them one thing to prepare or think about

The confirmation sets the frame for the call. A lead who arrives knowing what to expect, having thought about their situation, is more likely to make a decision.

**Step 3: Write the 24-hour reminder**

The 24-hour reminder:
- Reminds them of the appointment details
- Reinforces why the call is worth their time
- Optionally: shares a case study or quick result to build anticipation
- Includes a link to reschedule if needed (better to reschedule than no-show)

**Step 4: Write the day-of reminders**

The 2-hour reminder: "Quick reminder - we're chatting today at [time]. See you then!"
The 15-minute reminder (optional): "Jumping on our call in about 15 minutes - looking forward to it!"

Day-of messages should be brief and warm. They are reminders, not pitches.

**Step 5: Define the no-show handling**

If the lead does not show:
- [15 min after start]: Send a "missed you" SMS
- [1 hour after]: Send a reschedule email
- [Next day]: Sales rep follow-up call

Move the lead from CALL BOOKED back to CONTACTED stage in GHL. Do not move to DISQUALIFIED just because of a no-show - no-shows can often be rebooked.

## Output Format

```
BOOKING REMINDER SEQUENCE - [Client/Offer] - [Date]

BOOKING PLATFORM: [Calendly / GHL / Acuity]
WHO THEY ARE MEETING: [Name, title]
WHAT THE CALL IS: [Discovery call / Strategy call / Consultation / Sales call]
CRM PLATFORM: GoHighLevel

---

REMINDER SEQUENCE:

IMMEDIATELY AFTER BOOKING - Confirmation

  SMS Confirmation:
    "Hey [First Name]! Your [Call type] with [Name] is confirmed for [Day] at [Time] [Timezone]. 
    Here's your calendar link: [Link]. Can't wait to talk - if anything comes up, just reply!"

  Email Confirmation:
    Subject: "Your call with [Name] is confirmed - here's what to expect"
    Content: 
      - Confirmed time (bold, prominent)
      - What the call covers (2-3 bullet points)
      - One thing to think about before the call
      - Link to add to calendar
      - Reschedule link if needed
      - Brief bio of who they are meeting

24 HOURS BEFORE - Reminder

  SMS:
    "Hey [First Name], just a reminder that you're talking with [Name] tomorrow at [Time]. 
    Here's the link if you need to adjust anything: [Link]. See you then!"

  Email:
    Subject: "Quick note before our call tomorrow"
    Content:
      - Reminder of time and link
      - One case study or result to build anticipation
      - 1-2 questions for them to think about before the call
      - Reschedule link

2 HOURS BEFORE - Day-of Reminder

  SMS:
    "Hey [First Name], we're on for today at [Time]! Looking forward to talking. 
    If anything comes up, reply here. See you shortly!"

15 MINUTES BEFORE (Optional)

  SMS:
    "Jumping on our call with you in about 15 min - [First Name], see you there!"

---

NO-SHOW HANDLING:

15 min after scheduled start:
  SMS: "Hey [First Name], looks like we missed each other. Want to reschedule? Here's my calendar: [Link]"

1 hour after:
  Email: "Missed you today - want to find another time?"
  Content: Easy reschedule link, no guilt, just an invitation

Next business day:
  Sales rep follow-up call attempt

CRM action on no-show:
  Move from CALL BOOKED → CONTACTED (re-enter follow-up sequence)
  Tag: "No-Show"
  Note: First no-show does not disqualify - attempt to rebook twice before moving to Long-term Nurture

---

COPY BRIEF FOR COPYWRITER:
Tone: Warm, personal, like it comes from a real person not a company
SMS length: Under 160 chars (day-of reminders) or up to 2 segments (confirmation)
Email length: Confirmation can be longer (300-400 words), reminders short (100-200 words)
Include in every message: First name, call time and date, timezone
Include in every message except 15-min: Reschedule/cancel link
```

## Quality Check

- [ ] Confirmation fires immediately after booking (not hours later)
- [ ] All time references include the timezone
- [ ] Reschedule link is included in all messages except the 15-minute reminder
- [ ] No-show sequence covers immediate, 1-hour, and next-day responses
- [ ] CRM action on no-show is documented (back to CONTACTED, not DISQUALIFIED)
- [ ] Day-of messages are brief and warm, not pitchy

## Status

Phase 3 complete.
