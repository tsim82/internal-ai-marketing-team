# /meta-ads-setup

## What It Does

This skill walks you through setting up the Meta Ads MCP server step-by-step so Claude Code can create, manage, and analyze your Meta ad campaigns directly from the terminal.

It handles everything: creating a Meta App, adding the Marketing API, generating a system user token (never expires), assigning your ad account, installing the MCP server, and registering it in your `.mcp.json` config. By the end, you'll have 15 Meta Ads tools available in Claude Code.

---

## When to Use It

- First-time setup - connecting Claude Code to Meta Ads
- When setting up a new client's ad account in Claude
- When your Meta token expires and you need to regenerate
- When troubleshooting Meta API connection issues

---

## How to Run It

```
/meta-ads-setup
```

Claude walks you through each step:

1. Checks that Python 3.10+ is installed
2. Guides you through creating a Meta App at developers.facebook.com
3. Adds the Marketing API product to your app
4. Creates a system user and generates a never-expire token
5. Assigns your ad account to the system user
6. Validates the token with a test API call
7. Installs the FastMCP server in a virtual environment
8. Registers the server in `~/.mcp.json` with your credentials
9. Verifies end-to-end with a test tool call

---

## Example Output

```
Meta Ads MCP Setup Wizard

Step 1/9: Checking Python version...
  Python 3.11.4 found

Step 2/9: Create your Meta App
  Go to: developers.facebook.com/apps
  Click "Create App" → Business type → name it "Claude Ads"
  Paste your App ID: ___

Step 3/9: Add Marketing API
  In your app dashboard, click "Add Product"
  Select "Marketing API"
  Done? (y/n): ___

[... guided steps ...]

Step 9/9: Verification
  Testing meta_list_campaigns...
  Success! Found 3 campaigns in ad account act_123456789

Setup complete! You now have 15 Meta Ads tools available:
  - meta_list_campaigns, meta_create_campaign
  - meta_list_adsets, meta_create_adset
  - meta_list_ads, meta_create_ad
  - meta_campaign_insights, meta_ad_insights
  - ... and 7 more
```

---

## The 15 Meta Ads Tools

Once installed, these tools are available in Claude Code:

| Tool | What It Does |
|------|-------------|
| `meta_list_campaigns` | List all campaigns |
| `meta_create_campaign` | Create a new campaign |
| `meta_update_campaign` | Update campaign settings |
| `meta_campaign_insights` | Get campaign performance data |
| `meta_list_adsets` | List all ad sets |
| `meta_create_adset` | Create targeting and budget |
| `meta_update_adset` | Update ad set settings |
| `meta_adset_insights` | Get ad set performance |
| `meta_list_ads` | List all ads |
| `meta_create_ad` | Create an ad |
| `meta_update_ad` | Update ad settings |
| `meta_ad_insights` | Get ad performance |
| `meta_list_audiences` | List saved audiences |
| `meta_create_audience` | Create a custom audience |
| `meta_account_insights` | Get account-level metrics |

---

## Requirements

- **Claude Code** - installed and running
- **Python 3.10+** - for the FastMCP server
- **Meta Business Account** - with admin access
- **Ad Account** - the account you want Claude to manage

---

## Download

This skill is included in the Premium toolkit. After running the installer, the file lives at:

```
~/.claude/skills/meta-ads-setup/SKILL.md
```

If you haven't downloaded the toolkit yet, head to **#Start Here** and complete the **Download ALL Resources** lesson.

---

## Part of the Ad System

```
/meta-ads-setup → /competitor-research → /scrape-ads → /ad-brief → /script-ads → /launch-ads
```

This is Step 1 - you need Meta Ads connected before you can launch campaigns with `/launch-ads`.

---

## Troubleshooting

**"Token validation failed"**
Make sure you assigned the ad account to the system user AND granted `ads_management` and `ads_read` permissions.

**"MCP server won't start"**
Check that the virtual environment was created correctly. Try: `cd ~/.claude/mcp-servers/meta-ads && source venv/bin/activate && python server.py`.

**"Permission denied on ad account"**
The system user needs to be added to the ad account with "Manage campaigns" permission in Business Settings.

---

## Changelog

- **v1.0** - Interactive setup wizard, system user token generation, FastMCP server installation, 15 Meta Ads tools, end-to-end verification.
