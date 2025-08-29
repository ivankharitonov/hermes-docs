---
title: "Template overlays"
description: "Pre-placed participants and fields you can apply to new signing sessions."
audience: ["admins", "senders"]
keywords: ["template overlays", "participants", "fields", "reusable"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["../how-to/create-and-send-document.md", "roles-permissions.md", "settings-sets.md", "../troubleshooting/sending.md"]
---

# Create and manage template overlays
**Applies to:** admins (create/manage), senders (apply)

## Overview
Use **template overlays** to save time on repeat documents (NDAs, onboarding packets, policy acks).  
An overlay stores **participants** (and optional signing order) plus **pre-placed fields** mapped to page positions.  
Senders then **apply** the overlay during session preparation right after they add a document.

**When to use**
- You send the same layout regularly.
- You want consistent **Signature**, **Full name**, **Date**, and other fields.
- You want to reduce mistakes from manual placement.

> **Note:** Overlays don’t replace your org’s **settings set**. The **From** address, reminders, and expiration still come from the settings set assigned to the organization.

## Example first
You routinely send an NDA that’s always 2 pages. Create the overlay **“NDA – Candidate”** with:
- Participants: **Candidate** (order 1) and **Hiring Manager** (order 2)
- Page 1: **Signature** (Candidate), **Date** (Candidate)
- Page 2: **Signature** (Hiring Manager), **Date** (Hiring Manager)

During a new session, upload the NDA and click **Apply template overlay → NDA – Candidate**. All fields appear in the right spots.

## Before you begin
- **Roles:**  
  - **Administrator** to create, edit, archive overlays.  
  - **Standard User** to apply overlays in a session.
- **Inputs:** A reference PDF (or an existing prepared session to “Save as template overlay”).
- **Environment:** In non-prod, verify email/SMS allow-lists before testing invitations.

## Create a template overlay (from scratch)
1. Go to **Template overlays** (left navigation).
2. Click **Add New Template Overlay**.
3. Enter **Name** and optional **Description**.
4. (Optional) Define default **Participants** and signing **Order**.
5. Upload a sample PDF (or choose a base) to place fields against the correct pages.
6. Place fields for each **active participant** on the page thumbnails.
7. Click **Save & Close** (keeps it **Draft**) or **Publish** to make it available to senders.

> **Tip:** Use a stable, final PDF as the base. If page order changes later, placements may misalign.

## Create a template overlay from a prepared session
1. Open an existing **Draft** session where you have already placed fields.
2. Select **More actions (⋯) → Save as template overlay**.
3. Name the overlay and review participant roles and field placements.
4. Click **Publish**.

> **Note:** If the document in the session has extra pages, remove unneeded placements before publishing.

## Apply a template overlay during a session
1. Create a new signing session and click **+ Add document** to upload the PDF.
2. In the document area, choose **Apply template overlay**.
3. Pick the overlay by name.  
   - If the overlay defines participants, they will be added automatically.  
   - If your tenant allows locking, locked placements can’t be moved by senders.
4. Review placements and make minor adjustments if needed.
5. **Finalize** and **Start now** when ready.

> **Tip:** If an overlay almost fits, adjust the fields and then **Save as template overlay** to create a variant.

## Edit, duplicate, or archive an overlay
- **Edit:** Update participants or field placements and **Publish** again.  
- **Duplicate:** Create a variant (e.g., different participant order).  
- **Archive:** Hides the overlay from pickers. Existing sessions already using it are unaffected.

> **Caution:** Publishing changes affects **future** sessions where the overlay is applied. It does not change already-started sessions.

## Field and behavior reference
| Item | Description |
|---|---|
| **Name** | Display name in pickers (e.g., *NDA – Candidate*). |
| **Description** | Optional internal notes about usage or scope. |
| **Participants** | Optional defaults (First Name/Last Name left blank; **Email** filled at send time). |
| **Order** | Optional signing order (1..n). |
| **Fields** | Pre-placed items like **Signature**, **Full name**, **Date**, **Initials**, etc. |
| **Page mapping** | Placements are bound to page index and coordinates. Changes in page order or scale may misalign. |
| **Locking** | If enabled by your tenant, admins can lock placements to prevent sender edits. |
| **Status** | **Draft**, **Published**, **Archived**. Only **Published** overlays are visible to senders. |

## Troubleshooting
| Symptom | Cause | Fix | Time to verify |
|---|---|---|---|
| Overlay not visible to senders | Status is **Draft** or **Archived** | **Publish** the overlay. | Immediate |
| Fields look shifted | Source PDF changed (page size/order) | Re-align fields; re-publish. Keep a canonical base PDF. | 2–5 min |
| Can’t move fields after apply | Locking enabled by admin | Edit the overlay (admin) or create a duplicate overlay with unlocked fields. | Immediate |
| Wrong participant on a field | Active participant switched during placement | Reassign the field to the correct participant in the overlay; re-publish. | 2–5 min |
| “Apply template overlay” not shown | Feature disabled in tenant or wrong permission | Ask an **Administrator** to enable or grant permission to **Apply signing session template overlay**. | Immediate |
| Overlay applies but no participants added | Overlay defines only placements | Add participants first in the session, or edit the overlay to include participants. | 1–2 min |

## FAQs
**Do overlays send emails or set expirations?**  
No. Those come from your org’s **settings set**.

**Can I restrict who can edit overlays?**  
Yes. Only **Administrators** can create/edit/archive overlays. **Standard Users** can apply them.

**What happens to sessions if I archive an overlay?**  
Existing sessions aren’t changed. The overlay just disappears from pickers for future sends.

**Can overlays include optional fields?**  
Yes. Optionality is set on the field when you place it in the overlay.

## API
Not applicable today. *(Add cURL/Node/Python once API is public.)*

**Related reading**
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)  
- See also: [Roles and permissions](./roles-permissions.md)  
- See also: [Settings sets](./settings-sets.md)  
- See also: [Troubleshooting: sending and signing](../troubleshooting/sending.md)
