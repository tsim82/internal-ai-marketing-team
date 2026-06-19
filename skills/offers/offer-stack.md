# Offer Stack

## Purpose

Build a value stack that makes the offer's price feel like a steal. The value stack lists every component of the offer with an individual value assigned to each, totaling to an amount significantly higher than the asking price. The output is what the Copywriter uses in VSL, landing page, and sales material copy.

## Used By

- Offer Agent (builds the stack)
- Copywriter (formats and writes the copy from the stack)
- Marketing Director (reviews for believability)
- QA Agent (checks that values are credible)

## Trigger

Use when completing an offer buildout, when existing copy does not include a value stack, or when the current value stack feels weak or unbelievable.

## Inputs Needed

- Completed offer buildout (offer-buildout.md) - required
- Offer price - required
- All included deliverables - required
- Any bonuses being added - helpful
- Competitor or alternative pricing for comparable components - helpful

## Process

**Step 1: List every component of the offer separately**

Do not list the whole offer as one item. Break it into every meaningful component. Each component will get its own value line.

Example for a lead generation service:
- Not: "Full lead gen service - $5,000/month value"
- Yes: Each component listed and valued separately

**Step 2: Assign a believable value to each component**

This is the most important and most commonly mishandled part of a value stack. Values must be defensible.

Three ways to assign value:
1. **Market rate**: What would it cost to hire someone to do this specifically? "Done-for-you ad copy: $500/month (agency rate for copy-only retainer)"
2. **Outcome value**: What is this component worth in outcomes? Only use if the outcome is clearly tied to this component. "Analytics report that identifies the leaking stage of your funnel - average fix increases booked calls by 20%"
3. **Competitor comparison**: What does a competitor charge for just this piece? Must be a real comparison, not fabricated.

Do not assign arbitrary values with no rationale. QA Agent will flag inflated values.

Values should be honest enough that the buyer could independently check them and agree.

**Step 3: Add bonuses**

Bonuses increase the perceived value of the stack and lower the barrier to saying yes. Strong bonuses:
- Solve a secondary problem related to the main offer
- Have a believable standalone value
- Are genuinely useful, not padding

Weak bonuses: generic templates, ebooks with no specificity, vague "access" to things.

**Step 4: Build the total value calculation**

```
Component 1: [Name] - $[X] value
Component 2: [Name] - $[X] value
Component 3: [Name] - $[X] value
[Bonuses if applicable]
TOTAL VALUE: $[X]
YOUR PRICE TODAY: $[X]
```

The total value should be at least 3-5x the asking price for the stack to create impact. If it is only 2x, the stack is not compelling.

**Step 5: Write the stack copy direction**

The Copywriter will use the stack list but also needs copy direction for how to introduce and close each component.

For each component:
- Name: what the Copywriter should call it in copy
- Value copy: one line explaining why it is worth that amount
- Outcome connection: what problem it solves or result it produces

## Output Format

```
OFFER STACK - [Client/Offer Name] - [Date]

OFFER PRICE: $[X]

---

VALUE STACK:

CORE COMPONENTS:

1. [Component Name]
   Value: $[X]
   What it is: [Plain description]
   Why it is worth this: [Market rate source / outcome connection / competitor comparison]
   Outcome: [What buyer gets from this component]

2. [Component Name]
   [Same format]

3. [Continue for all components]

BONUSES:

Bonus 1: [Name]
   Value: $[X]
   What it is: [Plain description]
   Why it is worth this: [Rationale]
   Why it is included: [What secondary problem it solves]

Bonus 2: [Same format]

---

TOTAL VALUE CALCULATION:

Core components: $[X]
Bonuses: $[X]
TOTAL STACK VALUE: $[X]
YOUR PRICE: $[X]
VALUE-TO-PRICE RATIO: [X]x

---

COPY DIRECTION FOR COPYWRITER:
Stack introduction line: "Here's everything you get when you join [Offer Name]:"
Stack close line: "Total value: $[X]. Your investment: just $[X]."
Best component to lead with: [Name - the most impressive or tangible item]
Weakest component to bury: [Name - least differentiated item]
```

## Quality Check

- [ ] Every component has a specific, defensible value with a rationale (not a made-up number)
- [ ] Total stack value is at least 3x the offer price
- [ ] Bonuses solve real secondary problems, not padding
- [ ] QA Agent reviews the values for credibility before any copy goes to market
- [ ] Copy direction is included for the Copywriter

## Status

Phase 3 complete.
