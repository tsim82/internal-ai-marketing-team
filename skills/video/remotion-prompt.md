# Remotion Prompt

## Purpose

Produce a structured brief for animated video content created with Remotion (or similar code-based animation tools). Remotion generates programmatic video from React components. The output is a content brief that a developer or AI coding assistant uses to produce the animation. This skill covers data visualization videos, motion graphic explainers, stat callouts, and animated social content.

## Used By

- Video Agent (primary)
- Creative Design Agent (visual direction reference)

## Trigger

Use when a video asset needs to be animated programmatically: stat callout videos, animated frameworks, data visualizations, motion graphic social content, or animated lower thirds.

## Inputs Needed

- Content to animate (stats, copy, framework, chart) - required
- Video dimensions and format (vertical 9:16, square 1:1, horizontal 16:9) - required
- Duration target - required
- Brand colors, fonts, and visual style - required
- Purpose (social post, ad overlay, VSL section, explainer) - required

## Process

**Step 1: Define the animation type**

| Type | What it is | When to use |
|------|-----------|-------------|
| Stat callout | A key number or metric animated in with emphasis | When a data point needs to stand alone |
| Framework reveal | A step-by-step process revealed sequentially | Explaining a process or system |
| Data chart animation | A bar chart, line graph, or funnel animated in | When showing growth, comparison, or funnel data |
| Text motion graphic | Bold text that appears and animates with rhythm | Short-form hooks, quote overlays |
| Animated lower third | Name, title, or label that appears over video | When overlaying on talking head video |
| Full explainer | Multi-scene animation with icons, paths, and voiceover sync | For 30-120 second animated explainers |

**Step 2: Plan the scenes**

For each animation, break it into scenes or moments:
- Scene 1: What appears first
- Scene 2: What transitions in next
- Final state: What the viewer sees when the animation completes

**Step 3: Specify the visual elements**

For each element that appears in the animation:
- Text content (exact copy)
- Position (center, left, bottom, etc.)
- Entry animation (fade in, slide in from left, scale up, etc.)
- Timing (at what second does it appear?)
- Exit animation (fade out, hold until video ends, etc.)
- Style (color, font, size)

**Step 4: Define the timing**

Map every element to a timeline in seconds:

```
0.0s: Background appears
0.5s: Logo fades in (top left)
1.0s: Main stat number counts up from 0 to 47
2.0s: Label "Leads Generated" slides in below the number
3.0s: Supporting line fades in: "In 30 Days"
4.0s: Hold
5.0s: Fade out
```

**Step 5: Write the Remotion component brief**

The brief tells a developer (or AI coding assistant) what components to build.

## Output Format

```
REMOTION PROMPT - [Client/Asset Name] - [Date]

ANIMATION TYPE: [Stat callout / Framework reveal / Chart / Text motion / Lower third / Explainer]
DIMENSIONS: [1080x1920 (9:16 vertical) / 1080x1080 (1:1) / 1920x1080 (16:9)]
DURATION: [X seconds]
FRAME RATE: [30 fps]
PURPOSE: [Social post / Ad overlay / VSL section / Explainer]

---

BRAND SPECS:
  Primary color: [Hex code]
  Secondary color: [Hex code]
  Background: [Hex code or gradient]
  Font (heading): [Font name or fallback]
  Font (body): [Font name or fallback]

---

SCENE BREAKDOWN:

SCENE 1 - [Scene name]
  Duration: [0:00-0:XX]
  Background: [Color / gradient / image]
  Elements:
    Element 1:
      Type: [Text / Icon / Shape / Logo]
      Content: "[Exact text or description]"
      Position: [Center / Top left / Bottom right / etc.]
      Entry: [Fade in at Xs / Slide from left at Xs / Scale up at Xs]
      Exit: [Hold / Fade out at Xs]
      Style: [Color, size, weight]
    
    Element 2:
      [Same format]

SCENE 2 - [Scene name]
  [Same format]

---

FULL TIMELINE:

| Time | Element | Action |
|------|---------|--------|
| 0.0s | Background | Appears |
| 0.5s | [Element] | [Entry animation] |
| 1.0s | [Element] | [Entry animation] |
| [X]s | [Element] | [Exit / hold] |
| [Duration]s | All elements | Fade out or hold to end |

---

DEVELOPER/AI NOTES:
Animation style: [Smooth and clean / Bold and fast / Minimal / Dynamic]
Easing: [Ease in-out / Spring / Linear]
Audio sync needed: [Yes - sync to voiceover at timestamps listed / No]
Key emphasis moment: [The most important visual moment in the animation - timestamp and what should look most prominent]
```

## Quality Check

- [ ] Dimensions and duration are specified
- [ ] Brand colors and fonts are documented
- [ ] Every element has an exact entry time, position, and animation direction
- [ ] Full timeline is documented
- [ ] Brief is specific enough for a developer or AI coding tool to produce without follow-up

## Status

Phase 3 complete.
