# HeyGen Script

## Purpose

Format a video script specifically for HeyGen AI avatar video generation. HeyGen has strict formatting requirements that differ from standard scripts. Improperly formatted scripts produce avatars that sound robotic, rush through sentences, mispronounce words, or speak without natural emphasis. This skill takes an existing script (or briefs a new one) and produces a HeyGen-ready formatted document.

## Used By

- Video Agent (primary)
- Copywriter (writes the source script, Video Agent formats for HeyGen)

## Trigger

Use when any video will be produced through HeyGen with an AI avatar rather than a real presenter. Also use when a HeyGen video sounds unnatural and needs the script fixed.

## Inputs Needed

- Source script (existing copy or briefed for this video) - required
- Video goal and audience - required
- Tone direction (professional, conversational, authoritative, warm) - required
- Avatar selection (if already chosen) - helpful
- Target video length - required

## Process

**Step 1: Apply the core HeyGen formatting rules**

These rules apply to every HeyGen script without exception:

| Rule | Why |
|------|-----|
| 15-20 words max per sentence | Longer sentences cause the avatar to rush and sound unnatural |
| No em dashes | HeyGen reads the em dash symbol aloud or pauses awkwardly |
| No ellipsis (...) | Produces unnatural pauses or gets read literally |
| No abbreviations or acronyms without writing them out | "SEO" should be "S E O" or "search engine optimization" - test both to see which sounds better |
| No symbols ($, %, &, #) - write them out | "Dollar sign" reads better as "dollars" |
| Write numbers as words when needed | "3" can sometimes read unnaturally - "three" is safer for emphasis |

**Step 2: Structure the script with [TONE] and [PAUSE] markers**

HeyGen allows basic tone direction markers. Use them at the start of sections:

```
[TONE: Conversational and warm]
[TONE: Confident and direct]
[TONE: Concerned]
[TONE: Excited]
```

Use [PAUSE] where the speaker would naturally pause in speech:
- After a strong statement the viewer should absorb
- Before a list begins
- Before a CTA

Example:
```
Most business owners make this mistake without knowing it. [PAUSE]

They focus on getting more leads. [PAUSE] When the real problem is what happens after the lead comes in.
```

**Step 3: Rewrite long sentences**

Every sentence over 20 words must be split. Take the source script and rewrite any long sentence into two shorter ones.

Before: "If you're a service business owner who's been running Facebook ads for a while but hasn't seen the results you were hoping for, this video is going to explain exactly why that's happening and what you can do about it."

After:
"You've been running Facebook ads for a while. [PAUSE] But the results haven't come through. [PAUSE] This video explains why. And what to actually do about it."

**Step 4: Test pronouncements**

If the script contains:
- Industry terms that might be mispronounced
- Brand names that are not standard English
- Acronyms

Write a pronunciation note. If an acronym should be spelled out letter by letter, write it with spaces between letters: "S E O" not "SEO".

**Step 5: Break the script into scenes**

For HeyGen, structure the script in numbered scenes. Each scene can have different:
- Avatar tone
- Background (if using HeyGen's background features)
- Pace notes

This helps if the script has multiple sections with different energy levels.

## Output Format

```
HEYGEN SCRIPT - [Client/Video Title] - [Date]

VIDEO GOAL: [What this video is for]
TARGET LENGTH: [X minutes]
AVATAR: [Selected avatar name or "TBD"]
TONE DIRECTION: [Overall tone for this video]

---

FORMATTING CONFIRMATION:
[ ] All sentences 15-20 words or fewer
[ ] No em dashes
[ ] No ellipsis
[ ] All abbreviations written out
[ ] All symbols replaced with written words
[ ] [PAUSE] markers placed at natural rest points
[ ] [TONE] markers placed at section transitions

---

HEYGEN SCRIPT:

SCENE 1

[TONE: Conversational and direct]

[Line 1 of script - 15-20 words max]

[Line 2 of script] [PAUSE]

[Continue]

---

SCENE 2

[TONE: Confident]

[Continue]

---

[Continue for all scenes]

---

PRONUNCIATION NOTES:
- [Word or acronym]: pronounce as "[pronunciation guide or phonetic spelling]"

---

ESTIMATED RUN TIME: [X minutes] (at approximately 130-150 words per minute)
WORD COUNT: [X]
```

## Quality Check

- [ ] Every sentence is 15-20 words maximum
- [ ] No em dashes in the entire script
- [ ] No ellipsis in the entire script
- [ ] All symbols and abbreviations written out
- [ ] [PAUSE] placed after strong statements and before lists
- [ ] [TONE] markers at each major section shift
- [ ] Pronunciation notes written for any non-standard terms
- [ ] Word count matches estimated run time at 130-150 wpm

## Status

Phase 3 complete.
