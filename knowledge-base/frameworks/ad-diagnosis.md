# Ad Diagnosis Framework

The structured process for diagnosing why ads are not performing. Reading metrics out of order leads to wrong diagnoses and wrong fixes. This framework is the sequence the Analytics Agent and Paid Ads Agent follow on every review.

---

## The Diagnosis Order

Always read metrics in this order. Do not skip steps.

```
1. IMPRESSIONS
   Are ads being served?
   Low impressions = budget issue, bid issue, or policy flag
   Fix: Check budget pacing, bid strategy, or account flags

2. FREQUENCY
   How many times has the same person seen this ad?
   Over 3.5 in 7 days = creative fatigue, even if other metrics look fine
   Fix: Rotate creative before touching anything else

3. CTR (Click-Through Rate)
   Are people clicking?
   Under 0.5% = creative or hook problem
   1%+ = creative is working
   Fix: Test new hooks or creative concepts

4. CPC (Cost Per Click)
   How much does each click cost?
   High CPC + low CTR = creative problem
   High CPC + good CTR = audience is competitive
   Fix: Creative issue → new hook. Audience issue → new audience or placement

5. LP CVR (Landing Page Conversion Rate)
   What % of clicks become leads?
   Under 20% = landing page problem, not ad problem
   25-40% = good
   Fix: Mobile speed, headline, form friction

6. CPL (Cost Per Lead)
   What does each lead cost?
   Above target with good CTR and good LP CVR = volume problem (need more budget or audience)
   Above target with issues at 3, 4, or 5 = fix those first
   Fix: Based on what was found in steps 1-5

7. LEAD QUALITY
   Are leads converting downstream?
   Low show rate or close rate despite OK CPL = targeting wrong people
   Fix: Tighten audience, adjust copy promise, update qualification criteria
```

---

## Common Pattern Diagnoses

| Pattern | Diagnosis | Fix |
|---------|----------|-----|
| High CPL + Low CTR | Creative fatigue or wrong hook | New creative or hook test |
| High CPL + Good CTR + Low LP CVR | Landing page problem | Fix page - check mobile, speed, headline |
| High CPL + Good CTR + Good LP CVR + Poor lead quality | Targeting wrong audience | Adjust copy or tighten audience |
| Good CPL + Low volume | Budget constrained or audience too small | More budget or broader audience |
| Good CTR + High CPC | Competitive auction | Adjust bid or shift placement |
| Frequency 3.5+ in 7 days | Creative fatigue | Rotate creative regardless of other metrics |

---

## Decision Framework

After diagnosis, every active ad gets one decision:

| Decision | Condition |
|---------|----------|
| **SCALE** | CPL below target after 15-20 leads, leads converting downstream. Increase budget 20%. |
| **KEEP** | On target. No change. |
| **ITERATE** | Within 20% of target, under 7 days. Change one variable. |
| **KILL** | CPL 2x+ target with no conversions after 5x CPL in spend, OR CTR under 0.3% after 3 days/$50. |
| **TEST** | Pattern indicates new concept needed. Pull a new creative brief. |
| **ESCALATE** | Something is broken (pixel, billing, account flags) that requires account-level attention. |

---

## Price Floor Check

Before killing an ad due to high CPL, confirm the economics allow for the target CPL:

```
Price Floor = Delivery Cost ÷ (1 - Target Margin)
Max Allowable CPA = Gross Profit - Target Net Profit
```

If Max Allowable CPA is lower than the industry average CPL, the offer economics need to change, not the ads.

---

## Where This Framework Is Used

- `skills/analytics-optimization/ad-performance-review.md` - Weekly ad review
- `skills/paid-ads/optimization-review.md` - Decision logic
- `skills/analytics-optimization/weekly-report.md` - Performance findings
- `skills/cfo/offer-profitability.md` - Max CPA calculation

---

## Status

Active. Use on every ad review, in this order.
