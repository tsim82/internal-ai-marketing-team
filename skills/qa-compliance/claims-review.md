# Claims Review

## Purpose

Audit all marketing copy for unsubstantiated, misleading, or legally risky claims before any asset goes live. Marketing copy that makes specific income, results, or outcome claims without proper substantiation or disclaimers creates legal and regulatory risk. The output is a marked-up inventory of every claim, a verdict per claim, and specific fixes for every failure.

## Used By

- QA Agent (primary)
- Copywriter (receives the fixes)
- Marketing Director (reviews before anything with income or outcome claims goes live)

## Trigger

Use before any VSL, sales page, email sequence, or ad copy that includes income claims, specific result claims, testimonials, or before/after comparisons goes live. Also use when a client has a history of bold claims.

## Inputs Needed

- The full copy to review - required
- Documentation or evidence for any specific claims - required
- Industry and regulatory context (health, finance, business opportunity have stricter rules) - required

## Process

**Step 1: Identify all claims in the copy**

Pull every claim that is:
- A specific number or result ("Generated 47 leads in 30 days")
- A comparative claim ("Better than X")
- An income or revenue claim ("Made $20,000 in 90 days")
- A timeframe claim ("See results in 2 weeks")
- An outcome promise ("You will get X")
- A testimonial or client result
- A guarantee or refund statement

**Step 2: Evaluate each claim**

Each claim gets one verdict:

| Verdict | What it means |
|---------|--------------|
| PASS | Claim is accurate, substantiated, and not misleading |
| PASS WITH DISCLAIMER | Claim is acceptable but needs a disclaimer nearby |
| FAIL | Claim cannot be substantiated or is misleading as written |

**Step 3: Apply the claim type rules**

| Claim type | What is required to PASS |
|-----------|------------------------|
| Specific client result | Documented proof this result occurred, "results may vary" disclaimer nearby |
| Income claim | Documented proof, earnings disclaimer, disclosure results are not typical |
| Timeframe claim | Real example of this timeframe being achieved, not presented as a guarantee |
| Guarantee / refund | The guarantee must be real and enforceable - see guarantee-logic.md |
| Testimonial | Real client, not fabricated, no outcome promises without disclaimer |
| Before/after | Genuine, not exaggerated or compressed timeframe |

**Step 4: Write the required fix for every FAIL**

For every failed claim:
- Quote the exact copy
- State why it fails
- Write the specific fix (rewrite option or disclaimer to add)

**Step 5: Flag high-risk niches**

If the niche is health, finance, business opportunity, weight loss, or other regulated areas, flag for Marketing Director review before any live launch.

## Output Format

```
CLAIMS REVIEW - [Client/Asset Name] - [Date]
QA Agent

ASSET TYPE: [VSL / Sales page / Ad copy / Email sequence / Social post]
NICHE: [Industry - note if regulated]
RISK LEVEL: [Standard / Elevated - regulated niche]

---

CLAIMS INVENTORY:

CLAIM 1
  Copy: "[Exact quote of the claim]"
  Claim type: [Specific result / Income / Timeframe / Testimonial / Guarantee]
  Verdict: [PASS / PASS WITH DISCLAIMER / FAIL]

  If PASS WITH DISCLAIMER:
    Disclaimer required: "[Exact disclaimer text]"
    Placement: [Immediately below the claim / Footer / Beginning of section]

  If FAIL:
    Why it fails: [Specific reason]
    Required fix: [Rewrite option or documentation needed]
    Rewrite: "[Suggested compliant version]"

CLAIM 2
  [Same format]

[Continue for all claims]

---

SUMMARY:

Total claims reviewed: [N]
PASS: [N]
PASS WITH DISCLAIMER: [N]
FAIL: [N] - must fix before launch

DISCLAIMERS TO ADD:
| Location in copy | Disclaimer text |
|----------------|----------------|
| [Location] | "[Disclaimer]" |

FAILS REQUIRING FIX:
| Claim # | Issue summary | Fix summary |
|---------|--------------|------------|
| [#] | [What is wrong] | [What to do] |

---

VERDICT: [PASS / CONDITIONAL PASS - add disclaimers before launch / HOLD - failed claims must be rewritten]

If CONDITIONAL PASS: Copywriter adds disclaimers. QA re-checks those additions only.
If HOLD: All FAIL claims must be rewritten and re-submitted for review.

---

HIGH-RISK NOTES:
[Any claim needing Marketing Director or legal review before proceeding]
```

## Quality Check

- [ ] Every specific number, result, income, timeframe, and testimonial claim is inventoried
- [ ] Every claim has a verdict
- [ ] Every FAIL has a specific fix option
- [ ] Every PASS WITH DISCLAIMER has the exact disclaimer text written out
- [ ] Overall verdict is clear and blocks launch if any FAIL exists
- [ ] High-risk niches are flagged for director review

## Status

Phase 3 complete.
