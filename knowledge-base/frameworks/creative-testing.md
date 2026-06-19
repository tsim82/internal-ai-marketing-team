# Creative Testing Framework

The structured approach for testing ad creatives on Meta (and Google Display). Testing one variable at a time is the only way to know what actually caused a result. This framework is used by the Paid Ads Agent and Creative Design Agent on every campaign.

---

## The Testing Hierarchy

Test in this order. Each level must be settled before moving to the next.

```
1. FORMAT
   (What kind of ad is this?)
   Options: Static image / Single video / Carousel / UGC-style
   Test: Run each format against the same copy, same audience
   Why first: Format affects delivery, cost, and attention differently

2. BACKGROUND / CONCEPT
   (What is the core visual idea?)
   Options: Pain moment / Result moment / Direct offer / Social proof / Pattern interrupt
   Test: Same format, different concept
   Why: The concept is the biggest creative driver after format

3. HOOK
   (What is the first line or first 3 seconds?)
   Options: Question / Bold claim / Curiosity gap / Contrarian / Pain mirror / Direct benefit
   Test: Same format and concept, different hooks
   Why: Hook determines scroll-stop rate

4. COLOR / BACKGROUND TREATMENT
   (Color temperature, dominant color, background)
   Test: Same hook and concept, different color treatment
   Why: Affects attention and brand recognition

5. COPY LENGTH / STRUCTURE
   (Short vs. long primary text, bullet vs. paragraph)
   Test: Same creative, different copy structure
   Why: Tested last because it has the smallest effect on most accounts
```

---

## One Variable Per Test

Only change one element at a time. If you change the hook AND the color, you do not know which change caused the result.

---

## Kill Thresholds

Stop spending on a creative when any of these conditions are met:

| Condition | Action |
|-----------|--------|
| CPL is 2x+ target AND zero conversions after spending 5x target CPL | Kill immediately |
| CTR under 0.3% after 3 days and $50+ spend | Kill (hook is not working) |
| Frequency above 3.5 in 7 days | Rotate creative regardless of other metrics |
| CPC increasing week over week while CTR holds | Creative fatigue starting |

---

## Scale Thresholds

Move toward scaling when:
- CPL is below target after 15-20 leads
- CTR is 1%+
- Lead quality is converting downstream (booking and showing rates on target)

Scale by increasing budget 20% per week, not more.

---

## Iterate Threshold

Do not kill or scale. Test a small change when:
- CPL is within 20% of target
- Campaign is under 7 days old
- The data is not conclusive yet

---

## Naming Convention for Test Tracking

Format: `[Audience]-[Format]-[Concept]-[Hook#]-[Variant]`

Example: `TOF-Static-Pain-H1-A` and `TOF-Static-Pain-H1-B`

This makes it possible to read performance by test variable at a glance in the ads manager.

---

## Decision Dates

Every ad that is not killed immediately must have a decision date. If it has not hit a kill threshold and has not hit a scale threshold by the decision date, mark it as Iterate and make one change.

Minimum time before a decision: 3-7 days and at least $50 in spend. Do not make decisions earlier.

---

## Where This Framework Is Used

- `skills/paid-ads/creative-testing-plan.md` - Full testing plan process
- `skills/paid-ads/optimization-review.md` - Weekly review and decision logic
- `skills/creative-design/ad-creative-brief.md` - Creative brief format
- `skills/analytics-optimization/ad-performance-review.md` - Scale/kill decisions

---

## Status

Active. Use on every campaign from day one.
