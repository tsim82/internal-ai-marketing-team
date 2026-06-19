# Creative Testing Plan

## Purpose

Produce a structured creative testing plan that isolates one variable at a time, defines what winning and losing look like, and gives the Paid Ads Agent a clear decision framework for when to kill, scale, or iterate. Testing without a plan produces data but no decisions.

## Used By

- Paid Ads Agent (primary)
- Creative Design Agent (knows what to produce next)
- Copywriter (knows which copy angles to prioritize)
- Analytics Agent (tracks against the plan)

## Trigger

Use when launching a new campaign (test from day one), when current creative is fatiguing, when CTR or CPL is drifting, or when the team does not know which creative is actually working.

## Inputs Needed

- Current performance data (if testing replacement for existing creative) - helpful
- Available creative concepts and copy angles - required
- Budget available for testing - required
- Target CPL or ROAS - required
- Platform (determines format options and volume thresholds) - required

## Process

**Step 1: Identify what is being tested**
Use the creative testing hierarchy. Always test in this order. Do not jump ahead:

1. **Format**: Static vs. video vs. carousel. This is the biggest variable. Test format first.
2. **Background/concept**: Once format is decided, test the visual concept. Lifestyle scene vs. plain background vs. text-on-color.
3. **Hook/opening**: Once format and concept win are known, test hook variations.
4. **Color/style**: Once hook is known, test color or visual treatment variations.
5. **Copy length**: Once everything else is stable, test long vs. short copy.

**Step 2: Set the testing parameters**

For each test:
- Control: what is the current baseline (if any)?
- Challenger(s): what are the new variants?
- Variable: what is the single thing being changed?
- Duration: how many days before a decision?
- Budget: how much per variant?
- Success threshold: what CPL or CTR makes a variant a winner?
- Loser threshold: what metric kills a variant early?

**Step 3: Write the kill/scale rules**

Kill a variant early (before the test period ends) if:
- Spend exceeds 2x the average CPL target with zero conversions
- CTR is below 0.3% after 3+ days of delivery and 5,000+ impressions
- Frequency exceeds 3.5 in under 7 days (audience exhausted, not creative failure)

Scale a winner if:
- CPL is below target after 15-20 leads generated
- CTR is 1%+ with consistent delivery
- ROAS is at or above target with sufficient volume

Iterate (do not kill, do not scale) if:
- CPL is within 20% of target but not yet reaching threshold volume
- Ad has been running less than 7 days and has fewer than 10 conversions

**Step 4: Name and track each variant**
Each ad variant must be named in a way that makes it immediately clear what was changed.

Example naming:
- `Pain-Static-DarkBG-Hook1` = Pain angle, static image, dark background, hook option 1
- `Proof-Video-Hook2` = Proof angle, video format, hook option 2

**Step 5: Schedule the decision point**
Set a calendar date for reviewing each test. "We will review on [date] after each ad has spent at least $[X] or received at least [N] leads."

Without a scheduled decision point, tests run indefinitely and underperformers silently drain budget.

## Output Format

```
CREATIVE TESTING PLAN - [Client/Campaign] - [Date]

WHAT IS BEING TESTED THIS ROUND: [Format / Concept / Hook / Color / Copy length]
TESTING RATIONALE: [Why this variable, at this point in the campaign]

---

TEST SETUP:

Control (current baseline if any):
  Ad name: [Name]
  Performance: CPL $[X], CTR [X]%, [N] leads

Challenger A:
  Ad name: [Name per convention]
  Variable changed: [What is different from control]
  Creative: [Brief description or reference]
  Copy: [Brief description or reference]

Challenger B:
  Ad name: [Name per convention]
  Variable changed: [What is different from control]
  [Same format]

Challenger C (if testing 3 variants):
  [Same format]

---

PARAMETERS:

Budget per variant: $[X]/day
Duration: [N] days before decision (or until [N] conversions per variant)
Decision date: [Date]

Success threshold (WINNER):
  CPL below $[X] after [N] leads
  CTR above [X]%

Kill threshold (EARLY KILL):
  Spend $[X] with 0 conversions
  CTR below 0.3% after [N] days and [N] impressions
  Frequency above 3.5 in 7 days

Iterate threshold (NOT A WINNER, NOT DEAD):
  CPL within 20% of target but fewer than [N] leads
  Running fewer than 7 days

---

DECISION FRAMEWORK:

If [Challenger A] wins → [What to do: pause control, scale winner, run next test on variable 2]
If control wins → [What to do: revert to control, test different concept for challenger]
If no winner → [What to do: extend test or increase budget to reach statistical confidence]

---

NEXT TEST (planned):
After this test concludes, the next variable to test is: [Variable]
Why: [Rationale for the sequence]
```

## Quality Check

- [ ] Only one variable is changing between control and challenger(s)
- [ ] Kill and scale thresholds are documented before the test runs
- [ ] Decision date is set and calendared
- [ ] Budget per variant is sufficient to reach the conversion threshold
- [ ] Ad naming follows the convention so reports are readable
- [ ] Next test is planned so momentum continues after the decision

## Status

Phase 3 complete.
