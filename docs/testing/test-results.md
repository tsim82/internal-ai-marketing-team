# Phase 7 Test Results

**Test date:** 2026-06-19
**Mock client used:** SkyLine Roofing Co. (see `docs/testing/mock-client.md`)
**Agents tested:** Marketing Director, CFO Agent, Copywriter, QA/Compliance Agent

---

## Test 1: Marketing Director - Routing Logic

**Task given:** Plan a full Meta campaign launch for a residential roofing client. Break into tasks, route to the correct agents, and define the order of operations.

**Result:** PASS

**What worked:**
- Produced a 6-phase launch plan with clear sequencing (research/foundation → structure → copy/creative → automation → build/QA → final approval)
- Correctly identified all relevant agents and what each one delivers
- Told each agent what to read before starting
- Identified the critical missing information (landing page platform) before committing to Phase 4 automation planning
- Flagged that the timeline was tight and recommended treating July 1 as a target, not a hard date
- Secondary open questions (existing assets, sales process) were identified correctly and marked as non-blocking

**What to note:**
- The director referenced some agent paths using informal shorthand (e.g., `agents/paid-ads/agent.md`) when the actual folder is `agents/paid-ads-agent/`. This was not a functional problem in the test, but if the agent reads this literally and the path doesn't resolve, it could cause a file-not-found issue. See the gap note below.

**Gap found:** Agent folder naming is inconsistent. Some folders have the `-agent` suffix (e.g., `paid-ads-agent`, `creative-design-agent`) while others do not (`market-research`, `cfo`, `copywriter`, `marketing-director`). This means internal references between agents may sometimes use the wrong path. Documented in `docs/testing/known-gaps.md`.

---

## Test 2: CFO Agent - Budget Planning

**Task given:** Run full reverse-engineered funnel math for the mock client. Validate whether the $4,000/month budget can hit the 40 leads/10 jobs goal. Calculate min viable budget and max allowable CPA.

**Result:** PASS

**What worked:**
- Applied the funnel math framework correctly from revenue goal down to required budget
- Correctly identified the $4,000 budget as technically viable but fragile
- Recommended $5,000/month with clear rationale (25% CPL buffer for the learning phase)
- Calculated the max allowable CPA at 40% gross margin: $1,200 (actual projected CPA: $400 - strong economics)
- Flagged that the 55% close rate is unverified and a drop to 40% loses 3 jobs
- Set client expectations correctly (6-8 jobs in month 1, not 10)
- Saved output to `outputs/cfo/2026-06-19-skyline-roofing-budget-plan.md` without being asked to

**What to note:**
- Output was saved to the correct folder automatically. The outputs folder structure is working.

**Gap found:** None for this agent.

---

## Test 3: Copywriter - Ad Copy

**Task given:** Write 3 primary text variations (pain mirror, proof/result, contrarian), 5 headline variations, and 3 CTA options for a Meta lead gen campaign. Flag any claims that need QA review.

**Result:** PASS

**What worked:**
- Three variations used genuinely different hooks - not variations of the same idea
- Copy followed all voice rules: no em dashes, no banned words, contractions used naturally, conversational tone
- Proof and contrarian variations were specific and believable without requiring claims not in the brief
- Proactively flagged 5 items for QA review before the copy goes live: review count accuracy, one-day timeline qualification, insurance story consent, warranty terms verification, borderline insurance payout language
- Self-organized output cleanly with variation labels and format notes for creative
- Included production notes for the Creative Design Agent (where to add proof assets per variation)

**What to note:**
- The copy was clean enough to likely pass QA on the first review. The QA flags the Copywriter added were largely the same ones QA would catch - suggesting the agent has internalized the review criteria.

**Gap found:** None for this agent.

---

## Test 4: QA Agent - Brand Voice Check and Claims Review

**Task given:** Review intentionally flawed ad copy with known violations: em dashes, banned words (transform, cutting-edge, seamlessly, unleash, robust, elevate), a fabricated guaranteed ROI claim (15% home value increase), and manufactured urgency.

**Result:** PASS

**What worked:**
- Caught all 6 banned words (transform, cutting-edge, seamlessly, unleash, robust, elevate)
- Caught both em dashes with exact locations in the copy
- Issued a HOLD verdict for both the brand voice check and the claims review independently
- Caught the "15% home value guarantee" as a legal exposure item and flagged it for the Marketing Director (not just the Copywriter)
- Caught the manufactured urgency claim and explained why it fails
- Gave a specific rewrite suggestion for every single flagged item, not just "fix this"
- Correct routing: sent the 15% guarantee issue to Marketing Director as a framing decision, not just a wording fix
- Correct disclaimer language specified for the 3 claims that received "PASS WITH DISCLAIMER" verdicts
- Produced a prioritized fix checklist (Priority 1 legal/claims, Priority 2 voice, Priority 3 disclaimers)

**What to note:**
- The QA agent initially referenced `agents/qa-compliance-agent/agent.md` which is the correct path. No pathing issue here.

**Gap found:** None for this agent.

---

## Summary

| Agent | Test | Result | Gaps Found |
|-------|------|--------|-----------|
| Marketing Director | Campaign routing | PASS | Agent folder naming inconsistency |
| CFO Agent | Budget planning | PASS | None |
| Copywriter | Ad copy (3 variations) | PASS | None |
| QA Agent | Brand voice + claims review | PASS | None |

**Overall system verdict:** The core workflow is functioning correctly. All four agents read the right files, applied the right frameworks, and produced client-ready or near-client-ready outputs on the first run.

**One structural gap** was found: agent folder naming inconsistency. Documented and tracked in `docs/testing/known-gaps.md`.

---

## Tests Not Yet Run

These workflows were not tested in Phase 7 due to requiring live tool connections (MCP) or more complex multi-agent orchestration. They should be tested as the first real client engagements run through the system.

| Test | Agent(s) | Blocker |
|------|---------|---------|
| Audience research via Apify | Market Research Agent | Apify MCP not connected |
| GHL pipeline setup | CRM Follow-Up Agent | GHL MCP not connected |
| n8n workflow creation | n8n Automation Agent | n8n MCP not connected |
| Landing page wireframe | Funnel Agent | No live funnel tool |
| Full QA pre-launch check | QA Agent | Requires real landing page URL |
| Weekly report | Analytics Agent | Requires live GA4 and Meta data |
| Creative brief to output | Creative Design Agent | Requires AI image tool connection |

These will be addressed as part of Phase 8 (real client onboarding and live tool use).
