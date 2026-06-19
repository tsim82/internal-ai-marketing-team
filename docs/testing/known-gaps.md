# Known Gaps

Issues found during Phase 7 testing. Tracked here until resolved. Each item has a severity, description, and fix.

---

## Open Gaps

### GAP-001: Agent Folder Naming Inconsistency

**Severity:** Low (does not break current functionality, but could cause file-not-found errors if agents reference each other by path)

**Found in:** Marketing Director test (2026-06-19)

**Description:** Agent folders in `agents/` use two different naming conventions:

| Convention | Folders Using It |
|-----------|----------------|
| Name only (no suffix) | `market-research`, `cfo`, `copywriter`, `marketing-director` |
| Name + `-agent` suffix | `paid-ads-agent`, `creative-design-agent`, `crm-follow-up-agent`, `n8n-automation-agent`, `analytics-optimization-agent`, `qa-compliance-agent`, `funnel-agent`, `geo-agent`, `social-media-agent`, `video-agent`, `offer-agent` |

When the Marketing Director routes tasks and tells agents what to read, it may reference an incorrect path. For example, it said `agents/paid-ads/agent.md` but the actual path is `agents/paid-ads-agent/agent.md`.

**Impact:** If an agent tries to read a file using the wrong path, it will get a file-not-found error and either skip the context or produce worse output.

**Fix options:**
1. Rename the four no-suffix folders to add `-agent` for consistency (preferred - matches the majority)
2. Or remove `-agent` from the majority (more work)
3. Or document the exact paths in each agent's definition file so they know what to read

**Recommended fix:** Rename the four inconsistent folders by adding `-agent` suffix:
- `market-research` → `market-research-agent`
- `cfo` → `cfo-agent`
- `copywriter` → `copywriter-agent`
- `marketing-director` → `marketing-director-agent`

Then update any references in agent.md files, id.md files, and the docs that mention these paths.

**Status:** Open

---

## Resolved Gaps

None yet.

---

## Monitoring

Update this file as new gaps are found during testing or real client use. Each entry should include when it was found, what caused it, and what was done to fix it.
