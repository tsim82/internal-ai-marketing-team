# Speed to Lead

## Purpose

Document and configure the speed-to-lead protocol for a client. Speed to lead is the time between a lead submitting their information and the first contact attempt. Every minute after 5 minutes reduces the chance of reaching the lead. After 30 minutes, conversion rates drop significantly. This skill produces the documented protocol and automation spec so the n8n Automation Agent can build it.

## Used By

- CRM Follow-Up Agent (primary)
- n8n Automation Agent (builds the automation)

## Trigger

Use when setting up a new lead intake for paid traffic, when leads are not being contacted quickly enough, or when the conversion rate from lead to booked call is below target.

## Inputs Needed

- Lead source (paid Facebook/Google, organic, referral) - required
- CRM platform (GHL assumed) - required
- Available contact channels (SMS, phone, email) - required
- Hours of operation (if applicable) - required
- Sales team capacity (is there a human sales rep, or is this fully automated?) - required

## Process

**Step 1: Establish the timing protocol**

The speed-to-lead timing by lead source:

| Lead source | Target first contact | Maximum acceptable |
|------------|--------------------|--------------------|
| Paid Facebook / Google traffic | Under 5 minutes | 10 minutes |
| Organic / content leads | Under 30 minutes | 2 hours |
| Referral leads | Under 1 hour | 4 hours |
| Inbound calls | Immediate | Not applicable |

**Step 2: Define the contact sequence for the first hour**

Standard speed-to-lead sequence (paid traffic):

| Timing | Channel | Action |
|--------|---------|--------|
| [0:00] Lead submits | Webhook | Trigger fires in n8n, lead created in GHL |
| [Minute 1] | SMS | Touch 1: Intro SMS fires automatically |
| [Minute 2] | Phone | Call Attempt 1 (automated dial or sales rep alert) |
| [Minute 5] | SMS | Touch 2: Check-in SMS if no reply |
| [Hour 1] | Email | Email Touch 1 fires |
| [Hour 4] | Phone | Call Attempt 2 (if no contact made) |
| [Hour 4] | SMS | Touch 3: Follow-up SMS |

**Step 3: Define the SMS content for Touch 1**

Touch 1 must be:
- Under 160 characters
- Friendly and clear about who it is from
- Ask a yes/no or simple question to generate a reply
- No links in the first message (reduces deliverability)

Example Touch 1 (the Copywriter writes the final version):
"Hey [First Name], this is [Name] from [Company]. I saw you were interested in [Topic] - quick question: are you still looking for help with [Problem]? Reply YES and I'll reach out."

**Step 4: Define the human handoff (if applicable)**

If a sales rep is involved:
- When does the rep get notified? (immediately on lead creation, or after the first automated touch)
- How are they notified? (Slack, email, GHL notification, phone call)
- What information do they receive? (Lead name, source, any qualification data)

**Step 5: Define what counts as "contact made"**

Contact is made when:
- The lead replies to an SMS
- The lead picks up a phone call
- The lead replies to an email
- The lead re-books or completes a form

Once contact is made: move to CONTACTED stage in CRM, stop the speed-to-lead sequence.

**Step 6: Specify the hours-of-operation handling**

If leads come in outside of business hours:
- Do SMS messages still fire? (Yes - SMS does not require business hours)
- Do phone calls still fire? (Usually no - flag for next business day)
- If the lead comes in after hours: queue the call attempt for the next morning

## Output Format

```
SPEED-TO-LEAD PROTOCOL - [Client] - [Date]

LEAD SOURCE(S): [Paid Meta / Google / Organic / Referral]
CRM: GoHighLevel
CONTACT CHANNELS: [SMS / Phone / Email]
HOURS OF OPERATION: [Hours or 24/7]
SALES REP INVOLVEMENT: [Yes - [Name] / Fully automated]

---

TIMING PROTOCOL:

| Time from opt-in | Channel | Action |
|-----------------|---------|--------|
| 0:00 | System | Lead created in GHL, "New Lead" tag applied, speed-to-lead sequence triggers |
| Minute 1 | SMS | Touch 1 fires |
| Minute 2 | Phone | Call Attempt 1 [Automated / Sales rep alert fires] |
| Minute 5 | SMS | Touch 2 fires (if no reply to Touch 1) |
| Hour 1 | Email | Email Touch 1 fires |
| Hour 4 | Phone | Call Attempt 2 (if no contact made) |
| Hour 4 | SMS | Touch 3 fires |

STOP TRIGGER: Any reply or contact made → Cancel remaining sequence / Move to CONTACTED stage

---

SMS TOUCH 1 CONTENT:
"[Message - under 160 chars, no links, personalized with first name]"

SMS TOUCH 2 CONTENT:
"[Brief check-in - under 160 chars]"

---

HUMAN HANDOFF (if applicable):
Notification fires: [Timing - on lead creation / after Touch 1 / etc.]
Channel: [Slack / Email / GHL notification / Phone call to rep]
Message to rep: "[What they receive - lead name, source, phone, any notes]"

---

CONTACT CONFIRMATION:
Counts as contact made: [Reply to SMS / Pick up phone / Email reply]
On contact: Stop sequence + Move to CONTACTED stage in GHL + Remove "New Lead" tag

---

HOURS OF OPERATION:
After-hours behavior:
  SMS: [Still fires / Queued for next morning]
  Phone calls: [Queued for next morning - fires at [time]]
  Email: [Still fires]

---

AUTOMATION BUILD SPEC FOR n8n Automation Agent:
Trigger: New contact created in GHL with "New Lead" tag
Sequence: GHL workflow or n8n sequence with timing nodes
Conditional: Stop all nodes when "Contacted" tag is applied to contact
Error handling: If SMS fails → alert via Slack, attempt email instead
```

## Quality Check

- [ ] First contact attempt is within 5 minutes for paid traffic
- [ ] All three channels (SMS, phone, email) are addressed
- [ ] Stop trigger is defined (what stops the sequence when contact is made)
- [ ] Hours of operation handling is documented
- [ ] SMS Touch 1 content direction is written
- [ ] Human handoff is documented if a sales rep is involved
- [ ] Automation build spec is complete enough for the n8n Automation Agent

## Status

Phase 3 complete.
