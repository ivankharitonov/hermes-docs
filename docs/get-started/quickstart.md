---
title: "Quickstart: send your first document"
description: "Start a signing session and track status in under 10 minutes."
audience: ["senders", "admins"]
keywords: ["e-sign", "signing session", "quickstart"]
easyink_version: "web"
last_reviewed: "2025-01-27"
related: ["../how-to/create-and-send-document.md", "../admin/roles-permissions.md"]
---

# Quickstart: send your first document

**Goal:** upload a document, add recipients, start a signing session, and see its status.

## Prerequisites
- An EasyInk account with **Standard User** or **Administrator** role.
- **Environment:** Use **Production** at `https://easyink.io`. If your organization has a customer-safe **test environment**, use the URL provided by your administrator.
- A PDF to sign.  
**Note:** If your org enforces SSO, use **OneLogin** on the sign-in page.

## 1. Sign in
1. Open `https://easyink.io`.
2. Enter **Username** and **Password**, or choose **OneLogin**.
3. Click **Login**.

**Tip:** If you can’t sign in, contact your admin to confirm your role and SSO access.

## 2. Start a new signing session
1. From the left navigation, click **New signing session**  
   *or* on **Home**, click **Start new signing session**.
2. In **Create new signing session**, enter a **Subject** (example: `2025 Handbook Signing – Mikhailova`) and click **Create**.

## 3. Add recipients
1. Click **Add Participant**.
2. Fill **First Name**, **Last Name**, **Email**.  
   (Optional) Choose delivery method (**email** and/or **sms/text**), add **Phone**, and set **Language**.
3. Click **Save**. Add more participants as needed.
4. (Optional) Set a **signing order** if some recipients must sign before others.

**Note:** Your admin controls whether you can apply template overlays and which notification senders are available.

## 4. Add your document and place fields
1. Click **+ Add document** and select your PDF.
2. In the page list, open the target page (e.g., **Page 14**).
3. Drag **Full name**, **Signature**, and **Date** fields into position for the active recipient.

**Tip:** Ensure the intended recipient is selected in the left panel before placing fields.

## 5. Finalize and start
1. Click **Finalize**.
2. When prompted **Your signing session is ready**, click **Start now**.  
   (Or choose **Start later** to keep it in **Ready to start**.)

## 6. Track status
Use the status filters on **Home**:
- **In progress** while recipients are signing.
- **Finished** after all required actions are complete.

**Tip:** Click a session to view details, resend notifications, or (with permission) **Void** the session.

## Troubleshooting
| Symptom | Likely cause | Fix |
|---|---|---|
| Recipient did not receive email | Spam filtering or typo | Verify email address; ask recipient to check spam; resend notification. |
| **Start now** does not appear | Session not finalized | Click **Finalize** first. |
| Can’t edit after start | Permission or session state | Ask an **Administrator** to enable **Change signing session** or void and recreate. |

## Next steps
- Create a reusable **template overlay** so senders don’t manually place fields.
- Configure **notification senders** and **settings sets** for consistent reminders and expirations.

**Related reading**
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)  
- See also: [Roles and permissions](../admin/roles-permissions.md)
