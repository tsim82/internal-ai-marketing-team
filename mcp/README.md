# MCP Tool Planning

This folder contains planning docs, config templates, and credential guides for every tool the internal agency team may connect via MCP.

No tools are connected yet. This is Phase 5 work.

---

## What Is Here

- `tools/` - One planning file per tool. Describes purpose, agents, use cases, credentials needed.
- `configs/` - Example config files and setup guides.
- `.env.example` - All environment variable names (no real values).
- `mcp-registry.md` - Master list of all planned tools and their connection status.

---

## How To Connect A Tool

1. Read the tool's planning file in `mcp/tools/`.
2. Copy `mcp/configs/mcp.json.example` and fill in your values.
3. Add real credentials to `.env` (never commit `.env`).
4. Update `mcp/mcp-registry.md` to mark the tool as connected.
5. Test the tool in Claude Code before using it in live work.

---

## Security Rules

- Never put real API keys in any file in this folder.
- Never commit `.env` files.
- `.env.example` contains only placeholder variable names.
- Scope every token to the minimum permissions needed.

---

## Status

Planning phase. No tools are connected. See `docs/build-roadmap.md` for Phase 5 connection plan.
