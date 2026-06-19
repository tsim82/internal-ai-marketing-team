# n8n MCP Tool

## Purpose

Read and write access to an n8n instance. Used to list, trigger, inspect, and manage automation workflows from Claude Code.

## Agents That Use This Tool

- **n8n Automation Agent** (primary) - creating and managing all workflows
- **CRM Follow-Up Agent** (supporting) - triggering follow-up sequences
- **Marketing Director** (supporting) - checking automation status for reporting

---

## Setup

**Config file:** `mcp-configs/n8n.json`

**Credentials needed:**
- n8n API Key
- n8n Base URL (your cloud or self-hosted instance URL)

**How to get credentials:**

*For n8n Cloud:*
1. Log into app.n8n.cloud
2. Go to Settings → API
3. Create an API key
4. Copy the key and your cloud instance URL (format: `https://your-org.app.n8n.cloud`)

*For self-hosted n8n:*
1. Log into your n8n instance
2. Go to Settings → API → Enable API
3. Create an API key
4. Your base URL is the URL you use to access n8n

**Environment variables:**
```
N8N_API_KEY=your_n8n_api_key
N8N_BASE_URL=https://your-instance.app.n8n.cloud
```

---

## What the n8n Automation Agent Uses This For

### Inspecting workflows
- List all active and inactive workflows
- Read a specific workflow's node structure
- Check the execution history of a workflow
- View the last N executions and their status (success/error)

### Triggering workflows
- Manually trigger a workflow by ID (for testing)
- Send a test payload to a webhook-triggered workflow

### Managing workflows
- Activate or deactivate a specific workflow
- Create a new workflow from a JSON definition
- Update an existing workflow's nodes or connections
- Duplicate a workflow for modification

### Debugging
- Pull the error details from a failed execution
- Check which node in a workflow caused a failure
- Review the input/output data at each node for a failed execution

---

## Workflow Categories in This System

| Category | What It Does | Trigger Type |
|---------|-------------|-------------|
| Speed-to-lead | Fires within 5 min of a new lead | Webhook (form submit) |
| SMS sequence | Sends timed follow-up SMS messages | Schedule + GHL webhook |
| Email sequence | Sends timed follow-up emails | Schedule + GHL webhook |
| CRM sync | Syncs lead data between platforms | Webhook |
| Booking reminders | Sends call reminders | GHL appointment webhook |
| Lead routing | Routes lead to correct pipeline | Webhook |
| Error notification | Alerts on automation failures | n8n error trigger |
| Weekly report pull | Pulls and assembles weekly data | Schedule (Monday AM) |

---

## n8n Node Types Reference

The n8n Automation Agent uses these node types when building or reviewing workflows:

| Node Type | Purpose | Priority |
|-----------|---------|---------|
| Webhook | Receive external data | Trigger first |
| Schedule | Time-based triggers | Trigger first |
| GHL node | Read/write GHL contacts | Native first |
| Airtable node | Read/write Airtable | Native first |
| Slack node | Send notifications | Native first |
| Set | Transform or format data | Utility |
| IF | Branching logic | Utility |
| Switch | Multi-branch routing | Utility |
| Code | Custom JS when no native node exists | Last resort |
| HTTP Request | External API calls with no native node | Before Code node |

---

## Error Handler Pattern

Every workflow must include this error handler setup:

```
Error trigger node
  → Set node (capture: workflow name, error message, timestamp, lead ID if available)
  → Slack node (notify: post to #automation-errors with the captured fields)
  → Airtable node (log: create record in the n8n Error Log table)
  → Stop And Error node
```

See `skills/n8n/error-handling.md` for full error type handling.

---

## Test Task (Verify Connection Works)

After adding credentials, run this to confirm the connection:

> "List all workflows in my n8n instance and show me which ones are currently active."

If it returns workflow names and statuses, the connection is working.

---

## Risks and Permissions

- Triggering a live workflow can send real SMS/emails and update real CRM records
- Always test workflows in an n8n sandbox or against a test contact before enabling on live leads
- Deactivating a workflow that is mid-sequence may cause leads to miss follow-up steps
- Activating a workflow that has not been fully tested can route leads incorrectly

---

## Status

Not connected. Config template is at `mcp-configs/n8n.json`. Fill in credentials when ready.
