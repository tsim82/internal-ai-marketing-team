# Node Plan

## Purpose

Translate the workflow map into a specific node-by-node configuration plan for n8n. The node plan is more detailed than the workflow map - it names the exact n8n node type for each step, the configuration required, and the expected data shape at each point. The output is what the n8n Automation Agent uses to build the workflow directly.

## Used By

- n8n Automation Agent (primary)

## Trigger

Use after the workflow map is approved, immediately before building in n8n.

## Inputs Needed

- Approved workflow map - required
- Data structure of the trigger payload (what fields does the trigger send?) - required
- Data requirements for the output systems (what fields do they need?) - required
- n8n version in use (for node compatibility) - helpful

## Process

**Step 1: Map each workflow step to the best n8n node**

Node priority order (from the n8n Automation Agent's operating principles):
1. Native n8n trigger nodes (Webhook, Cron, Google Sheets Trigger, etc.)
2. Service-specific integration nodes (GoHighLevel, Airtable, Google Sheets, Slack, etc.)
3. Core utility nodes (Set, Switch, IF, Merge, Code)
4. HTTP Request node (when no native node exists)
5. Code node (JavaScript) - last resort only

For each step in the workflow map, identify:
- Which n8n node handles it
- Which node type within that node (action)
- What configuration is required

**Step 2: Document the expected data at each node**

Before configuring expressions, document the data shape:
- What fields arrive from the previous node?
- What fields does this node need?
- What fields does this node output to the next node?

This prevents "can't read property of undefined" errors during build.

**Step 3: Plan the expressions**

For any node that transforms, filters, or maps data, write the expression logic in plain English before writing n8n expressions:

"Take the `email` field from the webhook body, lowercase it, and pass it as `contact.email` to the GHL node."

**Step 4: Plan the routing (IF and Switch nodes)**

For any conditional logic:
- What is the condition being checked?
- What are the possible paths?
- What happens in each path?
- What happens if none of the conditions match?

**Step 5: Document the test payload**

Write a sample test payload that will be used to test the workflow end-to-end:

```json
{
  "email": "test@example.com",
  "firstName": "Test",
  "lastName": "Lead",
  "phone": "+15551234567",
  "source": "facebook-lead-form"
}
```

## Output Format

```
NODE PLAN - [Workflow Name] - [Date]

WORKFLOW MAP REF: [Link or file name]

---

NODE-BY-NODE PLAN:

NODE 1: [Node name/label]
  n8n Node Type: [Webhook / GoHighLevel / IF / Set / HTTP Request / etc.]
  Action: [Specific action within the node]
  
  Configuration:
    [Field]: [Value or expression direction]
    [Field]: [Value or expression direction]
  
  Input data expected:
    [Field name]: [Type and description]
  
  Output data passed to next node:
    [Field name]: [Type and description]
  
  Error handling: [Yes - what / No]

NODE 2: [Node name/label]
  [Same format]

NODE 3 (IF/Switch - conditional):
  n8n Node Type: [IF / Switch]
  Condition: [What is being evaluated]
  
  True branch → NODE 4A
  False branch → NODE 4B
  No match (Switch only) → [What happens]

NODE 4A: [True path]
  [Same format]

NODE 4B: [False path]
  [Same format]

[Continue for all nodes]

---

EXPRESSION REFERENCE:

| Node | Field | Expression logic |
|------|-------|----------------|
| NODE 2 | contact.email | Lowercase value from NODE 1 body.email |
| [Node] | [Field] | [Plain English expression direction] |

---

TEST PAYLOAD:

```json
{
  "field1": "test value",
  "field2": "test value"
}
```

Expected output after full run: [What should appear in the destination system]

---

BUILD ORDER:
1. Start with the trigger node
2. Build the success path end-to-end
3. Add conditional branches
4. Add error handlers last
```

## Quality Check

- [ ] Every step in the workflow map has a corresponding node
- [ ] Node type is named specifically (not "n8n node" or "integration")
- [ ] Input and output data is documented for each node
- [ ] Expressions are planned before building (not figured out during build)
- [ ] Test payload is written before build starts
- [ ] Error handling nodes are noted (even if not yet planned in full - use error-handling.md)
- [ ] No real credentials or API keys in this document

## Status

Phase 3 complete.
