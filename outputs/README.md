# Outputs

All agent outputs are saved here, organized by type.

---

## Folder Mapping

| Output Type | Folder | Primary Agent |
|-------------|--------|--------------|
| Research briefs, audience profiles, competitor research | `outputs/research/` | Market Research Agent |
| Offer docs, pricing docs, offer stacks | `outputs/offers/` | Offer Agent |
| Copy assets (landing pages, emails, ads, VSLs) | `outputs/copy/` | Copywriter |
| Funnel maps, wireframes, nurture flows | `outputs/funnels/` | Funnel Agent |
| GEO reports, visibility snapshots, citation audits | `outputs/geo/` | GEO Agent |
| Social content calendars and posts | `outputs/social/` | Social Media Agent |
| Video plans, scripts, Remotion prompts, HeyGen scripts | `outputs/video/` | Video Agent |
| Creative briefs, image prompts, thumbnail briefs | `outputs/creative/` | Creative Design Agent |
| Ad strategies, campaign structures, testing plans | `outputs/ads/` | Paid Ads Agent |
| Automation workflow maps and node plans | `outputs/automations/` | n8n Automation Agent |
| CRM pipelines, follow-up sequences, qualification docs | `outputs/crm/` | CRM Follow-Up Agent |
| Reports, performance reviews, next-action plans | `outputs/analytics/` | Analytics Agent |
| QA review reports, launch checklists, handoff approvals | `outputs/qa/` | QA Agent |
| CFO reports, pricing reviews, budget plans | `outputs/cfo/` | CFO Agent |
| Final approved deliverables ready for client | `outputs/final-handoffs/` | Marketing Director |

---

## File Naming Convention

Use this format for all output files:

`[date]-[client-or-project]-[type]-[version].md`

Examples:
- `2026-06-18-acme-landing-page-copy-v1.md`
- `2026-06-18-acme-meta-campaign-structure.md`
- `2026-06-18-acme-qa-review.md`

---

## How Outputs Move Through The Team

1. Agent produces output and saves to the matching subfolder.
2. QA Agent reviews before anything goes to client.
3. Marketing Director approves final work.
4. Approved work is copied to `outputs/final-handoffs/`.

---

## Status

Folder structure is ready. No output files yet.
