---
title: "Settings sets"
description: "Define one shared sender and expiration rules per organization. Multiple orgs can reuse the same settings set."
audience: ["admins"]
keywords: ["e-sign", "settings", "expiration", "notification sender", "organizations"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["../how-to/create-and-send-document.md", "roles-permissions.md", "notification-senders.md", "environments.md", "../troubleshooting/sending.md"]
---

# Create and manage settings sets
**Applies to:** admins

## Overview
A **settings set** bundles defaults your organization uses when sending documents:

- **Notification sender** (From name + From email)
- **Expiration window** (add days / add hours)
- **Time zone**
- **SMS rules** (send-from number + allowed hours)
- **Notification templates** (invite, reminder, completed, expired, voided, etc.)

**How it works**
- **Each user belongs to exactly one organization.**
- **Each organization uses exactly one settings set.** You assign the set to the org once; senders don’t choose per session.
- **A settings set can be shared by many organizations.** The **sender** defined in the set applies to **all** organizations that use it.

**Caution:** Changing a settings set updates **future** sessions for organizations that use it. It typically **does not** change already-sent sessions.

## Example first
You manage two orgs—**Sales** and **HR**—that should send from the same mailbox.

- Create **Set: “Default – Corp”**
  - Time zone: **UTC**
  - Add days to sign by date: **7**
  - Add hours to sign by time: **17**
  - Send from email name: **EasyInk Team**
  - Send from email address: **signing@yourorg.com**
  - SMS hours: **08:00–21:00**
- **Associate organizations:** Sales, HR
- **Finalize**

Both orgs will send emails from `signing@yourorg.com`. If you later change the sender, new sessions from both orgs use the new address.

## Before you begin
- **Role:** Administrator with permission to **Manage settings sets**.
- **Access:** **Settings sets** in the left navigation.
- **Inputs:** Name, time zone, expiration (days + hours), **From** name/address, optional SMS number & hours; which **organizations** should use this set.
- **Environment:** Test in a non-prod environment first. See [Environments](environments.md).

## Steps

### 1) Create a settings set
1. Go to **Settings sets** → **Add New Settings Set**.
2. Enter a **Setting Set Name** (e.g., *Default – Corp*).
3. Set **Time zone**.
4. Define the **expiration window**:  
   - **Add days to sign by date**  
   - **Add hours to sign by time**
5. Configure **Email sender**:  
   - **Send from email name**  
   - **Send from email address** (must be a verified sender per your policy)
6. (Optional) Configure **SMS**: **Send SMS from number** and **Allowed time for sending SMS notifications**.
7. (Optional) Open **Templates** and edit your invite, reminder, completed, expired, and voided messages.
8. Click **Save & Close** (keeps it **Draft**) or continue to assign organizations.

### 2) Assign the settings set to organizations
1. In the set editor, use **Associated organizations** (top of page).
2. Add the organizations that should use this set.
3. Click **Finalize**.

**Note:** Once finalized and associated, this set becomes the **org default**. Senders in those orgs will not pick a different set during the send flow.

### 3) Edit, duplicate, or archive
- **Edit:** Adjust fields and **Save & Close** / **Finalize** again. Affects **future** sessions from associated orgs.
- **Duplicate:** Create a variant (e.g., different sender or expiry) and associate to other orgs.
- **Archive:** Hide the set from new org associations. Existing org associations remain until you reassign them.

## Fields reference
| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| Setting Set Name | text | Yes | — | Display name of the set. |
| Time zone | select | Yes | Org default | Used for deadlines and SMS windows. |
| Add days to sign by date | integer | Yes | 0 | Days until the session expires. |
| Add hours to sign by time | integer (0–23) | Yes | 0 | Hour/minute of the deadline on the target day. |
| Send from email name | text | Yes | — | Friendly **From** name. |
| Send from email address | email | Yes | — | **From** address; applies to **all organizations** using this set. |
| Send documents in e-mail attachments | checkbox | No | Off | Include signed docs as attachments if allowed by policy. |
| Send SMS from number | select | No | — | Originating number for SMS notifications. |
| Allowed time for sending SMS notifications | time range | No | 08:00–21:00 | Quiet-hours window for SMS. |
| Templates | links | No | Platform defaults | Edit text for invites, reminders, completed, expired, voided, terms, instructions. |
| Associated organizations | selector | Yes (to activate) | — | Organizations that **use** this set. One set per org; a set can be shared across many orgs. |

## Troubleshooting
| Symptom | Cause | Fix | Time to verify |
|---|---|---|---|
| Emails show an unexpected **From** | Your org is associated to a different settings set | Open the set and check **Associated organizations**; reassign the org if needed | Immediate |
| Sender can’t change the **From** address in the send flow | Sender selection is controlled by the **org’s settings set** | Update the **Send from** fields in the set, then **Finalize** | Next email |
| Set is **Draft** and not in effect | Not **Finalized** or no orgs associated | Add **Associated organizations**, then **Finalize** | Immediate |
| Sessions expire too early/late | Wrong time zone or days/hours | Adjust **Time zone** and expiration fields; resend | Immediate after resend |
| SMS not delivered during the day | Quiet hours too tight | Widen **Allowed time** range | Next SMS window |

## FAQs
**Can one settings set be used by multiple organizations?**  
Yes. Add each org in **Associated organizations**.

**Can an organization use more than one settings set?**  
No. Each organization has **one** applied settings set at a time.

**Can senders override the sender per session?**  
No. The **From** address is defined in the settings set used by the org.

**Do edits affect sessions already sent?**  
No. Edits apply to **future** sessions.

## API
Not applicable today. *(Add cURL/Node/Python once API is public.)*

**Related reading**
- [Create and send a document](../how-to/create-and-send-document.md)
- [Roles and permissions](roles-permissions.md)
- [Notification senders](notification-senders.md)
- [Environments](environments.md)
- [Troubleshooting sending](../troubleshooting/sending.md)
