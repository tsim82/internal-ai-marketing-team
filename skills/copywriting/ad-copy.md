# Ad Copy

## Purpose

Write paid ad copy for Meta (Facebook/Instagram), Google Search, and YouTube pre-roll. Produces primary text, headline, description, and hook variations for each ad format. Every output goes directly to the Paid Ads Agent and Creative Design Agent for use.

## Used By

- Copywriter (primary)
- Paid Ads Agent (uses output to set up campaigns)
- Creative Design Agent (uses headline for creative briefs)
- QA Agent (reviews before launch)

## Trigger

Use when launching a new campaign, testing new angles, replacing fatigued ad copy, or building a new creative batch.

## Inputs Needed

- Audience awareness level (cold, warm, retargeting) - required
- Offer name and primary promise - required
- Target audience profile (from Market Research Agent) - required
- Hook angles to test (from hook research or Market Research Agent) - required
- Platform and ad format (Feed, Story, Search, etc.) - required
- Brand voice rules - required
- Any fatigued angles or messages to avoid - helpful

## Process

**Step 1: Confirm the awareness level and format**
Cold audience ads lead with the problem or a curiosity hook. Warm audience ads can lead with the proof or the offer directly. Retargeting ads can be direct and specific about what they left behind. Confirm this before writing a single word.

**Step 2: Write the hook first**
The hook is the first 1-2 lines of the primary text for Meta, or the headline for Google. It determines whether anyone reads the rest.

Write 3-5 hook options per angle being tested:
- Curiosity: "The reason your ads aren't converting has nothing to do with your budget."
- Proof: "We generated 47 leads in 14 days for this roofing company. Here's how."
- Pain: "You've probably burned $3,000 or more on ads that didn't close a single deal."
- Contrarian: "Running ads to a landing page is the wrong move if your offer isn't dialed in first."
- Bold: "Most ad agencies are optimizing the wrong metric. Here's what we watch instead."

**Step 3: Write the primary text body**
For Meta feed ads, the primary text supports the hook:
- Hook (line 1-2)
- Brief agitation or expansion (1-2 sentences)
- The promise or proof (1-2 sentences)
- CTA (1 sentence)

Keep primary text under 150 words for cold traffic. Retargeting can run slightly longer.

**Step 4: Write the headline**
The Meta headline appears below the image. Direct benefit statement or amplification of the hook. Keep under 40 characters for clean display. Be specific: "Get Your First 10 Leads Free" not "Learn More."

**Step 5: Write the description**
25-30 characters. Reinforces the headline or adds a secondary benefit. Example: "No long-term contract" or "Results in 30 days or less."

**Step 6: Recommend the CTA button**
"Book Now" for high-intent. "Learn More" for cold awareness. "Sign Up" for opt-in. "Get Quote" for service businesses.

**Step 7: Write variations for testing**
Produce at minimum:
- 3 hook variations (same angle, different opening line)
- 2 angle variations (different emotional approach to the same offer)

Label each clearly for the Paid Ads Agent's testing plan.

## Output Format

```
AD COPY - [Campaign Name] - [Angle Name]
Platform: [Meta / Google / YouTube]
Format: [Feed / Story / Search / Pre-roll]
Audience: [Cold / Warm / Retargeting]
Awareness level: [Level 1-5]

---

ANGLE A: [Angle name/description]

Hook option 1: "[First 1-2 lines]"
Hook option 2: "[First 1-2 lines]"
Hook option 3: "[First 1-2 lines]"

Selected hook: Hook [1/2/3]

Primary text:
"[Hook]
[Agitation/expansion]
[Promise or proof]
[CTA line]"

Headline: "[text]" ([N] chars)
Description: "[text]" ([N] chars)
CTA button: [Learn More / Book Now / Sign Up / Get Quote]

---

ANGLE B: [Angle name/description]
[Same structure]

---

TESTING NOTES:
Variable being isolated: [Hook / Angle / Format]
Naming convention for Paid Ads Agent: [how to label in campaign]
Audience this copy is written for: [description]
```

**Google Search format:**

```
GOOGLE SEARCH AD - [Campaign]
Keyword target: "[keyword]"

Headline 1 (30 char): "[text]"
Headline 2 (30 char): "[text]"
Headline 3 (30 char): "[text]"
Description 1 (90 char): "[text]"
Description 2 (90 char): "[text]"
```

## Quality Check

- [ ] Hook is the first line - no warm-up sentences
- [ ] Primary text is under 150 words for cold traffic
- [ ] Headline is under 40 characters (count verified)
- [ ] At least 3 hook options per angle
- [ ] Awareness level reflected in tone and approach
- [ ] CTA is specific - not just "learn more" with no context
- [ ] No unsubstantiated result claims
- [ ] No em dashes, no banned words from voice-rules.md
- [ ] Variations clearly labeled for the Paid Ads Agent
- [ ] Route to Paid Ads Agent and Creative Design Agent together

## Status

Phase 3 complete.
