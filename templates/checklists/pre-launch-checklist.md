# Pre-Launch Checklist

Complete this before any campaign, funnel, or automation goes live. Nothing ships until every item is checked or explicitly flagged as N/A with a reason.

**Client:**
**Campaign / project:**
**Launch date:**
**Checklist completed by:**
**Date:**

---

## 1. Tracking

- [ ] Meta Pixel is installed on the landing page
- [ ] Pixel fires correctly on page load (verified in Meta Pixel Helper or Events Manager)
- [ ] Conversion event fires on the thank-you page (verified - not just assumed)
- [ ] CAPI is connected and sending server-side events
- [ ] Google Analytics is installed (if applicable)
- [ ] GA4 conversion goal is configured for the form submit event
- [ ] UTM parameters are on all destination URLs (source, medium, campaign)
- [ ] UTM parameters encode correctly (no spaces, special chars)

**Issues found:**

---

## 2. Landing Page and Funnel

- [ ] Landing page loads correctly on mobile (tested on actual phone, not just browser resize)
- [ ] Landing page loads in under 3 seconds on mobile
- [ ] Headline matches the ad's promise
- [ ] Form works end-to-end (submitted a test lead - confirmed it appeared in CRM)
- [ ] Thank-you page loads after form submit
- [ ] Thank-you page has correct next step instructions for the lead
- [ ] All images and videos on the page load correctly
- [ ] No broken formatting or overlapping elements on mobile

**Issues found:**

---

## 3. Copy and Claims

- [ ] All ad copy has been reviewed by QA Agent (brand-voice-check.md)
- [ ] All specific claims, results, and guarantees have been reviewed (claims-review.md)
- [ ] No claims received a FAIL verdict - all are PASS or PASS WITH DISCLAIMER
- [ ] Required disclaimers are present in the copy where marked
- [ ] No em dashes in any copy
- [ ] No banned words from voice-rules.md appear in any copy

**Issues found:**

---

## 4. Links

- [ ] All links in ads point to the correct URL
- [ ] All links in emails point to the correct URLs
- [ ] All links in SMS messages are tested (short links resolve to correct destination)
- [ ] Unsubscribe link in emails works
- [ ] Calendar booking link works and shows available times
- [ ] All URLs are HTTPS (no HTTP)

**Issues found:**

---

## 5. Campaign Setup (Paid Ads)

- [ ] Campaign objective is correct (Leads or Conversions - never Traffic for lead gen)
- [ ] Campaign structure matches the campaign brief (TOF / MOF / BOF)
- [ ] CBO is enabled at campaign level
- [ ] Ad account, pixel, and conversion event are correctly linked
- [ ] Budget is set correctly and matches the approved amount
- [ ] Start date and time are correct
- [ ] Ad set audiences are correct and not overlapping
- [ ] All ad previews have been reviewed (desktop and mobile)
- [ ] All ads are in Active status (or Scheduled for future start)
- [ ] Campaign naming convention is applied

**Issues found:**

---

## 6. Automations and CRM

- [ ] Speed-to-lead automation is active and tested with a real test submission
- [ ] First contact fires within 5 minutes of form submit (verified with test)
- [ ] Follow-up SMS sequence is active (if applicable)
- [ ] Follow-up email sequence is active (if applicable)
- [ ] Test lead is in the correct CRM pipeline and stage
- [ ] Test lead has the correct tags applied
- [ ] Booking reminder automation is active (if applicable)
- [ ] n8n error handler is active on all workflows

**Issues found:**

---

## 7. Legal and Compliance

- [ ] TCPA opt-in language is present on the form (for SMS)
- [ ] Privacy policy link is on the landing page
- [ ] Terms of service link is on the landing page (if collecting payments)
- [ ] No urgency or scarcity elements are fake (countdown timers reset, fake capacity limits)
- [ ] Income or results disclaimers are present where required
- [ ] All testimonials used have permission (written or explicit consent)

**Issues found:**

---

## Final Verdict

- [ ] **READY** - All items checked or documented as N/A. Approved to launch.
- [ ] **HOLD** - One or more Must Fix items are open. Do not launch until resolved.

**Must Fix before launch:**
(List any items that are blocking launch)

**Should Fix soon (not blocking):**
(List any items to address in the first 7 days)

---

**Approved by:**

**Date:**
