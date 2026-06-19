# Ad Creative Brief

## Purpose

Produce a complete creative brief for a paid ad image or video creative. The brief tells a designer, AI image tool, or video producer exactly what to make without requiring a follow-up conversation. A brief that requires back-and-forth is not complete. The output is one brief per creative concept.

## Used By

- Creative Design Agent (primary)
- Paid Ads Agent (commissions the brief based on campaign needs)
- Copywriter (provides headline and copy for the creative)

## Trigger

Use when a new ad creative needs to be made, when the creative testing plan calls for a new concept, or when existing creatives are fatiguing and new assets need to be briefed.

## Inputs Needed

- Ad copy (headline, primary text, and CTA from Copywriter) - required
- Platform and placement - required
- Campaign goal (lead gen, purchase, awareness) - required
- Creative testing plan (what concept/variable is being tested) - required
- Brand visual guidelines (colors, fonts, style direction) - required
- Reference examples (if any) - helpful

## Process

**Step 1: Confirm the creative concept**

Every ad creative has a concept - the central idea that makes it work visually and emotionally. The concept should match the copy angle.

Common ad creative concepts:
| Concept | What it shows | Best for |
|---------|--------------|---------|
| Pain moment | Someone experiencing the problem the ad solves | Cold traffic, problem-aware audiences |
| Result moment | Someone experiencing the solution's outcome | Warm traffic, proof-based angles |
| Plain/direct | Product or offer against a simple background, headline prominent | Offer-aware audiences, retargeting |
| Social proof | Client result, testimonial text, or star ratings | All traffic levels |
| Pattern interrupt | Something visually unexpected that stops the scroll | Cold traffic, saturated markets |
| UGC-style | Feels authentic and person-filmed, not polished | Cold traffic, trust-building |

**Step 2: Define the format and dimensions**

| Platform | Placement | Dimensions | Format |
|---------|----------|-----------|--------|
| Meta | Feed (Facebook + Instagram) | 1080x1080 | Square - static or video |
| Meta | Stories / Reels | 1080x1920 | Vertical - static or video |
| Meta | Feed landscape | 1200x628 | Landscape - static |
| Google | Display | 1200x628 and 300x250 | Multiple sizes |
| YouTube | In-stream | 1920x1080 | 16:9 horizontal video |

**Step 3: Define the visual components**

Every creative has elements that must be specified:
- **Background/scene**: What is behind the main subject?
- **Main subject**: What or who is the center of attention?
- **Headline placement**: Where does text appear and what does it say?
- **Copy overlay**: Is there additional text on the creative beyond the headline?
- **Logo placement**: Where and how prominent?
- **Mood/lighting**: Warm? Cool? High contrast? Natural?
- **What to avoid**: Any visual direction on what not to include

**Step 4: Write the image prompt (if using AI generation)**

If the creative is being generated with an AI image tool (Midjourney, Dall-E, Firefly, etc.):

Prompt structure:
`[Subject doing action], [setting/background], [lighting], [mood], [camera angle], [style reference], [negative prompts]`

Example: "A service business owner looking at a phone notification showing a new lead, sitting at a clean modern desk, natural window light, expression of relief and excitement, eye-level close-up portrait, cinematic realistic style, no text, no stock photo look"

## Output Format

```
AD CREATIVE BRIEF - [Client/Campaign] - [Date]

CREATIVE CONCEPT: [One sentence describing the central idea]
COPY ANGLE: [Pain / Proof / Curiosity / Direct / Social proof]
TESTING VARIABLE: [What this creative is testing per the creative testing plan]

---

FORMAT:
  Platform: [Meta / Google / YouTube]
  Placement: [Feed / Stories / Display / In-stream]
  Dimensions: [WxH]
  Creative type: [Static image / Video / Carousel - first slide]

---

COPY (from Copywriter):
  Headline: "[Text - max 40 chars for Meta]"
  Primary text: "[First 125 chars that appear without truncation]"
  CTA button: "[Button text]"

---

VISUAL BRIEF:

Concept: [One sentence]
Background: [What is behind the main subject]
Main subject: [Who or what, doing what]
Text overlay: [Yes - "overlay text here" / No]
  Text position: [Top / Center / Bottom / Lower third]
  Text style: [Bold, large / Smaller supporting text]
Logo: [Placement and size - bottom right, small / Top left / None]
Mood: [Warm and aspirational / Bold and direct / Clean and minimal / Candid and real]
Lighting: [Natural / Studio / High contrast / Warm]
What to AVOID: [Specific directions on what not to include]

---

AI IMAGE PROMPT (if generating with AI):
"[Full prompt following the structure: subject + setting + lighting + mood + angle + style + negatives]"

---

REFERENCE:
[Link or description of any reference image or example to guide the direction]

---

CREATIVE TESTING NOTES:
This creative tests: [Variable - format / concept / color / copy placement]
Control: [What it is being compared against]
Named: [Ad name per the naming convention - e.g., Pain-Static-Hook1]
```

## Quality Check

- [ ] Creative concept is specific (not "an ad about our service")
- [ ] Dimensions are correct for the platform and placement
- [ ] Copy is included in the brief (from Copywriter output)
- [ ] Every visual element is specified
- [ ] Text overlay is either written out or marked as "None"
- [ ] What to avoid is included
- [ ] AI prompt is written if AI generation is being used
- [ ] Creative name follows the naming convention

## Status

Phase 3 complete.
