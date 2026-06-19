# Build Roadmap

Phase-by-phase plan for building out the complete internal AI marketing team.

---

## Phase 1 - Team Shell (Complete)

Status: Done.

What was built:
- Full folder structure
- All 15 agent folders with id.md, agent.md, README.md
- All 15 .claude/agents/ subagent definition files
- All placeholder skill files across 13 categories (60+ files)
- Knowledge base structure with brand voice rules
- MCP tool planning files for 21 tools
- Output folder structure
- Full documentation suite
- Imported files audit from all-skills.zip

---

## Phase 2 - Full Agent Instructions

Status: COMPLETE. All 15 agents have full operating instructions.

Goal: Write detailed, complete operating instructions for all 15 agents.

Tasks:
- [x] Marketing Director - Full decision logic, routing table, 5 example project plans, edge case handling
- [x] Copywriter - 8 strategies: awareness levels, PAS, AIDA, BAB, VSL structure, email sequence logic, headline toolkit, proof hierarchy
- [x] Paid Ads Agent - 8 strategies: CBO/ABO, creative testing, audience layering, funnel stages, scaling, cost control, fatigue diagnosis, Google Ads
- [x] Market Research Agent - 8 strategies: JTBD, competitor matrix, hook mining, objection mapping, psychographics, market sophistication, ad intelligence, VoC
- [x] Offer Agent - 8 strategies: value ladder, Hormozi formula, unique mechanism, guarantee construction, value stack, pricing/anchoring, urgency/scarcity, status quo positioning
- [x] Funnel Agent - 8 strategies: funnel type selection, CR benchmarks, wireframe formulas, upsell/downsell, nurture flow, funnel audit, checkout optimization, traffic matching
- [x] CFO Agent - 8 strategies: unit economics, budget planning, pricing/margin analysis, monthly KPI review, cash flow forecasting, ROAS/MER, P&L review, pricing increase logic
- [x] Social Media Agent - 4 strategies: content pillar system, platform-specific format rules, hook framework, content repurposing system
- [x] Video Agent - 4 strategies: short-form structure, YouTube long-form, VSL production framework, HeyGen/avatar script formatting
- [x] Creative Design Agent - 4 strategies: ad creative brief formula, creative testing hierarchy, thumbnail/carousel direction, brand visual consistency check
- [x] n8n Automation Agent - 4 strategies: workflow design principles, CRM sync patterns, error handling/fallback logic, approval flow design
- [x] CRM Follow-Up Agent - 5 strategies: speed-to-lead system, SMS sequence architecture, pipeline stage framework, lead qualification logic, GoHighLevel operator notes
- [x] Analytics Agent - 4 strategies: weekly report framework, funnel drop-off diagnosis, ad performance review, content performance review
- [x] GEO Agent - 4 strategies: AI visibility snapshot, entity authority framework, citation gap analysis, AI-optimized content plan
- [x] QA Agent - 4 strategies: claims review framework, brand voice compliance check, pre-launch checklists by asset type, handoff readiness check

---

## Phase 3 - Detailed Skill Buildout

Status: Not started.

Goal: Replace all placeholder skill files with complete, step-by-step skill content.

Tasks:
- Write the full process for each skill file
- Add examples and frameworks to each skill
- Cross-reference skills with the relevant knowledge base docs
- Map skills to Claude Code skills in uploads/extracted/ where applicable

Priority order:
1. Skills used in the highest-frequency workflows (copywriting, research, paid ads)
2. Skills that have matching extracted content in uploads/extracted/
3. Remaining skills

---

## Phase 4 - Knowledge Base Ingestion

Status: Not started.

Goal: Fill the knowledge base with real client and agency content.

Tasks:
- Complete the agency-owner.md profile
- Create at least one client doc in knowledge-base/clients/
- Add at least one offer doc in knowledge-base/offers/
- Import relevant frameworks into knowledge-base/frameworks/
- Add example copy and swipe files
- Add at least one case study
- Map all imported files to their skills

---

## Phase 5 - MCP Setup And Tool Connections

Status: COMPLETE (infrastructure ready, credentials not yet added).

Goal: Connect live tools so agents can act, not just plan.

