# Imported Files Audit

Audit of files found in the repo during Phase 1 build. Routing table updated in Phase 2 after reading all SKILL.md files.

---

## Files Found

### all-skills.zip

- **Location:** `/all-skills.zip` (root of repo)
- **Extracted to:** `uploads/extracted/`
- **Type:** Collection of Claude Code skill files

---

## Extracted Skills - Full Routing Table

37 skill folders extracted. Each has a SKILL.md. Some have supporting scripts/ and references/ subfolders.

**Primary agent** = the agent that owns this skill.
**Also used by** = agents that reference or depend on this skill's output.
**Match type** = Direct (replaces a placeholder), Extends (adds capability), Utility (support tool), or Internal (not a marketing skill).

---

| Skill Folder | What It Actually Does | Primary Agent | Also Used By | Match Type | Notes |
|-------------|----------------------|---------------|--------------|------------|-------|
| `ad-brief` | Generates an Ad Intelligence Brief from scraped competitor ads in Airtable. Produces executive summary, competitor breakdowns, hook analysis, and a strategic playbook ranked by ad longevity. Requires `/scrape-ads` output. | `paid-ads-agent` | `market-research` | Extends | Adds real competitive creative intelligence. Complements `skills/paid-ads/ad-performance-review.md` and `skills/creative-design/ad-creative-brief.md` |
| `ad-order` | Creates a structured ad order document for a client. Pulls client info from Airtable CRM, generates creative briefs, audience targeting, and budget allocation. | `paid-ads-agent` | `cfo`, `creative-design-agent` | Extends | Connects offer + budget + creative into one doc. Complements `skills/paid-ads/campaign-structure.md` |
| `analyze-content` | Bulk-analyzes short-form videos. Downloads, transcribes via Whisper, extracts hooks via Claude/GPT, runs visual analysis via Gemini, generates embeddings, and writes results to Supabase + Airtable. | `analytics-optimization-agent` | `market-research`, `social-media-agent` | Extends | Heavy pipeline skill. Needs Supabase, OpenAI, and Gemini keys. Complements `skills/analytics-optimization/content-performance-review.md` |
| `build-page` | Builds complete conversion-optimized landing pages as self-contained HTML/CSS/JS files. Reads offer and audience context from CLAUDE.md before building. | `funnel-agent` | `copywriter` | Direct | Direct match for `skills/funnels/landing-page-wireframe.md`. This skill actually builds the page; the placeholder skill defines the wireframe structure. Both are useful. |
| `claude-api` | Guide for building apps with the Claude API and Anthropic SDK. Covers Python and TypeScript patterns, streaming, tool use, multi-turn conversations. | None | None | Internal | Not a marketing skill. Infrastructure reference. Does not map to any agent. |
| `cleanup` | Weekly workspace audit. Scans all project folders for bloated CLAUDE.md files, broken references, stale tasks, root clutter, and empty folders. Flags issues and proposes fixes before acting. | None | None | Internal | Maintenance utility. Not a marketing output skill. Use it on this repo itself periodically. |
| `competitor-analyst` | Analyzes competitor content (from Supabase database) to find top-performing hooks, video structures, and topics. Compares competitor wins against your own content to surface gaps. | `market-research` | `analytics-optimization-agent` | Extends | Requires content database in Supabase. Complements `skills/research/competitor-research.md`. This goes deeper than basic competitor research. |
| `competitor-research` | Builds a complete competitor database from scratch. Web search + finds Facebook Pages + scrapes Meta Ad Library Page IDs via Apify + populates Airtable with logos, handles, descriptions, and working Ad Library links. | `market-research` | `paid-ads-agent` | Direct | Direct match for `skills/research/competitor-research.md`. Replace the placeholder with this skill's workflow. Requires Airtable + Apify. |
| `content-analyst` | Analyzes the creator's own short-form content performance. Queries Supabase for hook effectiveness, engagement patterns, and outlier videos. Weekly reporting. | `analytics-optimization-agent` | `social-media-agent` | Extends | Requires Supabase with a `content` table. Complements `skills/analytics-optimization/content-performance-review.md`. Focused on your own content vs. `/competitor-analyst` which covers competitors. |
| `content-ideator` | Pulls ideas from Airtable Content Pipeline, researches each topic, and generates 5 video variations per topic. Saves each variation as its own Airtable record. Turns 1 idea into 3-5 filmable scripts. | `social-media-agent` | `video-agent` | Extends | Requires Airtable Content Pipeline with status fields. Bridges research to content creation. Sits between `/daily-content-researcher` (finds topics) and `/content-scripter` (writes the script). |
| `content-scripter` | Writes video scripts using proven hook frameworks (Kallaway hook psychology, 3-beat rule). Covers short-form (TikTok, Reels, Shorts) and long-form (YouTube, VSL). Reads scripting framework and hook swipe file before writing. Interactive filming card output. | `video-agent` | `copywriter`, `social-media-agent` | Direct | Direct match for `skills/video/short-form-video-script.md` and `skills/video/youtube-script.md`. More structured and framework-driven than the placeholders. |
| `daily-content-researcher` | Agentic morning researcher. Scrapes X, Reddit, and GitHub Trending live via Apify. Evaluates every result against content criteria (TAM, demo-ability, hook potential). Presents Top 10 filmable topics. Logs results to prevent repeat ideas. | `market-research` | `social-media-agent`, `video-agent` | Extends | Requires Apify + project reference files (avatar, viral content patterns, hook swipe file). Complements `skills/research/hook-research.md` significantly. |
| `launch-ads` | Launches Meta ad campaigns via the Graph API. Creates the full stack: campaign, ad set, creative, and ad. Handles objective, audience, placement, budget, and copy in one workflow. | `paid-ads-agent` | None | Direct | Direct match for `skills/paid-ads/launch-checklist.md`. This skill actually launches the campaign, not just checks a list. Requires Meta Ads MCP server (see `meta-ads-setup`). |
| `manage-email` | Scans Gmail, categorizes emails (brand deals, important, noise), drafts templated partnership replies with manager CC, and triages the inbox. | None | `crm-follow-up-agent` | Internal | Creator-focused email management. Not a direct marketing output skill. Useful for managing client comms if adapted. Does not cleanly map to an agent without customization. |
| `mcp-builder` | Guide for building MCP servers (Python/FastMCP and TypeScript). Covers design principles, tool planning, context limits, rate limiting, and evaluation. | None | None | Internal | Infrastructure skill. Not a marketing output. Use when building new MCP integrations for this team. |
| `meta-ads-setup` | Interactive wizard to install and configure the Meta Ads MCP server. Walks through Python setup, Facebook App creation, system user token, and `~/.mcp.json` registration. | `paid-ads-agent` | None | Extends | Prerequisites skill, not an output skill. Run once during Phase 5 (MCP setup). Maps to `mcp/tools/meta-ads.md`. |
| `morning` | Daily morning briefing. Runs full email triage (via `/manage-email`), fetches AI/Claude Code news, summarizes task priorities, and pulls account stats. All in one terminal output. | None | None | Internal | Creator/operator daily routine. Not a marketing output skill. Useful as a personal assistant workflow, not a client deliverable. |
| `my-business` | Interviews the user about their business through a friendly conversation and generates a complete, structured CLAUDE.md file from their answers. | None | None | Internal | Setup utility. The team already has `agency-owner.md` as the equivalent. Use this as a reference for how to structure a good CLAUDE.md profile interview. |
| `my-pitch` | Drafts cold DMs for a specific person (Noah) to pitch done-for-you Meta Ads to sports facility owners. Generates 3 DM angles: compliment opener, straight shooter, value drop. | `copywriter` | `crm-follow-up-agent` | Internal | Highly persona-specific (written for Noah). Useful as a pattern/template for writing cold outreach skills. The approach (3 angles, short format, CTA) can be adapted for general use. |
| `n8n` | Complete n8n workflow reference. Routes to sub-references for workflow patterns, MCP tools, node configuration, validation errors, expression syntax, JavaScript code nodes, and Python code nodes. | `n8n-automation-agent` | None | Direct | Direct match for all skills in `skills/n8n/`. Replace the placeholders with this skill's workflow. Has rich sub-references in a `references/` subfolder. |
| `nano-banana` | Generates professional images via the Gemini CLI nanobanana extension. Access to 6000+ curated pro prompts. Handles thumbnails, social graphics, product shots, illustrations, and image editing. | `creative-design-agent` | None | Extends | Extends `skills/creative-design/image-prompt.md` significantly. Provides an actual image generation pipeline, not just prompt writing. Requires GEMINI_API_KEY and nanobanana extension installed. |
| `onboard` | Full client onboarding workflow. Gathers business intel, sets up Airtable CRM record, creates project structure, configures tracking, and prepares for first campaign. | `crm-follow-up-agent` | `marketing-director` | Extends | Extends `skills/crm-follow-up/` and maps to `knowledge-base/sop/` (onboarding SOP). More complete than any existing skill. Run this at the start of every new client relationship. |
| `post-content` | End-to-end video publishing workflow. Takes a ready video, transcribes it, generates platform-specific captions in the creator's voice, runs a revision loop, then publishes to 6 platforms via Dropbox + Late API. | `social-media-agent` | `video-agent` | Extends | Requires Late API key and Dropbox setup. Complements `skills/social-media/content-calendar.md` and `skills/social-media/repurposing-system.md`. Production-ready workflow. |
| `post-record` | Post-recording workflow. Scans OBS footage folder, matches raw files to Airtable Content Pipeline records by reading the first few seconds of audio (creator announces video title), uploads to Dropbox, links in Airtable, and sets status to Editing. | `video-agent` | None | Extends | Requires Dropbox, Airtable, Whisper, and ffmpeg. OBS-specific. Maps to `skills/video/b-roll-plan.md` and `skills/video/short-form-video-script.md` pipeline. |
| `remotion-editor` | Edits videos programmatically using the Remotion framework. Adds captions, inserts b-roll, applies zooms and overlays. Handles the full video pipeline from raw file to final render. | `video-agent` | None | Direct | Direct match for `skills/video/remotion-prompt.md`. More detailed than the placeholder. Has its own project at `~/remotion-editor/`. |
| `repurpose` | Takes one piece of content and transforms it into multiple platform-specific formats. Covers Instagram caption, Twitter/X thread, LinkedIn post, email newsletter, YouTube description, TikTok caption, and blog post outline. | `social-media-agent` | `copywriter` | Direct | Direct match for `skills/social-media/repurposing-system.md`. This is a usable, production-ready version. |
| `respond-to-leads` | Manages and responds to inbound leads from ad campaigns. Reads lead data from CRM (Airtable or GHL), drafts personalized SMS and email responses, and tracks pipeline stage. Manages the New through Closed pipeline. | `crm-follow-up-agent` | None | Direct | Direct match for `skills/crm-follow-up/speed-to-lead.md` and `skills/crm-follow-up/sms-follow-up.md`. Requires Airtable or GHL MCP. |
| `scrape-ads` | Scrapes all competitor ads from Meta Ad Library via Apify. Downloads video ads, transcribes with Whisper, classifies angles and formats, and pushes complete database of competitor ads to Airtable. Requires `/competitor-research` output. | `market-research` | `paid-ads-agent` | Extends | Upstream dependency for `/ad-brief`. Extends `skills/research/competitor-research.md` significantly. Requires Apify + Airtable + optional Whisper + ffmpeg. |
| `script-ads` | Generates UGC ad scripts using the Problem-Agitate-Solution-CTA framework optimized for Meta and TikTok. Multiple script formats: talking head, voiceover + B-roll, screen recording, mixed. 3 variations by default. | `copywriter` | `paid-ads-agent`, `video-agent` | Direct | Direct match for `skills/copywriting/ad-copy.md`. More structured and format-specific than the placeholder. Also supports `skills/video/short-form-video-script.md`. |
| `setup` | One-time setup interview. Asks questions about business, audience, content, and tools. Generates a complete CLAUDE.md, scans installed skills, replaces all YOUR_* placeholders with real values, and configures MCP servers. | None | None | Internal | Setup utility for new projects. Already done for this repo. Reference this pattern if onboarding a new client into their own Claude Code project. |
| `shortform-analysis` | Deep 12-section analysis of short-form content performance. Covers hooks, topics, text hooks, visual formats, per-platform deep dives, and produces a scripter brief. Deeper than `/content-analyst`. | `analytics-optimization-agent` | `social-media-agent`, `video-agent` | Extends | Requires Supabase content database. Complements `skills/analytics-optimization/content-performance-review.md`. Use for quarterly reviews or when the weekly check is not enough. |
| `skill-creator` | Creates, edits, audits, and organizes Claude Code skills and CLAUDE.md files. Knows the skill anatomy rules, description requirements, and file structure standards. | None | None | Internal | Meta-skill for building skills. Useful for Phase 3 when building out detailed skill content. |
| `summarize` | Summarizes any content - URLs, articles, videos, documents, or pasted text - into a clean structured breakdown with TL;DR, key points, notable quotes, and action items. | None | `market-research`, `analytics-optimization-agent` | Internal | General utility. Not specific to marketing. Useful as a sub-step in research workflows. |
| `video-analyzer` | Analyzes any video using Gemini's video understanding. Breaks down content strategy, hooks, structure, pacing, and performance patterns. Accepts URL or local file. | `analytics-optimization-agent` | `market-research`, `video-agent` | Extends | Requires GEMINI_API_KEY. Pairs with `/video-downloader` for URLs. Complements `skills/analytics-optimization/content-performance-review.md`. |
| `video-downloader` | Downloads videos from YouTube, Instagram, TikTok, Twitter/X, and other platforms. Outputs to a local folder. Supports quality selection and format options. | `video-agent` | `analytics-optimization-agent`, `market-research` | Extends | Utility skill. Required by `/video-analyzer`, `/video-transcriber`, `/analyze-content`, and `/remotion-editor`. Maps to `skills/video/` as a supporting utility. |
| `video-transcriber` | Transcribes video files using Whisper. Cleans transcript, removes false starts, trims dead space. Accepts local file or URL. | `video-agent` | `analytics-optimization-agent` | Extends | Utility skill. Needed by multiple pipelines. Complements `skills/video/` and supports analytics workflows. |
| `youtube-competitor-analysis` | Scrapes YouTube competitor channels via YouTube Data API v3. Detects outlier videos (2x+ channel average). Grabs first 30s transcripts. Syncs everything to Supabase + Airtable. | `market-research` | `analytics-optimization-agent` | Extends | Requires YouTube Data API key + Supabase. Complements `skills/research/competitor-research.md`. YouTube-specific variation of the general competitor research pipeline. |

