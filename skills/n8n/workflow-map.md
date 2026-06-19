# Workflow Map

## Purpose

Produce the high-level map of an n8n automation workflow before building any nodes. The workflow map documents the full trigger-to-output path in plain language so the team can review and approve the logic before any configuration starts. Building before mapping produces workflows that have to be rebuilt. Mapping first catches logic errors in minutes rather than hours.

## Used By

- n8n Automation Agent (primary)
- Marketing Director (reviews before build approval)
- CRM Follow-Up Agent (reviews workflows that touch the CRM)

## Trigger

Use before building any n8n workflow, or when auditing an existing workflow to understand or document what it does.

## Inputs Needed

- Automation goal (what should happen, triggered by what, ending where) - required
- Tools and platforms involved - required
- Any business rules or conditions (if/then logic) - required
- Who or what consumes the output - required

## Process

**Step 1: Write the automation goal in one sentence**

Before mapping anything, confirm the goal:
"When [trigger event], [what happens], resulting in [output or destination]."

Example: "When a new lead submits the Facebook Lead Form, their data is validated and synced to GoHighLevel, tagged based on their source, and the CRM Follow-Up Agent's SMS sequence fires."

If you cannot write this sentence, the requirements are not clear enough to map. Clarify before continuing.

**Step 2: Identify the trigger**

The trigger is the event that starts the workflow. Be specific:
- Webhook received from [source]
- Schedule (cron) - every [X] at [time]
- New row in Google Sheets
- New record in Airtable
- Form submission from [platform]
- Manual trigger (human-initiated via n8n)

**Step 3: Map the full path in order**

List every step the workflow must take, in order:

```
TRIGGER: [What fires the workflow]
  ↓
STEP 1: [What happens first]
  ↓
STEP 2: [What happens next]
  ↓ [Branch if conditional]
CONDITION: If [X] → STEP 3A
           If NOT [X] → STEP 3B
  ↓
STEP 4: [What happens after the condition]
  ↓
OUTPUT: [Where the data ends up / what action is taken]
```

**Step 4: Identify every external system involved**

List every system that the workflow reads from or writes to:
- Platform A (reads lead data from)
- Platform B (writes contact to)
- Platform C (sends notification to)

These are the integration points where credentials will be needed.

**Step 5: Identify the error points**

For each step that involves an external API or data transformation:
- What happens if the API fails?
- What happens if the data is in the wrong format?
- What happens if the workflow fires but nothing should have happened (a false trigger)?

Mark these as error points on the map.

## Output Format

```
WORKFLOW MAP - [Workflow Name] - [Date]

GOAL: "When [trigger], [what happens], resulting in [output]."

TRIGGER: [Specific trigger - what event, from what source]

---

WORKFLOW PATH:

TRIGGER: [Event description]
  ↓
1. [Step 1: what happens]
   Platform: [Which tool]
   Action: [Read / Write / Transform / Send]
   Error point: [Yes - what could fail / No]
   
  ↓
2. [Step 2]
   [Same format]

  ↓ [Conditional branch if applicable]
  
3A. If [condition is true]: [What happens]
3B. If [condition is false]: [What happens instead]

  ↓
4. [Final step or output]
   Platform: [Which tool]
   Output: [What is produced or where data ends]

---

SYSTEMS INVOLVED:

| System | Role | Integration type |
|--------|------|----------------|
| [Platform] | [Source / Destination / Both] | [Webhook / API / Native n8n node] |
| [Platform] | [...] | [...] |

---

ERROR POINTS AND HANDLING PLAN:

| Step | Possible error | Handling approach |
|------|--------------|------------------|
| [Step N] | [What could fail] | [Catch → Notify / Retry / Skip] |

---

CREDENTIAL REQUIREMENTS:

| System | Credential type needed |
|--------|----------------------|
| [Platform] | [API key / OAuth / Webhook token] |
[Note: no real credentials documented here - see n8n credential vault]

---

BUILD NOTES FOR n8n Automation Agent:
[Any notes on complexity, node preference, or build order]
```

## Quality Check

- [ ] Automation goal is written in one sentence before mapping starts
- [ ] Trigger is specific (not "when something happens")
- [ ] Every step is in order
- [ ] All conditional branches are mapped for both true and false paths
- [ ] All external systems are listed
- [ ] Error points are identified for every API call
- [ ] Credential requirements are listed without real values

## Status

Phase 3 complete.
