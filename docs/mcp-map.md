# MCP Tool Map

Which agents use which MCP tools and for what.

---

## Tool-To-Agent Map

| Tool | Planning File | Primary Agent | Supporting Agents | Status |
|------|-------------|--------------|-------------------|--------|
| Claude Code | tools/claude-code.md | All agents | All agents | Active |
| n8n | tools/n8n.md | n8n Automation | CRM, Director | Not connected |
| Airtable | tools/airtable.md | n8n Automation | Analytics, Social | Not connected |
| Supabase | tools/supabase.md | n8n Automation | Analytics | Not connected |
| Apify | tools/apify.md | Market Research | Paid Ads | Not connected |
| Google Drive | tools/google-drive.md | Director | Analytics | Not connected |
| Meta Ads | tools/meta-ads.md | Paid Ads | Analytics, Creative | Not connected |
| Google Ads | tools/google-ads.md | Paid Ads | Analytics | Not connected |
| GoHighLevel | tools/gohighlevel.md | CRM Agent | n8n Automation | Not connected |
| Canva | tools/canva.md | Creative Design | Social Media | Not connected |
| Remotion | tools/remotion.md | Video Agent | Creative Design | Not connected |
| HeyGen | tools/heygen.md | Video Agent | Director | Not connected |
| YouTube | tools/youtube.md | Video Agent | Analytics, Social | Not connected |
| Facebook | tools/facebook.md | Social Media | Analytics | Not connected |
| Instagram | tools/instagram.md | Social Media | Creative Design | Not connected |
| LinkedIn | tools/linkedin.md | Social Media | Analytics | Not connected |
| TikTok | tools/tiktok.md | Social Media | Video Agent | Not connected |
| Slack | tools/slack.md | n8n Automation | Director, Analytics | Not connected |
| Gmail | tools/gmail.md | CRM Agent | Director | Not connected |
| Google Sheets | tools/google-sheets.md | Analytics | CFO | Not connected |
| Google Search Console | tools/google-search-console.md | GEO Agent | Analytics | Not connected |
| Google Analytics | tools/google-analytics.md | Analytics | Funnel, Paid Ads | Not connected |

---

## Agent-To-Tool Map

| Agent | Tools They Use |
|-------|---------------|
| Marketing Director | Google Drive, Slack |
| CFO | Google Sheets |
| Market Research | Apify, Google Search Console |
| Offer Agent | None required |
| Copywriter | None required |
| Funnel Agent | None required |
| GEO Agent | Google Search Console, Google Analytics |
| Social Media Agent | Instagram, Facebook, LinkedIn, TikTok, Canva |
| Video Agent | Remotion, HeyGen, YouTube |
| Creative Design Agent | Canva |
| Paid Ads Agent | Meta Ads, Google Ads |
| n8n Automation Agent | n8n, Airtable, Supabase, GoHighLevel, Slack |
| CRM Follow-Up Agent | GoHighLevel, Gmail |
| Analytics Agent | Google Analytics, Google Sheets, Meta Ads, Google Search Console |
| QA Agent | None required |

---

## Connection Priority

When ready to connect, start here:

1. Meta Ads (highest immediate impact)
2. GoHighLevel (lead follow-up)
3. Google Analytics (performance data)
4. Airtable (data management)
5. n8n (automation)
6. Apify (research)
7. Remaining tools as needed

---

## Status

All tools are in planning phase. No connections are live yet.
