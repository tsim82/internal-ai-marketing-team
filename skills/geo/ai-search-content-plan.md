# AI Search Content Plan

## Purpose

Build a content plan optimized for AI tools to discover, understand, and cite the brand. AI-optimized content is different from traditional SEO content. It answers questions directly, uses structured formats, and covers topics in ways that make the content easy for AI to extract and include in responses. The output is a prioritized content plan with specific topics, formats, and GEO goals per piece.

## Used By

- GEO Agent (builds the plan)
- Copywriter (writes the content from this plan)
- Marketing Director (reviews before content production begins)

## Trigger

Use after the entity audit and citation gap analysis, or when the team is building a content strategy and wants to include AI visibility alongside traditional SEO.

## Inputs Needed

- AI Visibility Snapshot (which queries is the brand missing from?) - required
- Entity audit findings (what topics does the brand need authority on?) - required
- Citation gap analysis (what publication types could the brand be featured in?) - helpful
- Competitor content audit (what topics are competitors owning in AI responses?) - helpful
- Keyword or topic list from traditional SEO (if available) - helpful

## Process

**Step 1: Identify the query types the brand needs to appear in**

Pull from the AI Visibility Snapshot. Which query types had the lowest scores?

Focus content on:
- **Problem/solution queries**: "How do I [problem]?" "What's the best way to [outcome]?"
- **Niche authority queries**: "Top [experts / agencies / solutions] for [niche]"
- **Comparison queries**: "[Brand] vs [Competitor]" or "Alternatives to [Competitor]"
- **Category definition queries**: "What is [category the brand belongs to]?"

**Step 2: Match content formats to AI tool preferences**

AI tools tend to pull from content with these characteristics:

| Content format | Why AI prefers it | Best for |
|--------------|-----------------|---------|
| Direct Q&A pages | Exact match to how users prompt AI | Problem/solution queries |
| Numbered listicles with specific detail | AI can extract items directly | Authority queries |
| Comparison articles | Direct match to comparison prompts | Competitor queries |
| "What is [X]?" definitions with examples | Entity recognition | Category authority |
| Case study with specific outcomes | Cited as evidence | Proof queries |
| FAQ with direct, specific answers | Mirrors AI response format | Objection-type queries |

**Step 3: Plan content with schema markup in mind**

Each content piece should have schema planned before writing:
- FAQ schema: for any FAQ or Q&A content
- HowTo schema: for process or tutorial content
- Article schema: for all blog content
- Review schema: for case studies or testimonials
- SpeakableSchema: for content intended for voice/AI assistants

**Step 4: Build the content plan**

Prioritize by gap. Topics where the brand has zero presence in AI responses should be addressed first.

For each content piece:
- Title / Topic
- Query it targets
- Format
- GEO goal (why this improves AI visibility)
- Schema type
- Target publication (on-site blog or external pitch)
- Priority level

**Step 5: Plan the distribution**

For on-site content: publish and ensure schema is added immediately.
For external content: match to citation gap analysis Tier 1-2 targets.

Content published on third-party authoritative sites provides both a citation and content that AI tools may source from.

## Output Format

```
AI SEARCH CONTENT PLAN - [Client/Brand] - [Date]

BASED ON:
  AI Visibility Snapshot: [Date]
  Entity Audit: [Date]
  Citation Gap Analysis: [Date]

TARGET QUERY TYPES WITH GAPS: [List from AI Visibility Snapshot]

---

CONTENT PLAN:

PRIORITY 1 CONTENT (highest GEO impact):

Piece 1:
  Title: "[Working title]"
  Target query: "[Exact query type this matches]"
  Format: [Q&A / Listicle / Comparison / Definition / Case study / FAQ]
  GEO goal: [Why this improves AI visibility - be specific]
  Schema type: [FAQ / HowTo / Article / etc.]
  Publication: [On-site blog / [Publication name from citation gap]]
  Word count target: [X words - AI-friendly content tends to be 800-2,000 words]
  Key questions to answer in this piece: [2-4 specific questions]
  Timeline: [Target publish date]

Piece 2:
  [Same format]

Piece 3:
  [Same format]

PRIORITY 2 CONTENT:

Piece 4:
  [Same format]

[Continue for all planned pieces]

---

SCHEMA MARKUP PLAN:

| Content piece | Schema type | Implementation |
|--------------|------------|---------------|
| [Piece 1] | [FAQ] | Add to existing FAQ page / new page |
| [Piece 2] | [HowTo] | Add to [URL] |

---

DISTRIBUTION:
  On-site: [N] pieces
  External/third-party: [N] pieces → aligned with citation gap Tier [1/2] targets

TOTAL CONTENT PIECES: [N]
ESTIMATED TIMELINE TO COMPLETE: [X weeks at [X] pieces per week]

---

SUCCESS METRICS:
How we'll know this is working:
  - AI Visibility Snapshot score improves from [X] to [Y] by [Date]
  - Brand appears in [specific query type] across [AI tools]
  - [N] external citations created
```

## Quality Check

- [ ] Every piece targets a specific query type with a documented GEO goal
- [ ] Schema type is planned for every piece before writing
- [ ] Priority order reflects the biggest gaps from the AI Visibility Snapshot
- [ ] External pieces are matched to specific citation gap targets
- [ ] Success metrics are defined before content is produced

## Status

Phase 3 complete.
