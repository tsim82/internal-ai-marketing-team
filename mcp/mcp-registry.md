# MCP Tool Registry

Master list of all planned MCP tool connections. Update this when a tool is connected or decommissioned.

---

## Registry

| Tool | Config File | Planning Doc | Primary Agent | Status |
|------|------------|-------------|--------------|--------|
| Meta Ads | `mcp-configs/meta-ads.json` | `mcp/tools/meta-ads.md` | Paid Ads Agent | Not connected |
| GoHighLevel | `mcp-configs/gohighlevel.json` | `mcp/tools/gohighlevel.md` | CRM Follow-Up Agent | Not connected |
| Google Analytics | `mcp-configs/google-analytics.json` | `mcp/tools/google-analytics.md` | Analytics Agent | Not connected |
| Airtable | `mcp-configs/airtable.json` | `mcp/tools/airtable.md` | Analytics + n8n Agent | Not connected |
| n8n | `mcp-configs/n8n.json` | `mcp/tools/n8n.md` | n8n Automation Agent | Not connected |
| Apify | `mcp-configs/apify.json` | `mcp/tools/apify.md` | Market Research Agent | Not connected |
| Slack | `mcp-configs/slack.json` | `mcp/tools/slack.md` | n8n + Director | Not connected |
| Google Drive | `mcp-configs/google-drive.json` | `mcp/tools/google-drive.md` | Director + Analytics | Not connected |
| Gmail | `mcp-configs/gmail.json` | `mcp/tools/gmail.md` | CRM + Director | Not connected |
| Google Calendar | `mcp-configs/google-calendar.json` | - | Director | Not connected |
| Supabase | `mcp-configs/supabase.json` | `mcp/tools/supabase.md` | n8n + Analytics | Not connected |
| Notion | `mcp-configs/notion.json` | - | Director | Not connected |
| GitHub | `mcp-configs/github.json` | - | Director | Not connected |
| Filesystem | `mcp-configs/filesystem.json` | - | All agents | Not connected |
| Canva | - (Claude.ai built-in) | `mcp/tools/canva.md` | Creative Design Agent | Available via Claude.ai |
| HeyGen | - (Claude.ai built-in) | `mcp/tools/heygen.md` | Video Agent | Available via Claude.ai |
| Google Ads | - | `mcp/tools/google-ads.md` | Paid Ads Agent | Not connected |
| Google Search Console | - | `mcp/tools/google-search-console.md` | GEO Agent | Not connected |
| Google Sheets | - | `mcp/tools/google-sheets.md` | Analytics + CFO | Not connected |
| YouTube | - | `mcp/tools/youtube.md` | Video Agent | Not connected |
| Facebook | - | `mcp/tools/facebook.md` | Social Media Agent | Not connected |
| Instagram | - | `mcp/tools/instagram.md` | Social Media Agent | Not connected |
| LinkedIn | - | `mcp/tools/linkedin.md` | Social Media Agent | Not connected |
| TikTok | - | `mcp/tools/tiktok.md` | Social Media Agent | Not connected |
| Claude Code | built-in | `mcp/tools/claude-code.md` | All agents | Active (built-in) |

---

## Connection Priority Order

Connect tools in this order. Each one adds more operational capability.

| Priority | Tool | Why This Order |
|---------|------|---------------|
| 1 | Meta Ads | Enables live campaign management and data pulls |
| 2 | GoHighLevel | Enables CRM and lead management |
| 3 | Google Analytics | Enables funnel data for reports |
| 4 | Airtable | Enables structured data storage and error logging |
| 5 | n8n | Enables automation management and testing |
| 6 | Apify | Enables market research and ad intelligence |
| 7 | Slack | Enables agent notifications and error alerts |
| 8 | Google Drive | Enables doc access and deliverable storage |
| 9+ | Remaining tools | Based on client and workflow needs |

---

## Already Available Via Claude.ai

These tools are available as pre-built integrations in the Claude.ai web app. No MCP config needed if using Claude.ai - connect them in Settings → Integrations.

If using Claude Code CLI or IDE extension, use the config files in `mcp-configs/` to connect them manually.

- Canva (Creative Design Agent)
- Gmail (CRM Follow-Up Agent, Marketing Director)
- Google Calendar (Marketing Director)
- Google Drive (Marketing Director, Analytics Agent)
- HeyGen (Video Agent)
- Meta Ads (Paid Ads Agent)

---

## Setup Instructions

See `mcp/SETUP.md` for the full step-by-step setup guide.

See individual planning docs in `mcp/tools/` for per-tool credential instructions and agent usage details.

---

## Security Notes

- All `mcp-configs/*.json` files contain placeholder values only
- Real credentials go in `.env` (never committed - in `.gitignore`)
- Two tokens were rotated before repo publication: Airtable and Apify
- Scope every token to minimum required permissions

---

## Status

Setup complete. All config files, planning docs, and credential templates are ready. No tools are connected yet - connection requires filling in real credentials. See `mcp/SETUP.md` to connect when ready.
