# Lead Qualification

## Purpose

Define the qualification criteria for a specific client's leads, produce a scoring system, and document the questions or data points used to qualify. The output is the qualification framework the CRM Follow-Up Agent uses to decide which leads to prioritize, which to put in long-term nurture, and which to disqualify.

## Used By

- CRM Follow-Up Agent (primary)
- Analytics Agent (tracks qualification rates)
- Marketing Director (reviews if lead quality is a concern)

## Trigger

Use when setting up a new client, when close rates are low and the suspected cause is unqualified leads on calls, or when the team does not have a consistent way to determine who is a good lead.

## Inputs Needed

- Offer and ideal client description - required
- Price point and buyer capacity - required
- Geographic requirements (if local service) - helpful
- Business-specific qualification requirements - required
- Any disqualification criteria from the client - helpful

## Process

**Step 1: Define the ideal client profile**

Before scoring, write out who is an ideal client for this offer:
- What situation are they in?
- What resources do they have (budget, team, time)?
- What outcome are they trying to achieve?
- What would make them a bad fit?

**Step 2: Build the BANT-adjacent qualification criteria**

Use four qualification dimensions:

| Dimension | Question to assess | Scoring |
|-----------|------------------|---------| 
| **Budget** | Do they have the budget or can realistically access it? | 1 point if yes |
| **Authority** | Can they make the buying decision, or do they need approval? | 1 point if decision-maker |
| **Need** | Do they have the problem this offer solves? | 1 point if yes |
| **Timeline** | Are they ready to act in the next 30 days? | 1 point if yes |

Scoring thresholds:
- 4/4: High priority lead. Fast-track to call booking.
- 3/4: Medium priority. Nurture with urgency.
- 2/4 or below: Long-term nurture or disqualify.

**Step 3: Write the qualification questions**

For each dimension, write the specific question(s) to ask in conversation:

Budget:
"Roughly, what's your monthly budget for [category of solution]?" or "[Offer price] is the investment for our program - is that in the range you're considering?"

Authority:
"Is it just you making this decision, or do you need to loop in a partner/team?" or "If this feels like a good fit on the call, is there anything stopping you from getting started?"

Need:
"What's the main thing you're trying to solve?" + confirm that it matches what the offer addresses

Timeline:
"Are you looking to solve this in the next 30-60 days, or is this more of a 3-6 month conversation?"

**Step 4: Define how qualification data is captured**

Where and how does the team capture qualification info?
- Application form (before the call): capture BANT data upfront
- SMS conversation: ask qualifying questions via text
- Sales call: qualify during discovery phase
- CRM tag: tag the lead with their score after qualification

**Step 5: Define what happens at each score level**

| Score | Pipeline action |
|-------|---------------|
| 4/4 | Fast-track to call booking, high-priority in queue |
| 3/4 | Standard follow-up sequence, book call |
| 2/4 | Long-term nurture sequence, monthly touchpoints |
| 1/4 or below | Disqualify (unless there is a compelling reason to keep) |

## Output Format

```
LEAD QUALIFICATION FRAMEWORK - [Client/Offer] - [Date]

OFFER: [Name and price]
IDEAL CLIENT: [One paragraph description of who this offer is for]

---

QUALIFICATION DIMENSIONS:

BUDGET
  Qualifying criteria: [What budget level qualifies? Be specific.]
  How to assess: [Form question / SMS question / Call question]
  Qualifying answer: [What they must say or indicate to get 1 point]
  Disqualifying answer: [What signals they cannot afford it]

AUTHORITY
  Qualifying criteria: [Who must they be - sole decision maker, one of two, etc.]
  How to assess: [Form question / conversation question]
  Qualifying answer: [What indicates they can buy without extra approval]
  If not decision-maker: [Do not disqualify - ask if the other decision-maker can be on the call]

NEED
  Qualifying criteria: [What problem must they have?]
  How to assess: [What they said on the form / what they say in conversation]
  Qualifying answer: [Specific problem they must name or indicate]
  Disqualifying answer: [Problem that this offer does not solve]

TIMELINE
  Qualifying criteria: [Ready to act in the next 30 days?]
  How to assess: [Form question or conversation]
  Qualifying answer: [30 days or sooner]
  If timeline is 3+ months: [Long-term nurture, not disqualify]

---

SCORING AND ROUTING:

| Score | Priority | Action |
|-------|---------|--------|
| 4/4 | High | Fast-track to call booking, tag: "Qualified-High" |
| 3/4 | Medium | Standard nurture, tag: "Qualified-Medium", book call |
| 2/4 | Low | Long-term nurture tag: "Long-Term-Nurture", monthly touchpoints |
| 1/4 or 0/4 | None | Disqualify, tag: "Disqualified", close stage |

---

QUALIFICATION QUESTIONS (for conversation or form):

[For SMS or call]
1. "What's the main thing you're trying to solve right now?"
2. "Is this something you're looking to tackle in the next month or so?"
3. "[Offer price] is the investment - is that in the range you're working with?"
4. "Is it just you making this call, or do you have a partner/co-founder involved?"

[Form version - shorter]
1. "What's your biggest challenge with [topic]?" (Open text)
2. "What's your monthly revenue / team size / budget?" (Depends on offer)
3. "When are you looking to solve this?" (Dropdown: Now / 1-3 months / 3-6 months / Just exploring)

---

GHL TAGS FOR QUALIFICATION:
  Qualified-High: [4/4 score]
  Qualified-Medium: [3/4 score]
  Long-Term-Nurture: [2/4 score]
  Disqualified: [1/4 or 0/4]
```

## Quality Check

- [ ] All four BANT dimensions are defined with specific qualifying criteria
- [ ] Scoring thresholds are set (4/4, 3/4, 2/4, below)
- [ ] Each score level has a defined pipeline action
- [ ] Qualification questions are written for both form and conversation
- [ ] GHL tags are defined for each score level
- [ ] Disqualification criteria is explicit (not just "low score" - specific disqualifying conditions)

## Status

Phase 3 complete.
