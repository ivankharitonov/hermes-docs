---
title: "Create and start a signing session"
description: "Upload a document, add participants, place fields, finalize, and start a signing session."
audience: ["senders", "admins"]
keywords: ["signing session", "send document", "participants", "fields"]
easyink_version: "web"
last_reviewed: "2025-08-28"
related: ["../get-started/quickstart.md", "../admin/roles-permissions.md"]
---

# Create and start a signing session

**Applies to:** senders, admins

## Overview
Use a signing session to collect signatures on one or more documents. This guide follows the current UI flow and exact labels you’ll see.

## Before you begin
- **Role:** Standard User or Administrator.
- **Environment:** Use **Production** at `https://easyink.io`. If your organization has a customer-safe **test environment**, use the URL provided by your administrator.
- **Document:** PDF ready for signing.

**Note:** The email **From** address is set by your organization’s **settings set**. Senders can’t change it during the send flow.
**Tip:** For many recipients, use **Bulk Upload** at the top of the session editor.

## Steps

1. **Create the session**
   - From the left nav, click **New signing session**  
     *or* on **Home**, click **Start new signing session**.
   - In **Create new signing session**, enter a **Subject** (example: `2025 Handbook Signing – Mikhailova`) and click **Create**.

2. **Add a participant**
   - Click **Add Participant**.
   - In **Add New Participant**, fill **First Name**, **Last Name**, **Email**.  
     (Optional) Choose delivery method (**email** and/or **sms/text**), enter **Phone**, and set **Language of the signing session**.
   - Click **Save**.
   - **Tip:** If you need to sign as well, click **Add Myself**.

3. **Add the document**
   - Click **+ Add document** (top right of the editor) and choose your PDF.
   - The file appears under **UPLOADED DOCUMENTS** with a list of **Page** thumbnails.

4. **Place fields**
   - Select the correct **participant** in the left panel.
   - In the page list on the right, open the target page (e.g., **Page 14**).
   - From the left field palette, drag **Full name**, **Signature**, and **Date** onto the document.
   - **Note:** If you add more recipients later, ensure the intended recipient is active when placing each field.

5. **Finalize**
   - Click **Finalize** (bottom right).

6. **Start the session**
   - When prompted **Your signing session is ready**, click **Start now**.  
     (Or choose **Start later** to keep it in **Ready to start**.)

7. **Track status**
   - Go to **Home** and use the status filters:
     - **In progress** while recipients are signing.
     - **Finished** once all required actions are complete.

8. **Download the signed documents**
   - Open the session under **Finished**.
   - Click **Download All** to get the signed, validated PDF bundle.  
   - You’ll see the *Validated by Entrust* badge in the session view.

**Caution:** If you must change field placement after starting, you need the **Change signing session** permission. Otherwise, void and recreate the session.

---

## Example: manual fields on a PDF (one common path)

1. **Home → New signing session** → set **Subject** `2025 Handbook Signing – Mikhailova` → **Create**.  
2. **Add Participant** → First Name `Svetlana`, Last Name `Mikhailova`, Email `smikhailova@…` → delivery **email** → **Save**.  
3. **+ Add document** → choose `Handbook RU.pdf`.  
4. In the pages list, open **Page 14** → drag **Full name**, **Signature**, **Date** to their places.  
5. **Finalize** → prompt **Your signing session is ready** → **Start now**.  
6. **Home → In progress** to monitor; when complete, find it under **Finished**.  
7. Open the finished session → **Download All** to retrieve the signed and **validated** document.

---

## Troubleshooting

| Symptom | Likely cause | Fix | Time to verify |
|---|---|---|---|
| **Start now** prompt doesn’t appear | Session not finalized | Click **Finalize** first. | Immediate |
| **Finalize** is disabled | Required fields missing for at least one participant | Place all required fields; check the active participant. | Immediate |
| Fields applied to the wrong person | Wrong participant selected while placing fields | Select the intended participant in the left panel and re-place the fields. | Immediate |
| Recipient didn’t get email | Typo or spam filtering | Verify the email; **Resend** from the session view; ask recipient to check spam. | 1–5 min |
| Can’t edit an active session | Missing permission | Ask an admin for **Change signing session** or void and recreate. | Immediate |

## API
**Not applicable.** EasyInk currently supports web flows only.

**Related reading**
- See also: [Quickstart: send your first document](../get-started/quickstart.md)  
- See also: [Roles and permissions](../admin/roles-permissions.md)
