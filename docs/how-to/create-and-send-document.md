---
title: "Create and start a signing session"
description: "Upload your document, add participants, place fields, finalize, and start."
audience: ["senders"]
keywords: ["e-sign", "signing session", "participants"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["../get-started/quickstart.md", "../admin/roles-permissions.md"]
---

# Create and start a signing session
**Applies to:** senders

## Overview
Use this guide to send a document for e-signature. You will:
1) create a session, 2) add participants, 3) upload your PDF and place fields, 4) **Finalize**, and 5) **Start now**.

**Tip:** If you send the same layout often, set up a **template overlay** so you don’t have to place fields every time.

## Before you begin
- **Role required:** **Standard User** or **Administrator**.
- **Access:** EasyInk web app (Production) or your org’s test URL.
- **Inputs:** A prepared PDF (flattened forms recommended).
- **Optional:** A **template overlay** and a configured **notification sender**.
- **Environment note:** In non-prod, ask an admin about outbound email/SMS allow-lists.

## Steps

### 1) Create a session
1. Go to **Home** → click **New signing session**.
2. In **Create new signing session**, enter a clear **Subject** (for example, `Q3 NDA – S. Zhang`).
3. Click **Create**.

### 2) Add participants
1. Click **Add Participant**.
2. Fill **First Name**, **Last Name**, **Email**.  
   (Optional) Choose delivery method (**Email** and/or **SMS**), add **Phone**, and set **Language**.
3. Click **Save**. Repeat for additional participants.
4. (Optional) Set **Signing order** if one participant must sign before others.

> **Tip:** Keep participant names consistent with your HR/CRM to simplify audits.

### 3) Upload your document
1. Click **+ Add document** and select your PDF.
2. Wait for the upload to finish. The page thumbnails appear on the left.

> **Note:** If available in your tenant, click **Apply template overlay** to preload participants and fields.

### 4) Place fields
1. Select the **active participant** in the left panel.
2. Drag fields onto the page (for example, **Full name**, **Signature**, **Date**).
3. Repeat for each participant and page that needs input.

> **Tip:** Place at least one **Signature** field for each required signer. Use **Date** for signing date, not text boxes.

### 5) Finalize and start
1. Click **Finalize** to lock the preparation.
2. In the prompt, choose **Start now** to send invitations immediately.  
   Or choose **Start later** to keep the session in **Ready to start**.

> **Caution:** Starting a session sends notifications to participants based on your **settings set** and **notification sender**. Double-check participant emails before you start.

## Track progress and manage
- Use status filters on **Home** (**Draft**, **Ready to start**, **In progress**, **Finished**).
- Open a session to **Resend** invitations, view activity, or (with permission) **Void** the session.
- After all participants sign, click **Download All** to get the signed PDF bundle and audit trail.

## Troubleshooting

| Symptom | Cause | Fix | Time to verify |
|---|---|---|---|
| **Finalize** is disabled | Missing required fields for one or more participants | Select each participant and page; add at least one required field; try Finalize again. | 1–2 min |
| **Start now** doesn’t appear after Finalize | Page not refreshed or you closed the prompt | Reopen the session and click **Start now** from the banner; or finalize again if you added changes. | 1–2 min |
| Participant didn’t get invite | Typo, spam filtering, or non-prod allow-list | Correct the email and **Resend**; ask the participant to check Spam/All Mail; in test, use an allow-listed domain. | 1–5 min |
| Fields show the wrong participant name | Placed while the wrong participant was active | Delete/move those fields with the correct participant selected; re-Finalize. | 2–5 min |
| Can’t edit after starting | Session state or missing permission | Ask an **Administrator** to use **Change signing session** (if enabled) or **Void** and recreate. | 2–10 min |

## API
Not applicable today. (Add cURL/Node/Python once API is public.)

**Related reading**
- See also: [Quickstart: send your first document](../get-started/quickstart.md)  
- See also: [Roles and permissions](../admin/roles-permissions.md)  
- See also: [Template overlays](../admin/template-overlays.md)  
- See also: [Troubleshooting: sending and signing](../troubleshooting/sending.md)
