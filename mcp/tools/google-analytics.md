# Google Analytics MCP Tool

## Purpose

Read access to Google Analytics 4 (GA4) data. Used to pull funnel conversion rates, traffic sources, landing page performance, and goal completions for weekly and monthly reports.

## Agents That Use This Tool

- **Analytics Agent** (primary) - weekly reports, funnel analysis, traffic analysis
- **Funnel Agent** (supporting) - landing page conversion rates, drop-off points
- **Paid Ads Agent** (supporting) - traffic quality from paid sources

---

## Setup

**Config file:** `mcp-configs/google-analytics.json`

**Credentials needed:**
- Google OAuth Client ID and Client Secret
- Google Refresh Token (generated after OAuth consent)
- GA4 Property ID (numbers only, no "G-" prefix)

**How to get credentials:**
1. Go to console.cloud.google.com → Create or open a project
2. Enable the **Google Analytics Data API**
3. Go to Credentials → Create Credentials → OAuth 2.0 Client ID
4. Application type: Web application
5. Add `http://localhost:3000/oauth2callback` as an authorized redirect URI
6. Copy Client ID and Client Secret
7. Run the OAuth flow (the MCP server will handle this on first run - a browser window will open)
8. After authorizing, the refresh token is stored automatically
9. Get your GA4 Property ID: analytics.google.com → Admin → Property Settings → Property ID (just the number)

**Environment variables:**
```
GA4_PROPERTY_ID=your_property_id_numbers_only
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GOOGLE_REFRESH_TOKEN=your_google_refresh_token
```

---

## What the Analytics Agent Uses This For

### Weekly report data pulls
- Sessions by source/medium for the week (paid vs. organic vs. direct)
- New users vs. returning users
- Landing page performance: sessions, bounce rate, engagement rate per page
- Goal/conversion completions (form submits, thank-you page views)
- Average session duration

### Funnel analysis
- Traffic to landing page (sessions on the opt-in page)
- Landing page to thank-you page (form submit conversion rate)
- Traffic by device type (mobile vs. desktop) - important for mobile optimization
- Page speed insights if GA4 is tracking Core Web Vitals

### Paid traffic quality
- Sessions from paid sources (utm_medium=cpc or paid_social)
- Bounce rate and engagement from paid vs. organic
- Conversion rate by traffic source

---

## Key GA4 Metrics Reference

| Metric Name in GA4 | What It Means | Used In |
|-------------------|--------------|---------|
| sessions | Total visits to the site | Weekly report |
| newUsers | First-time visitors | Weekly report |
| screenPageViews | Total page views | Funnel analysis |
| engagementRate | % of sessions with 10s+ engagement | Quality check |
| bounceRate | % of sessions with no engagement | Landing page QA |
| conversions | Goal completions (configured events) | Funnel analysis |
| sessionConversionRate | Conversions / sessions | Core funnel metric |

---

## Dimensions Reference

| Dimension | What It Segments By | Common Use |
|----------|---------------------|------------|
| sessionDefaultChannelGrouping | Traffic channel (Paid Search, Organic, etc.) | Source breakdown |
| landingPage | First page of session | LP performance |
| deviceCategory | desktop, mobile, tablet | Mobile optimization check |
| sessionSourceMedium | Exact source/medium (google/cpc) | Paid traffic analysis |

---

## Test Task (Verify Connection Works)

After adding credentials, run this to confirm the connection:

> "Pull sessions and conversions for the last 7 days from Google Analytics, broken down by channel grouping."

If it returns a table with channel data, the connection is working.

---

## Risks and Permissions

- Read-only access only. This tool cannot modify GA4 settings.
- Low risk, but ensure the OAuth scope is restricted to `analytics.readonly` to prevent any accidental writes.
- GA4 data has a standard processing delay of 24-48 hours for some metrics. Real-time data is limited.

---

## Status

Not connected. Config template is at `mcp-configs/google-analytics.json`. Fill in credentials when ready.
