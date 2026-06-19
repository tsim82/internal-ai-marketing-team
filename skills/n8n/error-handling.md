# Error Handling

## Purpose

Design and document the error handling strategy for an n8n workflow. Workflows fail. An API times out, a payload arrives malformed, a rate limit is hit, or a record already exists. Without a planned error handler, failures are silent and data is lost. This skill produces the error handling plan that gets built into every workflow before it goes live.

## Used By

- n8n Automation Agent (primary)

## Trigger

Use as part of every node plan, before any workflow goes live. Also use when a workflow has been failing silently and needs error handling retrofitted.

## Inputs Needed

- Workflow map and node plan - required
- All external systems in the workflow (to identify their failure modes) - required
- Notification system available (Slack, email, etc.) - required
- Error log destination (Airtable, Google Sheets, etc.) - helpful

## Process

**Step 1: Identify the error types for this workflow**

Common n8n error types:

| Error type | What causes it | Default behavior without handling |
|-----------|---------------|----------------------------------|
| Webhook validation failure | Payload missing required field | Workflow fails silently |
| API timeout | External API did not respond in time | Workflow fails, no retry |
| Duplicate key / record exists | CRM record already exists with that email | Write fails silently or throws error |
| Authentication error | API key expired or invalid | All API calls fail |
| Rate limit hit | Too many API calls in a short window | Queue backs up or fails |
| Data format mismatch | Field type does not match expected type | Expression throws error |

For each workflow, identify which of these error types are possible based on the nodes and APIs involved.

**Step 2: Design the standard error handler pattern**

The standard error handler for most workflows:
```
Try [main workflow]
  If error:
    → Set node: capture error details (error message, timestamp, input data)
    → Slack notification: ping the right person/channel with the error
    → Error log: write the error to Airtable or Google Sheets
    → STOP (do not continue the workflow with bad data)
```

**Step 3: Design retry logic where appropriate**

Not every error needs a retry. Retry rules:
- **API timeout**: Retry up to 3 times with 5-second delays
- **Rate limit**: Retry after the rate limit reset window (check API docs)
- **Auth error**: Do not retry - alert immediately
- **Duplicate key**: Do not retry - route to an update path instead
- **Validation failure**: Do not retry - log and alert for manual review

n8n's built-in retry: In node settings, "Retry On Fail" can be configured per node.

**Step 4: Design the notification content**

When an error notification fires, the recipient needs:
- Workflow name
- Error type and message
- Input data that caused the failure (sanitized - no passwords or full card numbers)
- Timestamp
- Link to the n8n execution log (if self-hosted)

**Step 5: Design the error log structure**

Error log fields in Airtable or Google Sheets:
- Workflow name
- Execution timestamp
- Error type
- Error message
- Input payload summary (not full payload - key identifying fields only)
- Status (New / Investigated / Resolved)
- Resolution notes

**Step 6: Handle the duplicate record case separately**

Duplicates are common in lead intake workflows and should not be treated as errors. When a contact already exists:
- Route to an update path rather than an error path
- Update existing record with any new data
- Log that an update was made (not an error)

## Output Format

```
ERROR HANDLING PLAN - [Workflow Name] - [Date]

WORKFLOW: [Name]
NOTIFICATION CHANNEL: [Slack channel / Email address]
ERROR LOG DESTINATION: [Airtable base / Google Sheets]

---

ERROR TYPES FOR THIS WORKFLOW:

| Error type | Possible? | Where in workflow | Handling approach |
|-----------|---------|------------------|------------------|
| Webhook validation failure | [Yes/No] | Node 1 | [Approach] |
| API timeout | [Yes/No] | [Node N] | [Retry 3x / Alert] |
| Duplicate record | [Yes/No] | [Node N] | [Update path] |
| Auth error | [Yes/No] | [Node N] | [Alert immediately] |
| Rate limit | [Yes/No] | [Node N] | [Retry after X seconds] |
| Data format mismatch | [Yes/No] | [Node N] | [Log and alert] |

---

STANDARD ERROR HANDLER NODES:

After each error-prone node, attach:

ERROR NODE 1: Set (Capture Error Details)
  Fields to capture:
    - error_message: {{ $json.error.message }}
    - timestamp: {{ new Date().toISOString() }}
    - workflow_name: [Workflow name]
    - trigger_data_summary: [Key fields from the input, not full payload]

ERROR NODE 2: Slack (Send Notification)
  Channel: [Channel name]
  Message format:
    "n8n Error: [Workflow name]
    Time: {{ $json.timestamp }}
    Error: {{ $json.error_message }}
    Lead ID / Email: {{ $json.trigger_data_summary }}
    Check execution logs for full details."

ERROR NODE 3: Airtable (Log to Error Table)
  Table: [Error Log]
  Fields:
    - Workflow Name: [Workflow name]
    - Timestamp: {{ $json.timestamp }}
    - Error Type: [Type]
    - Error Message: {{ $json.error_message }}
    - Input Summary: {{ $json.trigger_data_summary }}
    - Status: New

ERROR NODE 4: Stop and Error (halt workflow)

---

RETRY CONFIGURATION:

| Node | Retry? | Attempts | Delay |
|------|--------|---------|-------|
| [API node] | Yes | 3 | 5 seconds |
| [Duplicate check] | No - route to update path | - | - |
| [Auth node] | No - alert and stop | - | - |

---

DUPLICATE RECORD HANDLING:

Duplicate detection: [How duplicates are identified - email field, phone field]
Duplicate path: [Update existing record with new data] → [Log as update, not error]
Duplicate log: [Note in CRM contact record that an update was received]
```

## Quality Check

- [ ] All error types relevant to this workflow are identified
- [ ] Standard error handler (Set → Slack → Log → Stop) is documented for each error-prone node
- [ ] Retry logic is defined (and limited - not infinite retries)
- [ ] Duplicate records are routed to an update path, not treated as errors
- [ ] Notification content includes enough information for the recipient to investigate
- [ ] Error log structure is defined before build begins

## Status

Phase 3 complete.
