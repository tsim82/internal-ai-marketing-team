# Thank You Page

## Purpose

Design the thank you page that appears immediately after a conversion event (opt-in, application, purchase, or booking). The thank you page does three things: confirms the action the visitor just took, tells them exactly what happens next, and advances them one step further in the funnel if appropriate. A weak thank you page is a missed opportunity. A strong one increases show rates, pre-qualifies buyers, and starts the relationship right.

## Used By

- Funnel Agent (designs the page)
- Copywriter (writes the copy for this page)
- n8n Automation Agent (ensures automations fire when the page loads)

## Trigger

Use when building a new funnel, when a thank you page is missing or generic ("Thanks for signing up!"), or when show rates or booking confirmation rates are below target.

## Inputs Needed

- What conversion just happened (opt-in, booking, purchase, application) - required
- What the next step is for the buyer (check email, attend webinar, wait for call, access portal) - required
- Offer type and price point - helpful
- Any upsell or next-step offer being placed on this page - helpful
- Funnel map to understand what comes after - required

## Process

**Step 1: Confirm what conversion happened and what needs to happen next**

The thank you page must answer:
1. "Did that work?" (confirm the action was completed)
2. "What do I do now?" (clear single next step)
3. "What happens after that?" (set expectations)

**Step 2: Match page content to conversion type**

| Conversion type | Page priority | Required elements |
|----------------|--------------|------------------|
| Opt-in (free lead magnet) | Get them to open the email | "Check your email at [address]" + what they'll find inside |
| Webinar registration | Maximize attendance | Confirmation of date/time, add to calendar link, what the training covers |
| Application submitted | Set expectations + qualify | "What happens next" timeline, who reviews it, when they can expect a call |
| Call booked | Maximize show rate | Confirm time and date, what to prepare, what the call covers |
| Purchase | Grant access + set expectations | What they bought, how to access it, what happens next |

**Step 3: Design the page structure**

A thank you page should be simple. It is not a landing page. Do not oversell here.

Standard structure:
1. **Confirmation headline**: "You're in!" or "Your call is booked for [day/time]"
2. **Confirmation detail**: What exactly was confirmed
3. **Clear next step**: One thing to do right now (check email, add to calendar, watch the video below)
4. **What to expect**: The 2-3 thing sequence of what happens next and when
5. **Optional: VSL or next-step video**: For call-booking pages, a brief video (2-4 minutes) that pre-frames the call increases show rates
6. **Optional: Upsell or bump offer**: Only if it makes sense - do not interrupt a critical next step with an unrelated offer

**Step 4: Write the pre-frame content (for call booking pages)**

For booked-call thank you pages, a short video or text section that:
- Tells them what to expect on the call (not a sales pitch)
- Gives them one thing to prepare or think about before the call
- Reinforces why attending the call is the right move

This is not a pitch. It is a warm-up. The goal is to have them arrive to the call already thinking about their situation and what they want to change.

**Step 5: Set the expectations section**

"What happens next" reduces confusion and no-shows. Write it as a numbered list:
1. "You'll get a confirmation email in the next 5 minutes"
2. "We'll review your application and [what happens]"
3. "You'll hear from us by [timeframe]"

If it is a booking confirmation, include the name and face (photo or brief bio) of who they are meeting with. This personalizes the call and reduces no-shows.

## Output Format

```
THANK YOU PAGE - [Client/Offer] - [Conversion Type] - [Date]

CONVERSION THAT JUST HAPPENED: [Opt-in / Booking / Application / Purchase]
NEXT STEP FOR VISITOR: [Check email / Attend webinar / Wait for callback / Access portal]

---

PAGE STRUCTURE:

SECTION 1: CONFIRMATION HEADLINE
Copy direction: "[Confirm the specific action - e.g., 'Your call is booked!' or 'You're in - check your email']"
Required elements: [Headline, confirmation of what they did]

SECTION 2: CONFIRMATION DETAIL
Copy direction: [What was confirmed, with specifics - date/time for bookings, email address for opt-ins]
For call bookings: Include date, time, and the name/photo of who they are meeting with

SECTION 3: CLEAR NEXT STEP
The one thing to do right now: [Specific action]
CTA or instruction: "[Copy-ready direction]"

SECTION 4: WHAT TO EXPECT
Numbered sequence:
1. [Immediate: what happens in the next 5 minutes]
2. [Short-term: what happens in the next few hours or days]
3. [Meeting point: when they get the outcome they signed up for]

SECTION 5: PRE-FRAME CONTENT (for call booking pages only)
Video or text? [Video recommended / Text if no video asset]
Content direction: [What this section should accomplish - not a pitch, just a warm-up]
Key message: "[One thing they should be thinking about before the call]"

SECTION 6: OPTIONAL UPSELL / NEXT OFFER (if applicable)
Offer: [Name and brief description]
Placement rationale: [Why this is appropriate at this stage]
If not applicable: [Leave this section out]

---

AUTOMATION DEPENDENCIES:
[ ] Confirmation email fires when this page loads (pixel event or automation trigger)
[ ] CRM record is updated with lead/customer status
[ ] For bookings: calendar invitation sent to lead's email
[ ] For purchases: access granted before they leave this page

---

COPY NOTES FOR COPYWRITER:
Tone: [Warm and reassuring - they just took an action, confirm it was right]
Length: [Short - this is not a landing page]
Avoid: [Don't re-sell on this page unless there's a deliberate upsell strategy]
```

## Quality Check

- [ ] Confirmation is clear and specific (not generic "Thanks!")
- [ ] Single, clear next step - not multiple competing actions
- [ ] "What to expect" sets a timeline and specific sequence
- [ ] For call bookings: interviewer name and face included, pre-frame content included
- [ ] Automations are confirmed to fire before treating page as complete
- [ ] Page is simple and short - not a second landing page

## Status

Phase 3 complete.
