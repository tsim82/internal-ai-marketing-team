# CRM Sync

## Purpose

Document the full data synchronization configuration between an external system and GoHighLevel (or another CRM). A CRM sync ensures that lead data, contact updates, and pipeline stage changes are consistent across systems. This skill covers the field mapping, trigger conditions, update logic, and tag management for a specific sync.

## Used By

- n8n Automation Agent (primary)
- CRM Follow-Up Agent (reviews to confirm GHL configuration aligns)

## Trigger

Use when setting up a new lead intake to GHL, when syncing data from a form/ad platform to the CRM, or when existing sync is producing missing or incorrect data in GHL.

## Inputs Needed

- Source system (what is sending data to GHL) - required
- GHL pipeline and stage to place new contacts in - required
- Field mapping requirements - required
- Tag logic (which tags apply under which conditions) - required
- Deduplication rule (what makes a contact unique) - required
- Update vs. create logic (when to update existing vs. create new) - required

## Process

**Step 1: Confirm the GHL contact schema**

Before mapping, confirm the fields available in GHL for this client:
- Standard fields: First Name, Last Name, Email, Phone, Address, etc.
- Custom fields: any client-specific fields that have been set up in GHL

For custom fields, note the GHL field ID (required for API calls).

**Step 2: Write the create-or-update logic**

Every CRM sync must handle both new and existing contacts:

```
Incoming email → Search GHL for existing contact with this email
If NOT found → Create new contact
  - Set all mapped fields
  - Assign to pipeline stage: [Stage name]
  - Apply tags: [Tag list]
  - Set source: [Source value]

If FOUND → Update existing contact
  - Update fields where incoming data is newer or more complete
  - Do NOT overwrite: [List any fields that should not be overwritten]
  - Apply additional tags if applicable
  - Move pipeline stage only if [condition]
```

**Step 3: Build the field mapping**

| Source field | GHL field | GHL field ID | Transformation | Create | Update |
|------------|---------|------------|--------------|--------|--------|
| `email` | Email | standard | Lowercase | Yes | No (key field) |
| `firstName` | First Name | standard | Trim | Yes | Yes if empty |
| `phone` | Phone | standard | Format to E.164 | Yes | Yes if empty |
| `source` | Source | custom_field_id | Map to label | Yes | No |
| [Field] | [GHL field] | [ID] | [Transform] | [Y/N] | [Y/N] |

Update column logic:
- Yes: Always update this field with the incoming value
- Yes if empty: Only update if the GHL field is currently empty
- No: Never overwrite this field (preserve the original value)

**Step 4: Design the tag logic**

Tags in GHL control which sequences and automations fire. Document the logic for each tag:

| Condition | Tag to apply | Tag to remove |
|-----------|------------|-------------|
| New contact | "New Lead" | - |
| Source = Facebook Lead Form | "fb-lead" | - |
| Source = Website | "website-lead" | - |
| Lead qualifies (BANT score 3+) | "Qualified Lead" | - |
| Lead books a call | "Call Booked" | "New Lead" |
| [Condition] | [Tag] | [Tag to remove if applicable] |

**Step 5: Confirm the pipeline placement**

- Pipeline: [Pipeline name in GHL]
- Stage for new contacts: [Stage name]
- Stage update logic: Does the stage update automatically via GHL automations, or does n8n manage stage changes?

## Output Format

```
CRM SYNC CONFIGURATION - [Sync Name / Source-to-GHL] - [Date]

SOURCE SYSTEM: [Platform sending data]
DESTINATION: GoHighLevel
GHL PIPELINE: [Pipeline name]
DEFAULT STAGE FOR NEW CONTACTS: [Stage name]

---

CREATE OR UPDATE LOGIC:

Dedup key: Email
Search: Query GHL contacts by email
If not found: CREATE new contact
If found: UPDATE existing contact per rules below

---

FIELD MAPPING:

| Source field | GHL field | GHL custom field ID | Transformation | Create? | Update? |
|------------|---------|-------------------|--------------|---------|---------|
| [field] | [GHL field] | [ID or "standard"] | [Transform or none] | [Y/N] | [Y/N or Y-if-empty] |

---

TAG LOGIC:

| Condition | Tag added | Tag removed |
|-----------|----------|------------|
| [Condition] | [Tag] | [Tag or None] |

---

GHL AUTOMATION TRIGGERS (what GHL automations fire based on tags or stage):

| Tag or stage | GHL automation triggered |
|-------------|------------------------|
| "New Lead" tag added | Speed-to-lead SMS sequence starts |
| Pipeline stage = "Call Booked" | Booking confirmation SMS fires |
| [Tag / Stage] | [GHL automation] |

---

FIELDS NOT TO OVERWRITE (update rules):

These fields in GHL should NEVER be overwritten by the sync once set:
- [Field name]: [Reason - e.g., "Sales rep assigns this manually"]

---

SYNC NOTES:

Phone format: [How phone is formatted before writing to GHL]
Email: Lowercase before writing
Error if GHL returns conflict: [How to handle]
```

## Quality Check

- [ ] Create and update logic are both documented
- [ ] Field mapping is complete with GHL field IDs for custom fields
- [ ] Update column specifies Y / N / Y-if-empty for every field
- [ ] Tag logic covers all source scenarios
- [ ] Fields that should not be overwritten are listed explicitly
- [ ] GHL automations triggered by tags or stages are documented
- [ ] No actual API keys or credentials in this document

## Status

Phase 3 complete.
