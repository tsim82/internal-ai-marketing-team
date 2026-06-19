# Webhook Intake

## Purpose

Design and document the webhook intake configuration for receiving inbound data from external platforms. A webhook intake receives data, validates it, and routes it into the correct workflow. Getting this wrong means accepting bad data, missing required fields, or processing the same event multiple times. The output is the full intake design including validation rules, field mapping, and deduplication logic.

## Used By

- n8n Automation Agent (primary)

## Trigger

Use when any external platform needs to send data to n8n - form submissions, CRM events, payment confirmations, ad platform events, or any third-party webhook.

## Inputs Needed

- Sending platform (what system fires the webhook) - required
- Sample payload (what data it sends) - required
- Required fields for processing (what the workflow needs) - required
- Deduplication key (what field makes each event unique) - required
- Authentication method for the webhook (if any) - required

## Process

**Step 1: Document the incoming payload**

Before building, capture a sample payload from the sending system:
- Use the platform's test webhook feature (if available)
- Or document the expected payload from their API docs
- Note the exact field names and data types

The payload is the contract. The n8n workflow must handle exactly what the sending system sends.

**Step 2: Define the validation rules**

What must be true for the payload to be valid?

Required field validation:
- [ ] Email is present and is a valid email format
- [ ] Phone is present (if required)
- [ ] Lead source is identified
- [ ] Any other required field

Format validation:
- [ ] Phone is in [E.164 format / 10-digit / as-received from platform]
- [ ] Date fields are in [format]

If validation fails: reject the payload, log the failure, and alert.

**Step 3: Design the deduplication check**

What makes an incoming event unique? Usually email or a platform-provided lead ID.

Deduplication approach:
1. On receipt, check if a record with this email/ID already exists in the CRM
2. If record exists: route to update path (do not create duplicate)
3. If record does not exist: route to create path
4. Log the decision either way

**Step 4: Map the fields**

Build the field mapping from the incoming payload to the destination system:

| Incoming field | Destination field | Transformation |
|--------------|-----------------|--------------|
| `data.email` | `contact.email` | Lowercase |
| `data.firstName` | `contact.first_name` | Trim whitespace |
| `data.phone` | `contact.phone` | Format to E.164 |
| `form_id` | `contact.source` | Map to source label |
| [Field] | [Field] | [Transform or none] |

**Step 5: Authenticate the webhook**

Unsecured webhooks accept requests from anyone. Options:
- Header authentication: send a secret key in a custom header, validate it in n8n
- HMAC signature: platform signs the payload with a shared secret, n8n validates the signature
- IP allowlist: only accept requests from the sending platform's IP range

Document which method is used and what the validation logic is. Do not document the actual secret values.

## Output Format

```
WEBHOOK INTAKE DESIGN - [Intake Name] - [Date]

SENDING PLATFORM: [Platform name]
WEBHOOK URL: [n8n Webhook node URL - actual URL in credential vault, not here]
PURPOSE: [What event fires this webhook and why]

---

SAMPLE INCOMING PAYLOAD:

```json
{
  "field1": "example_value",
  "nested": {
    "field2": "example_value"
  }
}
```

---

VALIDATION RULES:

Required fields:
| Field | Required? | Validation | Action if missing |
|-------|---------|-----------|-----------------|
| [field] | Yes | Must be present and non-empty | Reject + log |
| [email field] | Yes | Valid email format | Reject + log |
| [phone field] | Yes/No | [Format requirement] | [Action] |

Format rules:
- [Field]: must be [format]
- [Date field]: convert from [format] to ISO 8601

If validation fails:
  → Set node: capture failure details
  → Log to error table
  → Slack alert
  → Return 400 response to sender (acknowledgment that data was rejected)

---

DEDUPLICATION:

Dedup key: [Email / Lead ID / Phone]
Check: Query [CRM/Airtable] for existing record with this key
If exists → UPDATE path
If does not exist → CREATE path
Log dedup decision to: [Field in CRM or Airtable]

---

FIELD MAPPING:

| Incoming field | Destination field | Transformation |
|--------------|-----------------|--------------|
| [path.to.field] | [destination.field] | [Lowercase / Format / Map / None] |

---

AUTHENTICATION:

Method: [Header token / HMAC signature / IP allowlist / None]
Where configured: [n8n node header validation / Code node / Incoming webhook settings]
What is validated: [Secret key in header named X-[Name] / HMAC of body with shared secret]
Secret stored in: [n8n credential vault - not documented here]

---

RESPONSE:

Success response: 200 OK (confirm receipt)
Validation failure: 400 Bad Request + error message
Auth failure: 401 Unauthorized
```

## Quality Check

- [ ] Sample payload is documented
- [ ] All required fields have validation rules with consequences if missing
- [ ] Deduplication key is identified and the check is designed
- [ ] Field mapping is complete for all fields being used
- [ ] Authentication method is documented (even if the secret itself is in the credential vault)
- [ ] Success and failure response codes are defined
- [ ] No actual secrets or credential values in this document

## Status

Phase 3 complete.
