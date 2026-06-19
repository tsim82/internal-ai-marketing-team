# Landing Page Copy

## Purpose

Produce complete, conversion-focused copy for a landing page. This skill covers opt-in pages, long-form sales pages, webinar registration pages, and VSL pages. The output is a full copy draft with every section written, not an outline.

## Used By

- Copywriter (primary)
- Funnel Agent (references for wireframe alignment)
- QA Agent (reviews output)

## Trigger

Use when a new landing page needs copy, an existing page needs a rewrite, or conversion rates have dropped and copy is the suspected cause.

## Inputs Needed

- Completed offer doc (from Offer Agent) - required
- Audience research brief or psychographic profile (from Market Research Agent) - required
- Awareness level of the traffic source (cold, warm, or hot) - required
- Brand voice rules (`knowledge-base/brand/voice-rules.md`) - required
- Funnel type and page goal (opt-in / VSL / long-form sale / application) - required
- Existing page copy if rewriting (optional)
- Competitor page examples (optional)

## Process

**Step 1: Identify the awareness level**
Check where the traffic is coming from. Cold traffic (paid ads, new audiences) needs more education and empathy before the pitch. Warm traffic (retargeting, email list) can go faster to the offer. Use the awareness level framework from `agents/copywriter/agent.md` to calibrate the opening.

**Step 2: Write the headline and subheadline**
The headline is the most important element. Write 5 options before choosing one. Use the headline formula toolkit from the Copywriter's strategies:
- Specific result + timeframe: "Get 20 Qualified Leads Per Week From Facebook Ads"
- Curiosity gap: "Why Your Landing Page Is Probably Losing 60% of Its Leads"
- Proof headline: "How Our Clients Are Booking 10-15 Calls Per Week Without Cold Outreach"

Choose the headline that is most specific and matches the awareness level of the traffic. The subheadline clarifies or adds urgency/specificity.

**Step 3: Write the hook / opening block**
This is the first paragraph or two. For cold traffic, open with the problem. For warm traffic, open with the promise. Apply the Before-After-Bridge or PAS framework depending on what the traffic knows.

PAS opening structure:
- Problem: Name the specific frustration they are experiencing right now
- Agitate: Make the problem feel real and urgent - what it costs them to not solve it
- Solve: Introduce the solution (do not pitch it yet - just name it)

**Step 4: Write the body sections**
For an opt-in page (short): Skip to the offer block directly after the hook. Single CTA above the fold.

For a long-form sales page, write these sections in order:
1. Hook / opening (done)
2. Credibility bridge - who you are and why the reader should listen
3. Story or proof of concept - what changed and how this solution was discovered
4. The problem explained in depth - education section using buyer language
5. The solution introduced - name the unique mechanism
6. What they get - the offer stack, detailed
7. Who this is for (and who it is not for)
8. Social proof block - testimonials and results, organized by strongest first
9. The guarantee
10. Price and value stack
11. Final CTA with urgency framing
12. FAQ section handling the top 3-5 objections

**Step 5: Write the CTA**
Every CTA must be specific. "Get Started" is not a CTA. "Book My Free Strategy Call" is. "Send Me The Free Guide" is. The CTA should say what they are getting or doing, not what they are clicking.

**Step 6: Write the proof block**
Pull the strongest testimonial or result first. Testimonials should be specific (numbers, timeframes, named if possible). Results without attribution should be qualified. Apply the proof hierarchy from the Copywriter's strategies.

**Step 7: Write the FAQ**
List the top 3-5 objections the sales team or research brief has identified. Answer each one directly. Do not hedge. Do not apologize for the objection.

**Step 8: Read aloud**
Read the full page aloud before submitting. Anything that sounds unnatural, stiff, or like it came from a brochure needs to be rewritten.

## Output Format

```
LANDING PAGE COPY - [Page Name] - [Client]
Page type: [Opt-in / VSL / Long-form sales / Application / Webinar reg]
Awareness level: [Cold / Warm / Hot]
Traffic source: [Paid / Email / Organic]

---

HEADLINE (SELECTED):
"[Headline text]"

HEADLINE ALTERNATIVES (backup options):
1. "[Alt 1]"
2. "[Alt 2]"

SUBHEADLINE:
"[Subheadline text]"

---

HOOK / OPENING:
[Full paragraph(s)]

---

[BODY SECTIONS - labeled by section name]

---

PRIMARY CTA:
Button text: "[CTA text]"
Supporting line below button: "[Risk-reducer or proof line]"

---

PROOF BLOCK:
[Testimonials or results - sourced and attributed]

---

FAQ:
Q: [Question]
A: [Answer]
[Repeat]

---

COPY NOTES:
- Awareness level applied: [state which level and how]
- Framework used: [PAS / AIDA / BAB / Direct offer]
- Proof level: [Verified / Attributed / Qualified - note which claims need sourcing]
- Placeholder items (need client input before launch): [list any]
```

## Quality Check

- [ ] Headline is specific - names a result, not just a topic
- [ ] Opening matches the awareness level of the traffic source
- [ ] Body flows from problem → solution → proof → offer, not the reverse
- [ ] CTA text says what the reader gets, not what they click
- [ ] All claims are categorized - no unsubstantiated income or result claims
- [ ] No em dashes
- [ ] No banned words from voice-rules.md
- [ ] No corporate language or passive voice
- [ ] Contractions used throughout
- [ ] Read aloud test passed
- [ ] Route to QA Agent before any page goes live

## Status

Phase 3 complete.
