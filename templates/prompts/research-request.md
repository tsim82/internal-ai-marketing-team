# Prompt: Market Research Request

Use this prompt to kick off a market research session before writing copy, building a campaign, or entering a new niche.

---

## When to Use

- Before writing the first ad copy for a new offer or audience
- When entering a new niche or market for the first time
- When copy is not converting and you need new angles
- When a client wants to understand their competitive landscape

---

## The Prompt (Full Research)

```
@market-research-agent

Market research for [Client name / Niche].

Business context: [What the client does and who they serve]
Offer: [What we're selling]
Audience: [Specific description of who we're targeting]

Research needed:
1. Audience research (skills/research/audience-research.md) - who they are, what they want, what they fear, what has failed them
2. Hook research (skills/research/hook-research.md) - what angles are working in this space
3. Objection research (skills/research/objection-research.md) - what is stopping people from buying

Deliver:
- Audience profile with psychographic details and exact language they use
- Top 5 hook angles with rationale for each
- Top 5 objections with suggested copy responses
- Any competitor patterns worth noting

This research will be used by the Copywriter to write the first ad copy and landing page.
```

---

## The Prompt (Targeted Research)

```
@market-research-agent

Quick research task: [Describe the specific thing you need]

Context: [Client, niche, offer]

Output needed:
- [Specific deliverable]
- [Specific deliverable]

This will be used by: [which agent will use this and for what]
```

---

## The Prompt (Competitor Ad Research via Apify)

```
@market-research-agent

Competitor ad research for [niche / keyword].

Pull competitor ads from the Meta Ad Library for:
- Keyword or niche: [describe]
- Geographic focus: [US only / specific region / global]
- Ad types: [all / video only / image only]

Deliver:
- Summary of the most common angles and hooks in this space
- Examples of copy patterns that appear frequently (likely working)
- Gaps or angles that are not being used (opportunity)
- Top 3 hooks worth testing adapted for our offer
```

---

## What Happens Next

The Market Research Agent will:
1. Run the requested research skills
2. Use Apify (if connected) to pull live ad data
3. Synthesize findings into a usable summary
4. Return the output in a format the Copywriter can act on immediately

---

## Notes

- Always run research before writing copy for a new offer, even if the niche seems familiar
- Research findings can be saved to knowledge-base/ for future use - ask the agent to store them if they should persist
- If Apify is not connected, the agent will use manual research methods from the skill file
