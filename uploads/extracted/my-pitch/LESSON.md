# /my-pitch

## What It Does

This skill drafts personalized cold DMs for outreach to potential clients. Give it a business name, their sport/industry, and location - and it generates 3 different DM angles you can send on Instagram or Facebook.

Each DM is under 4 sentences, casual and confident, mentions your done-for-you service, and includes a specific value hook. Pick the angle that fits and send it.

---

## When to Use It

- When doing cold outreach to potential clients
- When you've found a business you want to pitch
- When you need multiple DM angles to test
- When you want to personalize outreach at scale

---

## How to Run It

```
/my-pitch
```

Claude handles everything automatically:

1. Asks for the facility/business name, sport/industry, and location
2. Asks for any specific observations (optional - their content, their current ads, etc.)
3. Drafts 3 DM angles (compliment opener, straight shooter, value drop)
4. Each DM: under 4 sentences, casual tone, specific value hook
5. Asks which angle you prefer

---

## Example Output

```
Business: Peak Performance Training - Austin, TX
Sport: Baseball

### Angle 1: Compliment Opener
"Hey! Saw your facility - the batting cage setup is sick.
Quick question - have you tried running Meta ads for trial
sessions? We do it done-for-you for training facilities and
it's been filling up schedules. Happy to show you how it works."

### Angle 2: Straight Shooter
"Hey - I help sports training facilities fill their schedule
with Meta ads. We handle everything and you just show up to
train. Would you be open to a quick chat this week?"

### Angle 3: Value Drop
"Hey! Just helped a baseball training facility in Houston book
23 trial sessions in their first month with Meta ads. We do
everything done-for-you. Want me to show you what we did?"

Which angle? (1/2/3)
```

---

## Requirements

- **Claude Code** - installed and running
- No MCP servers required - this skill works standalone

---

## Download

This skill is included in the Premium toolkit. After running the installer, the file lives at:

```
~/.claude/skills/my-pitch/SKILL.md
```

If you haven't downloaded the toolkit yet, head to **#Start Here** and complete the **Download ALL Resources** lesson.

---

## Troubleshooting

**"DMs feel too generic"**
Add specific observations about the business - their Instagram content, their website, something you noticed. The more specific, the more personal the DM feels.

---

## Changelog

- **v1.0** - 3-angle DM generation, casual tone, under-4-sentence constraint, personalization from business observations.
