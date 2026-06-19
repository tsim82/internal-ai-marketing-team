# MCP Setup Guide

Step-by-step instructions for connecting tools to the internal AI marketing team. Follow this guide when you are ready to add real credentials and activate tool connections.

---

## Before You Start

1. Create a `.env` file in the project root by copying `.env.example`
2. Never commit `.env` to version control - it is already in `.gitignore`
3. Set up tools in the priority order below - the first three give the most immediate value
4. Test each connection before moving to the next

---

## Connection Priority Order

| Priority | Tool | Primary Agent | Config File |
|---------|------|--------------|-------------|
| 1 | Meta Ads | Paid Ads Agent | `mcp-configs/meta-ads.json` |
| 2 | GoHighLevel | CRM Follow-Up Agent | `mcp-configs/gohighlevel.json` |
| 3 | Google Analytics | Analytics Agent | `mcp-configs/google-analytics.json` |
| 4 | Airtable | Analytics + n8n Agent | `mcp-configs/airtable.json` |
| 5 | n8n | n8n Automation Agent | `mcp-configs/n8n.json` |
| 6 | Apify | Market Research Agent | `mcp-configs/apify.json` |
| 7 | Slack | Multiple agents | `mcp-configs/slack.json` |
| 8 | Google Drive | Director + Analytics | `mcp-configs/google-drive.json` |
| 9 | Gmail | CRM + Director | `mcp-configs/gmail.json` |

---

## How to Connect Each Tool

### Step 1: Get credentials

Read the tool's planning doc in `mcp/tools/[tool-name].md`. It includes step-by-step instructions for getting the credentials from each platform.

### Step 2: Add credentials to .env

Open your `.env` file and fill in the values for that tool. The `.env.example` file shows every variable name and where to get it.

### Step 3: Configure Claude Code

There are two ways to add MCP servers to Claude Code:

**Option A: Per-tool config files (recommended for this project)**

Each tool has its own JSON file in `mcp-configs/`. To activate a tool, add its config block to your Claude Code settings.

In Claude Code, go to Settings → MCP Servers → Add from file, and point it to the relevant `mcp-configs/[tool].json` file.

Or add the config block manually to `~/.claude/settings.json` under `mcpServers`:

```json
{
  "mcpServers": {
    "meta-ads": {
      "command": "npx",
      "args": ["-y", "@anthropic/meta-ads-mcp-server"],
      "env": {
        "META_APP_ID": "your_value_here",
        "META_APP_SECRET": "your_value_here",
        "META_ACCESS_TOKEN": "your_value_here",
        "META_AD_ACCOUNT_ID": "your_value_here"
      }
    }
  }
}
```

**Option B: Project-level MCP config**

Create `.claude/mcp.json` in the project root. This file is already in `.gitignore` so it will not be committed.

Note: `.claude/mcp.json` is the project-specific MCP config location in Claude Code. User-level config lives at `~/.claude/settings.json`. Either location works - use the project-level file if you want tool connections scoped to this project only.

### Step 4: Restart Claude Code

After updating the config, restart Claude Code (or reload the MCP connections from Settings) so the new server is picked up.

### Step 5: Test the connection

Each tool's planning doc has a test task at the end. Run that task to confirm the connection is working before using it in real work.

### Step 6: Update the registry

After confirming a tool is connected and working, update `mcp/mcp-registry.md`:
- Change the Status from "Not connected" to "Connected"
- Add the date connected

---

## Already Available in Claude.ai

These tools are available as pre-built integrations in the Claude.ai web app and do not require manual MCP config:

- **Canva** - Connect via Claude.ai Settings → Integrations
- **Gmail** - Connect via Claude.ai Settings → Integrations
- **Google Calendar** - Connect via Claude.ai Settings → Integrations
- **Google Drive** - Connect via Claude.ai Settings → Integrations
- **HeyGen** - Connect via Claude.ai Settings → Integrations
- **Meta Ads** - Connect via Claude.ai Settings → Integrations

If you're using Claude Code (CLI or IDE extension) rather than the Claude.ai web app, you will need to configure these via the MCP config files in `mcp-configs/`.

---

## Security Checklist

Before going live with any tool connection:

- [ ] `.env` is in `.gitignore` and has never been committed
- [ ] `mcp-configs/*.json` files contain only placeholder values (no real keys)
- [ ] Real credentials are only in `.env` or Claude Code's settings (never in tracked files)
- [ ] Each token is scoped to minimum required permissions
- [ ] Airtable token has been regenerated (previous token was rotated)
- [ ] Apify token has been regenerated (previous token was rotated)
- [ ] A sandbox or test sub-account is used for initial testing on GHL and Meta Ads

---

## Troubleshooting

**Tool shows as available but returns errors:**
- Check that environment variables match the exact names in the config
- Confirm the token has not expired (Meta tokens expire; use System User tokens for longer life)
- Check that the API key has the required scopes/permissions

**Tool is not appearing in Claude Code:**
- Restart Claude Code after adding config
- Check for JSON syntax errors in the config file
- Confirm the `npx` package name is correct and the package exists

**n8n connection fails:**
- Verify the N8N_BASE_URL includes the protocol (https://) and has no trailing slash
- Confirm the API key is active in n8n Settings → API

**GHL returns permission errors:**
- Confirm you're using the Location API key, not the Agency key
- Verify the Location ID matches the sub-account the API key belongs to

---

## Status

No tools are connected yet. This guide is ready to follow when credentials are available.
