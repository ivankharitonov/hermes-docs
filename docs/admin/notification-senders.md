---
title: "Notification senders"
description: "Configure the From identity used for signing invitations and reminders."
audience: ["admins"]
keywords: ["notification sender", "email", "from address", "deliverability"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["../get-started/quickstart.md", "../how-to/create-and-send-document.md", "./roles-permissions.md", "./settings-sets.md", "./environments.md", "../troubleshooting/sending.md"]
---

# Notification senders

Use notification senders to control the **From name** and **From email** that participants see on invitation and reminder emails.

## Example first
- From name: `EasyInk HR`
- From email: `hr@yourcompany.com`
- Reply-To (optional): `recruiting@yourcompany.com`
- Default for org: **On**

**Tip:** A recognizable sender improves open rates and reduces support tickets.

## Before you begin
- **Role:** Administrator.
- **Decisions:** Which **From name** and **From email** you want to use in production.
- **Deliverability:** Coordinate with IT to ensure your domain’s **SPF**, **DKIM**, and **DMARC** are correct.

**Caution:** Use only domains your company owns. Avoid free mailbox domains for production sending.

## Add a notification sender (UI)
1. Go to **Notification senders** in the admin navigation.  
   **Note:** The exact menu path can vary by tenant. If you can’t find it, search the admin menu for “sender.”
2. Click **Add sender**.
3. Fill:
   - **From name** (shown to participants)
   - **From email** (the address participants see)
   - **Reply-To** (optional)
4. (Optional) Toggle **Set as default for organization**.
5. Click **Save**.

**Tip:** Keep the From name short and clear (e.g., “Acme HR” or “Acme Contracts”).

## Use a sender when starting a session
- If your tenant shows a **Notification sender** selector in the session editor, choose the sender there.  
- If you don’t see a selector, your **organization’s default sender** (from its **settings set**) will be used.

**Note:** Standard Users can’t manage senders. They use the default or any sender that admins expose to them.

## Test before production
1. Create a test signing session addressed to your own inbox.
2. Verify:
   - The **From name** and **From email** match your settings.
   - The message lands in **Inbox** (not Spam/Promotions).
3. In customer-safe environments, ensure email is **allow-listed** as per your environment policy.

**Caution:** Do not send test invitations to real external participants from non-production environments.

## Deliverability checklist
- **SPF** includes your provider’s sending servers.
- **DKIM** is enabled and aligned for the sender domain.
- **DMARC** exists (`p=quarantine` or `p=reject` in production).
- **From** and **Reply-To** are consistent and recognizable.
- Avoid sudden **volume spikes** from new domains.
- Monitor **bounces** and reputation during the first week after changes.

## Troubleshooting

| Symptom | Likely cause | Fix | Time to verify |
|---|---|---|---|
| Participants report missing emails | Spam filtering or domain misconfiguration | Verify SPF/DKIM/DMARC; **Resend**; consider warming the domain. | 1–24 h |
| Sender not selectable in session | No org default set or selector hidden by tenant config | Set an org default in the **settings set**, or expose the selector to users. | Immediate |

## API
Not applicable today. *(Add cURL/Node/Python once API is public.)*

**Related reading**
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)
- See also: [Roles and permissions](./roles-permissions.md)
- See also: [Settings sets](./settings-sets.md)
- See also: [Environments (internal)](./environments.md)
- See also: [Troubleshooting: sending and signing](../troubleshooting/sending.md)
