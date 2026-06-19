# Test Runbook

A guide for testing agent workflows as new tools are connected and new clients are onboarded. Use this after connecting each MCP tool and before running the first real client task.

---

## How to Run Tests

1. Open a Claude Code session in the project directory
2. Use the mock client from `docs/testing/mock-client.md` as your context
3. Paste the prompt from each test below into Claude Code with the relevant @agent tag
4. Compare the output to the expected behaviors listed for that test
5. Document results and any gaps in `docs/testing/test-results.md`

---

## Test 1: Marketing Director Routing (No MCP Required)

**Status:** PASS (tested 2026-06-19)

**Prompt:**
```
@marketing-director

New campaign launch for SkyLine Roofing Co. (see docs/testing/mock-client.md for full client details).

Platform: Meta
Budget: $4,000/month
Goal: 40 leads/month, 10 jobs/month, $120,000 revenue/month
Landing page: needs to be built
CRM: GoHighLevel
Launch target: 2026-07-01

Create a campaign launch plan. Break the work into tasks, route each to the correct agent with a brief, and define the order of operations.
```

**Expected behaviors:**
- Routes to at minimum: Market Research, Offer Agent, CFO Agent, Paid Ads, Copywriter, Funnel Agent, CRM, n8n, Creative Design, QA
- Phases the work correctly (research before copy, copy before creative, creative before QA)
- Asks what landing page platform is being used before committing to automation plan
- Flags missing information without blocking on it

---

## Test 2: CFO Agent Budget Math (No MCP Required)

**Status:** PASS (tested 2026-06-19)

**Prompt:**
```
@cfo

Budget planning for SkyLine Roofing Co.

Avg job value: $12,000
Revenue goal: $120,000/month from paid ads
Ad budget: $4,000/month
Benchmarks: lead-to-booked 50%, show rate 80%, close rate 55%, LP CVR 30%

Run the full reverse-engineered funnel math and tell me if the budget works.
```

**Expected behaviors:**
- Works backward from revenue to leads to budget (not forward from budget to revenue)
- Flags if the proposed budget is insufficient or fragile at the benchmark rates
- Calculates minimum viable budget
- Calculates max allowable CPA
- Sets realistic month-1 expectations vs. steady-state

---

## Test 3: Copywriter Ad Copy (No MCP Required)

**Status:** PASS (tested 2026-06-19)

**Prompt:**
```
@copywriter

Write Meta ad copy for SkyLine Roofing Co.

Offer: Free roof inspection + estimate
Audience: Atlanta homeowners 35-65, homes 12+ years old
Main pain: Worry about failing roof, distrust of contractors
Key proof: 25-year warranty, 300+ 5-star reviews, one-day installs
CTA: Book a free inspection

Deliver:
- 3 primary text variations (pain mirror, proof/result, contrarian)
- 5 headline variations (under 40 characters)
- 3 CTA button options
- Flag any claims that need QA review
```

**Expected behaviors:**
- Three variations use genuinely different hook types, not rephrases of the same idea
- No em dashes anywhere in the copy
- No banned words (see voice-rules.md)
- Contractions used naturally
- Proactively flags unverified claims for QA

---

## Test 4: QA Agent Brand Voice + Claims Check (No MCP Required)

**Status:** PASS (tested 2026-06-19)

**Prompt:**
```
@qa-compliance-agent

Run a brand voice check and claims review on this ad copy before it goes live:

[Paste copy with intentional errors: em dashes, banned words, an unsubstantiated ROI guarantee, and manufactured urgency]

Deliver:
- Brand voice check with specific flags and rewrites
- Claims review with PASS/PASS WITH DISCLAIMER/FAIL per claim
- Overall verdict: PASS / MINOR REVISIONS / HOLD
```

**Expected behaviors:**
- Catches every em dash with its location in the copy
- Catches every banned word with a suggested replacement
- Gives FAIL to unsubstantiated guaranteed ROI claims
- Gives FAIL or flags manufactured urgency that is not based on a real constraint
- Produces a prioritized fix checklist, not just a list of problems
- Routes legal/framing issues to Marketing Director, not just the Copywriter

---

## Test 5: Market Research Agent + Apify (Requires Apify MCP)

**Status:** NOT YET RUN

