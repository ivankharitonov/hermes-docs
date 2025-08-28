---
title: "Notification senders"
description: "Configure the From identity used for signing invitations and reminders."
audience: ["admins"]
keywords: ["notification sender", "email", "from address", "deliverability"]
easyink_version: "web"
last_reviewed: "2025-08-28"
related: ["../get-started/quickstart.md", "./roles-permissions.md", "../how-to/create-and-send-document.md"]
---

# Notification senders

Use notification senders to control the **From name** and **From address** that recipients see on invitation and reminder emails.

**Example first**
- From name: `EasyInk HR`
- From email: `hr@yourcompany.com`
- Reply-To (optional): `recruiting@yourcompany.com`
- Default for org: **On**

**Tip:** A recognizable sender improves open rates and reduces support tickets.

## Before you begin
- **Role:** Administrator.
- **Decisions:** Which **From name** and **From address** you want to use in production.
- **Deliverability:** Coordinate with IT to ensure your domain’s **SPF**, **DKIM**, and **DMARC** are correct.

**Caution:** Use only domains your company owns. Avoid free mailbox domains for production sending.

## Add a notification sender (UI)
1. Open the admin area for senders.  
   - Go to your admin navigation and open **Notification senders**.  
   - **Note:** The exact menu path can vary by tenant. If you can’t find it, search the admin menu for “sender”.
2. Click **Add sender**.
3. Fill:
   - **From name** (shown to recipients)
   - **From email** (the address recipients see)
   - **Reply-To** (optional)
4. Choose **Set as default for organization** (optional).
5. Click **Save**.

**Tip:** Keep the From name short and clear (e.g., “Acme HR” or “Acme Contracts”).

## Use a sender when starting a session
- In the session editor, choose **Notification sender** if your tenant shows this option.  
- If you don’t see a selector, your **default sender** will be used.

**Note:** Standard Users don’t manage senders. They can use the default or any sender admins expose to them.

## Test before production
1. Create a test signing session addressed to your own inbox.
2. Verify:
   - The **From name** and **From email** match your settings.
   - The message lands in **Inbox** (not Spam/Promotions).
3. If testing in a customer-safe environment, ensure email is **allow-listed** as per your environment policy.

**Caution:** Do not send test invitations to real external recipients from non-production environments.

## Deliverability checklist
- **SPF** includes your email provider’s sending servers.
- **DKIM** is enabled and aligned for the sender domain.
- **DMARC** exists (`p=quarantine` or `p=reject` in production).
- **From** and **Reply-To** are consistent and recognizable.
- Avoid sudden **volume spikes** from new domains.

**Tip:** Ask IT to monitor bounces and reputation during the first week after changing senders.

## Troubleshooting

| Symptom | Likely cause | Fix | Time to verify |
|---|---|---|---|
| Recipients report missing emails | Spam filtering or domain misconfig | Verify SPF/DKIM/DMARC; resend; consider warming the domain. | 1–24 h |
| Sender not selectable in session | No default set or selector hidden by tenant config | Set an org default or expose the sender to users. | Immediate |
| “From” shows a generic address | Your provider rewrote the From due to policy | Align DMARC; use a verified sending domain. | 1–24 h |
| Bounces increase | Invalid addresses or blocklisted domain | Clean recipient lists; check bounce logs with IT. | 1–24 h |

## Security and compliance
- Use company-owned domains only.
- Rotate credentials in your email provider per policy.
- Audit who can **create** or **change** notification senders.

**Related reading**
- See also: [Roles and permissions](./roles-permissions.md)  
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)  
- See also: [Quickstart: send your first document](../get-started/quickstart.md)
