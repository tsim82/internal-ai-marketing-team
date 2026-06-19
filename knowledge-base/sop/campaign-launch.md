# Campaign Launch SOP

The step-by-step process for launching a new campaign, from brief to live. Applies to Meta Ads campaigns and Google Ads campaigns.

---

## Ownership

- Primary owner: Paid Ads Agent
- Support: Copywriter (copy), Creative Design Agent (creative), Funnel Agent (landing page), QA Agent (pre-launch check), n8n Automation Agent (automations)

---

## Pre-Launch Requirements

Before any campaign launch, confirm all of the following are ready:

**Strategy:**
- [ ] Campaign goal is defined (lead gen / purchase / call booking)
- [ ] Audience is defined (TOF, MOF, BOF - who is in each)
- [ ] Budget is set and approved by CFO Agent or client
- [ ] Offer and copy angle are approved
- [ ] Creative concepts are approved

**Copy:**
- [ ] Ad copy is written and approved (headlines, primary text, CTA)
- [ ] Landing page copy is written and approved
- [ ] Thank-you page copy is written
- [ ] Email sequence copy is written and approved (if applicable)
- [ ] SMS sequence copy is written and approved (if applicable)

**Creative:**
- [ ] Ad creative is produced (minimum 3-5 creative variations)
- [ ] Creative has passed brand-voice-check.md and brand-visual-check.md
- [ ] Correct dimensions for all placements

**Technical:**
- [ ] Pixel is installed and firing on the landing page
- [ ] Conversion event is set up and fires on the thank-you page
- [ ] CAPI is connected (for Meta)
- [ ] UTM parameters are set on all destination URLs
- [ ] Form is tested end-to-end (submits to correct CRM pipeline and stage)
- [ ] Speed-to-lead automation is tested with a real submission
- [ ] SMS and email sequences are confirmed active

**QA:**
- [ ] pre-launch-check.md is complete
- [ ] Verdict is READY

---

## Launch Sequence

**Step 1: Final creative review**
- Confirm all ad images and videos are uploaded in the correct formats
- Confirm no creative is pending platform review (or allow 24h for review)

**Step 2: Set up campaign structure**
- Campaign (CBO, correct objective)
- Ad sets (one audience per ad set, correct targeting)
- Ads (one creative per ad, correct copy and destination URL)
- Naming convention applied to all elements

**Step 3: Set budget and schedule**
- Daily or lifetime budget set as planned
- Start time confirmed (do not launch right before weekend if possible for first 48h monitoring)
- End date set if applicable (for time-limited campaigns)

**Step 4: Final check before publishing**
- All campaign settings reviewed
- All ad previews viewed
- Destination URLs tested one more time

**Step 5: Publish**
- Submit campaign for review
- Note the launch date and time in the client's CRM record

**Step 6: Monitor the first 48 hours**
- Day 1, 4 hours after launch: Check that ads are being served (impressions are generating)
- Day 1, end of day: Check spend is pacing as expected
- Day 2: Check first leads are being received and flowing into the CRM correctly
- Day 2: Confirm speed-to-lead is firing for the first real leads

---

## First Optimization Window

Do not make changes within the first 72 hours unless:
- Ads are not being served at all (delivery issue)
- Something is broken (pixel, form, automation)
- Spend is wildly off (burning budget with no delivery or all budget gone in hours)

The algorithm needs 72 hours and 15-20 optimization events before data is meaningful.

---

## First Formal Review

First formal optimization review: 7 days after launch. Use skills/paid-ads/optimization-review.md.

---

## Status

Active SOP. Use for every campaign launch.
