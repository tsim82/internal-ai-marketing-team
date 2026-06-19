# Airtable MCP Tool

## Purpose

Read and write access to Airtable bases. Used to store campaign data, track content calendars, log ad performance, manage client deliverables, and store structured data that needs to be referenced across multiple agents.

## Agents That Use This Tool

- **Analytics Agent** (primary) - logging weekly metrics, storing performance data
- **n8n Automation Agent** (primary) - logging automation errors, storing workflow data
- **Social Media Agent** (supporting) - reading content calendar data
- **Market Research Agent** (supporting) - storing research findings
- **Marketing Director** (supporting) - reviewing client status and deliverable tracking

---

## Setup

**Config file:** `mcp-configs/airtable.json`

**Credentials needed:**
- Airtable Personal Access Token
- Base ID for each base you want to access

**How to get credentials:**
1. Go to airtable.com/create/tokens
2. Click "Create new token"
3. Name it "Claude Code - Marketing Team"
4. Add these scopes: `data.records:read`, `data.records:write`, `schema.bases:read`
5. Under Access, select specific bases (do not grant access to all bases)
6. Copy the token (starts with `pat`)
7. Get Base IDs: open the base in Airtable → Help → API documentation → the Base ID is in the URL (starts with `app`)

**Environment variables:**
```
AIRTABLE_API_KEY=patXXXXXXXXX.XXXXXXXX
AIRTABLE_BASE_ID=appXXXXXXXXXXXXXX
```

If you have multiple bases (e.g., one for analytics, one for content), use multiple variables:
```
AIRTABLE_ANALYTICS_BASE_ID=appXXXXXXXX
AIRTABLE_CONTENT_BASE_ID=appXXXXXXXX
```

---

## Recommended Base Structure

### Base 1: Performance Tracking

**Table: Weekly Metrics**
- Week (date field)
- Client (text or linked record)
- Ad Spend ($)
- Leads
- CPL ($)
- Booked Calls
- Show Rate (%)
- Closed
- Revenue ($)
- Notes

**Table: Ad Performance Log**
- Ad Name
- Campaign
- Date Range
- Spend
- Impressions
- CTR
- CPL
- Decision (Scale/Keep/Iterate/Kill)
- Notes

### Base 2: Content Calendar

**Table: Content Pipeline**
- Post Title
- Platform
- Pillar (Education/Social Proof/Brand/Engagement/Offer)
- Format (Static/Carousel/Reel/Story)
- Status (Draft/In Review/Approved/Scheduled/Published)
- Publish Date
- Copy Doc Link
- Creative Link
- Engagement Rate (filled in after publish)

### Base 3: Automation Error Log

**Table: n8n Error Log**
- Timestamp
- Workflow Name
- Error Type
- Error Message
- Lead ID (if applicable)
- Resolution Status
- Notes

---

## What Each Agent Uses This For

**Analytics Agent:**
- Log weekly metrics after each report
- Read prior weeks' data for trend comparisons
- Store ad performance decisions (Scale/Kill/etc.)

**n8n Automation Agent:**
- Log all automation errors (this is the standard error handler output)
- Read error log to identify patterns
- Update resolution status when errors are fixed

**Social Media Agent:**
- Read the content calendar to understand what's scheduled
- Update post status as content moves through the pipeline
- Log engagement data after posts go live

**Market Research Agent:**
- Store audience research findings
- Log hook ideas and swipe file additions
- Record competitor ad observations

---

## Test Task (Verify Connection Works)

After adding credentials, run this to confirm the connection:

> "List all tables in my Airtable base and show me the first 3 records from each table."

If it returns table names and records, the connection is working.

---

## Risks and Permissions

- Write access can overwrite or delete records. Be specific with update operations.
- Never delete records unless explicitly instructed. Use a "Status: Archived" field instead.
- Scope the token to specific bases only, not the entire workspace.
- If multiple clients share one Airtable workspace, use separate bases per client.

---

## Status

Not connected. Config template is at `mcp-configs/airtable.json`. Token must be regenerated before use (previous token was rotated). Fill in new credentials when ready.
