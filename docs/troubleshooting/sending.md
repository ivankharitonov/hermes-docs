---
title: "Troubleshooting: sending and signing"
description: "Fix common issues with invitations, field placement, session states, and downloads."
audience: ["senders", "admins"]
keywords: ["troubleshooting", "email delivery", "statuses", "permissions"]
easyink_version: "web"
last_reviewed: "2025-08-28"
related: ["../get-started/quickstart.md", "../how-to/create-and-send-document.md", "../admin/roles-permissions.md"]
---

# Troubleshooting: sending and signing

Use this guide to resolve the most frequent problems when starting a signing session, getting participants to sign, and downloading results.

**Quick wins (try first)**
1. Confirm the session is **Finalized** and you clicked **Start now**.
2. Verify each participant has a valid **Email** (or SMS if used) and the correct **Language**.
3. Make sure fields were placed for the **active participant** before finalizing.
4. Resend the invitation from the session view and ask participants to check **Spam**.
5. If you need edits after starting and **Change signing session** is disabled for your role, ask an **Administrator** or **Void** and recreate.

---

## Symptoms and fast fixes

| Symptom | Likely cause | Fix | Time to verify |
|---|---|---|---|
| **Start now** prompt doesn't appear | Session not finalized | Click **Finalize**; try starting again. | Immediate |
| **Finalize** is disabled | Required fields are missing for one or more participants | Select each participant, place mandatory fields (e.g., **Signature**, **Full name**, **Date**). | Immediate |
| Participant didn't get invite | Typo, spam filtering, or blocked test domain | Correct the email; **Resend** invite; ask participant to check Spam/All Mail; if testing, use an allow-listed domain. | 1–5 min |
| Fields saved to the wrong person | Wrong participant was active during placement | Select the intended participant in the left panel; re-place fields; re-**Finalize**. | Immediate |
| Session stuck in **Ready to start** | You chose **Start later** | Open the draft and click **Start**. | Immediate |
| Session shows **Declined** | Participant rejected signing | Add or replace the participant; or create a new session. | Immediate |
| Session shows **Expired** | Expiration policy lapsed | Create a new session (or extend in advance using your **Settings set**, if allowed). | Immediate |
| Can't edit active session | Role lacks **Change signing session** | Ask an **Administrator** to grant the permission; otherwise **Void** and recreate. | Immediate |
| Can't **Void** a session | Role restriction | Ask an **Administrator** to void; or request the permission. | Immediate |
| Download is missing or partial | You opened the wrong session or it hasn't finished | Use the **Finished** filter; open the correct session; click **Download All**. | Immediate |
| No template picker in **New signing session** | This tenant uses ad-hoc start flow | Upload a file, then **Uploaded documents → ⋯ → Apply template overlay** | Immediate |
| Emails show the wrong **From** | Org is using a different **settings set** | Check **Settings sets → Associated organizations** and reassign if needed | Next email |
| **Apply template overlay** isn't visible | No document uploaded yet | Click **Add document**, then open the document menu (⋯) | Immediate |

**Note:** Exact UI text can vary per tenant. The flow in this page matches the current product labels.

---

## Email delivery checklist (for senders)

1. Open the session → verify participant **Email** is correct.
2. Click **Resend** invitation.
3. Ask the participant to check **Spam/All Mail/Updates** and to search for your org's **From** name.
4. If your org uses a **Notification sender**, confirm it's recognizable and properly configured by an **Administrator**.
5. If you're testing in a customer-safe environment, use an **allow-listed** domain and numbers.

**Tip:** If the participant still can't find the email, copy the **signing link** (if available in your tenant) and share it securely.

---

## Status guide and what to do

| Status | What it means | Action |
|---|---|---|
| **Draft** | You created the session but didn't finalize/start. | Add fields for all participants → **Finalize** → **Start now**. |
| **Ready to start** | All required details present; you chose **Start later**. | Open the session → **Start**. |
| **In progress** | Invitations sent; waiting on participants. | Monitor; **Resend** invites if needed. |
| **Finished** | All required participants completed signing. | Open session → **Download All** (validated bundle). |
| **Declined** | At least one participant declined. | Replace participant or recreate the session. |
| **Voided** | You or an admin canceled the session. | Create a new session to proceed. |
| **Expired** | Session hit its expiration policy. | Create a new session and consider adjusting expiration in your **Settings set**. |

---

## Field placement pitfalls (and fixes)

- **Wrong participant selected:** Always click the participant in the left panel first, then drag fields.
- **Missing required fields:** Some overlays or org rules require **Signature**, **Full name**, **Date**. Place them before **Finalize**.
- **Multi-participant sessions:** Repeat placement per participant; confirm the correct color/label for the active participant.

**Caution:** Changing fields after starting may require **Change signing session** permission.

---

## Permissions issues (for admins)

If users report blocked buttons or missing actions:

1. Go to **Security → Roles**.
2. Check the role (**Standard User** or **Administrator**).
3. Toggle capabilities as needed and **Save**:
   - **Create/Start signing session**
   - **Change signing session**
   - **Void signing session**
   - **Bulk send access**
   - Manage **template overlays**, **notification senders**, **settings sets** (admin functions)

**Tip:** Keep **Void** and **Change** restricted to reduce audit risk.

---

## Participant experience checks

Ask the participant to:
1. Open the link in a modern browser (latest Chrome/Edge/Safari/Firefox).
2. Disable aggressive ad/script blockers for the signing page.
3. Confirm the **Language** suits them (you set this when adding the participant).
4. Retry on another device or network if the page fails to load.

---

## Downloading signed documents

- Use the **Finished** filter on **Home**.
- Open the session → click **Download All** to get the signed, **validated** bundle.
- Look for the *Validated by Entrust* badge in the session view.

**Note:** If you can't find the session, search by **Subject** or participant email.

---

## What to collect before escalating

Provide this info to your admin or support:
- Session **Subject** and link (URL).
- Participant **Email** (and phone if SMS used).
- Current **Status** and last action taken.
- Time window of the issue (local time and timezone).
- Screenshots of any UI messages.
- Whether this is **Production** or a **test** environment.

**Tip:** Include the exact steps you took (click-path) to reproduce the issue.

---

**Related reading**
- See also: [Quickstart: send your first document](../get-started/quickstart.md)  
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)  
- See also: [Roles and permissions](../admin/roles-permissions.md)
