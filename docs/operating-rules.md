# Operating Rules

How the internal AI marketing team operates. These rules govern how agents behave, how work moves through the team, and what is expected of every output.

---

## Core Rules

1. **Start with the Marketing Director for broad tasks.** If the request spans more than one agent or the domain is unclear, route through the Marketing Director first.

2. **Read before you write.** Every agent must read its identity file, the relevant skill, and any applicable knowledge base docs before producing output.

3. **Check the skill map before creating a new skill.** If a skill already exists, use it. If it does not exist, create it in the right folder and add it to `skills/index.md` and `docs/skill-map.md`.

4. **Check the agent roster before adding an agent.** If a new agent is needed, it should have a clearly distinct domain that is not covered by an existing agent.

5. **Save outputs to the right folder.** Every agent output goes to the matching subfolder in `outputs/`. See `outputs/README.md` for the mapping.

6. **QA before client delivery.** Nothing goes to a client without a QA Agent review. Nothing goes to `outputs/final-handoffs/` without Marketing Director approval.

7. **No live tool calls without explicit permission.** Do not connect or use MCP tools in live mode without being asked to do so.

8. **Do not edit source files in uploads/extracted/.** These are original source files. Copy relevant content to knowledge-base/ instead.

9. **Do not invent credentials.** Never create placeholder values that look like real API keys or tokens.

---

## Writing Rules (All Agents)

- Never use em dashes.
- Use contractions.
- Write in plain English.
- Do not sound corporate.
- No AI hype language.
- Sound like someone explaining work over coffee.

Full writing rules are in `knowledge-base/brand/voice-rules.md`.

---

## Quality Standards

Every output must be:
- **Specific** - Not vague or generic. Tied to the actual task, audience, and offer.
- **Complete** - Has everything the next person needs to act on it.
- **Formatted correctly** - Headers, bullets, and structure match the output type.
- **On-voice** - Matches the brand voice rules.
- **Saved correctly** - In the right output folder with a clear file name.

---

## Asking Questions

- Ask only necessary questions.
- If you have enough context to make a grounded assumption, make it and state what you assumed.
- Do not ask for information that is already in the knowledge base or previous outputs.
- If critical information is missing and cannot be assumed, ask a single clear question.

---

## Delegation Rules

- Marketing Director delegates to the right agent by name.
- Delegation briefs must include: task, inputs available, expected output format.
- Agents do not delegate to each other directly. Handoffs go through the Marketing Director unless the agent.md explicitly allows direct handoffs.

---

## Handoff Rules

- Every handoff must note: what the output is, who receives it, and what they should do with it.
- Completed outputs go to `outputs/` in the right subfolder.
- Final approved outputs go to `outputs/final-handoffs/`.
- QA review notes go to `outputs/qa/`.

---

## What Is Off Limits

- Do not create fake credentials or placeholder values that look real.
- Do not overwrite files in `uploads/extracted/`.
- Do not produce outputs that contain unsubstantiated health, financial, or legal claims without flagging them for review.
- Do not add new agents or skills without checking the roster and skill map first.
- Do not start Phase 2 or later work without explicit instruction.
