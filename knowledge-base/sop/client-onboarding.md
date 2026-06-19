# Client Onboarding SOP

The step-by-step process for onboarding a new client from signed contract to first campaign live. This SOP covers the first 14 days of the client relationship.

---

## Ownership

- Primary owner: Marketing Director (orchestrates)
- Support: CRM Follow-Up Agent (CRM setup), Paid Ads Agent (campaign setup), Funnel Agent (funnel setup), QA Agent (pre-launch check)

---

## Onboarding Timeline

| Day | Milestone |
|-----|-----------|
| Day 1 | Kickoff call completed, intake form collected |
| Day 1-2 | Client folder and CRM record created, assets requested |
| Day 3-5 | Strategy brief created, funnel and copy started |
| Day 7 | First drafts delivered for client review |
| Day 10-12 | Revisions completed, QA check passed |
| Day 14 | Campaign live |

---

## Step 1: Kickoff Call (Day 1)

**Owner:** Marketing Director

Information to collect on the kickoff call:
- Business description (what they do, who they serve, how they get clients now)
- Revenue goal for the engagement
- Current traffic and lead volume (if any)
- Offer and pricing (what they sell, what it costs)
- Existing creative assets (photos, videos, testimonials, case studies)
- CRM and tech stack (what tools they are using)
- Access needed (ad accounts, CRM, website)
- Decision-making process (who approves copy and creative?)
- Communication preferences (response time, preferred channel)

After the call: Create the client brief from the kickoff notes.

---

## Step 2: Client Setup (Day 1-2)

**Owner:** CRM Follow-Up Agent + Marketing Director

Tasks:
- Create client folder in `knowledge-base/clients/[client-slug]/`
- Create `client-profile.md` from the kickoff notes (use the client template)
- Create GHL contact record for the client with all relevant tags
- Set up GHL pipeline for this client's leads
- Grant all necessary account access (ad manager, CRM, landing page builder)
- Confirm pixel is installed and firing (if running paid ads)
- Add client to the weekly reporting schedule

---

## Step 3: Intake and Asset Collection (Day 1-3)

**Owner:** Marketing Director

Send to client (immediately after kickoff):
- Client intake form (collects offer details, audience, goals in writing)
- Brand assets request (logo, colors, fonts, photos, videos)
- Testimonial / case study request (3-5 if possible)
- Ad account and CRM access request

Do not proceed to strategy until intake form and brand assets are received.

---

## Step 4: Strategy Brief (Day 3-5)

**Owner:** Marketing Director (routes to specialists)

Tasks:
- Market Research Agent: Run audience-research.md and objection-research.md
- Offer Agent: Review and document the offer using offer-buildout.md
- Paid Ads Agent: Create the campaign structure using campaign-structure.md
- Funnel Agent: Create funnel map using funnel-map.md
- CFO Agent: Run budget-planning.md and offer-profitability.md

Output: Strategy brief document covering audience, offer, campaign structure, funnel plan, and budget.

Send strategy brief to client for approval before building starts.

---

## Step 5: Build (Day 5-10)

**Owner:** Relevant specialized agents

Parallel workstreams:
- Copywriter: Write all copy (ads, landing page, email sequence, SMS)
- Funnel Agent: Build funnel structure (pages, forms, automation connections)
- Creative Design Agent: Design ad creatives per the creative brief
- n8n Automation Agent: Plan and build automations (lead intake, speed-to-lead, sequences)

Do not launch any workstream without the strategy brief approved.

---

## Step 6: QA Review (Day 10-12)

**Owner:** QA Agent

Run in order:
1. brand-voice-check.md on all copy
2. claims-review.md on all client-facing copy
3. pre-launch-check.md on the full campaign

All issues must be resolved before proceeding. No exceptions.

---

## Step 7: Client Review (Day 12-13)

**Owner:** Marketing Director

Send to client for final approval:
- Ad copy
- Creative assets
- Landing page
- Email and SMS sequences

Collect written approval before launch.

---

## Step 8: Launch (Day 14)

**Owner:** Paid Ads Agent + n8n Automation Agent

Tasks:
- Set campaigns live in the ad platform
- Confirm automations are active and tested
- Confirm pixel fires correctly on the live page
- Confirm speed-to-lead automation fires on a test lead
- Set first reporting date (7 days after launch)

---

## First 30 Days After Launch

- Day 7: First performance check (optimization-review.md)
- Day 14: First weekly report (weekly-report.md)
- Day 21: Funnel review (funnel-analysis.md)
- Day 30: Full monthly review (monthly-kpi-review.md)

---

## Status

Active SOP. Used for every new client.
