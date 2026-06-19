# Master Prompt Guide

Every prompt you need to run this team, from first setup to daily use. Copy, fill in the brackets, and paste into Claude Code.

---

## How to Use This Doc

- Prompts starting with `@agent-name` go directly to that agent
- Prompts starting with `@marketing-director` let the director route and coordinate
- Fill in everything in `[brackets]` before sending
- When MCP tools are connected, agents pull data directly - paste data manually if tools are not yet connected

---

## Table of Contents

1. [First-Time Setup](#1-first-time-setup)
2. [New Client Onboarding](#2-new-client-onboarding)
3. [Campaign Build](#3-campaign-build)
4. [Copy and Creative](#4-copy-and-creative)
5. [Funnels and Automations](#5-funnels-and-automations)
6. [CRM and Follow-Up](#6-crm-and-follow-up)
7. [Weekly Operations](#7-weekly-operations)
8. [Monthly Operations](#8-monthly-operations)
9. [Research and Intel](#9-research-and-intel)
10. [QA and Compliance](#10-qa-and-compliance)
11. [Finance and Budget](#11-finance-and-budget)
12. [Social and Video](#12-social-and-video)
13. [GEO and AI Search](#13-geo-and-ai-search)
14. [Quick Tasks](#14-quick-tasks)

---

## 1. First-Time Setup

### 1.1 Fill In Agency Profile

Run this after cloning the repo and filling in `agency-owner.md`.

```
@marketing-director

I've just filled in agency-owner.md with my agency details. Please:
1. Read agency-owner.md
2. Read knowledge-base/brand/voice-rules.md
3. Confirm you have everything you need to represent this agency correctly
4. List any gaps in the profile that would limit your ability to write branded content
```

### 1.2 Connect and Test a Tool

Run this after adding credentials for each MCP tool.

```
@marketing-director

I've just connected [Meta Ads / GoHighLevel / Google Analytics / Airtable / n8n / Apify].

Please:
1. Run the test task from mcp/tools/[tool-name].md to confirm the connection works
2. List what this agent can now do that it could not do before
3. Tell me what the next tool to connect is and why
```

### 1.3 Verify the Full System

Run this once all tools are connected.

```
@marketing-director

Full system check. Please:
1. Read docs/agent-roster.md and confirm all 15 agents are available
2. Read mcp/mcp-registry.md and list which tools are connected and which are not
3. Read knowledge-base/index.md and tell me what knowledge base gaps would limit real client work
4. Tell me what needs to be done before we can onboard the first client
```

---

## 2. New Client Onboarding

### 2.1 Send the Client Intake Form

Before the kickoff call. Send the client the content of `templates/intake/client-intake.md`.

### 2.2 New Client Kickoff

After the intake form is back.

```
@marketing-director

New client onboarding. Here are the details:

Client name: [Name]
Business: [What they do in 1-2 sentences]
Target audience: [Who they serve]
Primary offer: [What they sell and the price]
Revenue goal: [Monthly revenue target]
Ad budget: [Monthly ad spend they are starting with]
Platforms: [Meta / Google / Both / Organic only]
CRM: [GHL or other]
Contract start date: [Date]

Intake form responses:
[Paste the completed intake form here]

Please:
1. Identify any gaps in the intake before we begin strategy
2. Create the client profile in knowledge-base/clients/ using the client template
3. Run audience research and offer documentation in parallel
4. Run budget planning with the CFO Agent
5. Tell me what you need before we can move to the build phase
```

### 2.3 Document the Offer

```
@offer-agent

Document the offer for [Client name].

Here's what I know about their offer:
- What they sell: [Description]
- Price: $[X]
- Who it's for: [Audience]
- What the client gets: [Main components]
- Result/transformation: [What outcome the buyer gets]
- Timeline to results: [How fast]
- Guarantee: [If any]
- What they don't have to do: [Pain points removed]

Please build the offer document using skills/offers/offer-buildout.md and save it to knowledge-base/offers/[client-slug].md.
```

### 2.4 Create the Strategy Brief

```
@marketing-director

Strategy brief for [Client name].

We have completed:
- Client intake: knowledge-base/clients/[slug]/client-profile.md
- Offer doc: knowledge-base/offers/[slug].md
- Audience research: [yes / no - run it if not]
- Budget plan: [yes / no - run it if not]

Please create the full strategy brief covering:
1. Audience summary with the primary hook angle
2. Offer positioning
3. Campaign structure (platforms, budget split, funnel stages)
4. Funnel type recommendation
5. CRM pipeline map
6. Key risks or gaps before we build

This brief needs to be approved before any copy or creative work starts.
```

---

## 3. Campaign Build

### 3.1 Full Campaign Launch

```
@marketing-director

Campaign launch for [Client name].

Campaign goal: [Leads / Booked calls / Sales]
Offer: [Offer name and price]
Audience: [Who we're targeting]
Platform: [Meta / Google / Both]
Monthly budget: $[X]
Target CPL: $[X]
Landing page: [Existing URL or "needs to be built"]
Launch date target: [Date]

Please coordinate the full build:
1. Paid Ads Agent: Campaign structure and targeting plan
2. Copywriter: Ad copy and landing page copy
3. Creative Design Agent: [Number] ad creative variations
4. Funnel Agent: Landing page [build / review] and thank-you page
5. n8n Automation Agent: Speed-to-lead and follow-up sequences
6. CRM Follow-Up Agent: Pipeline and CRM configuration
7. CFO Agent: Confirm the budget math works
8. QA Agent: Pre-launch check before anything goes live

Give me the order of operations and what you need from me at each step.
```

### 3.2 Campaign Structure Only

```
@paid-ads-agent

Build the campaign structure for [Client name].

Platform: [Meta / Google]
Goal: [Leads / Purchases / Call bookings]
Monthly budget: $[X]
Target CPL: $[X]
Audience: [Description]
Offer: [What we're promoting]

Using skills/paid-ads/campaign-structure.md, please deliver:
1. Campaign and ad set structure with audience per ad set
2. Budget split across TOF / MOF / BOF
3. Creative testing plan (how many variations, what to test first)
4. Naming convention for all elements
5. Targeting notes (what to include, what to exclude)
```

### 3.3 Pre-Launch QA Check

```
@qa-compliance-agent

Pre-launch check for [Client name / Campaign name].

Assets to review:
- Landing page URL: [URL]
- Ad copy: [paste or reference file]
- Email sequence: [paste or reference file]
- SMS sequence: [paste or reference file]
- Creative assets: [describe or reference]

Run skills/qa-compliance/pre-launch-check.md and return:
1. A completed checklist with Pass / Fail per item
2. Overall verdict: READY or HOLD
3. A must-fix list if HOLD, with specific instructions per item
```

---

## 4. Copy and Creative

### 4.1 Ad Copy

```
@copywriter

Write Meta ad copy for [Client name].

Offer: [Offer name and what it costs]
Audience: [Who we're targeting and their awareness level]
Main pain: [Primary frustration or problem]
Main dream: [What they want most]
Key proof: [Best social proof available]
Key objections: [Top 2-3 objections to address]
CTA: [What we want them to do]
Destination: [Landing page or booking page]

Deliver:
1. Three primary text variations using different hook types (pain mirror, proof/result, contrarian)
2. Five headline variations under 40 characters each
3. Three CTA button options
4. Flag any claims that need QA review before going live
```

### 4.2 Landing Page Copy

```
@copywriter

Write landing page copy for [Client name].

Offer: [Offer name and one-sentence promise]
Traffic source: [Where the traffic is coming from - Meta, Google, organic]
Awareness level of visitor: [Problem aware / Solution aware / Product aware]
Available proof: [Testimonials, case studies, numbers available]
CTA: [What the form asks them to do]
Key objections to address on the page: [List them]

Using skills/copywriting/landing-page-copy.md, deliver:
1. Full page copy from headline to form CTA
2. Notes on where proof assets should be placed
3. Suggested form fields
4. Thank-you page copy
5. Any claims that need QA review
```

### 4.3 Email Sequence

```
@copywriter

Write a follow-up email sequence for [Client name].

Sequence type: [Post-opt-in nurture / Post-booking reminder / No-show re-engagement]
Offer being promoted: [Name and price]
Audience: [Who they are and where they are in the funnel]
Number of emails: [X]
Tone: [Conversational / Direct / Story-driven]
End goal of the sequence: [Book a call / Show up / Re-engage]

Using skills/copywriting/email-sequence.md, deliver:
1. Full copy for each email (subject line, preview text, body, CTA)
2. Three subject line options per email
3. Timing recommendation between each email
4. Stop conditions (what makes the sequence stop)
```

### 4.4 SMS Follow-Up Sequence

```
@crm-follow-up-agent

Write the SMS follow-up sequence for [Client name].

Lead source: [Meta ads / Google / Organic]
Goal of sequence: [Book a call / Confirm appointment / Re-engage cold lead]
Number of touches: [6 recommended for new leads]
Timeframe: [7 days]

Using skills/crm-follow-up/sms-follow-up.md, deliver:
1. Full SMS copy for each touch (under 160 characters per message)
2. Timing for each touch (minutes/hours/days after opt-in)
3. Stop conditions for the sequence
4. TCPA compliance notes
5. Opt-out language for the final touch
```

### 4.5 Ad Creative Brief

```
@creative-design-agent

Create ad creative briefs for [Client name].

Number of concepts: [X]
Platform: [Meta feed / Reels / YouTube / other]
Offer being promoted: [Name]
Ad copy hook (first line): [Paste the hook from the Copywriter]
Audience: [Who we're targeting]
Assets available: [Photos / Video / None - will need to generate]

For each concept, deliver:
1. Concept type (pain moment / result / social proof / pattern interrupt / talking head)
2. Visual direction (what the viewer sees, what text overlay says)
3. AI image prompt if using generated imagery
4. Dimensions for each placement
5. Notes for the Creative Design Agent on what to build
```

### 4.6 VSL Script

```
@copywriter

Write a VSL script for [Client name].

Offer: [Name and price]
VSL length: [15 / 20 / 30 minutes]
Audience awareness level: [Problem aware / Solution aware]
Key proof points: [List what's available]
Offer reveal timing: [Early / Mid / End]

Using skills/copywriting/vsl-script.md, deliver:
1. Full word-for-word script with section labels
2. Retention devices every 3-4 minutes
3. On-screen text and graphics notes
4. Estimated runtime at 130 words per minute
5. Opening hook variations (3 options)
```

---

## 5. Funnels and Automations

### 5.1 Funnel Map

```
@funnel-agent

Create a funnel map for [Client name].

Traffic source: [Meta / Google / Email / Organic]
Offer: [What we're selling]
Goal: [Lead gen / Call booking / Direct sale]
CRM: [GoHighLevel]

Using skills/funnels/funnel-map.md, deliver:
1. Page-by-page funnel map with the purpose of each page
2. Form fields to collect at each step
3. CRM handoff point and pipeline stage
4. Upsell or downsell paths if applicable
5. Traffic-to-funnel match check (does the funnel match what the ad promises)
```

### 5.2 Landing Page Wireframe

```
@funnel-agent

Create a landing page wireframe for [Client name].

Offer: [Name and one-sentence promise]
Traffic: [Cold / Warm / Retargeting]
Conversion goal: [Opt-in / Book a call / Purchase]
Available proof assets: [Testimonials / Case studies / Numbers / None]

Using skills/funnels/landing-page-wireframe.md, deliver:
1. Section-by-section wireframe with the purpose of each section
2. Headline recommendation for each section
3. Proof placement notes
4. Mobile-first notes
5. CTA placement and copy direction
```

### 5.3 Speed-to-Lead Automation

```
@n8n-automation-agent

Build the speed-to-lead workflow for [Client name].

Form platform: [GoHighLevel / ClickFunnels / Other]
CRM: [GoHighLevel]
First touch method: [SMS / Call / Both]
Target time to first contact: 5 minutes or less
Sales rep notification: [Slack / Email / SMS to rep]

Using skills/n8n/workflow-map.md and skills/crm-follow-up/speed-to-lead.md, deliver:
1. Workflow map (trigger → path → output)
2. Node plan for n8n
3. Error handler setup
4. Test checklist to confirm it fires within 5 minutes
```

### 5.4 Booking Reminder Automation

```
@crm-follow-up-agent

Set up booking reminders for [Client name].

Booking tool: [GHL calendar / Calendly / Other]
Call type: [Strategy call / Estimate / Demo]
Reminder sequence: [Immediate confirmation, 24h, 2h, 15min]
Include reschedule link: [Yes / No]

Using skills/crm-follow-up/booking-reminders.md, deliver:
1. Copy for each reminder (SMS and email versions)
2. Timing for each reminder
3. No-show follow-up sequence (what happens if they miss)
4. Re-engagement path (does no-show go back to Contacted or stay in Call Booked)
```

---

## 6. CRM and Follow-Up

### 6.1 Pipeline Setup

```
@crm-follow-up-agent

Set up the GHL pipeline for [Client name].

Business type: [Service / Coaching / E-commerce / Other]
Sales process: [Call-based / Automated / Hybrid]
Goal: [Booked estimates / Strategy calls / Purchases]

Using skills/crm-follow-up/pipeline-stages.md, deliver:
1. Recommended pipeline stages with entry and exit criteria for each
2. Max time a lead should sit in each stage before a stall action
3. Tags needed for each stage
4. Automation triggers to set up per stage transition
5. Benchmark conversion rates to track
```

### 6.2 Lead Qualification Check

```
@crm-follow-up-agent

Run BANT qualification on the following leads for [Client name].

[Paste lead details - name, answers from intake form or call notes]

Using skills/crm-follow-up/lead-qualification.md, score each lead:
1. BANT score (Budget / Authority / Need / Timeline)
2. Overall tier: High Priority / Standard / Nurture / Disqualify
3. Recommended next action for each lead
4. GHL tags to apply
```

### 6.3 Stalled Lead Re-Engagement

```
@crm-follow-up-agent

Re-engagement plan for stalled leads for [Client name].

Leads stalled in: [Pipeline stage]
Days since last contact: [X days]
What we know about them: [Brief description]

Please:
1. Write a re-engagement SMS (3 options)
2. Write a re-engagement email (2 options)
3. Recommend whether to re-qualify or go straight to re-offer
4. Set a decision point: if no response in X days, move to Long-term Nurture
```

---

## 7. Weekly Operations

### 7.1 Weekly Review - Single Client

```
@analytics-agent

Weekly performance review for [Client name]. Week ending [Date].

Meta Ads data: [Paste or "pull directly"]
GHL pipeline data: [Paste or "pull directly"]
Google Analytics data: [Paste or "pull directly"]

Targets:
- CPL target: $[X]
- Show rate target: [X]%
- Close rate target: [X]%
- Revenue target: $[X]/month

Please:
1. Complete the weekly report (templates/reports/weekly-report.md)
2. Make a Scale / Keep / Iterate / Kill decision for every active ad
3. Identify the top risk for next week
4. List recommended actions with owner and due date
```

### 7.2 Weekly Review - All Clients

```
@marketing-director

Weekly review for all active clients. Week ending [Date].

Active clients:
- [Client 1]
- [Client 2]
- [Client 3]

Route the weekly review to the Analytics Agent for each client and compile:
1. Which clients are on target and which are off
2. The single most important action across all accounts this week
3. Any account that needs immediate escalation
```

### 7.3 Ad Optimization Decision

```
@analytics-agent

Ad performance review for [Client name]. Week of [Date].

[Paste ad-level metrics: name, spend, impressions, CTR, CPC, CPL, results]

For each ad, read in this order: Impressions → Frequency → CTR → CPC → LP CVR → CPL → Lead quality.

Return a Scale / Keep / Iterate / Kill decision for every ad with the reason and the next action.
Kill decisions should trigger a new creative brief request.
Scale decisions should not exceed 20% budget increase.
```

### 7.4 Content Calendar Review

```
@social-media-agent

Review this week's content performance for [Client name].

[Paste post-level data: platform, pillar, format, reach, engagement rate, saves, comments]

Using skills/analytics-optimization/content-performance-review.md:
1. Identify top 3 and bottom 3 posts with the reason for each
2. Note any patterns (what pillar, format, or hook type is working)
3. Give me 3 specific content recommendations for next week based on what worked
```

---

## 8. Monthly Operations

### 8.1 Monthly KPI Review

```
@analytics-agent

Monthly KPI review for [Client name]. Month: [Month Year].

[Paste or note where to pull data: Meta Ads, GHL, Google Analytics]

Targets this month:
- Revenue: $[X]
- Ad spend: $[X]
- CPL: $[X]
- Leads: [X]
- Show rate: [X]%
- Close rate: [X]%

Using skills/cfo/monthly-kpi-review.md, deliver:
1. KPI scorecard (actual vs. target vs. prior month)
2. Top 3 wins and top 3 problems with root cause
3. Funnel drop-off analysis and revenue gap calculation
4. Lead quality breakdown by source
5. Completed monthly report (templates/reports/monthly-report.md)
```

### 8.2 Monthly Next Actions

```
@analytics-agent

After completing the monthly review for [Client name], run the next actions process.

Using skills/analytics-optimization/next-actions.md:
1. Build the impact × effort matrix for all open items
2. Select the top 3 high-priority actions per agent for next month
3. Format as an action table: action, why, owner, due date, expected outcome
4. Flag anything that needs Marketing Director approval before starting
```

### 8.3 Monthly Report Delivery Prep

```
@qa-compliance-agent

Review the monthly report for [Client name] before it goes to the client.

Report file: [Reference file or paste content]

Run skills/qa-compliance/formatting-review.md and skills/qa-compliance/brand-voice-check.md:
1. Flag any em dashes or banned words
2. Confirm all numbers are consistent across sections
3. Confirm no placeholders remain unfilled
4. Return PASS or HOLD with specific fixes
```

---

## 9. Research and Intel

### 9.1 Full Market Research

```
@market-research-agent

Full market research for [Client name / Niche].

Business: [What they do]
Offer: [What they sell]
Audience: [Who they target]

Run all three research skills:
1. skills/research/audience-research.md - who they are, JTBD, language they use
2. skills/research/hook-research.md - what angles are working in this market
3. skills/research/objection-research.md - what stops people from buying

Deliver one combined research brief the Copywriter can use immediately.
Save to knowledge-base/research/ if I ask you to.
```

### 9.2 Competitor Ad Research

```
@market-research-agent

Competitor ad research for [niche] in [geographic market].

Pull active Meta ads for this space using Apify.
Search terms: [list 3-5 keywords]

Deliver:
1. Most common hook angles (what is the market saying)
2. Proof types being used (testimonials, numbers, results)
3. Offers and angles that appear in multiple ads (likely working)
4. Gaps - angles nobody is using
5. Top 3 hooks I should test, adapted for [Client name]'s offer
```

### 9.3 Audience VoC Research

```
@market-research-agent

Voice of customer research for [niche].

Pull reviews, forum posts, and comments from:
- Google reviews for [competitor or category]
- Reddit: [relevant subreddits]
- Any other relevant source

Deliver:
1. Exact phrases people use to describe their problem (copy-ready)
2. Recurring complaints about existing solutions (objections to address)
3. What they say when something works (proof language)
4. The most emotionally loaded words they use
```

---

## 10. QA and Compliance

### 10.1 Brand Voice Check

```
@qa-compliance-agent

Brand voice check on the following copy before it goes live:

[Paste the copy]

Asset type: [Ad / Landing page / Email / Social post / Other]
Client: [Client name]

Using skills/qa-compliance/brand-voice-check.md:
1. Flag every em dash with its location
2. Flag every banned word with a suggested replacement
3. Assess overall tone against voice-rules.md
4. Return PASS / MINOR REVISIONS / HOLD with specific rewrites for every flag
```

### 10.2 Claims Review

```
@qa-compliance-agent

Claims review on the following copy:

[Paste the copy]

Identify every specific claim (numbers, results, timelines, guarantees, income references).
For each claim:
1. PASS - claim is accurate and defensible as written
2. PASS WITH DISCLAIMER - claim needs qualifying language added
3. FAIL - claim is unsubstantiated, misleading, or a legal risk

Provide the exact disclaimer text for PASS WITH DISCLAIMER items.
Provide a rewrite for FAIL items.
```

### 10.3 Handoff Check

```
@qa-compliance-agent

Handoff review before this output goes to [receiving agent / client].

Deliverable: [Describe what it is]
Original brief: [Paste or reference]
Output to review: [Paste or reference]

Using skills/qa-compliance/handoff-review.md:
1. Confirm the output matches the brief
2. Flag any placeholders or [TBD] items remaining
3. Confirm the receiver has everything they need to act without sending it back
4. Return READY or REWORK with specific fix instructions
```

---

## 11. Finance and Budget

### 11.1 Budget Plan

```
@cfo

Budget plan for [Client name].

Revenue goal: $[X]/month
Average sale value: $[X]
Ad platform: [Meta / Google]
Proposed budget: $[X]/month

Benchmarks (use these if no client history exists):
- Lead-to-booked rate: 50%
- Show rate: 75%
- Close rate: 25%
- LP conversion rate: 30%

Using skills/cfo/budget-planning.md:
1. Reverse-engineer from revenue to leads to required budget
2. Tell me if the proposed budget is sufficient, fragile, or over-funded
3. Recommend the minimum viable budget
4. Calculate the max allowable CPA at target margins
```

### 11.2 Offer Profitability Check

```
@cfo

Profitability check for [Client name]'s offer.

Offer price: $[X]
Delivery cost per client: $[X]
Ad cost per client (CPA target): $[X]
Other costs per client: $[X]

Using skills/cfo/offer-profitability.md:
1. Calculate gross margin per client
2. Calculate break-even CPA
3. Tell me if the offer can scale profitably at target CPL
4. Flag if the economics are too tight to run paid ads profitably
```

### 11.3 Pricing Analysis

```
@cfo

Pricing analysis for [Client name].

Current price: $[X]
Competitor price range: $[X] - $[X]
Delivery cost: $[X]
Target margin: [X]%
Revenue goal: $[X]/month

Using skills/cfo/pricing-analysis.md:
1. Is current pricing positioned correctly vs. the market?
2. What is the revenue impact of a 20% price increase?
3. What is the minimum price to maintain target margin at current volume?
4. Recommend a pricing move with the rationale
```

---

## 12. Social and Video

### 12.1 Monthly Content Calendar

```
@social-media-agent

Build a content calendar for [Client name] for [Month].

Platforms: [Instagram / Facebook / LinkedIn / TikTok / All]
Posting frequency: [X posts per week per platform]
Pillars to hit: Education 40%, Social Proof 20%, Brand 20%, Engagement 10%, Offer 10%

Available assets: [Photos / Videos / Case studies / None]
Upcoming promotions or launches: [Describe if any]

Using skills/social-media/content-calendar.md, deliver:
1. Full month calendar with date, platform, pillar, format, and topic per slot
2. Asset needs list for the Creative Design Agent
3. Suggested hooks for the top 5 posts
```

### 12.2 Short-Form Video Script

```
@video-agent

Write a short-form video script for [Client name].

Platform: [TikTok / Reels / YouTube Shorts]
Length: [30s / 45s / 60s]
Topic: [What this video is about]
Goal: [Drive profile visits / Build trust / Generate DMs / Promote offer]
Hook style: [Question / Bold claim / Pattern interrupt / Pain mirror]

Using skills/video/short-form-video-script.md, deliver:
1. Word-for-word script with section timing [0-3s], [3-8s], [8-45s], [45-60s]
2. Text on screen direction per section
3. Visual direction per section
4. Three hook variations to test
```

### 12.3 YouTube Script

```
@video-agent

Write a YouTube video script for [Client name].

Topic: [Video topic]
Target length: [8 / 12 / 20 minutes]
Audience: [Who is watching and what they already know]
Goal: [Build authority / Capture leads / Rank for a keyword]
Keyword target (if SEO): [keyword]

Using skills/video/youtube-script.md, deliver:
1. Full word-for-word script with chapter markers
2. Cold open that does not start with "Hey guys"
3. Retention hook every 2-3 minutes
4. Title formula (result + timeframe or condition)
5. Thumbnail brief
6. Description template with chapters
```

### 12.4 HeyGen Avatar Script

```
@video-agent

Format a script for HeyGen avatar delivery for [Client name].

Script content: [Paste the raw script or describe what the video should say]
Tone: [Professional / Friendly / Authoritative / Energetic]
Estimated length: [X minutes]

Using skills/video/heygen-script.md:
1. Break into sentences of 15-20 words max
2. Remove all em dashes and ellipsis
3. Write out all abbreviations and numbers
4. Add [TONE:] and [PAUSE] markers where needed
5. Flag any words that need pronunciation notes
6. Estimate runtime at 130-150 words per minute
```

### 12.5 Repurpose a Piece of Content

```
@social-media-agent

Repurpose the following content for [Client name]:

Source: [Long video / Long written / Short video]
Content: [Paste or describe the source material]
Platforms to create for: [Instagram / Facebook / LinkedIn / TikTok / Email]

Using skills/social-media/repurposing-system.md, deliver:
1. Full asset list (what gets created from this source)
2. Brief per asset (format, platform, hook angle, key moment to use)
3. Owner and priority for each asset
```

---

## 13. GEO and AI Search

### 13.1 AI Visibility Snapshot

```
@geo-agent

AI visibility snapshot for [Client name].

Business: [What they do]
Location: [City / Region if local]
Target keywords or topics: [List 3-5]

Using skills/geo/ai-visibility-snapshot.md:
1. Check how [Client name] appears in AI-generated answers for their key queries
2. Check competitors who do appear
3. Identify what content or entity signals they are missing
4. Give me 3 actions to improve AI visibility in the next 30 days
```

### 13.2 AI Search Content Plan

```
@geo-agent

AI search content plan for [Client name].

Business: [What they do]
Target topics: [List topics they should be known for]
Current content: [Describe what exists - blog, YouTube, social, etc.]

Using skills/geo/ai-search-content-plan.md:
1. Identify the highest-value topics to create content for
2. Format each recommendation as a specific piece of content (title, format, angle)
3. Prioritize by impact on AI citation likelihood
4. Tell me which pieces to create first
```

---

## 14. Quick Tasks

### Ask the Director Anything

Use this when you're not sure which agent handles something.

```
@marketing-director

[Describe what you need in plain language]

If this involves multiple agents, route it. If it's a single-agent task, tell me which agent and what to give them.
```

### Review Any Output Before It Leaves

```
@qa-compliance-agent

Review this before it goes to [client / next agent / live]:

[Paste the output]

Check for:
- Em dashes
- Banned words
- Unverified claims
- Incomplete placeholders

Return READY or REWORK.
```

### Save Something to the Knowledge Base

```
@marketing-director

Save the following to the knowledge base:

Content: [Paste what should be saved]
Type: [Client profile / Offer doc / Case study / Research finding / Framework / Example / Swipe file]
Client: [If client-specific]

Choose the right folder, create the file with the right format, and update knowledge-base/index.md.
```

### Get a Status Update on Any Client

```
@marketing-director

Status update for [Client name].

Please:
1. Read their client profile from knowledge-base/clients/
2. Check the most recent output files in outputs/
3. Tell me where we are in the campaign, what's working, and what the next action is
```

### Debug a Campaign That's Not Performing

```
@analytics-agent

Debug [Client name]'s campaign. It's not hitting targets.

Current metrics: [Paste what you have]
Targets: [CPL $X, Show rate X%, Close rate X%]

Read the metrics in order: Impressions → Frequency → CTR → CPC → LP CVR → CPL → Lead quality.

Tell me:
1. Exactly where the breakdown is happening
2. What the most likely cause is
3. What to change first, second, and third
```

---

## Reference

| Agent | Tag | Best For |
|-------|-----|---------|
| Marketing Director | `@marketing-director` | Multi-agent tasks, planning, routing, anything unclear |
| Copywriter | `@copywriter` | All written copy |
| Paid Ads Agent | `@paid-ads-agent` | Campaign structure, ad setup, optimization |
| Market Research Agent | `@market-research-agent` | Audience research, competitor intel, hook mining |
| Offer Agent | `@offer-agent` | Offer positioning, value stack, guarantees |
| Funnel Agent | `@funnel-agent` | Funnel maps, landing page wireframes, checkout |
| CFO Agent | `@cfo` | Budget planning, pricing, profitability |
| Creative Design Agent | `@creative-design-agent` | Ad creative briefs, image prompts, thumbnails |
| Video Agent | `@video-agent` | Video scripts, HeyGen formatting, VSLs |
| Social Media Agent | `@social-media-agent` | Content calendars, social posts, repurposing |
| n8n Automation Agent | `@n8n-automation-agent` | Workflow builds, automation planning |
| CRM Follow-Up Agent | `@crm-follow-up-agent` | Pipeline setup, SMS/email sequences, qualification |
| Analytics Agent | `@analytics-agent` | Weekly reviews, performance data, funnel analysis |
| GEO Agent | `@geo-agent` | AI search visibility, entity authority, local SEO |
| QA Agent | `@qa-compliance-agent` | Any review before delivery or launch |
