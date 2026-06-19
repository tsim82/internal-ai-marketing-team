# Entity Audit

## Purpose

Audit the brand's entity signals - the structured information that AI tools use to understand who the brand is, what it does, and whether it is credible. When AI tools do not mention a brand, it is often because the brand is not recognized as a clear entity. This audit identifies every entity signal, scores its current state, and prioritizes what to fix first.

## Used By

- GEO Agent (primary)
- Marketing Director (receives the findings and action plan)

## Trigger

Use after the AI Visibility Snapshot if the brand has low visibility scores, or as a standalone audit for any brand investing in GEO for the first time.

## Inputs Needed

- Brand name and all name variations used publicly - required
- Brand website URL - required
- Founder name(s) and professional presence - required
- Business category and location (if local) - required
- AI Visibility Snapshot results - helpful

## Process

**Step 1: Audit each entity signal type**

Work through each signal type and document what currently exists:

**Signal 1: Wikipedia / Wikidata**
- Does a Wikipedia page exist for the brand? (Yes / No / Redirect only)
- Does a Wikipedia page exist for the founder? (Yes / No)
- Does a Wikidata entry exist? (Yes / No)
- If no: note whether the brand meets Wikipedia's notability requirements
- If yes: does the description match the brand's current positioning?

**Signal 2: Consistent entity description**
AI tools use the description that appears consistently across multiple sources. Find what different sources say about the brand:
- Google Business Profile description
- LinkedIn company description
- Crunchbase description (if present)
- Press releases or About page
- How Wikipedia or AI tools describe the brand now (from snapshot)

Do they all say the same thing? Inconsistency confuses AI models.

**Signal 3: Schema markup**
- Does the website have Organization schema? (Check: Google's Rich Results Test)
- Does it include: name, url, description, foundingDate, sameAs links?
- Does it link to social profiles and authoritative third-party pages?

**Signal 4: Authoritative third-party citations**
Citations from authoritative sources tell AI tools the brand is real and recognized.
- Is the brand listed in relevant industry directories?
- Has the brand been mentioned or featured in industry publications?
- Are there press mentions with links?
- Are there podcast appearances, conference speaking, or guest articles?

**Signal 5: Founder entity**
The founder's personal entity strengthens the brand entity.
- LinkedIn presence: is it complete and active?
- Are there articles, interviews, or quotes that mention the founder by name with their company?
- Is the founder mentioned in third-party content in a professional context?

**Signal 6: NAP consistency (for local businesses)**
NAP = Name, Address, Phone. Must be consistent everywhere.
- Google Business Profile: [Check]
- Yelp: [Check]
- Local directories: [Check]
- Website contact page: [Check]
Inconsistencies in NAP can reduce local authority signals.

**Step 2: Score each signal**

| Signal | Status | Score |
|--------|--------|-------|
| Wikipedia/Wikidata | Exists + accurate / Exists but outdated / Missing | High / Medium / Low |
| Consistent entity description | All sources match / Partial / Inconsistent | [...] |
| Schema markup | Complete / Partial / Missing | [...] |
| Third-party citations | Strong (5+) / Moderate (2-4) / Weak (0-1) | [...] |
| Founder entity | Strong / Moderate / Weak | [...] |
| NAP consistency | Consistent / Minor discrepancies / Major issues | [...] |

**Step 3: Prioritize fixes**

Priority fix order (from highest to lowest impact on AI visibility):
1. Schema markup (quick to fix, high impact)
2. Consistent entity description across all public profiles
3. Third-party authoritative citations (takes time but high value)
4. Founder entity strength
5. Wikipedia/Wikidata (highest effort, not always achievable)
6. NAP consistency (critical for local, less relevant for national brands)

## Output Format

```
ENTITY AUDIT - [Client/Brand] - [Date]

BRAND: [Name]
WEBSITE: [URL]
FOUNDER: [Name]

---

SIGNAL AUDIT:

WIKIPEDIA / WIKIDATA:
  Brand Wikipedia page: [Exists - accurate / Exists - outdated / Missing]
  Founder Wikipedia: [Exists / Missing]
  Wikidata entry: [Exists / Missing]
  Notability status: [Meets criteria / Does not yet meet criteria]
  Score: [High / Medium / Low]

CONSISTENT ENTITY DESCRIPTION:
  Current description on primary sources:
    Website About page: "[First line of current description]"
    Google Business Profile: "[Description]"
    LinkedIn: "[Description]"
    Crunchbase: "[Description or N/A]"
  Consistency: [All match / Partially aligned / Inconsistent]
  Recommended canonical description: "[One version the team should standardize]"
  Score: [High / Medium / Low]

SCHEMA MARKUP:
  Organization schema present: [Yes / No]
  Fields included: [List what is present]
  Fields missing: [List gaps]
  SameAs links: [Present / Missing]
  Score: [High / Medium / Low]

THIRD-PARTY CITATIONS:
  Count of authoritative mentions: [N]
  Top sources: [List]
  Gaps vs. competitors: [What competitors have that this brand lacks]
  Score: [High / Medium / Low]

FOUNDER ENTITY:
  LinkedIn completeness: [Complete / Partial]
  Third-party mentions with brand association: [List any found]
  Score: [High / Medium / Low]

NAP CONSISTENCY (local brands):
  Issues found: [List discrepancies or "None found"]
  Score: [High / Medium / Low]

---

PRIORITY ACTION PLAN:

Priority 1 (fix first): [Signal]
  Action: [What specifically to do]
  Effort: [Low / Medium / High]
  Expected impact: [What this will improve]

Priority 2: [Same format]

Priority 3: [Same format]

[Continue for all signals with issues]

---

CANONICAL ENTITY DESCRIPTION:
"[Brand Name] is a [category] [company/agency/platform] that helps [audience] [achieve outcome]. [One sentence about the approach or founding context if relevant]."
Use this description consistently across all profiles and directories.
```

## Quality Check

- [ ] All six signal types audited
- [ ] Each signal scored
- [ ] Canonical entity description written
- [ ] Priority order follows the recommended sequence (schema first)
- [ ] Inconsistencies specifically documented (not just noted as "inconsistent")
- [ ] Actions are specific enough to hand off immediately

## Status

Phase 3 complete.