---

## Agent Routing Summary

How the extracted skills distribute across the team:

| Agent | Extracted Skills That Route To It |
|-------|----------------------------------|
| `market-research` | competitor-research, competitor-analyst, daily-content-researcher, scrape-ads, youtube-competitor-analysis |
| `paid-ads-agent` | ad-brief, ad-order, launch-ads, meta-ads-setup, scrape-ads (output) |
| `analytics-optimization-agent` | analyze-content, content-analyst, shortform-analysis, video-analyzer, youtube-competitor-analysis (output) |
| `social-media-agent` | content-ideator, post-content, repurpose |
| `video-agent` | content-scripter, post-record, remotion-editor, video-downloader, video-transcriber |
| `copywriter` | script-ads, content-scripter (shared), repurpose (shared) |
| `funnel-agent` | build-page |
| `crm-follow-up-agent` | respond-to-leads, onboard |
| `n8n-automation-agent` | n8n |
| `creative-design-agent` | nano-banana |
| `marketing-director` | onboard (shared) |
| Internal / no agent | claude-api, cleanup, manage-email, mcp-builder, morning, my-business, my-pitch, setup, skill-creator, summarize |

---

## Pipeline Dependencies

Skills that must run in a specific order:

```
competitor-research
    |
    +--- scrape-ads (needs Competitors table from competitor-research)
              |
              +--- ad-brief (needs Ad Research table from scrape-ads)
                        |
                        +--- script-ads / ad-order (uses brief for copy + targeting)
                                  |
                                  +--- launch-ads (needs creative + copy ready)

---

daily-content-researcher (finds topics)
    |
    +--- content-ideator (develops topics into 5 variations)
              |
              +--- content-scripter (writes the actual script)
                        |
                        +--- post-record (matches raw footage to pipeline)
                                  |
                                  +--- post-content (transcribes, captions, publishes)
```

