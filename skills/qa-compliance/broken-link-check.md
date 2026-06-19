# Broken Link Check

## Purpose

Verify that every URL in a campaign, funnel, email sequence, or asset is working correctly before or after launch. Broken links are a silent conversion killer - leads click and land on a 404, a wrong page, or a redirect loop. The output is a complete link inventory with the status of each.

## Used By

- QA Agent (primary)

## Trigger

Use before any campaign launches (part of pre-launch-check.md), when a client reports that links are broken, after any site migration or URL change, or as a periodic audit on live campaigns.

## Inputs Needed

- All assets containing links to check - required
- Any known URL changes or redirects in the past 30 days - helpful
- Access to the landing page, funnel, and email sequence - required

## Process

**Step 1: Build the complete link inventory**

Go through every asset and collect every URL:

From ads:
- Destination URL in each ad
- Display URL (must match destination domain)

From landing pages:
- All CTA button links
- Footer links (Privacy Policy, Terms, etc.)
- Form action URL (where the form submits)
- Embedded video links

From emails:
- Every link in the email body
- Unsubscribe link
- CTA button links

From SMS:
- Every URL in every touch

From thank-you pages:
- Next-step links
- Resource links

**Step 2: Test each URL**

For each URL:
1. Visit it in a browser
2. Confirm it loads without error
3. Confirm it loads the correct page
4. Confirm it loads on mobile
5. Note the response code

Status codes:
- 200: Working
- 301/302: Redirect - confirm it ends at the right destination
- 404: Broken - page not found
- 500+: Server error
- Redirect loop: URL redirects to itself or in a circle

**Step 3: Check UTM parameters**

- Confirm parameters are not double-encoded (%2526 instead of %26)
- Confirm UTM values are correct (source, medium, campaign names)
- Confirm the CRM or analytics platform is receiving the UTM data

**Step 4: Check domain and SSL**

- Is the landing page on HTTPS? HTTP triggers browser security warnings.
- Is the SSL certificate valid? An expired cert blocks the page.
- Is the domain production, not staging?

**Step 5: Check mobile behavior**

Visit each link on a real mobile device or browser mobile emulator:
- Does the page load fully?
- Does the form render correctly?
- Do CTA buttons work?

## Output Format

```
BROKEN LINK CHECK - [Client/Campaign] - [Date]
QA Agent

ASSETS REVIEWED: [List all assets checked]

---

LINK INVENTORY:

ADS:
| Ad Name | URL | Status | Notes |
|---------|-----|--------|-------|
| [Ad 1] | [URL] | [200 / 301 correct / 404 / Error] | [Notes] |

LANDING PAGES:
| Page | Element | URL | Status | Notes |
|------|---------|-----|--------|-------|
| [Page] | [CTA Button / Footer / Form] | [URL] | [Status] | [Notes] |

EMAILS:
| Email # | Element | URL | Status | Notes |
|---------|---------|-----|--------|-------|
| [Email 1] | [CTA] | [URL] | [Status] | [Notes] |
| [Email 1] | [Unsubscribe] | [URL] | [Status] | [Notes] |

SMS:
| Touch | URL | Status | Notes |
|-------|-----|--------|-------|
| [Touch 1] | [URL] | [Status] | [Notes] |

THANK-YOU PAGES:
| Page | Element | URL | Status | Notes |
|------|---------|-----|--------|-------|

---

TECHNICAL CHECKS:

| Check | Status | Notes |
|-------|--------|-------|
| All landing pages on HTTPS | [PASS / FAIL] | [...] |
| SSL certificates valid | [PASS / FAIL] | [...] |
| Domains are production, not staging | [PASS / FAIL] | [...] |
| UTM parameters not double-encoded | [PASS / FAIL] | [...] |
| Mobile rendering confirmed | [PASS / FAIL] | [...] |

---

BROKEN OR INCORRECT LINKS:

| # | Asset | Element | URL | Issue | Fix |
|---|-------|---------|-----|-------|-----|
| 1 | [Asset] | [Location in asset] | [URL] | [404 / Wrong page / Redirect loop] | [What to change] |

---

VERDICT: [ALL LINKS WORKING / ISSUES FOUND - fix before launch]

If issues found: [N] link(s) must be fixed before launch.
```

## Quality Check

- [ ] Every URL across all assets is inventoried
- [ ] Each URL is actually tested, not just listed
- [ ] Mobile behavior is confirmed
- [ ] HTTPS and SSL are verified
- [ ] UTM parameters are confirmed correct
- [ ] Every broken or wrong URL has a specific fix noted

## Status

Phase 3 complete.
