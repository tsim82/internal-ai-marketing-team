# /respond-to-leads

## What It Does

This skill manages and responds to inbound leads from your ad campaigns. It pulls new leads from your CRM (Airtable or GoHighLevel), drafts personalized SMS and email responses using 5 proven templates, sends them with your approval, and updates the pipeline stage.

No more leads sitting in your CRM uncontacted. Run this daily and every lead gets a fast, personalized response.

---

## When to Use It

- Daily lead response - check for new leads and respond
- When leads are piling up and you need to clear the queue
- When you want to re-engage leads that went cold
- When following up with no-shows

---

## How to Run It

```
/respond-to-leads
```

Claude handles everything automatically:

1. Pulls new leads from Airtable/GHL
2. Drafts personalized response for each lead using the best-fit template
3. Shows you each draft for review/approval
4. Sends approved messages
5. Updates pipeline stage (New → Contacted)
6. Shows follow-up queue for older leads
7. Offers to send follow-ups

---

## Example Output

```
Lead Response Queue - March 5, 2026

3 new leads found:

### Lead 1: Sarah M. - Submitted 2 hours ago
- Source: Instagram ad (Free Trial)
- Kid's sport: Soccer | Age: 12
- Draft (Intro template):
  "Hey Sarah! Thanks for signing up for the free trial session
  at D1 Training. We'd love to get your son in this week -
  we have openings Tuesday and Thursday at 4pm. Which works
  better for you?"
- Send? (y/n/edit): ___

### Lead 2: Mike R. - Submitted 5 hours ago
- Source: Facebook ad (Free Trial)
- Kid's sport: Basketball | Age: 14
- Draft (Value-first template):
  "Hey Mike! Just saw you signed up. Quick heads up - our
  basketball-specific speed program has helped 40+ kids
  improve their first step this season. Want to book your
  son's free session?"
- Send? (y/n/edit): ___

[... Lead 3 ...]

Follow-up queue (leads > 24h, no response):
- Jason T. - 3 days, no reply → Re-engage template ready
- Lisa K. - 2 days, no reply → Re-engage template ready
```

---

## The 5 Response Templates

| Template | When to Use | Tone |
|----------|------------|------|
| **Intro** | First contact, new lead | Warm, welcoming |
| **Value-First** | Lead who needs convincing | Lead with social proof |
| **Direct Book** | Hot lead, ready to buy | Skip the pitch, book now |
| **Re-Engage** | No response after 24-48h | Casual follow-up |
| **Post No-Show** | Booked but didn't show | Understanding, re-book |

---

## Pipeline Stages

```
New → Contacted → Engaged → Booked → Showed → Closed
                                            → Lost
```

The skill automatically moves leads through stages as you interact.

---

## Requirements

- **Claude Code** - installed and running
- **Airtable MCP** - for lead data and pipeline tracking (included in Premium toolkit)
- **GoHighLevel** - optional, for SMS/email sending

---

## Configure Your CLAUDE.md

```markdown
## Lead Response
Airtable base: appXXXXXXXXXXXX
Leads table: tblXXXXXXXXXXXX
Business name: D1 Training Plano
Calendar link: https://calendly.com/your-link
Phone: (555) 123-4567
```

---

## Download

This skill is included in the Premium toolkit. After running the installer, the file lives at:

```
~/.claude/skills/respond-to-leads/SKILL.md
```

If you haven't downloaded the toolkit yet, head to **#Start Here** and complete the **Download ALL Resources** lesson.

---

## Troubleshooting

**"No new leads found"**
Check that your ad campaigns are active and the lead form is connected to your CRM.

**"GHL integration not working"**
GoHighLevel is optional. The skill works with Airtable alone - GHL adds SMS/email sending capabilities.

---

## Changelog

- **v1.0** - 5 response templates, pipeline stage tracking, follow-up queue, Airtable + GHL integration, approval flow before sending.
