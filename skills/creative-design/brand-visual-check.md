# Brand Visual Check

## Purpose

Audit a set of creative assets for visual brand consistency. When ads, social posts, and organic content all look different from each other, the brand loses recognition and trust. This check identifies what is off-brand before assets go live and produces a specific list of fixes. The output is a report with [PASS] or [FLAG] per element.

## Used By

- Creative Design Agent (primary)
- QA Agent (runs before handoff to client)
- Marketing Director (reviews when creative inconsistency is flagged)

## Trigger

Use when a new set of creative assets is ready for launch, when a new designer produces work and brand consistency needs to be confirmed, or when multiple pieces of content are going live across platforms and the team needs to confirm they look cohesive.

## Inputs Needed

- Brand visual guidelines document or brand kit - required
- All assets to be reviewed (images, ad creatives, social post graphics) - required
- Platform destinations for each asset - required

## Process

**Step 1: Confirm the brand visual baseline**

Before checking assets, confirm the current approved brand standards:

| Element | Brand standard |
|---------|---------------|
| Primary color | [Hex code] |
| Secondary color | [Hex code] |
| Accent color | [Hex code] |
| Background color | [Hex code] |
| Heading font | [Font name] |
| Body font | [Font name] |
| Logo file | [Which version: full color / white / dark] |
| Logo minimum size | [X px] |
| Logo clear space | [X px on all sides] |
| Image style | [Photography style or illustration style description] |

**Step 2: Run the audit on each asset**

For each asset, check the following elements:

| Check | What to look for |
|-------|----------------|
| Color palette | Are only brand-approved colors used? Any off-brand colors? |
| Font hierarchy | Is the heading font correct? Body font? No random fonts introduced? |
| Logo placement | Is the logo present where required? Correct placement and size? |
| Image/photo style | Does the image style match the brand aesthetic (lighting, subject, mood)? |
| Text contrast | Is text readable against the background? (Min 4.5:1 contrast ratio for body text) |
| Spacing and margins | Are margins consistent? Does the design feel balanced? |
| Ad-specific rules | Does the text stay within safe zones? Any text in first/last 10% of video? |
| Platform dimensions | Are dimensions correct for the platform and placement? |

**Step 3: Mark each element as PASS or FLAG**

PASS: The element meets the brand standard.
FLAG: The element is off-brand and needs to be corrected. Describe specifically what is wrong and what the correct version should be.

**Step 4: Write the summary verdict**

After reviewing all assets:
- **APPROVED**: All elements pass. Asset is ready to publish or launch.
- **MINOR REVISIONS**: 1-2 small fixes needed before launch.
- **SIGNIFICANT REVISIONS**: Multiple or critical items flagged. Return to designer before proceeding.
- **REJECT**: Asset does not meet brand standards and needs to be rebuilt.

**Step 5: Provide specific fix instructions**

For every FLAG, write one sentence describing exactly what to fix and how:
"Flag: Heading font is Helvetica but brand standard is [Font Name]. Replace with [Font Name] at the same size and weight."

## Output Format

```
BRAND VISUAL CHECK - [Client] - [Asset Set] - [Date]

ASSETS REVIEWED: [List all assets - ad creatives, social posts, thumbnails]
BRAND KIT REFERENCE: [File or location of brand guidelines]
REVIEWER: Creative Design Agent

---

BRAND BASELINE (confirmed):
  Primary color: [Hex]
  Secondary color: [Hex]
  Heading font: [Name]
  Body font: [Name]
  Image style: [Description]

---

ASSET-BY-ASSET REVIEW:

ASSET 1: [Name / Description]
  Platform: [Meta Feed / Instagram Reel / LinkedIn / etc.]
  Dimensions: [Correct WxH]

  | Element | Status | Notes |
  |---------|--------|-------|
  | Color palette | [PASS / FLAG] | [If FLAG: what is wrong and what should it be] |
  | Font hierarchy | [PASS / FLAG] | [...] |
  | Logo placement | [PASS / FLAG] | [...] |
  | Image/photo style | [PASS / FLAG] | [...] |
  | Text contrast | [PASS / FLAG] | [...] |
  | Spacing | [PASS / FLAG] | [...] |
  | Dimensions | [PASS / FLAG] | [...] |
  | Other: [Custom rule] | [PASS / FLAG] | [...] |

  Asset verdict: [APPROVED / MINOR REVISIONS / SIGNIFICANT REVISIONS / REJECT]

ASSET 2: [Name / Description]
  [Same format]

[Continue for all assets]

---

OVERALL VERDICT: [APPROVED / MINOR REVISIONS / SIGNIFICANT REVISIONS / REJECT]

FIXES REQUIRED (all FLAGs consolidated):

1. [Asset name]: [Specific fix instruction]
2. [Asset name]: [Specific fix instruction]
[Continue]

APPROVED ASSETS (no changes needed):
[List assets that passed completely]

NOTES:
[Any patterns observed - e.g., "three different designers seem to be using different blue values - recommend setting up a shared color palette file"]
```

## Quality Check

- [ ] Brand baseline is confirmed before reviewing any assets
- [ ] Every element is checked for every asset
- [ ] Every FLAG has a specific fix instruction (not just "wrong color")
- [ ] Overall verdict is clear
- [ ] Fixes are listed consolidated so the designer has one list to work from

## Status

Phase 3 complete.
