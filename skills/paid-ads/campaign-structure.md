# Campaign Structure

## Purpose

Document the complete structural plan for any paid campaign across Meta, Google, or other platforms. The structure defines campaigns, ad sets or ad groups, ads, naming conventions, and the logic behind every organizational decision. The output is what the Paid Ads Agent uses to build the campaign in the platform and what the Analytics Agent uses to read reports accurately.

## Used By

- Paid Ads Agent (primary)
- Analytics Agent (reads reports against this structure)
- Marketing Director (reviews for strategic alignment)

## Trigger

Use when launching a new campaign, restructuring an existing one, or when reporting is confusing because naming and structure are inconsistent.

## Inputs Needed

- Platform (Meta, Google, or other) - required
- Campaign goal (lead gen, purchase, awareness, etc.) - required
- Budget and duration - required
- Audience data available (custom lists, pixel data, interest groups) - required
- Number of offers or products being promoted - required
- Creative assets available (how many ads and in what formats) - helpful

## Process

**Step 1: One campaign per goal**
Each campaign should have exactly one goal and one objective. Do not mix lead gen and purchase campaigns. Do not mix cold traffic and retargeting under the same campaign.

One campaign = one goal = one objective = one budget optimization level.

**Step 2: Ad set level = audience and placement**
Each ad set represents a distinct audience or placement combination. Do not mix audiences within an ad set. The ad set level is where you control:
- Who sees the ads (audience)
- Where they see them (placement)
- How much is spent on that audience

**Step 3: Ad level = creative and copy variation**
Each ad within an ad set is a unique creative/copy combination. The ad level is where testing happens. 3-5 ads per ad set is standard for most campaigns.

**Step 4: Document the structure in a hierarchy**

```
Campaign (Goal/Objective/Budget)
├── Ad Set 1 (Audience A)
│   ├── Ad 1a (Creative A + Copy A)
│   ├── Ad 1b (Creative B + Copy A)
│   └── Ad 1c (Creative A + Copy B)
├── Ad Set 2 (Audience B)
│   ├── Ad 2a
│   └── Ad 2b
└── Ad Set 3 (Audience C)
    └── [...]
```

**Step 5: Apply the naming convention**
Names must be decodable by anyone on the team reading a report without a legend.

**Meta:**
```
Campaign: [Client]-[Offer]-[Objective]-[YYYY-MM]
Ad Set: [AudienceType]-[AudienceDescription]-[Size or Window]
Ad: [HookType]-[CreativeFormat]-[Angle]
```

**Google:**
```
Campaign: [Client]-[Offer]-[MatchType]-[YYYY-MM]
Ad Group: [ThemeOrKeywordGroup]
Ad: [HeadlineTheme]-[Description Variant]
```

**Step 6: Document what is being tested**
Every campaign structure should have a documented testing hypothesis. What variable are we isolating? What does a winner look like?

"We are testing three audience types at TOF (Broad vs LAL 1% vs Interest). A winning audience is defined as CPL below $X with at least 10 leads generated."

## Output Format

```
CAMPAIGN STRUCTURE - [Client/Offer] - [Date]

Platform: [Meta / Google / Other]
Goal: [Lead gen / Purchase / Awareness]
Duration: [Start date to end date or ongoing]
Total budget: $[X]/day or $[X]/month

---

CAMPAIGN HIERARCHY:

CAMPAIGN 1: [Name per convention]
  Objective: [Leads / Conversions / Search / etc.]
  Budget: $[X]/day (CBO) or [see Ad Set level for ABO]

  AD SET 1: [Name per convention]
    Audience: [Full description]
    Audience size: ~[X]M
    Placement: [Auto / Manual - if manual, list placements]
    Budget: $[X]/day (if ABO) or [managed by campaign]
    
    AD 1A: [Name per convention]
      Copy: [Brief description or ref to ad copy doc]
      Creative: [Brief description or ref to creative brief]
    
    AD 1B: [Name per convention]
      [Same format]
    
    AD 1C: [Name per convention]
      [Same format]

  AD SET 2: [Name per convention]
    [Same format]

  AD SET 3: [Name per convention]
    [Same format]

---

TESTING HYPOTHESIS:
Variable being tested: [Audience / Creative / Copy / Offer]
What a winner looks like: [Metric, threshold, and timeline]
Decision point: [When and how we will call a winner and what we will do with losing variants]

---

EXCLUSIONS APPLIED:
[List all audiences excluded at campaign or ad set level]

---

NAMING CONVENTION REFERENCE:
Campaign: [Blank template]
Ad Set: [Blank template]
Ad: [Blank template]
```

## Quality Check

- [ ] One goal per campaign
- [ ] One audience type per ad set
- [ ] 3-5 ads per ad set
- [ ] Naming convention is consistent across all levels
- [ ] Testing hypothesis is documented with a clear winner definition
- [ ] Exclusions are applied and documented
- [ ] Structure matches the platform's best practices for the campaign objective

## Status

Phase 3 complete.
