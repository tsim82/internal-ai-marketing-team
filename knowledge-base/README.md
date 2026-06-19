# Knowledge Base

The shared context library for the internal AI marketing team. Agents read from here before doing work. Humans add docs here to give agents better context.

---

## How It Works

Agents reference this knowledge base when they need:

- Brand voice and visual rules
- Offer documentation
- Client context
- Strategy frameworks
- Example copy or creative
- Swipe files for research
- Case studies and proof
- SOPs for recurring processes

The knowledge base does not replace skills. Skills define how to do a task. Knowledge base docs provide the context and material to do it well.

---

## Folder Structure

| Folder | Contents |
|--------|----------|
| `brand/` | Voice rules, visual standards, brand identity |
| `offers/` | Offer docs and pricing for agency and clients |
| `clients/` | Client-specific context and campaign notes |
| `frameworks/` | Strategy frameworks and models |
| `examples/` | Example copy, ads, and content for reference |
| `swipe-files/` | Reference material and inspiration |
| `case-studies/` | Results and proof points |
| `sop/` | Standard operating procedures |
| `incoming-docs/` | Staging area for raw files before they are filed |

---

## How To Add Documents

1. Drop raw files in `incoming-docs/` first.
2. Review and categorize them.
3. Move or copy them to the right folder.
4. Update the index at `knowledge-base/index.md`.
5. Do not reference files from `incoming-docs/` in agent prompts until they are reviewed.

---

## Source Uploads

Raw uploaded files from external sources are in `uploads/extracted/`.

Before using any extracted file in knowledge base docs:
- Read the file to understand what it is.
- Check `docs/imported-files-audit.md` for the audit summary.
- Copy (do not move) relevant sections to the right knowledge base folder.
- Do not edit source files in `uploads/extracted/`.

---

## Status

Structure is in place. Content is pending. Add the `agency-owner.md` context first, then add client and offer docs as they become available.
