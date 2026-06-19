# Approval Flow

## Purpose

Design an n8n workflow that pauses for a human decision before continuing. Approval flows are used when an automation should not proceed until a person has reviewed and approved the action - sending a large batch of emails, publishing content, firing a high-value sequence, or making a significant system change. The output is the full approval workflow design with both the request path and the response paths.

## Used By

- n8n Automation Agent (primary)
- Marketing Director (is often the approver in these flows)

## Trigger

Use when an automation needs a human checkpoint before a consequential action, when a client requires sign-off before anything goes out, or when a workflow has caused errors in the past that a review step would have caught.

## Inputs Needed

- What action needs approval - required
- Who needs to approve (and who can approve as backup) - required
- How approval is given (Slack button, email link, form, webhook) - required
- What happens if approval is given - required
- What happens if rejected - required
- What happens if no response within [timeframe] - required

## Process

**Step 1: Define the three approval paths**

Every approval flow has exactly three outcomes:
1. **Approved**: The approver said yes. The workflow continues.
2. **Rejected**: The approver said no. The workflow stops or takes an alternative path.
3. **Timed out**: No response within the window. The workflow takes the default action (usually stops or alerts again).

All three must be designed before building.

**Step 2: Choose the approval mechanism**

| Mechanism | How it works | Best for |
|-----------|------------|---------|
| Slack button | Approval message sent to Slack with Approve/Reject buttons. Buttons fire webhooks back to n8n. | Fast approvals, team already uses Slack |
| Email link | Email contains a link that fires an n8n webhook when clicked. Two links: approve and reject. | External approvers or clients |
| n8n webhook | A unique webhook URL per approval request. Approver hits the URL to approve. | Technical approvers who can trigger webhooks |
| Form | A simple form (typeform, GHL form, etc.) sends the response back. | Non-technical approvers, multi-field responses |

**Step 3: Build the approval request path**

What does the approver receive?
- What information they need to make the decision
- A clear approve/reject action
- The deadline for response

**Step 4: Build the response paths**

Approved path:
- Log the approval (who approved, timestamp)
- Continue the workflow

Rejected path:
- Log the rejection with reason if captured
- Stop the workflow
- Notify the originator of the rejection

Timeout path:
- Log the timeout
- Send a reminder (if within timeout window)
- After final timeout: take the defined default action (usually STOP and alert)

**Step 5: Generate unique approval tokens**

If using email links or webhook URLs, each approval request must have a unique identifier to prevent:
- Replay attacks (clicking an old link)
- One approval covering multiple requests

Use a UUID generated per request, stored in the workflow state.

## Output Format

```
APPROVAL FLOW DESIGN - [Workflow Name] - [Date]

ACTION REQUIRING APPROVAL: [What will happen if approved]
APPROVER(S): [Primary] and [Backup if primary does not respond]
APPROVAL MECHANISM: [Slack button / Email link / Webhook / Form]
APPROVAL WINDOW: [How long before timeout - e.g., 4 hours / 24 hours]

---

APPROVAL REQUEST:

What the approver receives:
  Channel: [Slack / Email / Other]
  Content: "[Full message - what they're approving, key details, approve/reject options]"
  Approve action: [Button label / Link text] → fires [Webhook URL or action]
  Reject action: [Button label / Link text] → fires [Webhook URL or action]

---

WORKFLOW PATHS:

APPROVED PATH:
  1. Log approval: [Who, timestamp, workflow ID]
  2. Continue: [Next step in the main workflow]

REJECTED PATH:
  1. Log rejection: [Who, timestamp, reason if captured]
  2. Notify originator: "[Message to send]"
  3. Stop workflow

TIMEOUT PATH:
  Reminder fires at: [X hours]
  Content: "[Reminder message]"
  Final timeout at: [Y hours]
  Default action on final timeout: [STOP and alert / Take default action]
  Alert to: [Who gets notified of the timeout]

---

TOKEN GENERATION:

Unique identifier per request: {{ Math.random().toString(36).substr(2, 9) }}
Where stored: [n8n workflow data / Airtable table / GHL custom field]
Expiry: [Matches the approval window]
What happens if expired token is used: [Reject and alert]

---

NODE SEQUENCE:

1. [Trigger or previous workflow step]
2. Set node: Generate unique approval token
3. [Approval request node - Slack / Email / etc.]
4. Wait node: [X hours] OR Webhook node (listens for response)
5. IF node: Was response received AND was it approved?
   - Approved → Continue workflow
   - Rejected → Rejection path
   - No response → Timeout path
```

## Quality Check

- [ ] All three outcome paths are designed (approved, rejected, timeout)
- [ ] Approval mechanism is specified and buildable
- [ ] Unique token is generated per approval request
- [ ] Approver message includes all information needed to make the decision
- [ ] Timeout has both a reminder and a final action
- [ ] Approval and rejection are both logged with timestamps

## Status

Phase 3 complete.
