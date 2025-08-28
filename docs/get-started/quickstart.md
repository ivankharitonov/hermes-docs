---
title: "Quickstart: send your first document"
description: "Start a signing session and track status in under 10 minutes."
audience: ["senders", "admins"]
keywords: ["e-sign", "signing session", "quickstart"]
easyink_version: "web"
last_reviewed: "2025-08-27"
related: ["../how-to/create-and-send-document.md", "../admin/roles-permissions.md"]
---

# Quickstart: send your first document

**Goal:** upload a document, add recipients, start a signing session, and see its status.

## Prerequisites
- An EasyInk account with **Standard User** or **Administrator** role.
- Access to **staging** (`https://staging.easyink.io`) or **production** (`https://easyink.io`).
- A PDF or DOCX to sign.  
**Note:** If your org enforces SSO, use **OneLogin** on the sign-in page.

## 1. Sign in
1. Open your environment URL.
2. Enter **Username** and **Password**, or choose **OneLogin**.
3. Click **Login**.

**Tip:** If you can’t sign in, contact your admin to confirm your role and SSO access.

## 2. Start a new signing session
**UI**
1. From the left navigation, click **New signing session** (or **Home → Start new signing session**).
2. Upload your document(s).
3. (Optional) Select a **template overlay** if your admin prepared one.
4. Click **Continue**.

## 3. Add recipients
1. Add each recipient’s **Name** and **Email**.
2. (Optional) Set a **signing order** if some recipients must sign before others.
3. (Optional) Choose a **notification sender** and a **settings set** (e.g., reminders, expirations) if available in your org.
4. Click **Review**.

**Note:** Your admin controls whether you can apply template overlays and which notification senders are available.

## 4. Start the session
1. Review recipients and settings.
2. Click **Start signing session**.

Recipients receive invitations to sign. You can track progress on the dashboard.

## 5. Track status
Use the status filters on **Home**:
- **Need to sign**, **Draft**, **Ready to start**, **In progress**, **Finished**, **Declined**, **Voided**, **Expired**.

**Tip:** Click a session to view details, resend notifications, or (with permission) **Void** the session.

## Troubleshooting
| Symptom | Likely cause | Fix |
|---|---|---|
| Recipient did not receive email | Spam filtering or typo | Verify email address; ask recipient to check spam; resend notification. |
| **Start signing session** disabled | Missing permission or incomplete setup | Ask an **Administrator** to confirm your role and required fields. |
| Can’t apply a template overlay | Overlay not shared with your org/role | Ask an **Administrator** to grant access or apply the overlay for you. |

## Next steps
- Create a reusable **template overlay** so senders don’t manually place fields.
- Configure **notification senders** and **settings sets** for consistent reminders and expirations.

**Related reading**
- See also: [Create and send a document](../how-to/create-and-send-document.md)  
- See also: [Roles and permissions](../admin/roles-permissions.md)