What was built:
- [x] `.gitignore` created - protects .env and .claude/mcp.json from being committed
- [x] `.env.example` created - all variable names with instructions for each tool
- [x] `mcp/SETUP.md` created - full step-by-step connection guide
- [x] `mcp-configs/google-analytics.json` created - was missing from prior phase
- [x] All 5 priority tool planning docs updated with detailed setup and agent usage instructions: meta-ads.md, gohighlevel.md, google-analytics.md, airtable.md, n8n.md, apify.md
- [x] `mcp/mcp-registry.md` updated with full tool table, priority order, and security notes
- [x] Two exposed tokens (Airtable, Apify) replaced with placeholders and flagged for rotation

To activate tools when ready:
1. Copy `.env.example` to `.env` and fill in real credentials
2. Follow `mcp/SETUP.md` in priority order
3. Test each connection before moving to the next
4. Update mcp-registry.md status as each tool goes live

---

## Phase 6 - Output Templates

Status: COMPLETE.

Goal: Create reusable templates for every major deliverable type.

What was built:
- [x] `templates/intake/client-intake.md` - New client intake form
- [x] `templates/intake/project-intake.md` - New project intake form
- [x] `templates/briefs/campaign-brief.md` - Campaign brief template
- [x] `templates/briefs/copy-brief.md` - Copy brief template
- [x] `templates/briefs/creative-brief.md` - Creative brief template
- [x] `templates/reports/weekly-report.md` - Weekly performance report template
- [x] `templates/reports/monthly-report.md` - Monthly KPI report template
- [x] `templates/checklists/pre-launch-checklist.md` - Pre-launch QA checklist
- [x] `templates/checklists/handoff-checklist.md` - Handoff readiness checklist
- [x] `templates/prompts/new-client-kickoff.md` - Claude Code prompt for new client onboarding
- [x] `templates/prompts/campaign-launch.md` - Claude Code prompt for campaign launch
- [x] `templates/prompts/weekly-review.md` - Claude Code prompt for weekly review
- [x] `templates/prompts/research-request.md` - Claude Code prompt for market research
- [x] `templates/README.md` - Updated with full file index

---

## Phase 7 - Testing Workflows

Status: COMPLETE (partial - 4 of 9 tests run; remaining 5 require live MCP tools).

Goal: Run real tasks through the full team and validate outputs.

What was built:
- [x] `docs/testing/mock-client.md` - SkyLine Roofing Co. fictional client with full campaign details
- [x] `docs/testing/test-runbook.md` - 9 test scripts with prompts and expected behaviors
- [x] `docs/testing/test-results.md` - Results from the 4 tests run
- [x] `docs/testing/known-gaps.md` - Agent folder naming inconsistency documented

Tests run and results:
- [x] Marketing Director routing - PASS. Produced correct 6-phase plan, asked the right clarifying question, flagged timeline risk.
- [x] CFO Agent budget math - PASS. Identified budget as fragile, recommended $5K/month, calculated max CPA correctly. Output saved to outputs/cfo/.
- [x] Copywriter ad copy - PASS. Three clean variations, no voice violations, proactively flagged QA items.
- [x] QA Agent brand voice + claims - PASS. Caught all 6 banned words, both em dashes, FAIL on fabricated ROI guarantee, FAIL on manufactured urgency, produced prioritized fix checklist.

Tests pending (require MCP connections):
- [ ] Market Research Agent + Apify (competitor ad scraping)
- [ ] CRM Agent + GoHighLevel (pipeline setup)
- [ ] n8n Agent + n8n (speed-to-lead workflow build)
- [ ] QA Agent full pre-launch check (requires live landing page)
- [ ] Analytics Agent weekly report (requires live Meta and GHL data)

Known gap: Agent folder naming inconsistency (4 folders without -agent suffix vs. 11 with). Low severity. Documented in known-gaps.md.

---

## Phase 8 - Internal Agency Use

Status: Not started.

Goal: Full operational use of the team for real client and internal work.

Tasks:
- Onboard first real client using the system
- Run first real campaign through the team
- Identify what needs improvement from real use
- Build out additional skills based on real-world needs

---

## Notes

Do not start Phase 2 or later until Phase 1 is verified complete.

Use this roadmap to track progress and decide what to build next.
