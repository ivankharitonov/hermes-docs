---
title: "Troubleshooting: sending and signing"
description: "Fix common issues with Finalize, Start now, delivery, and status."
audience: ["senders", "admins"]
keywords: ["troubleshooting", "email delivery", "finalize", "start now", "void"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["../get-started/quickstart.md", "../how-to/create-and-send-document.md", "../admin/roles-permissions.md", "../admin/notification-senders.md", "../admin/environments.md"]
---

# Troubleshooting: sending and signing

Use this guide to diagnose and fix issues during preparation, sending, and completion of signing sessions.

> **Tip:** Open the session while you troubleshoot. Most fixes are immediate after you refresh the session page.

## Quick diagnostic
1. **Check the session state** (Draft → Ready to start → In progress → Finished).
2. **Confirm your role** (some actions require **Administrator**).
3. **Verify participants** (names, emails, order).
4. **Review fields** (each required signer has at least one required field).
5. **Confirm environment rules** (allow-lists, quiet hours, purge windows).

## Common symptoms and fixes

| Symptom | Likely cause | Fix | Time to verify |
|---|---|---|---|
| **Finalize** is disabled | Required fields missing for at least one participant | Select each participant and page; add at least one required field (e.g., **Signature**); try **Finalize** again. | 1–2 min |
| **Start now** not shown after Finalize | You closed the prompt or the page didn’t refresh | Reopen the session and click **Start now** from the banner; or **Finalize** again if you made edits. | 1–2 min |
| Participant didn’t get invite | Typo, spam filtering, or non-prod allow-list | Correct the **Email** and **Resend**; ask the participant to check **Spam/All Mail**; in test, use an allow-listed domain. | 1–5 min |
| Wrong participant name on a field | Field placed while the wrong participant was active | Select the correct participant; move or reassign the field; **Finalize** again. | 2–5 min |
| Can’t edit after starting | Session state or missing permission | Ask an **Administrator** to use **Change signing session** (if enabled) or **Void** and recreate. | 2–10 min |
| Status stuck **In progress** | A participant hasn’t completed required fields | Open **Activity**; locate the participant; **Resend** or copy the secure signing link (if enabled) and share. | Immediate |
| **Download All** missing or empty | Session not **Finished** or files still generating | Wait a minute and refresh; if still missing, confirm all participants finished. | 1–3 min |
| Invite shows the wrong **From** | Organization uses a different **settings set** | Check **Associated organizations** on the settings set; update the **From** fields and **Finalize**. | Next email |
| SMS never arrives | SMS disabled, outside quiet hours, or wrong number | Check **settings set** SMS window; confirm a routable test number; retry. | Next SMS window |
| Webhook consumer sees nothing | Webhooks disabled or wrong endpoint for this environment | Enable webhooks for the environment and point to the right endpoint; resend a test. | 5–10 min |
| Link invalid or expired | Expiration window elapsed or link copied incorrectly | Extend expiry (if supported) or **Resend** a fresh invite; avoid forwarding raw links via chat. | Immediate |

## Email delivery checklist
1. Open the session and verify the participant **Email** is correct.
2. **Resend** the invitation and ask the participant to check **Inbox**, **Spam**, and **All Mail**.
3. If permitted in your tenant, **Copy signing link** and share it securely.
4. Confirm the organization’s **notification sender** (From name/address) is correct.
5. In non-prod, make sure the email domain is on the **allow-list** or routed to a sandbox inbox.

> **Caution:** Do not send test invitations to real external participants from non-production environments.

## Permissions that affect fixes
Some actions require **Administrator** role or specific capabilities:
- **Change signing session** (edit after start)
- **Void signing session**
- **Manage settings sets** and **notification senders**
- **Manage template overlays**

See the [Roles and permissions](../admin/roles-permissions.md) matrix for details.

## Environment notes (testing safely)
- **Staging:** Prefer email allow-lists or sandbox inboxes; keep short expirations.
- **Developer Test:** Email/SMS usually off or sandboxed; frequent purges may remove data.
- **Production:** Use verified notification senders and real endpoints.

> **Note:** If policies are **TBD** in your tenant, coordinate with an admin and update the [Environments](../admin/environments.md) page when decisions are finalized.

**Related reading**
- See also: [Quickstart: send your first document](../get-started/quickstart.md)  
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)  
- See also: [Roles and permissions](../admin/roles-permissions.md)  
- See also: [Notification senders](../admin/notification-senders.md)  
- See also: [Environments (internal)](../admin/environments.md)
