# Checkout Flow

## Purpose

Map and optimize the checkout and payment flow for any offer that involves a direct transaction. The checkout flow covers everything from the moment a buyer clicks "buy" to the order confirmation. A broken or confusing checkout is one of the most common reasons carts are abandoned. This skill documents the correct flow and flags common errors.

## Used By

- Funnel Agent (maps and audits the checkout flow)
- n8n Automation Agent (sets up post-purchase automations)
- Analytics Agent (tracks conversion rate at checkout stage)

## Trigger

Use when setting up a new checkout flow, when cart abandonment rates are high, or when a checkout audit is needed before a launch.

## Inputs Needed

- Offer and price - required
- Tech stack (Stripe, ThriveCart, GHL Payments, Shopify, Kajabi, etc.) - required
- Upsell or downsell offers (if any) - required
- Order bump (if any) - helpful
- Confirmation and delivery method - required
- CRM integration for post-purchase tagging - required

## Process

**Step 1: Define the checkout path**

A checkout flow has a defined sequence. Document every step:

1. **Cart / Order page**: Shows what the buyer is purchasing and the total
2. **Order bump** (optional): A one-click add-on offer at the bottom of the order form
3. **Payment page**: Where card details are entered
4. **Upsell 1** (optional): Post-purchase offer shown before the confirmation
5. **Downsell** (optional): Shown if the buyer declines the upsell
6. **Upsell 2** (optional): Second upsell if the first was accepted
7. **Order confirmation / Thank you page**: Final confirmation

**Step 2: Audit for friction points**

Common friction points that increase abandonment:
- Too many form fields (keep to essential info only: name, email, phone if needed)
- Forced account creation before purchase
- No trust signals near the payment field (SSL badge, money-back guarantee reminder)
- Confusing pricing (unclear what the buyer is paying today vs. future)
- Mobile payment experience not tested
- Upsell page breaks the flow and confuses the buyer

**Step 3: Design the upsell logic**

If upsells exist, define:
- What is offered and at what price
- What copy and CTA is used (keep it brief - "Add this to my order" not another full sales pitch)
- What happens if they accept (payment processes automatically, redirect to next step)
- What happens if they decline (redirect to next step or downsell)

Upsell acceptance rates benchmark: 20-35% for well-positioned upsells. Above 40% may mean the upsell should be part of the core offer. Below 15% usually means the upsell is misaligned.

**Step 4: Define post-purchase automations**

What happens immediately after purchase?
- [ ] Confirmation email fires with receipt and access instructions
- [ ] CRM contact tagged as "customer" and removed from prospect sequences
- [ ] Access to product or service is granted (portal, calendar link, login)
- [ ] Onboarding sequence starts (if applicable)
- [ ] Finance notification fires (if needed)
- [ ] Delivery team is notified (for service-based offers)

**Step 5: Test the full checkout before launch**

Run a test transaction through the entire flow:
1. Place a test order (use platform's test mode)
2. Confirm the order bump appears correctly
3. Confirm upsell flow works in both accept and decline paths
4. Confirm confirmation email delivers
5. Confirm CRM tags apply correctly
6. Confirm product or service access is granted

## Output Format

```
CHECKOUT FLOW - [Client/Offer] - [Date]

OFFER: [Name and price]
TECH STACK: [Payment processor / Cart platform]
UPSELLS: [Yes / No - list]
ORDER BUMP: [Yes / No - describe]

---

CHECKOUT SEQUENCE:

STEP 1: Cart / Order Page
  URL: [URL]
  Shows: [Offer name, price breakdown, order summary]
  Order bump: [Yes / No]
    If yes: [Name, price, one-line description]
  Trust signals required: [SSL badge, guarantee, payment logos]

STEP 2: Payment Page
  URL: [URL]
  Fields required: [Name, Email, Phone, Card details]
  Fields to remove: [Anything non-essential]
  Trust signals: [Guarantee reminder near submit button]
  Mobile test: [Required before launch]

STEP 3: Upsell 1 (if applicable)
  Offer: [Name and price]
  Copy direction: [Brief - what this upsell is and why they should add it]
  Accept path: → [Next step]
  Decline path: → [Downsell or confirmation]

STEP 4: Downsell (if applicable)
  Offer: [Reduced version at lower price]
  Accept path: → [Confirmation]
  Decline path: → [Confirmation]

STEP 5: Order Confirmation / Thank You Page
  URL: [URL]
  Required elements:
    - Confirmation message
    - Receipt summary
    - Access instructions or next steps
    - What to expect and when
  See thank-you-page.md for full wireframe

---

POST-PURCHASE AUTOMATIONS:

| Action | Tool | Timing |
|--------|------|--------|
| Confirmation email | [Email tool] | Immediate |
| CRM tag: Customer | [CRM] | Immediate |
| Remove from prospect sequences | [CRM] | Immediate |
| Product/service access granted | [Platform] | Immediate |
| Onboarding sequence starts | [Email tool] | Immediate or [X] hours delay |
| Delivery team notification | [Slack / Email / etc.] | Immediate |

---

FRICTION AUDIT:

[ ] No forced account creation before purchase
[ ] Form fields reduced to essential only
[ ] Trust signals present near payment field
[ ] Pricing is clear (no hidden costs)
[ ] Mobile checkout tested
[ ] Upsell copy is brief and does not re-sell the main offer

---

PRE-LAUNCH TEST CHECKLIST:
[ ] Test order placed in test mode
[ ] Order bump displays correctly
[ ] Upsell accept and decline paths work
[ ] Confirmation email delivers
[ ] CRM tags apply
[ ] Access is granted
```

## Quality Check

- [ ] Full checkout sequence documented step by step
- [ ] Upsell logic covers both accept and decline paths
- [ ] Post-purchase automations are named with tools and timing
- [ ] Friction audit is completed
- [ ] Pre-launch test is required before any campaign sends real traffic

## Status

Phase 3 complete.
