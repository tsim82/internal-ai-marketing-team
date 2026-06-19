# Internal AI Marketing Team

A complete internal agency team built inside Claude Code. 15 specialized agents, shared skills, a knowledge base, MCP tool planning, and organized outputs.

This is not a SaaS app or a chatbot. It is an internal system for running marketing execution at an agency level.

---

## The 15 Agents

| # | Agent | Slug | What It Does |
|---|-------|------|-------------|
| 1 | Marketing Director | `marketing-director` | Routes tasks, plans projects, reviews final work |
| 2 | CFO | `cfo` | Pricing, offer math, budgets, profitability |
| 3 | Market Research | `market-research` | Audience, competitors, hooks, objections |
| 4 | Offer Agent | `offer-agent` | Offer creation, positioning, stack, guarantee |
| 5 | Copywriter | `copywriter` | Landing pages, VSLs, emails, ads, scripts |
| 6 | Funnel Agent | `funnel-agent` | Customer journey, opt-ins, checkout, nurture |
| 7 | GEO Agent | `geo-agent` | AI visibility, entity audit, citation gaps |
| 8 | Social Media Agent | `social-media-agent` | Calendars, posts, captions, repurposing |
| 9 | Video Agent | `video-agent` | VSL plans, Remotion prompts, HeyGen scripts |
| 10 | Creative Design Agent | `creative-design-agent` | Ad briefs, image prompts, thumbnails |
| 11 | Paid Ads Agent | `paid-ads-agent` | Meta, Google, campaign structure, testing |
| 12 | n8n Automation Agent | `n8n-automation-agent` | Workflows, webhooks, node plans, CRM sync |
| 13 | CRM / Sales Follow-Up | `crm-follow-up-agent` | Pipeline, speed-to-lead, SMS, email follow-up |
| 14 | Analytics / Optimization | `analytics-optimization-agent` | Reports, funnel analysis, next actions |
| 15 | QA / Compliance | `qa-compliance-agent` | Claims review, brand check, launch readiness |

---

## How The Shared Structure Works

Skills, knowledge base docs, and MCP connectors are shared across agents. They live at the repo level, not inside each agent folder. This prevents duplication and makes updates easy.

```
skills/          Skills grouped by category. Agents call the skills they need.
knowledge-base/  Context docs, client info, frameworks, examples, swipe files.
mcp/             Tool planning, configs, environment variable templates.
outputs/         Organized by output type. Agents save work here.
```

---

## How Skills Work

Each skill file in `skills/` describes a specific task an agent can perform. Skills include a purpose, trigger, required inputs, process outline, and output format.

Before creating a new skill, check `skills/index.md` to see if one already exists.

To find which skill handles a task, check `docs/skill-map.md`.

---

## How To Add Knowledge Base Docs

Put raw source docs in `knowledge-base/incoming-docs/` first.

Then move or copy them into the right category folder:

- `brand/` for voice, visual, and brand rules
- `offers/` for offer docs and pricing
- `clients/` for client-specific context
- `frameworks/` for strategy frameworks and models
- `examples/` for example copy, ads, and content
- `swipe-files/` for reference copy and creative
- `case-studies/` for results and proof
- `sop/` for internal process docs

See `knowledge-base/index.md` for guidance on each category.

---

## How MCP Tools Will Be Connected

MCP connections are planned, not live yet. Each tool has a planning file in `mcp/tools/`.

When you are ready to connect a tool:
1. Read `mcp/tools/[tool-name].md` for credentials and setup notes.
2. Copy `mcp/configs/mcp.json.example` and fill in real values.
3. Add the credentials to `.env` (not committed to the repo).
4. Update `mcp/mcp-registry.md` to reflect the status change.

---

## How To Save Outputs

Save outputs to the right folder based on type. See `outputs/README.md` for the full mapping.

Quick reference:
- Research briefs: `outputs/research/`
- Copy assets: `outputs/copy/`
- Ad plans: `outputs/ads/`
- Reports: `outputs/analytics/`
- Final packaged work: `outputs/final-handoffs/`

---

## How To Use The Marketing Director Agent

Open Claude Code and reference the Marketing Director Agent for any broad request:

```
Use the marketing director agent. We need a full launch plan for [offer].
```

The Marketing Director Agent will read the project context, break the work into tasks, route those tasks to the right agents, and check the outputs before they are finalized.

---

## What Is Built Now

- Full folder structure
- All 15 agent folders with `id.md`, `agent.md`, `README.md`
- All 15 `.claude/agents/` subagent definition files
- All placeholder skill files across 13 categories
- Knowledge base folder structure with index and brand voice rules
- MCP tool planning files for 21 tools
- Output folder structure
- Documentation suite in `docs/`
- Imported files audit reflecting the extracted zip contents

---

## What Still Needs To Be Built

- Full agent instructions (Phase 2)
- Detailed skill buildout (Phase 3)
- Knowledge base ingestion from uploads and client docs (Phase 4)
- MCP connections and live tool setup (Phase 5)
- Output templates (Phase 6)
- Testing workflows (Phase 7)

See `docs/build-roadmap.md` for the phased plan.
