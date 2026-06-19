# CLAUDE.md - Internal AI Marketing Team

This is an internal agency AI marketing team repo built for Claude Code.

---

## What This Repo Is

A 15-agent internal marketing team that handles research, planning, copywriting, funnels, paid ads, automation, analytics, video, social media, creative direction, and more.

Use the Marketing Director Agent for any task that involves multiple agents or is unclear which agent should handle it.

Use specialized agents when the task is clearly in one domain.

---

## How To Behave In This Repo

- Read the relevant agent files before acting.
- Check `skills/index.md` before creating new skill files.
- Use `knowledge-base/index.md` to find existing context.
- Check `docs/agent-roster.md` before adding a new agent.
- Check `docs/skill-map.md` before adding a new skill.
- Save outputs to the right folder as listed in `outputs/README.md`.
- Ask only necessary questions. Make grounded assumptions when you have enough context.
- Keep outputs client-ready and implementation-ready.

---

## Writing Rules For Every Output

- Never use em dashes.
- Use contractions.
- Write in plain English.
- Sound conversational and natural.
- Do not sound corporate.
- Do not use AI hype language.
- Do not use rhythmic three-part phrasing.
- Do not use repetitive sentence patterns.
- Do not over-explain unless the task requires it.
- Write like you are explaining the work over coffee.
- Focus on outcomes, not abstract theory.

**Avoid these words unless specifically asked:**
delve, dive, revolutionize, cutting edge, supercharge, crucial, harness, catapult, paramount, unlock, unleash, skyrocket, foster, elevate, game changer, embark, transform, resonate, robust, seamless, trailblazer, unveil, arsenal, fast-paced

---

## Agent Routing

Use the **Marketing Director Agent** when:
- You need to plan a project or campaign
- The task spans multiple agents
- You are not sure which agent handles it
- You need a final quality check before anything goes out

Use specialized agents when the domain is clear. See `docs/agent-roster.md` for the full list.

---

## Safety Rules

- Do not modify files in `uploads/extracted/` unless asked.
- Do not create fake credentials or placeholder API keys with real-looking values.
- Do not connect live tools unless asked to do so.
- Do not add agents or skills without checking the roster and skill map first.
- Do not use em dashes anywhere in outputs.

---

## File Reference

| Purpose | File |
|---------|------|
| Agent roster | `docs/agent-roster.md` |
| Skill map | `docs/skill-map.md` |
| Knowledge base index | `knowledge-base/index.md` |
| Output folder guide | `outputs/README.md` |
| MCP tool registry | `mcp/mcp-registry.md` |
| Build roadmap | `docs/build-roadmap.md` |
| Operating rules | `docs/operating-rules.md` |
| Architecture overview | `docs/architecture.md` |
| Agency owner profile | `agency-owner.md` |

---

## Current Build Status

Phase 1 complete: team shell, placeholders, repo structure, docs.

Phases 2 through 8 are planned. See `docs/build-roadmap.md`.