---

## Skills With Active MCP/Tool Requirements

These skills require live tool connections to function. They are not usable until Phase 5 (MCP setup).

| Skill | Tools Required |
|-------|---------------|
| `competitor-research` | Airtable MCP, Apify MCP |
| `scrape-ads` | Airtable MCP, Apify MCP, Whisper (local), ffmpeg (local) |
| `ad-brief` | Airtable MCP |
| `ad-order` | Airtable MCP |
| `launch-ads` | Meta Ads MCP (run `meta-ads-setup` first) |
| `analyze-content` | OpenAI API, Gemini API, Airtable MCP, Supabase MCP, yt-dlp (local), ffmpeg (local) |
| `content-analyst` | Supabase MCP |
| `competitor-analyst` | Supabase MCP |
| `shortform-analysis` | Supabase MCP |
| `youtube-competitor-analysis` | YouTube Data API, Supabase MCP, Airtable MCP, Apify MCP (fallback) |
| `content-ideator` | Airtable MCP |
| `content-scripter` | Airtable MCP |
| `daily-content-researcher` | Apify MCP |
| `post-content` | Late API, Dropbox |
| `post-record` | Dropbox, Airtable MCP, Whisper (local), ffmpeg (local) |
| `respond-to-leads` | Airtable MCP or GHL MCP |
| `onboard` | Airtable MCP |
| `manage-email` | Gmail MCP |
| `nano-banana` | Gemini API, nanobanana Gemini CLI extension |
| `video-analyzer` | Gemini API |
| `video-downloader` | yt-dlp (local) |
| `video-transcriber` | Whisper (local), ffmpeg (local) |

