---
title: "Template overlays"
description: "Preconfigure fields, roles, and notifications on top of a base file or template so senders can launch sessions fast and error-free."
audience: ["admins"]
keywords: ["e-sign", "templates", "overlays", "fields", "roles"]
easyink_version: "web"
last_reviewed: "2025-08-28"
related: ["../how-to/create-and-send-document.md", "settings-sets.md", "roles-permissions.md", "notification-senders.md", "../troubleshooting/sending.md"]
---

# Create and manage template overlays
**Applies to:** admins (senders use overlays created by admins)

## Overview
A **template overlay** is a reusable layer that adds **recipient roles**, **placed fields**, and **notification text** on top of a base file or template. Use overlays when the same document needs the same fields and roles every time.

- Reduce errors by fixing role names and signing order.
- Save time by pre-placing signatures, initials, text, and checkboxes.
- Keep messaging consistent with prewritten **Instructions**, **Terms**, and **Notifications**.

## Example first
You send the same NDA to candidates weekly. Create an overlay named **“NDA – Candidate”**:

- **Roles:** `Candidate (Signer)`, `Recruiter (CC)`
- **Fields (Candidate):** Signature on page 2, Initials on each page, Text for Full Name
- **Order:** Candidate signs → Recruiter is CC'ed
- **Messaging:** Pre-filled **Instructions to signer** and **Terms and conditions**
- **Defaults:** Attach the **Settings set** “NDA – Standard” for expiry and sender

Next time, senders choose this overlay and only enter recipient emails.

## Before you begin
- **Role:** Admin with permission to create/edit templates and overlays.
- **Access:** **Manage templates** from the left navigation.
- **Inputs:** Base file (PDF/DOCX), overlay name, roles, field placements, optional default **Settings set**.
- **Environment:** Build and test in a non-prod environment first.

## Steps

### 1. Create an overlay
1. Go to **Manage templates**.
2. Click **Add new** (or similar) and choose **Create overlay**.  
   **Note:** If your tenant uses “Template” first, select the base template then **Add overlay**. *(TBD: exact button labels)*
3. Enter an **Overlay name** and (optional) **Description**.
4. Select the **Base file or template** this overlay will apply to.

### 2. Define recipient roles and order
1. Add each **Role** (e.g., *Signer*, *Approver*, *CC*).
2. Set the **Signing order** if sequential signing is required.  
   **Tip:** Use descriptive role names like *Candidate (Signer)* to help senders pick the right person.

### 3. Place fields on the document
1. Open the field editor.
2. Drag required fields (e.g., **Signature**, **Initials**, **Date**, **Text**, **Checkbox**) to the correct spots.
3. Assign each field to a **Role**.
4. Set **required/optional** and validation where available. *(TBD: validation types)*

### 4. Configure messages and defaults
1. Edit **Instructions to signer** and **Terms and conditions** (overlay-specific).
2. Choose notification templates for **Invite**, **Reminder**, **Completed**, **Expired**, **Voided** if the overlay supports them. *(TBD: which notices are per-overlay vs global)*
3. (Optional) Set a default **Settings set** for this overlay (expiry, sender, SMS hours).

### 5. Publish the overlay
1. **Save** your changes.
2. Click **Publish** (or **Finalize**) to make the overlay selectable for senders.  
   **Caution:** Overlays left in **Draft** will not appear in the send flow.

## Use an overlay when sending
1. Start the **Create & send** flow.
2. Choose your **Template** and then select the **Overlay**.
3. Add recipients to the predefined roles and review the summary.
4. Start the session.

## Editing and versioning
- **Edit:** Changes apply to **future** sessions that use the overlay.
- **Duplicate:** Make a variant (e.g., *NDA – Vendor*).
- **Archive:** Hide from selection without deleting historical usage. *(TBD: exact impact on live sessions)*

## Troubleshooting

| Symptom | Cause | Fix | Time to verify |
|---|---|---|---|
| Overlay not visible to senders | Not **Published/Finalized** or archived | Publish/Unarchive the overlay | Immediate |
| Fields don’t show for a recipient | Field not assigned to the correct **Role** | Reassign fields to proper role and republish | Immediate |
| Wrong signing order | Roles have same order or out of sequence | Update **Signing order** and republish | Immediate |
| Sender can’t change a role | Overlay locks role names/types | Provide a flexible overlay variant or create a new overlay | Immediate |
| Emails show wrong text | Using global templates instead of overlay messages | Edit overlay’s **Instructions/Terms/Notifications**, republish | Next email |

## FAQs
**Can senders change roles or fields at send time?**  
Only if your overlay allows it. Most teams lock fields/roles in overlays to reduce risk. *(TBD: per-tenant controls)*

**Can one overlay point to multiple base files?**  
Typically no—one overlay per base file/template. *(Confirm for your tenant.)*

**Do edits affect in-flight sessions?**  
Usually no. Edits apply to future sends that use the overlay.

**Can I set a default Settings set per overlay?**  
Yes, if exposed by your tenant. *(TBD: exact control and location)*

## Open questions (track for internal follow-up)
- Exact UI labels and click-path (**Create overlay**, **Publish/Finalize**, where **Settings set** is attached).
- Which **notification texts** are per-overlay vs global.
- Field **validation** types (regex, date formats, required behavior).
- Whether overlays can **lock** or **allow** sender edits; per-tenant toggle.
- Impact of **Archive** on live sessions already using the overlay.
- Export/import or **clone** behavior across environments.
- Limits: max overlays per org/workspace.

## API
Not applicable today. *(Add cURL/Node/Python once API is public.)*

**Related reading**
- [Create and send a document](../how-to/create-and-send-document.md)
- [Settings sets](settings-sets.md)
- [Roles and permissions](roles-permissions.md)
- [Notification senders](notification-senders.md)
- [Troubleshooting sending](../troubleshooting/sending.md)
