# Brand Voice Check

## Purpose

Review any written asset for adherence to the brand voice rules and the global writing rules from CLAUDE.md. A brand voice check catches tone, word choice, phrasing, and structural problems before copy goes to a client or goes live. The output is a marked-up document with [PASS] or [FLAG] per section and specific rewrites for every flagged issue.

## Used By

- QA Agent (primary)

## Trigger

Use before any client-facing written asset is delivered: ads, emails, social posts, landing pages, VSLs, scripts, and reports. Also use when a piece of copy feels off and needs a structured review.

## Inputs Needed

- The written asset to review - required
- Brand voice guidelines (if client-specific, beyond CLAUDE.md) - required
- The target audience for this piece - required

## Process

**Step 1: Apply the universal writing rules from CLAUDE.md**

| Rule | What to flag |
|------|-------------|
| No em dashes | Flag every — and suggest replacement |
| Use contractions | Flag "it is," "we have," "do not" when natural contractions would sound better |
| Plain English | Flag unnecessarily complex words or formal phrasing |
| Conversational and natural | Flag any sentence that sounds like a press release |
| Not corporate | Flag phrases like "we are committed to," "leverage our expertise," "synergistic approach" |
| No AI hype language | Check against the full CLAUDE.md banned word list |
| No rhythmic three-part phrasing | Flag constructions like "plan, execute, and deliver" or "think, act, and grow" |
| No repetitive sentence patterns | Flag if three or more consecutive sentences start the same way |
| Focus on outcomes not theory | Flag paragraphs that explain what something is without connecting to what it does for the reader |

**Step 2: Assess the tone**

Read the piece as the target audience would. Does it sound like a real person writing directly to them?

Signs of the right tone:
- Uses "you" and "your" frequently
- References the reader's situation specifically
- Does not over-explain things the audience already knows
- Phrasing sounds like how the audience actually talks

Signs of the wrong tone:
- Formal or stiff sentence structure
- Too much "we" (about the brand), not enough "you" (about the reader)
- Abstract language instead of concrete specifics
- Multi-paragraph introductions before getting to the point

**Step 3: Check for banned words**

The following words are banned from all outputs unless specifically asked for:
delve, dive, revolutionize, cutting edge, supercharge, crucial, harness, catapult, paramount, unlock, unleash, skyrocket, foster, elevate, game changer, embark, transform, resonate, robust, seamless, trailblazer, unveil, arsenal, fast-paced

**Step 4: Flag and rewrite**

For every flagged item:
- Quote the exact text
- State which rule it violates
- Write an alternative version

## Output Format

```
BRAND VOICE CHECK - [Asset Name] - [Date]
QA Agent

ASSET TYPE: [Ad copy / Email / Social post / Landing page / Script / Report]
AUDIENCE: [Who this is written for]

---

UNIVERSAL RULES CHECK:

| Rule | Status | Instances found |
|------|--------|----------------|
| No em dashes | [PASS / FLAG - N found] | [Location of each] |
| Contractions used | [PASS / FLAG] | [Formal alternatives found] |
| No corporate language | [PASS / FLAG] | [Phrases flagged] |
| No AI hype language | [PASS / FLAG] | [Words found] |
| No rhythmic three-part phrasing | [PASS / FLAG] | [Instances] |
| No repetitive sentence patterns | [PASS / FLAG] | [Location] |
| Outcomes over theory | [PASS / FLAG] | [Sections that explain without connecting to reader] |

---

TONE ASSESSMENT:

Sounds like a real person: [Yes / Somewhat / No]
"You" / "Your" frequency: [High / Medium / Low]
Concrete specifics present: [Throughout / Missing in: list sections]
Audience-level language: [Correct / Too formal / Too casual]

Overall tone verdict: [Matches brand voice / Needs adjustment]

---

FLAGGED ITEMS:

FLAG 1
  Location: [Section or line reference]
  Text: "[Exact quoted text]"
  Rule violated: [Which rule]
  Suggested rewrite: "[Alternative text]"

FLAG 2
  [Same format]

---

SUMMARY:

Total flags: [N]
Must fix (tone-breaking or rule violations): [N]
Should fix (minor improvements): [N]

---

VERDICT: [PASS / MINOR REVISIONS - fix list below / HOLD - significant voice issues, needs rewrite]

If MINOR REVISIONS: Copywriter makes flagged changes. No resubmission needed unless changes are extensive.
If HOLD: Return to Copywriter with this review document for a full revision.
```

## Quality Check

- [ ] All CLAUDE.md writing rules were checked
- [ ] Banned word list was fully scanned
- [ ] Em dash check was run
- [ ] Tone assessment includes specific evidence
- [ ] Every flagged item has a specific rewrite suggestion
- [ ] Verdict is clear and actionable

## Status

Phase 3 complete.
