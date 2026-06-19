# /ad-order

## What It Does

This skill generates a structured ad order document for a client. It pulls client info from your CRM, walks you through campaign parameters, builds targeting briefs, generates creative briefs for each ad, and allocates budget across the campaign timeline.

The output is a complete ad order document that your team can execute against - every ad scripted, targeted, and budgeted.

---

## When to Use It

- When a client approves a new campaign and you need to plan the ads
- When preparing a batch of creatives for a filming session
- When presenting a campaign plan to a client for approval
- When briefing your team on what to build

---

## How to Run It

```
/ad-order
```

Claude handles everything automatically:

1. Searches Airtable for the client
2. Defines campaign parameters (goal, budget, formats, platforms, duration)
3. Builds targeting brief
4. Generates creative briefs (one per ad - angle, format, hook, body, CTA, visual direction)
5. Allocates budget across weeks
6. Saves the complete ad order document
7. Creates Airtable record (optional)

---

## Example Output

```
# Ad Order: D1 Training - March 2026 Campaign

## Client
D1 Training Plano | Budget: $1,500/mo | Goal: Trial session signups

## Campaign Overview
- Duration: 4 weeks (March 4 - March 31)
- Platform: Instagram + Facebook
- Formats: Video (UGC), Static image
- Total ads: 4

## Targeting
- Location: 15mi radius of Plano, TX
- Age: 28-50 | Gender: All
- Interests: Youth sports, kids activities, parenting
- Custom: Website visitors (retargeting)

## Creative Briefs

### Ad 1: Parent Testimonial (UGC Video)
- Angle: Transformation
- Hook: "My son went from benchwarmer to starter in 8 weeks"
- Body: Parent tells story of transformation
- CTA: "Book a free trial session"
- Visual: Parent talking to camera, B-roll of kid training

### Ad 2: Before/After Montage (Video)
- Angle: Social Proof
- Hook: "What 8 weeks of speed training looks like"
- Body: Side-by-side training footage
- CTA: "Free trial this week"
- Visual: Split screen before/after clips

[... Ad 3, Ad 4 ...]

## Budget Allocation
| Week | Spend | Focus |
|------|-------|-------|
| Week 1 | $300 | Testing all 4 ads |
| Week 2 | $375 | Kill losers, scale winners |
| Week 3 | $400 | Scale top 2 ads |
| Week 4 | $425 | Maximize winners |
```

---

## Requirements

- **Claude Code** - installed and running
- **Airtable MCP** - for client lookup and order storage (included in Premium toolkit)

---

## Download

This skill is included in the Premium toolkit. After running the installer, the file lives at:

```
~/.claude/skills/ad-order/SKILL.md
```

If you haven't downloaded the toolkit yet, head to **#Start Here** and complete the **Download ALL Resources** lesson.

---

## Part of the Ad System

```
/ad-brief → /ad-order → /script-ads → /launch-ads
```

- **`/ad-brief`** - competitive intelligence to inform strategy
- **`/ad-order`** - the campaign plan document
- **`/script-ads`** - detailed scripts for each creative

---

## Troubleshooting

**"Client not found in Airtable"**
Run `/onboard` first, or manually add the client to your CRM table.

**"Budget allocation doesn't match total"**
The skill auto-adjusts weekly allocation to match total budget. If the math looks off, specify your preferred weekly split manually.

---

## Changelog

- **v1.0** - Client CRM lookup, campaign parameter builder, targeting briefs, creative briefs per ad, weekly budget allocation, Airtable integration.
