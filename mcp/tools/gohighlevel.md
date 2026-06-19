# GoHighLevel MCP Tool

## Purpose

Read and write access to GoHighLevel (GHL) CRM. Used to manage contacts, pipeline stages, tags, conversations, and follow-up sequences directly from Claude Code.

## Agents That Use This Tool

- **CRM Follow-Up Agent** (primary) - contact management, pipeline moves, sequence management
- **n8n Automation Agent** (supporting) - verifying CRM sync, checking field mappings, testing automations
- **Analytics Agent** (supporting) - pulling pipeline conversion data for reports

---

## Setup

**Config file:** `mcp-configs/gohighlevel.json`

**Credentials needed:**
- GHL Location API Key (for a specific sub-account, not the agency-level key)
- Location ID for the sub-account

**How to get credentials:**
1. Log into GoHighLevel
2. Go to Settings (gear icon) → Integrations → API Keys
3. Create a new Location API Key for the sub-account you want to connect
4. Copy the API key and the Location ID (visible in Settings → Business Info or in the URL)
5. Use the v2 API base URL: `https://services.leadconnectorhq.com`

**Environment variables:**
```
GHL_API_KEY=your_location_api_key
GHL_LOCATION_ID=your_location_id
```

---

## What the CRM Follow-Up Agent Uses This For

### Reading data
- Look up a contact by email or phone number
- Get all contacts in a specific pipeline stage
- Get the conversation history for a contact
- Check which tags are applied to a contact
- Pull contacts who haven't been contacted in X days (stalled leads)
- Get current pipeline stage counts for reporting

### Writing / making changes
- Create a new contact with fields: name, email, phone, source, tags
- Update an existing contact's fields (name, custom fields, notes)
- Move a contact to a different pipeline stage
- Add or remove tags from a contact
- Add a note to a contact record
- Mark a conversation as read
- Check and update appointment status

### What this tool should NOT be used for
- Sending bulk messages outside of approved sequences
- Creating or modifying automations directly in GHL (use n8n for automation logic)
- Deleting contacts unless explicitly instructed
- Changing pipeline structure or stage names

---

## Contact Schema

Standard fields used across all client pipelines:

| GHL Field | What It Stores | Notes |
|-----------|---------------|-------|
| firstName | First name | Required at creation |
| lastName | Last name | Required at creation |
| email | Email address | Required if no phone |
| phone | Phone number | Required if no email |
| source | Lead source | Matches UTM source or "Organic" |
| tags | Array of tag strings | Used to trigger automations |
| customField.[id] | Any custom field | Map by GHL custom field ID |

---

## Pipeline Stage Reference

Default stages (customize per client):
1. New Lead
2. Contacted
3. Qualified
4. Call Booked
5. Call Completed
6. Closed/Won
7. Long-term Nurture
8. Disqualified

See `skills/crm-follow-up/pipeline-stages.md` for entry/exit criteria per stage.

---

## Tag Logic

Tags are used to trigger GHL automations. Common tags used by the CRM Follow-Up Agent:

| Tag | When Applied | Triggers |
|----|-------------|---------|
| `new-lead` | On form submit | Speed-to-lead automation |
| `sms-sequence-active` | When sequence starts | Nothing (tracking only) |
| `sms-sequence-stopped` | When lead replies or books | Stops sequence |
| `call-booked` | On calendar booking | Booking confirmation + reminders |
| `no-show` | After missed call | No-show re-engagement sequence |
| `disqualified` | BANT score 1/4 | Removes from active pipeline |
| `long-term-nurture` | BANT score 2/4 | Moves to nurture sequence |
| `high-priority` | BANT score 4/4 | Flags for immediate human follow-up |

---

## Test Task (Verify Connection Works)

After adding credentials, run this to confirm the connection:

> "Pull the 5 most recently created contacts in GoHighLevel and show me their name, email, pipeline stage, and tags."

If it returns real contact data, the connection is working.

---

## Risks and Permissions

- Adding wrong tags can trigger unwanted automations on real leads
- Moving a contact to the wrong stage can break reporting and trigger incorrect sequences
- Never bulk-update more than 10 contacts at a time without confirming the operation
- Use a sandbox sub-account for testing before working on a live account

---

## Status

Not connected. Config template is at `mcp-configs/gohighlevel.json`. Fill in credentials when ready.
