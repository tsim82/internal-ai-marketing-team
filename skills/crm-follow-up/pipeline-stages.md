# Pipeline Stages

## Purpose

Define the complete pipeline stage structure for a client in GoHighLevel (or another CRM). The pipeline stages document is the architecture of how leads move through the system from first contact to closed. Every automation, sequence, and follow-up action references these stages. Without a documented pipeline structure, the team cannot build automations, track performance, or hand off between agents consistently.

## Used By

- CRM Follow-Up Agent (primary)
- n8n Automation Agent (builds automations based on stage transitions)
- Analytics Agent (tracks conversion rates by stage)
- Marketing Director (reviews for strategic alignment)

## Trigger

Use when setting up a new client in GHL, when restructuring an existing pipeline, or when the current pipeline stages do not reflect how the business actually works.

## Inputs Needed

- Offer and sales process description - required
- Revenue goal and close rate targets - helpful
- Current CRM setup (if restructuring) - helpful
- Sales cycle length - required
- Whether the business uses a call-booking model or direct sales - required

## Process

**Step 1: Identify the standard pipeline stages for this business type**

Standard pipeline for a call-booking service business:

| Stage | Name | What it means |
|-------|------|--------------|
| 1 | New Lead | Lead came in, has not been contacted yet |
| 2 | Contacted | First contact made (SMS, call, or email) |
| 3 | Qualified | Lead has met the BANT qualification criteria |
| 4 | Call Booked | Discovery or sales call is scheduled |
| 5 | Call Completed | The call happened |
| 6 | Closed/Won | Client paid and onboarding started |
| - | Long-term Nurture | Not ready now, check back in 30-90 days |
| - | Disqualified | Does not meet qualification criteria |

Adjust based on the client's actual process. A direct-purchase funnel has fewer stages.

**Step 2: Define entry, goal, automations, and exit for each stage**

For each stage:
- **Entry condition**: How does a lead arrive in this stage?
- **Automations that fire**: What happens automatically when a lead enters this stage?
- **Goal**: What should happen while the lead is here?
- **Exit condition**: What moves the lead to the next stage?
- **Maximum time in stage**: How long before the lead is considered stalled?

**Step 3: Define the stall rules**

Stalled leads are leads that have been in a stage longer than the maximum time. Document:
- Stall threshold per stage (how many days?)
- What happens when a lead stalls (re-engagement sequence, alert to sales rep, move to long-term nurture)

**Step 4: Define the two off-track stages**

Long-term Nurture:
- Entry: Lead is qualified but not ready to buy now
- Automations: Monthly value email, quarterly check-in
- Exit: Lead re-engages and books a call

Disqualified:
- Entry: Lead does not meet qualification criteria
- Automations: None (or opt-out confirmation)
- Exit: Does not exit unless they re-engage with new information

**Step 5: Set conversion benchmarks**

For each stage-to-stage transition, document the target conversion rate. This gives the Analytics Agent a baseline to compare against.

## Output Format

```
PIPELINE STAGES - [Client] - [Date]

CRM PLATFORM: GoHighLevel
PIPELINE NAME: [Name]
BUSINESS TYPE: [Service business / E-commerce / Coaching / etc.]
SALES MODEL: [Call-booking / Direct purchase / Hybrid]

---

PIPELINE STRUCTURE:

STAGE 1: NEW LEAD
  Entry condition: Lead submits form or ad. Automatically entered by n8n sync.
  Automations on entry: Speed-to-lead SMS sequence starts (Touch 1 immediate)
  Goal: Make first contact within 5 minutes
  Exit condition: First contact confirmed (lead replies or picks up call) → CONTACTED
  Max time in stage: 24 hours
  Stall action: Alert to sales rep + second SMS sequence

STAGE 2: CONTACTED
  Entry condition: First contact made and confirmed
  Automations on entry: [Follow-up sequence continues per speed-to-lead plan]
  Goal: Qualify the lead (run BANT qualification)
  Exit condition: Qualified → QUALIFIED / Does not qualify → DISQUALIFIED
  Max time in stage: 3 days
  Stall action: Additional outreach attempt → Long-term Nurture if no response

STAGE 3: QUALIFIED
  Entry condition: Lead meets BANT qualification criteria (score 3/4 or 4/4)
  Automations on entry: Booking link sent via SMS + Email
  Goal: Get the call booked
  Exit condition: Call scheduled → CALL BOOKED / Declines → Long-term Nurture
  Max time in stage: 5 days
  Stall action: Re-send booking link, offer alternative times

STAGE 4: CALL BOOKED
  Entry condition: Lead selects a time on the calendar
  Automations on entry: Booking confirmation SMS + Email / Reminder sequence starts
  Goal: Lead shows up to the call
  Exit condition: Call happens → CALL COMPLETED / No-show → CONTACTED (re-book)
  Max time in stage: Until scheduled call date + 2 hours
  Stall action: No-show handling sequence fires

STAGE 5: CALL COMPLETED
  Entry condition: Sales call was completed (manually moved by sales rep)
  Automations on entry: Post-call follow-up email sends in [X] hours
  Goal: Get a decision (yes or no)
  Exit condition: Pays → CLOSED/WON / Declines → Long-term Nurture or Disqualified
  Max time in stage: 5 days
  Stall action: Sales rep follow-up call

STAGE 6: CLOSED/WON
  Entry condition: Payment received
  Automations on entry: Welcome email + onboarding sequence starts / Remove from prospect sequences
  Goal: Smooth onboarding
  Exit condition: Onboarding complete (move to Client tag, out of pipeline)

LONG-TERM NURTURE
  Entry condition: Qualified but not ready / Stalled in Contacted or Qualified
  Automations on entry: 30-day and 90-day check-in sequences
  Goal: Keep warm until they are ready to buy
  Exit condition: Re-engages and books a call → QUALIFIED or CALL BOOKED

DISQUALIFIED
  Entry condition: Does not meet qualification criteria
  Automations on entry: Opt-out confirmation (if requested) / No sequences
  Exit condition: Does not exit

---

CONVERSION BENCHMARKS:

| Transition | Target rate | Current rate (if known) |
|-----------|------------|----------------------|
| New Lead → Contacted | 80%+ (within 24 hours) | [...] |
| Contacted → Qualified | 40-60% | [...] |
| Qualified → Call Booked | 50-70% | [...] |
| Call Booked → Showed | 70-80% | [...] |
| Showed → Closed/Won | 20-30% | [...] |

---

GHL SETUP NOTES:
Pipeline name: [Name]
Automations needed per stage: [List which GHL automations need to exist for each stage entry]
Tags required: [List all tags the pipeline stages require]
```

## Quality Check

- [ ] Every stage has entry condition, automations, goal, exit condition, and max time
- [ ] Long-term Nurture and Disqualified stages are defined
- [ ] Stall rules are documented for each stage
- [ ] Conversion benchmarks are documented
- [ ] GHL setup notes are complete enough for the n8n Automation Agent to build

## Status

Phase 3 complete.
