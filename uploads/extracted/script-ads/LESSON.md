# /script-ads

## What It Does

This skill generates direct-response UGC ad scripts using 5 proven frameworks. Give it what you're advertising, who the target is, and the angle - and it produces 3+ complete ad scripts with hooks, body copy, CTAs, visual directions, and platform ad copy (primary text, headline, description).

Each script includes specific filming instructions so your UGC creator (or you) knows exactly what to record.

---

## When to Use It

- After `/ad-brief` when you know which ad types to create
- When a client needs new ad creatives scripted
- When testing multiple angles on the same offer
- When briefing UGC creators on what to film

---

## How to Run It

```
/script-ads
```

Claude handles everything automatically:

1. Gathers context (product/service, target audience, angle, format, length, number of variations)
2. Generates 3+ scripts using proven frameworks (PAS, I Tried X, Before/After, Controversy, Story)
3. Formats each with hook, body, CTA + visual direction for filming
4. Adds platform ad copy (primary text, headline, description, CTA button)
5. Saves to `ad-scripts/` directory

---

## Example Output

```
# Ad Script: D1 Training - Free Trial Session

## Script 1: PAS Framework
### Hook (0-3s)
"Your kid is falling behind in sports and you don't even know it"
[Parent sitting at kitchen table, concerned look, phone in hand]

### Agitate (3-12s)
"Every week they sit on the bench while other kids get faster,
stronger, more confident. And it's not about talent - it's about
training they're not getting."
[B-roll: kids on bench, other kids training, scoring goals]

### Solution (12-25s)
"D1 Training's youth program changed everything for my son.
8 weeks in, he went from benchwarmer to starting lineup."
[B-roll: kid training at D1, high-fiving coach, game footage]

### CTA (25-30s)
"They're doing free trial sessions this week. Link in bio."
[Face to camera, point down, D1 logo overlay]

### Platform Ad Copy
- Primary: "My son sat on the bench for 2 years. Then we found D1 Training. 8 weeks later, he's starting every game. Free trial sessions available this week."
- Headline: "Free Trial Session - This Week Only"
- Description: "Youth speed & agility training. Results in 8 weeks."
- CTA Button: Sign Up

---

## Script 2: Before/After Framework
[...]
```

---

## The 5 UGC Frameworks

| Framework | Structure | Best For |
|-----------|----------|----------|
| **PAS** | Problem → Agitate → Solution → CTA | Pain-point driven offers |
| **I Tried X** | Setup → Experience → Result → CTA | Product/service reviews |
| **Before/After** | Before state → Transformation → After state → CTA | Visual results |
| **Controversy** | Hot take → Evidence → Reframe → CTA | Attention-grabbing |
| **Story** | Character → Conflict → Resolution → CTA | Emotional connection |

---

## Requirements

- **Claude Code** - installed and running
- No MCP servers required - this skill works standalone

---

## Configure Your CLAUDE.md

For best results, add client context:

```markdown
## Client
Business: [name]
Service: [what they offer]
Target: [who they serve]
Pain points: [top 3 customer pain points]
Social proof: [testimonials, results, numbers]
```

---

## Download

This skill is included in the Premium toolkit. After running the installer, the file lives at:

```
~/.claude/skills/script-ads/SKILL.md
```

If you haven't downloaded the toolkit yet, head to **#Start Here** and complete the **Download ALL Resources** lesson.

---

## Part of the Ad System

```
/ad-brief → /script-ads → /launch-ads
```

- **`/ad-brief`** - tells you which ads to create
- **`/script-ads`** - writes the scripts
- **`/launch-ads`** - launches them on Meta

---

## Troubleshooting

**"Scripts feel generic"**
Add more specific context - real testimonials, exact numbers, specific pain points. The more detail you give, the better the scripts.

**"Need more variations"**
Just ask: "Give me 3 more using the Story framework." The skill generates as many as you need.

---

## Changelog

- **v1.0** - 5 UGC frameworks, visual filming directions, platform ad copy generation, batch script output.
