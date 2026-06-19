# Pre-Launch Check

## Purpose

Run a complete QA check on a campaign, funnel, or automation before it goes live. The pre-launch check catches every category of error - tracking, copy, links, legal, formatting, mobile experience, and automation logic - before anything touches a real audience. Nothing goes live without a completed pre-launch check. The output is a READY or HOLD verdict.

## Used By

- QA Agent (primary)
- Marketing Director (receives the verdict before giving launch approval)

## Trigger

Use before any paid campaign launches, before a new funnel goes live, or before a new automation fires for real traffic.

## Inputs Needed

- All assets and URLs associated with the launch - required
- Campaign structure and targeting setup - required
- Tracking and pixel configuration - required
- Automation map or workflow doc - required
- Copy for all assets - required

## Process

**Section 1: Tracking and analytics**

- [ ] Facebook Pixel fires on the landing page (confirm in Pixel Helper)
- [ ] Conversion event fires on the thank-you page or booking confirmation
- [ ] Conversion event is the correct event type for the campaign objective
- [ ] CAPI (Conversions API) is connected and sending matching events
- [ ] No duplicate pixel fires
- [ ] UTM parameters are on all ad destination URLs
- [ ] Google Analytics (if used) is receiving traffic from the campaign source

**Section 2: Landing page and funnel**

- [ ] Landing page loads in under 3 seconds on mobile (test via PageSpeed Insights)
- [ ] Landing page is fully functional on mobile
- [ ] All form fields work and submit correctly
- [ ] Form submission sends to the correct CRM pipeline and stage
- [ ] Thank-you page fires after form submit with the correct next-step instruction
- [ ] Any video on the page loads and plays on mobile

**Section 3: Copy and claims**

- [ ] No em dashes in any copy (CLAUDE.md rule)
- [ ] No banned words from the CLAUDE.md word list
- [ ] All specific claims have evidence (see claims-review.md for full claims check)
- [ ] Income claims include appropriate disclaimers
- [ ] Testimonials do not make outcome promises without "results may vary" or equivalent
- [ ] No fake urgency that cannot be enforced

**Section 4: Links and URLs**

- [ ] All links in ads go to the correct landing page
- [ ] Destination URL is not a redirect loop
- [ ] All links on the landing page work
- [ ] CTA buttons point to the correct destination
- [ ] Email links work (for any email sequence launching alongside)
- [ ] Booking calendar link is correct and shows available times

**Section 5: Campaign setup**

- [ ] Campaign objective matches the goal (Lead gen objective for lead gen, not Traffic)
- [ ] Budget is set correctly
- [ ] Schedule is set correctly (start date/time, end date if applicable)
- [ ] Audience is correct (targeting, exclusions, lookalikes)
- [ ] Bid strategy is correct (Highest Volume for new campaigns)
- [ ] Ad creative is approved by platform (no pending review status)
- [ ] Naming convention is followed for campaigns, ad sets, and ads

**Section 6: Automation and CRM**

- [ ] Speed-to-lead automation is active and tested with a real test submission
- [ ] SMS sequence fires correctly (test with personal number)
- [ ] Email sequence fires correctly
- [ ] Lead is created in the correct CRM pipeline and stage
- [ ] Tags apply correctly based on source
- [ ] No duplicate sequences fire

**Section 7: Legal and compliance**

- [ ] Privacy Policy link is present on the landing page
- [ ] Terms of Service link is present (if required)
- [ ] SMS opt-in language is present at form level
- [ ] TCPA opt-in checkbox is present (if applicable)
- [ ] Guarantee language matches what the QA Agent approved in claims-review.md

## Output Format

```
PRE-LAUNCH CHECK - [Client/Campaign] - [Date]
QA Agent

LAUNCH DATE: [Planned date and time]
CAMPAIGN/FUNNEL: [Name]

---

SECTION 1: TRACKING
[Checklist with status per item]
Issues found: [List or None]

SECTION 2: LANDING PAGE AND FUNNEL
[Checklist with status per item]
Issues found: [List or None]

SECTION 3: COPY AND CLAIMS
[Checklist with status per item]
Issues found: [List or None]

SECTION 4: LINKS AND URLS
[Checklist with status per item]
Issues found: [List or None]

SECTION 5: CAMPAIGN SETUP
[Checklist with status per item]
Issues found: [List or None]

SECTION 6: AUTOMATION AND CRM
[Checklist with status per item]
Issues found: [List or None]

SECTION 7: LEGAL AND COMPLIANCE
[Checklist with status per item]
Issues found: [List or None]

---

ISSUES LOG:

| # | Section | Issue | Severity | Owner | Fixed? |
|---|---------|-------|---------|-------|--------|
| 1 | [Section] | [Specific issue] | [Must fix / Should fix] | [Agent] | [No] |

---

VERDICT: [READY TO LAUNCH / HOLD - issues must be resolved first]

If HOLD: Launch is blocked until all Must Fix items are resolved.
Re-check required: [Yes - affected sections / No]
```

## Quality Check

- [ ] Every section was checked (no sections skipped)
- [ ] Every issue is specific (location + what is wrong)
- [ ] Severity is assigned to every issue
- [ ] Verdict is stated clearly
- [ ] HOLD verdict blocks launch until resolved

## Status

Phase 3 complete.
