# Launch Checklist

## Purpose

Verify that every element of a paid campaign is correctly set up before the first dollar is spent. A missed pixel, wrong URL, or broken form means wasted ad spend and corrupted data. This checklist is run before every campaign launch, no exceptions.

## Used By

- Paid Ads Agent (primary)
- QA Agent (runs pre-launch check on copy and creative elements)
- Marketing Director (confirms launch readiness)

## Trigger

Use any time a new campaign, new ad set, or new creative is about to go live.

## Inputs Needed

- Campaign structure document
- All ad copy and creative assets
- Landing page URL
- Pixel and tracking confirmation
- Offer details and pricing
- Thank you page or confirmation flow

## Process

**Step 1: Verify tracking before anything else**

Tracking errors cannot be fixed retroactively. Corrupted data from the first week can affect campaign optimization for weeks.

- [ ] Meta Pixel fires on the landing page (verify with Facebook Pixel Helper or Meta Events Manager)
- [ ] Lead event fires on the thank you page / confirmation page (not just the landing page)
- [ ] Purchase event fires on the order confirmation page (for purchase campaigns)
- [ ] Conversions API (CAPI) is active and sending server-side events (for purchase or high-budget lead gen)
- [ ] No duplicate pixel fires (check Events Manager for duplicate events)
- [ ] Google Analytics tracking active on all pages (if applicable)
- [ ] UTM parameters are in all ad destination URLs

**Step 2: Verify the landing page and funnel**

- [ ] Landing page loads correctly on mobile (test on an actual phone, not just desktop browser mobile view)
- [ ] Page load time is under 3 seconds (use PageSpeed Insights if needed)
- [ ] The form works and submits successfully (test with a real submission)
- [ ] The thank you page or redirect fires correctly after form submission
- [ ] Any booked-call page or calendar embed loads and allows booking
- [ ] No broken images or placeholder text on the landing page
- [ ] Privacy policy link is present
- [ ] Copy on the landing page matches what the ad promises (no disconnect)

**Step 3: Verify the campaign setup**

- [ ] Campaign objective matches the goal (Leads for lead gen, not Traffic)
- [ ] Budget is set correctly (CBO at campaign level or ABO at ad set level, not both)
- [ ] Daily budget matches the approved amount from the CFO Agent budget plan
- [ ] Schedule is set correctly (if using a schedule - confirm time zone)
- [ ] Correct ad account selected (not a different client's account)

**Step 4: Verify audiences**

- [ ] Each ad set has the correct audience assigned
- [ ] Audience sizes are within expected ranges (not too narrow, not too broad)
- [ ] Exclusion audiences are applied (buyers excluded from cold traffic, etc.)
- [ ] Custom audiences are correctly sourced (pixel-based, not empty)
- [ ] Lookalike audiences are using the correct source and percentage

**Step 5: Verify creative and copy**

- [ ] All ad images and videos are approved by Meta (no disapprovals in review)
- [ ] Images are the correct dimensions for each placement
- [ ] Videos play correctly with and without sound
- [ ] Primary text is complete with no placeholder text
- [ ] Headline is under the character limit and displays correctly
- [ ] CTA button is set to the correct type (Book Now, Learn More, Sign Up, etc.)
- [ ] Destination URL is correct and live for every ad
- [ ] UTM parameters are in every destination URL

**Step 6: Verify naming and organization**

- [ ] Campaign name follows the naming convention
- [ ] All ad set names follow the convention
- [ ] All ad names follow the convention
- [ ] No ad sets or ads are left with default names (Ad Set 1, etc.)

**Step 7: Run a final test**

Before launching, submit a test lead through the actual ad flow:
1. Verify the ad loads and displays correctly in preview
2. Click through to the landing page
3. Submit the form or complete the opt-in
4. Confirm the thank you page appears
5. Confirm the lead event fired in Events Manager
6. Confirm the lead appeared in the CRM

Do not skip the test submission. It is the only way to confirm the full flow works.

## Output Format

```
LAUNCH CHECKLIST - [Client/Campaign] - [Launch Date]

CAMPAIGN: [Name]
PLATFORM: [Meta / Google]
LAUNCH DATE/TIME: [Date and time in client's time zone]

---

TRACKING
[ ] Pixel confirmed on landing page
[ ] Conversion event confirmed on thank you/confirmation page
[ ] CAPI active (if applicable)
[ ] No duplicate events
[ ] UTM parameters in all URLs

LANDING PAGE AND FUNNEL
[ ] Mobile load test passed
[ ] Page speed under 3 seconds
[ ] Form tested and confirmed working
[ ] Thank you page fires correctly
[ ] No placeholder text on page
[ ] Privacy policy present
[ ] Ad-to-page message match confirmed

CAMPAIGN SETUP
[ ] Correct objective
[ ] Correct budget amount and level
[ ] Correct ad account

AUDIENCES
[ ] All audiences verified and sized
[ ] Exclusions applied
[ ] Custom audiences not empty

CREATIVE AND COPY
[ ] All ads approved by platform
[ ] Correct dimensions for all placements
[ ] All destination URLs correct and live
[ ] All UTM parameters in place
[ ] No placeholder text in copy

NAMING
[ ] Campaign naming convention followed
[ ] Ad set naming convention followed
[ ] Ad naming convention followed

FINAL TEST SUBMISSION
[ ] Test lead submitted through full ad flow
[ ] Lead event confirmed in Events Manager
[ ] Lead appeared in CRM

---

LAUNCH SIGN-OFF:
Checked by: [Agent or person]
Launch status: [Ready to launch / HOLD - issues below]

Issues (if HOLD):
1. [Issue - what needs to fix and who fixes it]
```

## Quality Check

- [ ] Every section of this checklist is completed before any campaign goes live
- [ ] Test submission is completed and confirmed - this is not optional
- [ ] Any HOLD items are documented with who is responsible for fixing them
- [ ] After fixes, checklist is re-run for the affected sections

## Status

Phase 3 complete.
