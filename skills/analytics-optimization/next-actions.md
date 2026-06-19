# Next Actions

## Purpose

Convert all findings from any analytics review (weekly report, funnel analysis, ad performance review, content review, lead quality review) into a single prioritized action list. Without a next actions output, findings get noted but nothing changes. The output is what the Marketing Director uses to assign work and what each agent uses to know what to do this week.

## Used By

- Analytics Agent (produces this at the end of every review cycle)
- Marketing Director (approves priority order and assigns owners)
- All specialized agents (execute the actions assigned to them)

## Trigger

Use at the end of any analytics review session, or when multiple review documents have been produced and need to be consolidated into a single work list.

## Inputs Needed

- All analytics review outputs for the period - required
- Current resource constraints (who is available, what is in flight) - helpful
- Business priorities for the week - helpful

## Process

**Step 1: Collect all findings from all reviews**

Pull every finding and recommendation from:
- Weekly report recommendations
- Funnel analysis fix list
- Ad performance review decisions
- Content performance review recommendations
- Lead quality review recommendations

This may total 10-20 action items.

**Step 2: Assign impact and effort to each action**

For each action:
- **Impact**: High (directly affects revenue this week), Medium (improves over 2-4 weeks), Low (hygiene / marginal improvement)
- **Effort**: Quick (under 2 hours), Standard (half day), Heavy (1+ days)

**Step 3: Prioritize**

Priority order:
1. High impact + Quick - do these first, no reason to wait
2. High impact + Standard - schedule this week
3. High impact + Heavy - break into smaller steps or assign when capacity is available
4. Medium impact - schedule next cycle if High impact items are consuming capacity
5. Low impact - backlog

Do not assign more than 3 High-priority actions per agent per week.

**Step 4: Write each action**

Every action must have:
- What to do (specific)
- Why (which finding triggered this)
- Owner (which agent)
- Due date
- Expected outcome

**Step 5: Flag blockers**

If an action cannot start because something else must happen first, note the dependency.

## Output Format

```
NEXT ACTIONS - [Client] - Week of [Date]
Prepared by: Analytics Agent
Sources: [List of reviews that fed into this]

---

HIGH PRIORITY (Act this week):

ACTION 1
  What: [Specific action]
  Why: [Finding from which review]
  Owner: [Agent]
  Due: [Date]
  Expected outcome: [What changes]
  Blocker: [None / Depends on: ...]

ACTION 2
  [Same format]

ACTION 3
  [Same format]

---

STANDARD PRIORITY (Complete this cycle):

ACTION 4
  [Same format]

ACTION 5
  [Same format]

---

BACKLOG (Next cycle or when capacity allows):

ACTION N
  [Same format]

---

IN-FLIGHT (Already assigned, monitoring only):

| Action | Owner | Status | Expected completion |
|--------|-------|--------|-------------------|
| [Action from prior cycle] | [Agent] | [In progress] | [Date] |

---

BLOCKERS AND DEPENDENCIES:

[Any actions that cannot start without another completing first]

---

DIRECTOR APPROVAL NEEDED:

[High-impact actions that require client or director sign-off before starting]

---

SUMMARY - TOP 3 THIS WEEK:
1. [Action 1] - Owner: [Agent] - Due: [Date]
2. [Action 2] - Owner: [Agent] - Due: [Date]
3. [Action 3] - Owner: [Agent] - Due: [Date]
```

## Quality Check

- [ ] Every action is specific (not "improve targeting")
- [ ] Every action is tied to a finding from a specific review document
- [ ] Every action has an owner and a due date
- [ ] Priority is assigned (not everything is high priority)
- [ ] No more than 3 high-priority actions per agent
- [ ] Blockers and dependencies are noted
- [ ] In-flight items from prior cycle are tracked

## Status

Phase 3 complete.
