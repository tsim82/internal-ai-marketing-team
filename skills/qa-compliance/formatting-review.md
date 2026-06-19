# Formatting Review

## Purpose

Review a written document, email, social post, script, or any other text asset for formatting issues before it goes out. Formatting problems erode professionalism and can break how copy renders in an email client, CRM, or social post. The output is a specific list of every formatting issue with the fix, and a PASS or HOLD verdict.

## Used By

- QA Agent (primary)

## Trigger

Use before any written asset goes to a client, goes live on a platform, or is passed from one agent to another as a final handoff. Also use when a client flags that something "looked wrong" after publishing.

## Inputs Needed

- The finished written asset to review - required
- The platform or destination it will publish to - required
- Platform-specific formatting rules (HeyGen rules, email client rendering, etc.) - helpful

## Process

**Step 1: Apply the universal formatting rules from CLAUDE.md**

These rules apply to every output without exception:

| Rule | What to check |
|------|--------------|
| No em dashes | Search for — and replace with a comma, period, or rewrite |
| Contractions | Confirm contractions are used (it's, we've, don't) not formal alternatives |
| Plain English | Flag corporate language, jargon, or unnecessarily formal phrasing |
| No banned words | Check against the CLAUDE.md banned word list |
| Conversational tone | Does it sound like a person talking, or like a brand announcing? |

**Step 2: Apply platform-specific rules**

**Email:**
- Subject line under 50 characters
- Preview text present and does not repeat the subject
- Links use correct URLs (not placeholders)
- Footer has unsubscribe link
- Personalization tokens are correct format for the platform

**Instagram / Facebook post:**
- Line breaks are intentional (white space for readability)
- Hashtags at end of post, not mid-sentence
- No URLs in Instagram post body (link in bio instead)

**LinkedIn post:**
- First line is a standalone hook
- Heavy line breaks throughout
- Hashtags at end, 0-3 only

**HeyGen script:**
- All sentences under 20 words
- No em dashes
- No ellipsis (...)
- All abbreviations written out
- [PAUSE] markers placed

**Landing page copy:**
- Bullet points are parallel in structure
- CTA button copy is action-oriented

**Step 3: Check for consistency issues**

- [ ] Capitalization is consistent
- [ ] Number style is consistent (write out "three" or use "3" - not both)
- [ ] Brand and name references are spelled correctly and consistently

**Step 4: Check character limits where applicable**

| Element | Platform | Limit |
|---------|---------|-------|
| Subject line | Email | 50 chars for preview |
| Meta headline | Facebook / Instagram ads | 40 chars |
| Meta primary text | Facebook / Instagram ads | 125 chars before truncation |
| LinkedIn post | LinkedIn | 3,000 chars |
| SMS | SMS | 160 chars per segment |

## Output Format

```
FORMATTING REVIEW - [Asset Name] - [Date]
QA Agent

ASSET TYPE: [Email / Social post / Script / Landing page / Ad copy]
PLATFORM DESTINATION: [Where this publishes]

---

UNIVERSAL RULES CHECK:

| Rule | Status | Location of issue |
|------|--------|------------------|
| No em dashes | [PASS / FLAG - N found] | [Paragraph and line if flagged] |
| Contractions used | [PASS / FLAG] | [Formal alternatives found] |
| No corporate language | [PASS / FLAG] | [Phrases flagged] |
| No banned words | [PASS / FLAG] | [Words found] |

---

PLATFORM-SPECIFIC RULES CHECK:

| Rule | Status | Notes |
|------|--------|-------|
| [Rule 1] | [PASS / FLAG] | [Notes] |
| [Rule 2] | [PASS / FLAG] | [...] |

---

CONSISTENCY CHECK:

| Element | Status | Notes |
|---------|--------|-------|
| Capitalization | [PASS / FLAG] | [...] |
| Number style | [PASS / FLAG] | [...] |
| Brand/name spelling | [PASS / FLAG] | [...] |

---

CHARACTER LIMIT CHECK (if applicable):

| Element | Limit | Actual | Status |
|---------|-------|--------|--------|
| [Element] | [N chars] | [N chars] | [Pass / Over limit] |

---

ISSUES LOG:

| # | Location | Issue | Fix |
|---|---------|-------|-----|
| 1 | [Section / Line] | [What is wrong] | [What to change] |

---

VERDICT: [PASS / MINOR ISSUES - fix list below, no resubmission needed / HOLD - multiple issues, resubmit after corrections]
```

## Quality Check

- [ ] Em dash check is always run
- [ ] Platform-specific rules are applied for the destination
- [ ] Every issue has a location
- [ ] Character limits are checked where applicable
- [ ] Verdict is clear

## Status

Phase 3 complete.
