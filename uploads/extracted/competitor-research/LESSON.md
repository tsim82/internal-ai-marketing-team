# /competitor-research

## What It Does

This skill builds a complete competitor database from scratch for any niche. It researches competitors via web search, finds their Facebook Pages, scrapes Ad Library page IDs via Apify, and populates an Airtable table with logos, social handles, descriptions, and working Ad Library links.

The critical detail: Facebook has two different ID systems. A profile ID is NOT the same as an Ad Library ID. This skill uses Apify's Facebook Pages Scraper to get the correct `pageAdLibrary.id` - the one that actually works in Ad Library URLs.

---

## When to Use It

- When onboarding a new client and need to map their competitive landscape
- When entering a new niche and want to see who's running ads
- When building an ad strategy and need competitor intelligence
- When your competitor database is stale and needs refreshing

---

## How to Run It

```
/competitor-research
```

Claude handles everything automatically:

1. Asks for your niche, any seed competitors, and target count (default: 10+)
2. Creates a Competitors table in Airtable (if it doesn't exist)
3. Uses web search to find competitors across 3 tiers (micro, macro, ad leaders)
4. Runs Apify Facebook Pages Scraper to get page IDs and logos
5. Builds working Ad Library URLs using `pageAdLibrary.id`
6. Populates Airtable with all data (name, logo, category, social handles, Ad Library URL)
7. Verifies totals and category breakdown

---

## Example Output

```
Competitor Research: Sports Training Facilities (Dallas, TX)

Found 12 competitors:

| Name | Category | Ad Library | Ads Active |
|------|----------|-----------|-----------|
| D1 Training Plano | Macro | Link | Yes |
| Athlete's Arena | Micro | Link | Yes |
| EXOS | Ad Leader | Link | Yes |
| Cressey Sports | Macro | Link | No |
| ... | ... | ... | ... |

Breakdown: 4 micro, 5 macro, 3 ad leaders
All 12 saved to Airtable Competitors table.
Ad Library links verified: 10/12 active.
```

---

## The Facebook Dual-ID System

This is the #1 gotcha in competitor research:

| ID Type | Where It Comes From | Works in Ad Library? |
|---------|-------------------|---------------------|
| Profile ID | Facebook profile URL | NO |
| Ad Library ID | `pageAdLibrary.id` from Pages Scraper | YES |

The skill uses Apify to scrape the correct Ad Library ID. If you try to build Ad Library URLs with profile IDs, they'll return empty results.

---

## Requirements

- **Claude Code** - installed and running
- **Apify MCP** - for Facebook Pages Scraper (included in Premium toolkit)
- **Airtable MCP** - for storing competitor data (included in Premium toolkit)

---

## Configure Your CLAUDE.md

```markdown
## Agency
Airtable base ID: appXXXXXXXXXXXX
```

---

## Download

This skill is included in the Premium toolkit. After running the installer, the file lives at:

```
~/.claude/skills/competitor-research/SKILL.md
```

If you haven't downloaded the toolkit yet, head to **#Start Here** and complete the **Download ALL Resources** lesson.

---

## Part of the Ad System

```
/competitor-research → /scrape-ads → /ad-brief → /script-ads → /launch-ads
```

- **`/competitor-research`** - builds competitor database with Ad Library links
- **`/scrape-ads`** - scrapes all their active ads
- **`/ad-brief`** - generates intelligence report from scraped ads

---

## Troubleshooting

**"Apify scraper returned no results"**
The Facebook Pages Scraper needs valid Facebook Page URLs (not profile URLs). Double-check the URLs being passed.

**"Ad Library links show no ads"**
Make sure you're using `pageAdLibrary.id`, not the profile ID. Re-run the Apify scraper if needed.

**"Airtable table creation failed"**
Verify your Airtable base ID in CLAUDE.md and that your API token has write permissions.

---

## Changelog

- **v1.0** - Multi-tier competitor discovery, Apify Facebook Pages Scraper integration, correct Ad Library ID extraction, Airtable population, link verification.
