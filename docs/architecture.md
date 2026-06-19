# Architecture

How the internal AI marketing team is structured and how the pieces work together.

---

## Overview

This is a 15-agent internal agency team running in Claude Code. Each agent is a specialized unit with a defined domain. They share skills, a knowledge base, and MCP tool connections. Outputs are organized by type.

The Marketing Director Agent coordinates everything. Specialized agents execute domain-specific work. QA Agent reviews before anything goes out.

---

## Layer Structure

```
User or operator
    |
Marketing Director Agent
    |
    +--- Market Research Agent
    +--- CFO Agent
    +--- Offer Agent
    +--- Copywriter Agent
    +--- Funnel Agent
    +--- GEO Agent
    +--- Social Media Agent
    +--- Video Agent
    +--- Creative Design Agent
    +--- Paid Ads Agent
    +--- n8n Automation Agent
    +--- CRM Follow-Up Agent
    +--- Analytics Agent
    +--- QA Agent
```

---

## Shared Resources

All agents pull from shared resources rather than maintaining duplicates.

| Resource | Location | What It Contains |
|----------|----------|-----------------|
| Skills | `skills/` | Task playbooks grouped by category |
| Knowledge Base | `knowledge-base/` | Brand rules, offers, client context, frameworks |
| MCP Tools | `mcp/` | Tool planning and connection configs |
| Outputs | `outputs/` | All agent outputs organized by type |

---

## Agent Definition Files

Each agent has three files in its folder:

| File | Purpose |
|------|---------|
| `id.md` | Identity: role, ownership, quality standards, handoff rules |
| `agent.md` | Operations: workflow, questions, assumptions, output rules |
| `README.md` | Quick reference: what it does, when to use it, related files |

---

## Claude Code Subagents

Each agent is also defined as a Claude Code subagent in `.claude/agents/`. These files use YAML frontmatter and tell the subagent which files to read before starting work.

The subagent files are lightweight. The full context lives in `agents/[slug]/`.

---

## Data Flow Example

A typical campaign launch flows through the team like this:

1. Marketing Director reviews the request and creates a project plan.
2. Market Research Agent produces audience and competitor research.
3. Offer Agent builds or refines the offer.
4. CFO Agent checks the pricing and budget.
5. Copywriter writes the landing page and ad copy.
6. Funnel Agent maps the customer journey.
7. Creative Design Agent produces creative briefs.
8. Paid Ads Agent builds the campaign structure.
9. QA Agent reviews all assets before launch.
10. Marketing Director approves final handoff.

---

## What Is Not Here

- Live tool connections (Phase 5)
- Detailed skill content (Phase 3)
- Client-specific content (added as clients onboard)
- Template files (Phase 6)

---

## Status

Phase 1 complete. Shell structure, all 15 agents, shared resources, and documentation are in place.
