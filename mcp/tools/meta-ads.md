# Meta Ads MCP Tool

## Purpose

Read and write access to Meta (Facebook and Instagram) advertising accounts. Used to pull performance data, inspect campaigns, and create or update ads directly from Claude Code.

## Agents That Use This Tool

- **Paid Ads Agent** (primary) - campaign management, creative uploads, optimization
- **Analytics Agent** (supporting) - pulling performance metrics for reports
- **Creative Design Agent** (supporting) - confirming creative specs and active creatives

---

## Setup

**Config file:** `mcp-configs/meta-ads.json`

**Credentials needed:**
- Meta App ID and App Secret (from Meta for Developers)
- Long-lived Access Token with ad management scope
- Ad Account ID (format: `act_XXXXXXXXXX` - include the `act_` prefix)

**How to get credentials:**
1. Go to developers.facebook.com/apps → Create or open your app
2. Add the Marketing API product to your app
3. Go to Tools > Access Token Tool → Generate a token
4. Convert to a long-lived token (90-day or System User token recommended)
5. Required permissions: `ads_management`, `ads_read`, `pages_manage_ads`, `pages_read_engagement`
6. Get your Ad Account ID from Business Manager → Ad Accounts

**Environment variables:**
```
META_APP_ID=your_app_id
META_APP_SECRET=your_app_secret
META_ACCESS_TOKEN=your_long_lived_token
META_AD_ACCOUNT_ID=act_your_ad_account_id
```

---

## What the Paid Ads Agent Uses This For

### Reading data
- List all active campaigns and their status
- Pull campaign-level spend, impressions, reach, CPM
- Pull ad set-level CPM, frequency, CPR, CTR
- Pull ad-level CTR, CPC, CPL, spend, results
- Pull creative performance breakdown (by image/video)
- Pull audience insights for active ad sets

### Writing / making changes
- Create a new campaign (CBO, correct objective)
- Create ad sets under a campaign (audience, budget, schedule)
- Upload ad creatives (images/videos)
- Create ads linking creative to ad set
- Pause or activate individual ads, ad sets, or campaigns
- Update daily budgets (only within the 20% per 7-day rule)
- Duplicate an ad set for testing

### What this tool should NOT be used for
- Making budget changes without the CFO Agent or client approving the amount
- Activating campaigns that have not passed the QA Agent's pre-launch-check
- Increasing budgets by more than 20% in a 7-day window
- Running campaigns on the Traffic objective for lead gen (always Leads or Conversions)

---

## What the Analytics Agent Uses This For

- Pull the weekly performance table: all active campaigns and ad sets
- Pull creative-level performance for the ad performance review
- Pull frequency data to check for creative fatigue
- Pull spend data for the monthly report

---

## Test Task (Verify Connection Works)

After adding credentials, run this to confirm the connection:

> "List all active campaigns in the Meta Ads account and show me their current daily budget and spend today."

If it returns campaign names, budgets, and today's spend, the connection is working.

---

## Risks and Permissions

- Budget changes trigger real spend immediately
- Never activate a paused campaign without confirming with the owner
- Scope the token to the minimum needed: `ads_management` and `ads_read`
- If running campaigns for multiple clients, use separate ad accounts per client - never mix client data in one account

---

## Status

Not connected. Config template is at `mcp-configs/meta-ads.json`. Fill in credentials when ready.
