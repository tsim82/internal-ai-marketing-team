# Agent Roster

All 15 agents in the internal AI marketing team. Check this before adding a new agent.

---

| # | Agent Name | Slug | Primary Role | Main Outputs | Skill Folders | MCP Tools | Status |
|---|-----------|------|-------------|-------------|--------------|-----------|--------|
| 1 | Marketing Director | `marketing-director` | Orchestration, routing, quality review | Project plans, routing briefs, final approvals | All (via delegation) | mcp-registry.md | Phase 1 |
| 2 | CFO | `cfo` | Financial decision support | Pricing reviews, budget plans, KPI reports | `skills/cfo/` | google-sheets | Phase 1 |
| 3 | Market Research | `market-research` | Audience, competitor, and hook research | Research briefs, audience profiles, hook lists | `skills/research/` | apify, google-search-console | Phase 1 |
| 4 | Offer Agent | `offer-agent` | Offer creation and positioning | Offer one-pagers, stack docs, guarantee language | `skills/offers/` | None | Phase 1 |
| 5 | Copywriter | `copywriter` | All written conversion assets | Landing pages, VSLs, emails, ad copy | `skills/copywriting/` | None | Phase 1 |
| 6 | Funnel Agent | `funnel-agent` | Customer journey and funnel structure | Funnel maps, wireframes, nurture flows | `skills/funnels/` | None | Phase 1 |
| 7 | GEO Agent | `geo-agent` | AI visibility and entity authority | Visibility snapshots, entity audits, GEO content plans | `skills/geo/` | google-search-console | Phase 1 |
| 8 | Social Media Agent | `social-media-agent` | Organic content planning | Content calendars, platform posts, repurposing plans | `skills/social-media/` | instagram, facebook, linkedin | Phase 1 |
| 9 | Video Agent | `video-agent` | Video strategy and production planning | VSL plans, Remotion prompts, HeyGen scripts, YouTube scripts | `skills/video/` | remotion, heygen, youtube | Phase 1 |
| 10 | Creative Design Agent | `creative-design-agent` | Static creative direction | Ad briefs, image prompts, thumbnail briefs, carousel briefs | `skills/creative-design/` | canva | Phase 1 |
| 11 | Paid Ads Agent | `paid-ads-agent` | Paid traffic strategy and optimization | Campaign structures, testing plans, optimization reviews | `skills/paid-ads/` | meta-ads, google-ads | Phase 1 |
| 12 | n8n Automation Agent | `n8n-automation-agent` | Workflow automation design | Workflow maps, node plans, webhook docs | `skills/n8n/` | n8n, airtable, supabase, gohighlevel | Phase 1 |
| 13 | CRM / Sales Follow-Up | `crm-follow-up-agent` | Lead follow-up and pipeline | Pipeline maps, SMS sequences, email follow-up | `skills/crm-follow-up/` | gohighlevel | Phase 1 |
| 14 | Analytics / Optimization | `analytics-optimization-agent` | Performance reporting and next actions | Weekly reports, funnel analyses, ad reviews | `skills/analytics-optimization/` | google-analytics, google-sheets, meta-ads | Phase 1 |
| 15 | QA / Compliance | `qa-compliance-agent` | Quality control and launch readiness | QA reports, pre-launch checklists, handoff approvals | `skills/qa-compliance/` | None | Phase 1 |

---

## Agent File Locations

Each agent has three files:

```
agents/[slug]/
  id.md         Identity and ownership
  agent.md      Operating instructions
  README.md     Quick reference

.claude/agents/[slug].md   Claude Code subagent definition
```

---

## How To Add A New Agent

Before adding a new agent:
1. Confirm there is no existing agent that already covers this domain.
2. Check that the scope is specific enough to warrant its own agent.
3. Get approval from the Marketing Director Agent or the human owner.
4. Create: `agents/[new-slug]/id.md`, `agent.md`, `README.md`.
5. Create: `.claude/agents/[new-slug].md`.
6. Add to this roster.
7. Add skills to `skills/` and reference in `skills/index.md`.

---

## Status

All 15 agents built in Phase 1. Full instruction buildout is Phase 2.
