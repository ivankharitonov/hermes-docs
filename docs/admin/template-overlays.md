---
title: "Template overlays"
description: "Create reusable overlays (participants + placed fields) and apply them to an uploaded file during session preparation."
audience: ["admins"]
keywords: ["e-sign", "templates", "overlays", "participants", "fields"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["../how-to/create-and-send-document.md", "settings-sets.md", "roles-permissions.md", "notification-senders.md", "../troubleshooting/sending.md"]
---

# Create and manage template overlays
**Applies to:** admins

## Overview
A **template overlay** predefines:
- **Participants** (who signs)
- **Placed fields** (Initials, Signature, Date, Checkbox, Free text, Full name, Date Time Signature)

Overlays live under **Manage templates** and are **applied during session preparation** after you add a document.

## Example first
You send the same NDA weekly. Build an overlay **"NDA — Candidate"** with:
- Participant: **Candidate** (Signer)
- Fields: **Signature** on page 2, **Initials** on each page, **Full name** on page 1

During a new session, upload the NDA, open the document menu, and choose **Apply template overlay**. Fields appear in the right places. Enter the Candidate's email and finalize.

## Before you begin
- **Role:** Admin with permission to manage templates/overlays (see [Roles and permissions](roles-permissions.md)).
- **Access:** **Manage templates** (to create/edit overlays) and **New signing session** (to apply overlays).
- **Inputs:** Overlay name, base file, participants, field placements.
- **Environment:** Build and test in a non-prod tenant first.

## Create an overlay (from Manage templates)
1. Go to **Manage templates**.
2. (Optional) **Add folder** to organize overlays.
3. Click **Create new template** → Name the overlay → **Create**.
4. Click **Add document** (top-right) and upload the base file.
5. **Add Participant** in the left panel and name the participant(s).
6. Drag fields from the left palette onto pages (make sure the correct participant is selected).
7. Click **Finalize** (bottom-right). The overlay is now available to apply.

## Apply an overlay during session preparation
1. Start a **New signing session**.
2. Click **Add document** and upload your file.
3. In **UPLOADED DOCUMENTS**, open the document's menu (⋯) and choose **Apply template overlay**.
4. Pick your overlay. Fields and participants are added to the session.
5. Use **+ Add Myself** if you are also a participant; **Bulk Upload** is available when adding many participants/files (if enabled).
6. Enter emails for the predefined participants and complete the session.

**Tip:** If you fine-tune placements ad-hoc and want to reuse them, use the same menu (⋯) and select **Save as template overlay**.

## Edit or duplicate an overlay
- From **Manage templates**, locate the overlay, click the **pencil** icon to edit, then **Finalize** again.
- To create a variant (e.g., different field set), duplicate the overlay (if your build supports duplication) or **Save as template overlay** from a prepared session.

## UI reference (session + overlay)
| UI label | Where | Purpose |
|---|---|---|
| **Add Participant** | Overlay editor | Create a participant. |
| **Add document** | Overlay editor / Session | Attach/replace the base file. |
| **Bulk Upload** | Session | Upload participants/files in bulk (if enabled). |
| **+ Add Myself** | Session | Add yourself as a participant quickly. |
| **Apply template overlay** | Session → Uploaded documents (⋯) | Apply an existing overlay to the uploaded file. |
| **Save as template overlay** | Session → Uploaded documents (⋯) | Save current placements as a reusable overlay. |
| **Finalize** | Overlay editor | Publish the overlay for use. |

## Troubleshooting
| Symptom | Cause | Fix | Time to verify |
|---|---|---|---|
| **Apply template overlay** not visible | No document uploaded yet | Click **Add document**, then open the document menu (⋯) | Immediate |
| Overlay fields apply to the wrong person | Wrong participant selected during design | Re-edit overlay and reassign fields; **Finalize** | Immediate |
| Overlay doesn’t appear in the picker | Overlay still **Draft** | Open overlay and **Finalize** | Immediate |
| Sender can’t modify fields after applying | Overlay locks placements by design | Create a flexible variant or edit ad-hoc and **Save as template overlay** | Immediate |

## FAQs
**Can overlays include multiple participants and many pages of fields?**  
Yes. Add all participants you need and place fields across pages.

**Can I reuse overlays across different documents?**  
Overlays are tied to page geometry; reuse only with the same or equivalent base file.

**Do changes to an overlay affect already prepared sessions?**  
No. Edits apply to **future** sessions where the overlay is applied.

## API
Not applicable today. *(Add cURL/Node/Python once API is public.)*

**Related reading**
- [Create and send a document](../how-to/create-and-send-document.md)
- [Settings sets](settings-sets.md)
- [Roles and permissions](roles-permissions.md)
- [Notification senders](notification-senders.md)
- [Troubleshooting sending](../troubleshooting/sending.md)