---

## Skills Usable Right Now (No Live Connections Needed)

These skills work with file context and no external APIs:

| Skill | What You Can Do With It |
|-------|------------------------|
| `build-page` | Build a landing page as HTML from any offer and audience context |
| `repurpose` | Turn any existing content into multi-platform formats |
| `script-ads` | Write UGC ad scripts from a brief or CLAUDE.md context |
| `my-pitch` | Use the 3-angle DM pattern as a template for outreach copy |
| `summarize` | Summarize any pasted content |
| `n8n` | Plan and design n8n workflows (without executing them) |
| `skill-creator` | Create new skills for this team |
| `cleanup` | Audit this repo for drift and bloat |

---

## Files That Should Not Be Edited

All files in `uploads/extracted/` are source files. Do not edit them.

If content from these files is useful:
- Reference them from skill files with a note
- Copy relevant sections to `knowledge-base/` or skill content during Phase 3 buildout

---

## Existing Files Found (Not From Zip)

| File | Location | What It Is | Action |
|------|----------|-----------|--------|
| `agency-owner.md` | Root | Template for agency owner profile | Complete this file. Once done, pull voice and brand context into `knowledge-base/brand/voice-rules.md` |
| `mcp-configs/` | Root | Pre-built MCP config JSON files for 13 tools | Use in Phase 5 when connecting live tools |

### MCP Configs Found

The `mcp-configs/` folder contains pre-built JSON config files:
- `airtable.json`
- `apify.json`
- `filesystem.json`
- `github.json`
- `gmail.json`
- `gohighlevel.json`
- `google-calendar.json`
- `google-drive.json`
- `meta-ads.json`
- `n8n.json`
- `notion.json`
- `slack.json`
- `supabase.json`

These are reference configs for MCP connections. Use them in Phase 5. Do not publish or commit real API keys.

---

## Status

Phase 2 routing complete (2026-06-18). All 37 skills read and mapped to agents. No source files were edited.

Next step: Phase 3 - replace placeholder skill files with the detailed workflows from these extracted skills where a direct match exists.
