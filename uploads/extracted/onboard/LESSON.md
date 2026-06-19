# /onboard

## What It Does

This skill runs the full client onboarding flow for your ad agency. It interviews you about the new client, researches their business and competitors, builds a customer avatar, creates the project folder structure, sets up the CRM record, and prepares everything for the first campaign.

One command replaces hours of onboarding work - gathering intel, creating folders, setting up tracking, and documenting everything.

---

## When to Use It

- When a new client signs and you need to onboard them
- When starting a new project and need the full research + setup package
- When you want a standardized onboarding process across all clients

---

## How to Run It

```
/onboard
```

Claude handles everything automatically:

1. Gathers client info (business name, contact, goals, budget, previous ad history)
2. Researches their business (website scrape, social media scan)
3. Researches their market and competitors
4. Builds a customer avatar (demographics, pain points, desires, objections)
5. Creates project folder structure (client folder, README, avatar, market intel)
6. Sets up CRM record in Airtable
7. Creates file storage (Dropbox/Drive if configured)
8. Sends notification webhook (optional)
9. Delivers summary with next steps

---

## Example Output

```
Client Onboarding: D1 Training - Plano, TX

Business Research:
  Website: d1training.com/plano
  Services: Youth speed/agility, adult fitness, team training
  Social: 2.4K IG followers, posts 3x/week
  Current ads: None running

Customer Avatar:
  Primary: Parents (35-50) of athletes aged 10-16
  Pain: Kid not improving, sitting on bench, falling behind peers
  Desire: Kid becomes starter, earns scholarship, builds confidence
  Objections: "Is it worth the money?" "Will my kid actually improve?"

Project Structure Created:
  Agency/clients/d1-training-plano/
    ├── README.md (client overview)
    ├── avatar.md (customer avatar)
    ├── market-intel.md (competitive landscape)
    └── campaigns/ (future campaign folders)

CRM Record: Created in Airtable (Status: Onboarding)

Next Steps:
  1. Run /competitor-research for their niche
  2. Run /scrape-ads to see competitor ads
  3. Run /ad-brief to build strategy
  4. Run /script-ads for first campaign creatives
```

---

## Requirements

- **Claude Code** - installed and running
- **Apify MCP** - for website/social research (included in Premium toolkit)
- **Airtable MCP** - for CRM record creation (included in Premium toolkit)

---

## Configure Your CLAUDE.md

```markdown
## Agency
Clients folder: Agency/clients/
Airtable base: appXXXXXXXXXXXX
CRM table: tblXXXXXXXXXXXX
```

---

## Download

This skill is included in the Premium toolkit. After running the installer, the file lives at:

```
~/.claude/skills/onboard/SKILL.md
```

If you haven't downloaded the toolkit yet, head to **#Start Here** and complete the **Download ALL Resources** lesson.

---

## Part of the Ad System

```
/onboard → /competitor-research → /scrape-ads → /ad-brief → /script-ads → /launch-ads
```

Onboarding is Step 0 - it sets up everything the rest of the pipeline needs.

---

## Troubleshooting

**"Website scrape returned nothing"**
Some sites block scraping. The skill falls back to manual info gathering if the scrape fails.

**"CRM record creation failed"**
Verify your Airtable base ID and table ID in CLAUDE.md. The table needs these fields: Client Name, Status, Contact, Notes.

---

## Changelog

- **v1.0** - Full onboarding flow: business research, avatar creation, project structure, CRM setup, notification webhooks.
