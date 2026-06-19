# Apify MCP Tool

## Purpose

Web scraping and data extraction platform. Used by the Market Research Agent to collect competitor ad data, audience insights, social proof, and market research at scale.

## Agents That Use This Tool

- **Market Research Agent** (primary) - all research and scraping tasks
- **Copywriter** (supporting) - pulling customer language from reviews and forums

---

## Setup

**Config file:** `mcp-configs/apify.json`

**Credentials needed:**
- Apify API Token

**How to get credentials:**
1. Log into console.apify.com (or create a free account)
2. Go to Settings → Integrations (or API & Integrations)
3. Copy your personal API token
4. Note: the free tier allows limited Actor runs per month - upgrade for regular use

**Environment variable:**
```
APIFY_TOKEN=your_apify_api_token
```

---

## What the Market Research Agent Uses This For

### Facebook/Meta Ad Library Scraping
- Actor: Search Apify Store for "Facebook Ads Scraper" or "Meta Ad Library"
- Use case: Pull competitor ads for a specific keyword, page, or industry
- Output: Ad creative descriptions, copy text, active status, run duration
- How the agent uses it: Feed results into hook-research.md and objection-research.md

### Google Reviews and Trustpilot Scraping
- Actor: "Google Maps Reviews Scraper" or "Trustpilot Reviews Scraper"
- Use case: Pull customer language, recurring complaints, and praise from reviews
- Output: Review text, star rating, date
- How the agent uses it: Extract exact phrases for VoC copy, identify recurring pain points and objections

### Reddit and Quora Research
- Actor: "Reddit Scraper" or "Quora Scraper"
- Use case: Pull discussions about specific pain points or topics relevant to the target audience
- Output: Thread content, top comments, upvote counts
- How the agent uses it: Identify how the audience talks about their problem in their own words

### LinkedIn Company and Job Post Scraping
- Actor: "LinkedIn Scraper" or "LinkedIn Jobs Scraper"
- Use case: Research competitor agencies and B2B targets
- Output: Company info, job posts, employee counts

### Google Search Results (SERP)
- Actor: "Google Search Results Scraper"
- Use case: See what content ranks for specific queries relevant to the target audience
- Output: Title, URL, meta description, position
- How the agent uses it: Understand what information the audience is searching for

---

## Standard Research Process

When the Market Research Agent runs a research task:

1. Identify which Actor matches the data source needed
2. Search Apify Store for the best-rated Actor for that source
3. Run the Actor with the target URL, keyword, or search query
4. Pull the dataset output
5. Filter and extract the relevant content
6. Store findings in the appropriate knowledge base folder or return for the requesting agent

---

## Output Storage

Research outputs are stored in:
- `knowledge-base/` folders when they should persist across sessions
- Returned directly when the requesting agent only needs them for one task

Competitor ad findings are summarized and stored per the Market Research Agent's format.

---

## Test Task (Verify Connection Works)

After adding credentials, run this to confirm the connection:

> "Search the Apify Actor store for a Facebook ad scraper and show me the top 3 results."

If it returns Actor names, descriptions, and ratings, the connection is working.

---

## Risks and Permissions

- Scraping must comply with platform terms of service - do not scrape personal data
- Rate limit Actor runs to avoid hitting Apify usage limits
- Do not scrape private data or data behind authenticated walls without authorization
- Some Actors cost credits per run - check pricing before running large jobs

---

## Status

Not connected. Config template is at `mcp-configs/apify.json`. Token must be regenerated before use (previous token was rotated). Fill in new credentials when ready.
