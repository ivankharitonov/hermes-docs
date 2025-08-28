---
title: "Settings sets"
description: "Create reusable defaults for expiration, reminders, and sender. Apply them to documents and templates to stay consistent."
audience: ["admins"]
keywords: ["e-sign", "settings", "expiration", "reminders", "notification sender"]
easyink_version: "web"
last_reviewed: "2025-08-28"
related: ["../how-to/create-and-send-document.md", "roles-permissions.md", "notification-senders.md", "environments.md", "../troubleshooting/sending.md"]
---

# Create and manage settings sets
**Applies to:** admins

## Overview
Use a **settings set** to bundle defaults you reuse on many documents: **expiration window (days/hours)**, **notification sender (email)**, **time zone**, **SMS rules (number + allowed hours)**, and **notification templates**. You can also enable **Send documents in e-mail attachments** if your org allows it.

- Create once. Reuse across senders and templates.
- Change the set later to update **future** sends that use it.  
  **Caution:** Changing a settings set typically **does not** modify already-sent sessions. Confirm whether live sessions are affected before editing.

## Example first
You want every NDA to expire in **7 days at 17:00 local time**, and you want emails to come from `signing@yourorg.com`. SMS reminders should only send between **08:00–21:00**.

**Example: “NDA – Standard” settings set**
- Time zone: **UTC** (or your org default)
- Expiration: **Add days to sign by date = 7**; **Add hours to sign by time = 17**  
  (Deadline occurs 7 days out at 17:00 in the set’s time zone.)
- Email sender: **From name** `EasyInk Team`; **From email** `signing@yourorg.com`
- **Send documents in e-mail attachments:** Off
- SMS: **Send SMS from number** `+1 415…`; **Allowed time** `08:00–21:00`
- Templates: set your **Signing notification**, **Reminder**, **Expired**, and **Completed** copy.

## Before you begin
- **Role:** **Administrator** with permission to **Manage settings sets**.
- **Access:** Open **Settings sets** from the left navigation.
- **Inputs:** Name, time zone, expiration (days + hours), email **From name/address**, optional SMS number & hours, and the notification templates you plan to use.
- **Environment:** Use a customer-safe test environment to validate sender behavior and SMS windows. See [Environments](environments.md).

## Steps

### 1. Create a settings set
1. Sign in to EasyInk.
2. Go to **Settings sets** and click **Add New Settings Set**.
3. Enter a **Setting Set Name** (e.g., *NDA – Standard*).
4. Set **Time zone** (controls deadlines and SMS windows).
5. Define the **expiration window**:  
   - **Add days to sign by date** – number of days before the session expires.  
   - **Add hours to sign by time** – the hour/minute of the deadline on that day.  
   **Caution:** Confirm whether the deadline is anchored to **Start** vs **Finalize** time for your tenant.
6. Configure **Email sender**:  
   - **Send from email name** and **Send from email address**. (Must match a verified sender.)  
   - (Optional) **Send documents in e-mail attachments** if your policy allows sending attachments.
7. Configure **SMS** (optional):  
   - **Send SMS from number** (choose a provisioned number).  
   - **Allowed time for sending SMS notifications** (e.g., **08:00 AM → 09:00 PM**).
8. Edit **Templates** (notifications):  
   - **Signing notification**, **Reminder**, **Expired**, **Completed**, **Voided**, plus **Terms & conditions** and **Instructions to signer** as needed. Click the **pencil** icon to edit each.
9. Click **Save & Close** to keep it as a **Draft**, or **Finalize** to make it available for use.  
   **Note:** You may see **Associated organizations** at the top. Assign organizations if your tenant requires it before **Finalize**.

### 2. Apply a settings set when sending
1. Start the **Create & send** flow.
2. In **Settings**, choose **Settings set** if your tenant exposes the selector; otherwise, the org default applies.
3. Review the summary on the **Review** step.
4. **Start now**.

