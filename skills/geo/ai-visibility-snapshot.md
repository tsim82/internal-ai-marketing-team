# AI Visibility Snapshot

## Purpose

Document how a brand appears (or does not appear) in responses from major AI tools when potential buyers search for relevant solutions, competitors, or niche topics. The snapshot captures verbatim AI responses to four query types and identifies where the brand is visible, where it is missing, and where competitors have an advantage.

## Used By

- GEO Agent (primary)
- Marketing Director (receives the findings)

## Trigger

Use at the start of any GEO engagement, quarterly for active clients, or when a client reports that they are losing leads to AI-generated search results.

## Inputs Needed

- Brand name - required
- Brand website URL - required
- Main niche and service category - required
- 3-5 main competitors - required
- 5-10 target queries (the things buyers would search to find this solution) - required

## Process

**Step 1: Build the query list**

Prepare four types of queries. These should represent what a buyer in this niche actually asks AI tools.

| Query type | Example | What it reveals |
|-----------|---------|----------------|
| Direct brand | "What is [Brand Name]?" | Is the brand recognized as an entity? |
| Problem/solution | "How do I [problem this brand solves]?" | Does the brand appear in solution answers? |
| Competitor comparison | "What are alternatives to [Competitor]?" or "[Brand] vs [Competitor]?" | Where does the brand sit vs competitors? |
| Niche authority | "Who are the top [experts / agencies / tools] for [niche]?" | Is the brand included in authority lists? |

Build 2-3 queries per type. Use the language a real buyer would use.

**Step 2: Run queries across multiple AI tools**

Test across at least three tools:
- ChatGPT (GPT-4)
- Perplexity AI
- Claude
- Google AI Overviews (search in Google, review the AI-generated summary at the top)

For each query, document the verbatim response. Do not paraphrase. Exact wording matters for later comparison.

**Step 3: Score the brand's presence**

After running all queries, score each query result:

| Score | Meaning |
|-------|---------|
| 3 | Brand is named prominently with positive context |
| 2 | Brand is mentioned but briefly or without specific detail |
| 1 | Brand is not mentioned but competitors are |
| 0 | Neither brand nor relevant category is mentioned |

**Step 4: Compare against competitors**

For each query where a competitor appears and the brand does not, note:
- Which competitor is named
- What context they are given (what signals may be causing them to appear)

**Step 5: Write the findings**

Summarize what the brand currently looks like in AI search and what the gaps are.

## Output Format

```
AI VISIBILITY SNAPSHOT - [Client/Brand] - [Date]

BRAND: [Name]
WEBSITE: [URL]
NICHE: [Description]
COMPETITORS TESTED: [List]
AI TOOLS TESTED: [ChatGPT / Perplexity / Claude / Google AI Overviews]

---

QUERY RESULTS:

DIRECT BRAND QUERIES:

Query 1: "What is [Brand Name]?"
  ChatGPT: [Verbatim response or "Brand not found / generic response"]
  Perplexity: [Verbatim response]
  Claude: [Verbatim response]
  Google AI Overview: [Verbatim response if one appeared]
  Score: [0-3]
  Notes: [What this means]

Query 2: "[Brand Name] reviews" or similar
  [Same format]

PROBLEM/SOLUTION QUERIES:

Query 3: "How do I [problem]?"
  [Same format]

Query 4: "Best way to [solve problem] for [audience]"
  [Same format]

COMPETITOR COMPARISON QUERIES:

Query 5: "Alternatives to [Competitor 1]"
  [Same format]

Query 6: "[Brand] vs [Competitor]"
  [Same format]

NICHE AUTHORITY QUERIES:

Query 7: "Top [category] agencies / tools / experts"
  [Same format]

Query 8: "Who helps [audience] with [problem]?"
  [Same format]

---

VISIBILITY SCORECARD:

| Query | ChatGPT | Perplexity | Claude | Google AI | Avg |
|-------|---------|-----------|-------|-----------|-----|
| [Q1] | [0-3] | [0-3] | [0-3] | [0-3] | [...] |
[One row per query]

Overall brand visibility score: [X]/3

---

COMPETITOR ADVANTAGE SUMMARY:

| Competitor | Queries they appear in | Why they likely appear |
|-----------|----------------------|----------------------|
| [Name] | [Q3, Q7] | [Known entity, cited in roundups, Wikipedia entry] |

---

KEY FINDINGS:
1. [Finding 1: what is working]
2. [Finding 2: main gap]
3. [Finding 3: biggest competitor advantage to close]

PRIORITY ACTIONS (output to entity-audit.md and citation-gap-analysis.md):
- [Specific action with urgency level]
```

## Quality Check

- [ ] At least 8 queries run across at least 3 AI tools
- [ ] Verbatim responses documented (not paraphrased)
- [ ] All four query types represented
- [ ] Competitor comparison completed
- [ ] Score assigned to every query/tool combination
- [ ] Findings lead directly to priorities for the entity audit and citation gap analysis

## Status

Phase 3 complete.
