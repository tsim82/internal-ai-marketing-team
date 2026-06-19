# Email Sequence

## Purpose

Write a complete email sequence for lead nurture, post-opt-in follow-up, sales conversion, or post-purchase onboarding. Each email in the sequence is written in full, not summarized. The output is ready for the CRM Follow-Up Agent and n8n Automation Agent to load into the platform.

## Used By

- Copywriter (primary)
- CRM Follow-Up Agent (provides the sequence brief and timing)
- n8n Automation Agent (loads into workflow)
- QA Agent (reviews before activation)

## Trigger

Use when a new sequence is needed, an existing sequence has low open rates or conversion rates, or the CRM Follow-Up Agent has produced a sequence brief that needs copy written.

## Inputs Needed

- Sequence brief from CRM Follow-Up Agent (purpose, timing, number of emails) - required
- Offer details (from Offer Agent) - required
- Audience profile and awareness level - required
- Brand voice rules - required
- Lead source or entry point for the sequence - required
- Existing email data (open rates, click rates) if this is a rewrite - helpful

## Process

**Step 1: Read the sequence brief**
The CRM Follow-Up Agent provides the purpose of each email in the sequence. Read it completely before writing any email. If no brief exists, create one first: how many emails, what each email is for, timing.

**Step 2: Define the sequence arc**
Every sequence has a logic. Map the arc before writing:

Post-opt-in (lead magnet or free offer):
- Email 1: Deliver the promise (what they opted in for). No pitch.
- Email 2: One piece of standalone value. Build trust.
- Email 3: Transition - connect the value to the offer.
- Email 4: The offer. Clear, specific, one CTA.
- Email 5: Proof. Testimonial or case study matching the reader's situation.
- Email 6: Objection handler. Address the most common reason they have not bought.
- Email 7: Last call or scarcity (if real).

Sales nurture (longer buying cycle):
- Phase 1 (Emails 1-3): Education and value. No ask.
- Phase 2 (Emails 4-6): Social proof and authority. Soft offers.
- Phase 3 (Emails 7+): Direct offer, objections, urgency.

Post-purchase onboarding:
- Email 1: Confirmation and welcome. Reduce buyer's remorse.
- Email 2: Quick win or next step. Get them into the product/service.
- Email 3: Set expectations for what is coming.
- Email 4: Community or support invite.
- Email 5: Upsell or referral ask (if applicable).

**Step 3: Write each email in full**

Structure for every email:
- From name, subject line, preview text
- Body
- Sign-off
- CTA (if applicable)
- P.S. (optional but high-read)

Subject line rules:
- Under 50 characters for best mobile display
- Avoid spam triggers: ALL CAPS, excessive punctuation
- Write 3 options per email and pick the strongest
- Preview text extends the subject - does not repeat it

Body copy rules:
- First sentence must earn the second. Never open with "I hope this email finds you well."
- Short paragraphs: 1-3 sentences max
- One idea per email
- One CTA per email
- Human sign-off, not a department sign-off
- P.S. lines: use to add urgency, repeat the CTA, or add proof

**Step 4: Review the arc**
After all emails are written, read the sequence in order:
- Does it flow naturally from one to the next?
- Does it build logically from value to offer?
- Are there any emails that repeat without adding something new?
- Is there a clear ending - conversion or graceful close?

## Output Format

```
EMAIL SEQUENCE - [Sequence Name] - [Client]
Trigger: [What starts this sequence]
Entry point: [Lead source]
Total emails: [N]
Sequence goal: [Booked call / Purchase / Onboarding / Re-engagement]

---

EMAIL 1 of [N]
Send timing: [Immediately / X hours / X days after trigger]
Purpose: [What this email does in the arc]

Subject line (selected): "[Subject]"
Subject alternatives:
  A: "[Alt 1]"
  B: "[Alt 2]"
Preview text: "[Preview text - 25-40 words]"

BODY:
[Full email body]

Sign-off: "[Name]"
CTA: "[CTA text]" → [Link placeholder]
P.S.: "[P.S. content if applicable]"

---

EMAIL 2 of [N]
[Same format]

---

[Repeat for all emails]

---

SEQUENCE NOTES:
Arc: [Brief description of the logical flow]
Placeholder items: [Links, specific results, names needing client input]
Unsubscribe: [Confirm platform handles compliance]
```

## Quality Check

- [ ] Every email has subject line, preview text, body, and sign-off
- [ ] Three subject line options written per email
- [ ] No email opens with a generic greeting
- [ ] One CTA per email maximum
- [ ] Sequence arc makes logical sense first to last
- [ ] No unsubstantiated result claims - all results attributed or qualified
- [ ] No em dashes, no banned words
- [ ] Contractions used throughout
- [ ] Placeholder links and client-specific data clearly flagged
- [ ] Route to CRM Follow-Up Agent for timing and QA Agent for final review

## Status

Phase 3 complete.
