---
title: "Roles and permissions"
description: "Assign capabilities to users for drafting, starting, and administering signing sessions."
audience: ["admins"]
keywords: ["roles", "permissions", "admin"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["../get-started/quickstart.md", "../how-to/create-and-send-document.md", "./settings-sets.md", "./template-overlays.md", "./notification-senders.md"]
---

# Roles and permissions

Use roles to control who can manage org settings and who can draft or start signing sessions.

## Overview
EasyInk includes two built-in roles:
- **Administrator** – full admin and sending capabilities.
- **Standard User** – sending capabilities without org-level administration.

**Organization model**
- Each user belongs to **one** organization.
- Each organization has **one** applied **settings set** (a set can be shared across orgs).
- **Admins** configure **settings sets**, **notification senders**, and **template overlays**.
- **Senders** can apply template overlays during session preparation; the **From** address comes from the org’s settings set.

> **Note:** Your tenant may include more granular toggles. The table reflects the permissions visible in the current UI.

## Role capability matrix

| Capability | Administrator | Standard User |
|---|---|---|
| Manage document template overlays | ✅ | ⛔ |
| Apply signing session template overlay | ✅ | ✅ |
| Manage notification senders | ✅ | ⛔ |
| Manage organizations | ✅ | ⛔ |
| Manage settings sets | ✅ | ⛔ |
| Manage groups | ✅ | ⛔ |
| Manage roles | ✅ | ⛔ |
| Manage users | ✅ | ⛔ |
| Bulk send access | ✅ | ⛔ |
| Create signing session draft | ✅ | ✅ |
| Change signing session draft | ✅ | ✅ |
| Delete signing session draft | ✅ | ✅ |
| View signing session drafts | ✅ | ✅ |
| View signing session templates | ✅ | ✅ |
| Create signing session | ✅ | ✅ |
| Change signing session *(edit after start)* | ✅ | ⛔ |
| Start signing session | ✅ | ✅ |
| View organization signing sessions | ✅ | ⛔ |
| View signing sessions | ✅ | ✅ |
| Void signing session | ✅ | ✅ |

> **Note:** **Change signing session** allows editing active sessions after they’ve started. **Change signing session draft** only applies before **Finalize**.

## Default configuration (recommended)
- Assign **Administrator** to a small, trusted group who manage org configuration.
- Assign **Standard User** to most senders.
- Review **Bulk send access** and **Void signing session** before enabling for Standard Users.

## Manage roles (UI)
1. Go to **Security → Roles**.
2. Select a role (**Administrator** or **Standard User**).
3. Toggle capabilities as needed.
4. Click **Save**.

## Audit considerations
- Limit who can modify roles and org-wide settings.
- Record who changed role settings and when.
- Review role assignments quarterly.

**Related reading**
- See also: [Quickstart: send your first document](../get-started/quickstart.md)  
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)  
- See also: [Settings sets](./settings-sets.md)  
- See also: [Template overlays](./template-overlays.md)  
- See also: [Notification senders](./notification-senders.md)
