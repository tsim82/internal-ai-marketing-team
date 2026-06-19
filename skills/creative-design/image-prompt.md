# Image Prompt

## Purpose

Write a complete, precise prompt for AI image generation tools (Midjourney, DALL-E, Adobe Firefly, Stable Diffusion, or similar). A well-written image prompt produces a usable image on the first or second generation. A vague prompt requires 20+ iterations and often produces nothing usable. The output is a ready-to-paste prompt with optional style modifiers and negative prompts.

## Used By

- Creative Design Agent (primary)
- Video Agent (for AI-generated B-roll or thumbnail concepts)

## Trigger

Use whenever an image needs to be generated through an AI image tool rather than photographed or designed manually.

## Inputs Needed

- What the image is for (ad creative, thumbnail, social post, background) - required
- Subject and scene description (what should be in the image) - required
- Mood and tone - required
- Brand visual direction (colors, style) - required
- Platform and dimensions the image will be used in - required
- Tool being used (Midjourney, DALL-E, Firefly) - helpful (syntax differs by tool)

## Process

**Step 1: Structure the prompt in order of importance**

AI image tools weight the beginning of a prompt more heavily than the end. Put the most important elements first.

Prompt structure:
1. Subject + action (what is happening, who is doing it)
2. Setting / background (where this is)
3. Mood / emotion
4. Lighting
5. Camera angle / composition
6. Art style or photography style
7. Technical modifiers (resolution, quality)

**Step 2: Be specific about the subject**

Vague: "a business owner"
Specific: "a woman in her late 30s, business casual, confident posture, slight smile, looking at the camera"

The more specific the subject, the more consistent the results.

**Step 3: Describe what NOT to include**

Most AI image tools support negative prompts. Use them to exclude:
- Text in the image (almost always unwanted unless intentional)
- Stock photo aesthetics (fake smiling, over-posed)
- Extra limbs or distorted hands (a common AI image problem)
- Specific styles that conflict with the brand

**Step 4: Match style to the creative use**

| Use case | Style direction |
|---------|----------------|
| Ad creative (paid) | Cinematic, high-resolution, photorealistic |
| Organic social | Candid, natural, slightly imperfect |
| Thumbnail | Bold contrast, clear focal point, high saturation |
| Background/texture | Abstract, clean, minimal |
| Brand visual | Consistent with brand palette and aesthetic |

**Step 5: Add tool-specific syntax if known**

Midjourney modifiers: `--ar 16:9 --v 6 --style raw --q 2`
DALL-E: Describe in natural language without special syntax
Firefly: Describe natural language, use "Subject" and "Exclude" fields separately

## Output Format

```
IMAGE PROMPT - [Asset Name] - [Date]

TOOL: [Midjourney / DALL-E / Firefly / Stable Diffusion]
PURPOSE: [Ad creative / Thumbnail / Social post / Background]
DIMENSIONS TARGET: [WxH or aspect ratio]

---

FULL PROMPT:

"[Subject + action], [setting], [mood], [lighting], [camera angle], [style]"

Example:
"A service business owner in her late 30s reviewing a dashboard on a laptop showing rising lead metrics, modern bright home office with plants and natural light, expression of quiet satisfaction, eye-level shot, cinematic photorealistic style, clean professional aesthetic"

---

NEGATIVE PROMPT (exclude):
"text in image, watermarks, distorted hands, extra limbs, stock photo aesthetic, fake smile, heavy makeup, over-posed, blurry, low quality, anime style"

---

TOOL-SPECIFIC SYNTAX:
[Midjourney] Append: --ar [ratio] --v 6 --style raw
[DALL-E] No additional syntax needed
[Firefly] Paste prompt in main field, paste negatives in Exclude field

---

FULL PROMPT WITH SYNTAX (copy/paste ready for Midjourney):
"[Full prompt as above] --ar [ratio] --v 6 --style raw"

---

VARIATIONS TO TRY:
1. [Variation: change one element of the prompt]
2. [Variation: different angle or mood]

---

USAGE NOTES:
This image is for: [Where it will appear]
Brand color note: [Will brand colors be added in post / already in prompt / not needed]
Text overlay needed after generation: [Yes - what text / No]
```

## Quality Check

- [ ] Subject is described with specific details (not "a person")
- [ ] Setting and background are specified
- [ ] Lighting and mood are included
- [ ] Style direction matches the use case
- [ ] Negative prompt excludes text in image (unless intentional)
- [ ] Tool-specific syntax is added if known
- [ ] Prompt is copy-paste ready - no editing needed before using

## Status

Phase 3 complete.
