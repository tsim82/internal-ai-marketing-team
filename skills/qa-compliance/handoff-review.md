# Handoff Review

## Purpose

Review a completed work package before it is handed from one agent to another or delivered to a client. A handoff review checks that the output is complete, correctly formatted, actionable for the receiving party, and free of any issues that would require it to be sent back. The output is a READY or REWORK verdict with a clear list of what is missing or broken.

## Used By

- QA Agent (primary)
- Marketing Director (reviews final client-facing handoffs)

## Trigger

Use any time a major output moves from one agent to another (Copywriter to Paid Ads Agent, Funnel Agent to n8n Automation Agent, etc.), or before any deliverable goes to a client.

## Inputs Needed

- The completed work package to review - required
- The original brief or task that produced this work - required
- The name and role of the receiving agent or client - required

## Process

**Step 1: Confirm the output matches the brief**

- Did the output address all parts of the brief?
- Are there any obvious gaps (sections missing, deliverables not included)?
- Is the output in the right format?

**Step 2: Confirm completeness by output type**

**Copy handoff (Copywriter to Paid Ads or Social):**
- [ ] All required copy elements present (headline, body, CTA)
- [ ] Platform and character limit requirements met
- [ ] Tone and voice match brand guidelines
- [ ] Claim review completed (see claims-review.md)
- [ ] No em dashes, no banned words

**Creative brief handoff (any agent to Creative Design):**
- [ ] Visual concept fully described
- [ ] Dimensions and platform specified
- [ ] Copy to appear in the creative is provided
- [ ] AI image prompt written if using AI generation
- [ ] Reference or style direction included

**Automation doc handoff (n8n Agent to another agent or build):**
- [ ] Workflow map complete
- [ ] Node plan complete
- [ ] Error handling documented
- [ ] No real credentials or API keys in the document
- [ ] Test payload written

**Analytics handoff (Analytics Agent to Director or Agents):**
- [ ] All findings follow the four-part format
- [ ] Every recommendation has an owner and due date
- [ ] Data sources cited
- [ ] Executive summary present

**Campaign handoff (any agent to launch):**
- [ ] Pre-launch checklist complete
- [ ] Verdict is READY
- [ ] All open issues resolved

**Step 3: Check for anything that would cause the receiving party to send it back**

Common reasons a handoff gets returned:
- Missing a required element
- Incomplete instructions ("make it look good" with no further direction)
- Wrong format (bullet list when a table was needed)
- Outstanding questions that should have been answered before handoff
- Placeholder text or [TBD] items that the producing agent should have filled

**Step 4: Confirm the receiving agent has everything they need**

Would the receiving agent or client be able to act on this output without coming back with questions? If not, what is missing?

## Output Format

```
HANDOFF REVIEW - [Work Package] - [Date]
QA Agent

FROM: [Producing agent]
TO: [Receiving agent or client]
WORK PACKAGE: [Description of what is being handed off]
ORIGINAL BRIEF REF: [What brief or task this output is responding to]

---

COMPLETENESS CHECK:

| Part of brief | Delivered? |
|--------------|----------|
| [What was requested - Part 1] | [Yes / No / Partial] |
| [Part 2] | [Yes / No / Partial] |

Gaps found: [List or None]
Format correct for receiving party: [Yes / No - describe issue]

---

OUTPUT-TYPE CHECKLIST:

| Required element | Status | Notes |
|-----------------|--------|-------|
| [Element] | [PASS / FLAG] | [Notes] |

---

BLOCKER CHECK:

Would the receiving party need to send this back for more information?
  [Yes - what would they ask / No]

Placeholder or [TBD] items remaining?
  [Yes - list location / No]

Open questions that should have been resolved?
  [Yes - list / No]

---

ISSUES LOG:

| # | Issue | Severity | Fix required |
|---|-------|---------|-------------|
| 1 | [What is missing or wrong] | [Must fix / Should fix] | [What the producing agent does] |

---

VERDICT: [READY - handoff approved / REWORK - issues must be resolved before handing off]

If REWORK: Return to [producing agent] with issues log. Do not hand off until re-submitted and re-reviewed.
If READY: Proceed with handoff to [receiving agent / client].

NOTES FOR RECEIVING PARTY:
[Any context they should know that is not in the work package itself]
```

## Quality Check

- [ ] The output was compared to the original brief
- [ ] Every required element was confirmed present or flagged as missing
- [ ] Blocker check was done (would the receiver need to send it back?)
- [ ] Placeholder and [TBD] items were caught
- [ ] Verdict is clear
- [ ] If REWORK, it is specific about what needs to change before resubmitting

## Status

Phase 3 complete.
