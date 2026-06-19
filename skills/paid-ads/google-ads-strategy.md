# Google Ads Strategy

## Purpose

Produce the full strategic plan for a Google Ads campaign: campaign type, keyword strategy, match type logic, ad group structure, bidding strategy, and ad copy direction. The output is the plan the Paid Ads Agent uses to build Google campaigns. Works alongside the campaign-structure skill, which handles naming and structural hierarchy.

## Used By

- Paid Ads Agent (primary)
- Copywriter (ad copy direction for responsive search ads)
- Analytics Agent (tracks against targets)

## Trigger

Use when launching a new Google Ads campaign, when restructuring underperforming Google campaigns, or when a client wants to add search to an existing paid channel mix.

## Inputs Needed

- Offer and landing page URL - required
- Target keywords or topic areas (from client or research) - required
- Budget (daily or monthly) - required
- Conversion goal (form submission, phone call, purchase) - required
- Geographic targeting - required
- Any existing Google Ads data or account history - helpful

## Process

**Step 1: Choose the campaign type**

- **Search**: Shows ads when people search specific terms. Best for intent-based lead gen and service businesses.
- **Performance Max (PMax)**: Google's AI-driven campaign across all placements. Works when there is enough conversion data (50+ conversions/month) and clear creative assets. Not ideal for new campaigns without history.
- **Shopping**: Product-based campaigns. For e-commerce only.
- **Display / YouTube**: Brand awareness or retargeting. Not a primary lead gen channel for most service businesses.

For most service business lead gen campaigns, start with Search.

**Step 2: Build the keyword strategy**

The keyword strategy determines who sees the ads. Get this wrong and everything else is wasted.

**Keyword research process:**
1. Start with what buyers search when they are ready to buy, not when they are researching. "Hire social media manager" not "what is social media management."
2. Look at Google's suggested keywords but do not blindly use them. Remove anything generic, informational, or irrelevant.
3. Group keywords into themes. Each theme becomes one ad group.

**Match type logic:**
- **Exact match** [keyword]: Most controlled. Ads show for that exact search or very close variants. Lower volume but highest intent.
- **Phrase match** "keyword": Shows for searches that include the phrase. Good balance of control and reach.
- **Broad match** keyword: Maximum reach but least control. Only use broad match when using Smart Bidding with conversion data and a sufficient budget. Not recommended for new campaigns.

Start with Exact and Phrase match for new campaigns. Add Broad later if needed and only with Target CPA or ROAS bidding.

**Step 3: Structure ad groups**

One theme per ad group. Do not mix keywords across themes.

Example for a bookkeeping service:
- Ad Group 1: Small business bookkeeping (keywords: "bookkeeping for small business", "small business bookkeeper", etc.)
- Ad Group 2: QuickBooks setup (keywords: "QuickBooks setup service", "hire QuickBooks expert", etc.)
- Ad Group 3: Tax preparation (keywords: "small business tax prep", "CPA for small business", etc.)

Each ad group needs its own landing page that matches the ad group theme. Sending all ad groups to one generic homepage lowers Quality Score and raises CPC.

**Step 4: Set the bidding strategy**

- New campaign with no conversion data: Start with Manual CPC or Enhanced CPC to gather data without overpaying.
- Once 30-50 conversions in 30 days: Switch to Target CPA (set the target at 1.5x your actual conversion cost to start, then tighten).
- Once scaling: Target ROAS if purchase data is available.

Do not start with Target CPA or ROAS on a new campaign. Google needs data before Smart Bidding works.

**Step 5: Plan the negative keyword list**

Negative keywords exclude irrelevant searches before the campaign launches. Catch these early or waste budget.

Standard negative keyword categories:
- Informational intent: "how to", "what is", "free", "DIY", "learn"
- Job seekers: "jobs", "careers", "job posting", "salary"
- Competitor brand names (unless running competitor campaigns intentionally)
- Irrelevant industries if keywords are broad

Build the negative keyword list before launch. Add to it weekly based on the Search Terms report.

**Step 6: Write the ad copy direction**

Google Search uses Responsive Search Ads (RSAs). Each RSA has up to 15 headlines (30 char max each) and 4 descriptions (90 char max each). Google mixes and matches.

Write headlines in three categories:
1. **Keyword-aligned** (2-3): Include the main keyword for relevance ("Small Business Bookkeeping")
2. **Benefit-focused** (4-5): Specific outcomes ("Files Quarterly Taxes For You", "Save 5 Hours Per Month")
3. **Trust/differentiators** (3-4): Social proof or differentiators ("100+ Business Clients Served", "Local CPA, Available Same Day")

Write descriptions to reinforce the CTA and handle the top objection. Each description should stand alone if shown with any headline combination.

## Output Format

```
GOOGLE ADS STRATEGY - [Client/Offer] - [Date]

CAMPAIGN TYPE: [Search / PMax / Shopping / Display]
CONVERSION GOAL: [Form submission / Phone call / Purchase]
BUDGET: $[X]/day
GEOGRAPHY: [City, State, Country, or Radius]

---

CAMPAIGN STRUCTURE:

Campaign: [Name - see campaign-structure.md naming convention]
  Bid strategy: [Manual CPC / ECPC / Target CPA $[X] / Target ROAS [X]%]
  Daily budget: $[X]

  AD GROUP 1: [Theme name]
    Keywords:
      [keyword] - [Exact / Phrase]
      [keyword] - [Exact / Phrase]
    Landing page: [URL]

  AD GROUP 2: [Theme name]
    [Same format]

  AD GROUP 3: [Theme name]
    [Same format]

---

KEYWORD STRATEGY:
Primary keywords (highest priority): [List]
Secondary keywords: [List]
Negative keywords (pre-launch list): [List by category]

---

AD COPY DIRECTION:

Ad Group 1 - RSA Headlines:
  Keyword-aligned: [H1], [H2]
  Benefit: [H3], [H4], [H5]
  Trust: [H6], [H7]

Descriptions:
  [D1 - primary benefit + CTA]
  [D2 - objection handler or differentiator]

[Repeat per ad group]

---

BIDDING NOTES:
Start with: [Manual CPC / ECPC]
Switch to Smart Bidding when: [30-50 conversions in 30 days]
Target CPA (starting): $[X]
CPA tighten threshold: [when hitting 30-50 conversions/month at target]

---

QUALITY SCORE SETUP:
Ad group to landing page relevance: [Confirmed / Needs [X] page created]
```

## Quality Check

- [ ] Campaign type matches the conversion goal and budget level
- [ ] One theme per ad group, matching keywords to matching landing page
- [ ] Negative keyword list built before launch
- [ ] Bidding starts with manual or ECPC, not Smart Bidding
- [ ] RSA headlines cover all three categories (keyword, benefit, trust)
- [ ] Each ad group has a dedicated or relevant landing page (not homepage)
- [ ] Geographic targeting is confirmed

## Status

Phase 3 complete.