### 3. Edit, duplicate, or archive a settings set
1. Go to **Settings sets**.
2. Select a set.
3. Choose **Edit**, **Duplicate**, or **Archive**.  
   - **Edit**: Change values for **future** sends.  
   - **Duplicate**: Create a variant (e.g., *NDA – 14 days*).  
   - **Archive**: Hide from pickers. Existing sessions keep their original settings. *(Confirm behavior for your tenant.)*

## Fields reference

| Name | Type | Required | Default | Description |
|---|---|---|---|---|
| Setting Set Name | text | Yes | — | Display name shown in the list. |
| Time zone | select | Yes | Org default | Time zone used for expiration and SMS quiet hours. |
| Add days to sign by date | integer | Yes | 0 | Number of days after anchor time when the session should expire. |
| Add hours to sign by time | integer (0–23) | Yes | 0 | Hour component of the expiration deadline on the target day. |
| Send from email name | text | No | — | Friendly **From** name recipients see. |
| Send from email address | email | No | — | **From** address; should be a verified sender. |
| Send documents in e-mail attachments | checkbox | No | Off | Sends signed documents as attachments (if enabled by policy). |
| Send SMS from number | select | No | — | Originating number for SMS notifications. |
| Allowed time for sending SMS notifications | time range | No | 08:00–21:00 | Quiet-hours window for SMS sending. |
| Templates | links | No | platform defaults | Edit text for invites, reminders, expired/voided/completed notices, terms, and instructions. |

**Note:** Field names reflect the current UI.

## Troubleshooting

| Symptom | Cause | Fix | Time to verify |
|---|---|---|---|
| Settings set stays **(Draft)** or isn’t selectable | Not **Finalized** or missing org association | Open the set → complete required fields → **Finalize**; add **Associated organizations** if required | Immediate |
| Signers are **not receiving reminders** | Reminder text not configured; sender not verified | Edit **Templates**; verify the **From** address per your sender policy | Next reminder window |
| Session **expired earlier** than expected | Wrong time zone or anchor time assumption | Check **Time zone**; confirm anchor time (Start vs Finalize) for expiration; adjust days/hours | Immediate after resend |
| **Settings set missing** in the send flow | Selector hidden for your tenant or set archived | Use the org default or ask an admin to expose the selector; unarchive the set | Immediate |
| Emails show the **wrong From** | Different default sender applied | Edit the set’s **Send from** fields or set the org default correctly | Next email |
| SMS not sent during the day | Quiet-hours window too restrictive | Expand **Allowed time** range | Next SMS window |

## FAQs
**Do changes to a settings set update live sessions?**  
Usually no. Most tenants snapshot settings at send time. Confirm with your admin.

**Can I override settings per recipient?**  
Only if the send flow exposes per-recipient overrides.

**Is there a limit to the number of settings sets?**  
TBD (confirm org-level limit).

**Can I export/import settings sets between environments?**  
TBD (UI export/import).

## Open questions (track for internal follow-up)
- Anchor time for expiration (Start vs Finalize vs creation).
- Whether **Finalize** locks fields vs allows later edits; impact on in-flight sessions.
- Behavior of live sessions and scheduled reminders if the set changes.
- What **Archive** does to usage and live sessions.
- Org limits: max settings sets per workspace/org.
- Sender verification scope: per workspace vs org-wide.
- Whether **Post-sign redirect** exists per set (not visible in current UI).
- Locale options to document (requested: **en-US**, **es-MX**); where language is selected (per participant vs per set).
- Can a settings set be attached as a **default** to a Template/Overlay; exact click-path.
- Staging differences (email/SMS policy, purge window) and any audit-log events for create/edit/archive.

## API
Not applicable today. *(Add cURL/Node/Python once API is public.)*

**Related reading**
- [Create and send a document](../how-to/create-and-send-document.md)
- [Roles and permissions](roles-permissions.md)
- [Notification senders](notification-senders.md)
- [Environments](environments.md)
- [Troubleshooting sending](../troubleshooting/sending.md)