**Prompt:**
```
@market-research

Competitor ad research for Atlanta residential roofing.

Use Apify to pull active Meta ads from roofing contractors in the Atlanta area. Search for pages and ads related to "roof replacement Atlanta," "roofing Atlanta," and "Atlanta roofing contractor."

Deliver:
- Most common hook angles in this market
- Copy patterns appearing in multiple ads (likely working)
- Proof elements competitors are using
- Gaps or angles not being used
- Top 3 hooks to test for SkyLine adapted from what you found
```

**Expected behaviors:**
- Uses the Apify MCP to pull real ad data from Meta Ad Library or equivalent
- Synthesizes patterns, not just a raw data dump
- Identifies actual gaps, not just lists what competitors do
- Returns something the Copywriter can act on immediately

---

## Test 6: CRM Follow-Up Agent + GoHighLevel (Requires GHL MCP)

**Status:** NOT YET RUN

**Prompt:**
```
@crm-follow-up-agent

Set up the SkyLine Roofing pipeline in GoHighLevel.

Create:
- Pipeline: "SkyLine Roofing - Estimates"
- Stages: New Lead, Contacted, Qualified, Estimate Booked, Estimate Completed, Closed/Won, Long-term Nurture, Disqualified
- Tags needed: new-lead, sms-active, sms-stopped, estimate-booked, no-show, high-priority, disqualified

Verify the pipeline exists in GHL and confirm the tags were created.
```

**Expected behaviors:**
- Reads the GHL pipeline stages skill before acting
- Creates the pipeline and stages in the correct order
- Creates all requested tags
- Returns confirmation with the GHL location ID and pipeline ID for the automation agent

---

## Test 7: n8n Automation Agent + n8n MCP (Requires n8n MCP)

**Status:** NOT YET RUN

**Prompt:**
```
@n8n-automation-agent

Plan and build the speed-to-lead workflow for SkyLine Roofing.

Trigger: New form submission on the SkyLine landing page (GoHighLevel form)
Actions:
1. Write lead to GHL pipeline (New Lead stage, tag: new-lead)
2. Send immediate SMS to lead within 5 minutes
3. Notify sales rep via Slack
4. Log submission to Airtable error log (for tracking)
5. Error handler: if any step fails, notify via Slack and log to Airtable

First, create the workflow map. Then build it in n8n.
```

**Expected behaviors:**
- Creates the workflow map before building
- Uses native GHL and Slack nodes, not HTTP Request if native nodes are available
- Includes error handler on all paths
- Tests with a dummy submission before declaring done
- Returns the n8n workflow URL and workflow ID

---

## Test 8: Full Pre-Launch QA Check (Requires live landing page)

**Status:** NOT YET RUN

**Prompt:**
```
@qa-compliance-agent

Run the full pre-launch check for the SkyLine Roofing campaign.

Landing page URL: [real URL when available]
Ad copy: [attach completed copy]
Creative assets: [describe or attach]
Email sequence: [attach if built]
SMS sequence: [attach if built]

Use skills/qa-compliance/pre-launch-check.md and return a READY or HOLD verdict with a full issues log.
```

**Expected behaviors:**
- Tests every URL manually (not assumes they work)
- Confirms pixel fires on the LP and conversion event fires on the thank-you page
- Confirms form submits and appears in GHL
- Confirms speed-to-lead fires within 5 minutes of a test submission
- Returns a READY or HOLD verdict, not a partial answer

---

## Test 9: Analytics Agent Weekly Report (Requires live Meta and GHL data)

**Status:** NOT YET RUN

**Prompt:**
```
@analytics-agent

Run the weekly performance review for SkyLine Roofing. Week ending [date].

Pull data from Meta Ads and GHL. Targets: CPL $90, show rate 80%, close rate 55%.

Complete the weekly report template and give me a Scale/Keep/Iterate/Kill decision for every active ad.
```

**Expected behaviors:**
- Reads metrics in the correct order (Impressions → Frequency → CTR → CPC → LP CVR → CPL → Lead quality)
- Makes a Scale/Keep/Iterate/Kill decision for every ad based on the thresholds in the skill file
- Fills in the report template (templates/reports/weekly-report.md)
- Flags risks forward-looking, not just backward-looking

---

## Notes

- Tests 1-4 can be run at any time, no MCP required
- Tests 5-9 require specific MCP tools to be connected first
- Always use the mock client from `docs/testing/mock-client.md` for these tests, not a real client
- Document all results and gaps in `docs/testing/test-results.md`
