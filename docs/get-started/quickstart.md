---
title: "Quickstart: send your first document"
description: "Start a signing session and track status in under 10 minutes."
audience: ["senders", "admins"]
keywords: ["e-sign", "signing session", "quickstart"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["../how-to/create-and-send-document.md", "../admin/roles-permissions.md", "../troubleshooting/sending.md"]
---

# Quickstart: send your first document

> **Goal:** upload a document, add participants, start a signing session, and see its status.

## Prerequisites
- EasyInk account with **Standard User** or **Administrator** role.
- Environment: Production at `https://easyink.io` (or your org’s test URL).

## 1. Create a signing session
1. Go to **Home**.
2. Click **New signing session**.
3. In **Create new signing session**, enter a **Subject** (example: `2025 Handbook Signing – Mikhailova`) and click **Create**.

## 2. Add participants
1. Click **Add Participant**.
2. Fill **First Name**, **Last Name**, **Email**.  
   (Optional) Choose delivery method (**Email** and/or **SMS**), add **Phone**, and set **Language**.
3. Click **Save**. Add more participants as needed.
4. (Optional) Set a **Signing order** if some participants must sign before others.

**Note:** Your admin controls whether you can apply **template overlays** and which **notification senders** are available.

## 3. Add your document and place fields
1. Click **+ Add document** and select your PDF.
2. In the page list, open the target page (e.g., **Page 14**).
3. Drag **Full name**, **Signature**, and **Date** fields into position for the active participant.

**Tip:** Ensure the intended participant is selected in the left panel before placing fields.

## 4. Finalize and start
1. Click **Finalize**.
2. When prompted **Your signing session is ready**, click **Start now**.  
   (Or choose **Start later** to keep it in **Ready to start**.)

## 5. Track status
Use the status filters on **Home**:
- **In progress** while participants are signing.
- **Finished** after all required actions are complete.

**Tip:** Click a session to view details, resend notifications, or (with permission) **Void** the session.

## Troubleshooting
| Symptom | Likely cause | Fix |
|---|---|---|
| Participant did not receive email | Spam filtering or typo | Verify the email address; ask the participant to check Spam/All Mail; **Resend** the invitation. |
| **Start now** does not appear | Session not finalized | Click **Finalize** first. |
| Can’t edit after start | Permission or session state | Ask an **Administrator** to enable **Change signing session** or **Void** and recreate. |

## Next steps
- Create a reusable **template overlay** so senders don’t manually place fields.
- Configure **notification senders** and **settings sets** for consistent reminders and expirations.

**Related reading**
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)  
- See also: [Roles and permissions](../admin/roles-permissions.md)  
- See also: [Troubleshooting: sending and signing](../troubleshooting/sending.md)
