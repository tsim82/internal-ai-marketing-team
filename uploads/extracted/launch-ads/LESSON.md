# /launch-ads

## What It Does

This skill creates complete Meta ad campaigns from Claude Code - end to end. It builds the full stack: Campaign → Ad Set → Creative → Ad, all via the Meta Graph API. You confirm each step before it goes live.

No more clicking through Ads Manager. Describe your campaign, confirm the details, and Claude builds and launches it.

---

## When to Use It

- After `/script-ads` when you have creatives ready to launch
- When launching a new campaign for a client
- When duplicating a winning campaign with variations
- When you need to spin up ads fast without touching Ads Manager

---

## How to Run It

```
/launch-ads
```

Claude handles everything automatically:

1. Confirms campaign details (name, objective, budget, audience, placements)
2. Creates the campaign via Graph API
3. Creates the ad set with targeting and budget
4. Uploads creative assets (image or video)
5. Creates the ad creative
6. Creates the ad
7. Shows full summary and asks for activation confirmation
8. Activates the campaign
9. Logs to CRM if configured

---

## Example Output

```
Meta Campaign Builder

Campaign: D1 Training - Free Trial (March 2026)
Objective: Leads
Budget: $50/day

Ad Set: Dallas Parents 25-45
  Targeting: Dallas DMA, Parents, 25-45, Sports interests
  Placements: Instagram Feed, Stories, Reels
  Optimization: Lead form submissions

Creative: UGC Testimonial - Parent Story
  Format: Video (0:30)
  Primary text: "My son sat on the bench for 2 years..."
  Headline: "Free Trial Session - This Week Only"
  CTA: Sign Up
  Landing: Lead form

Ready to launch? (y/n)

Campaign activated!
  Campaign ID: 23850123456
  Ad Set ID: 23850234567
  Ad ID: 23850345678
  Status: ACTIVE

Logged to Airtable CRM.
```

---

## Requirements

- **Claude Code** - installed and running
- **Meta Ads MCP** - connected via `/meta-ads-setup` (required)
- **Airtable MCP** - for CRM logging (optional)

---

## Configure Your CLAUDE.md

```markdown
## Meta Ads
Ad Account ID: act_XXXXXXXXX
Page ID: XXXXXXXXX
Pixel ID: XXXXXXXXX
```

---

## Download

This skill is included in the Premium toolkit. After running the installer, the file lives at:

```
~/.claude/skills/launch-ads/SKILL.md
```

If you haven't downloaded the toolkit yet, head to **#Start Here** and complete the **Download ALL Resources** lesson.

---

## Part of the Ad System

```
/competitor-research → /scrape-ads → /ad-brief → /script-ads → /launch-ads
```

- **`/script-ads`** - writes the ad scripts
- **`/launch-ads`** - builds and activates the campaign on Meta

---

## Troubleshooting

**"Campaign creation failed - permission error"**
Your system user token needs `ads_management` permission. Re-run `/meta-ads-setup` to verify.

**"Creative upload failed"**
Video files must be < 4GB and in MP4/MOV format. Images must be JPG/PNG and < 30MB.

**"Ad rejected by Meta"**
Meta reviews ads after launch. If rejected, check the ad copy against Meta's advertising policies. Common issues: before/after claims, income claims, health claims.

---

## Changelog

- **v1.0** - Full campaign stack creation (campaign → ad set → creative → ad), confirmation flow, activation control, CRM logging.
