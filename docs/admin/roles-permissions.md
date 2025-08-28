---
title: "Roles and permissions"
description: "Assign capabilities to users for drafting, starting, and administering signing sessions."
audience: ["admins"]
keywords: ["roles", "permissions", "admin"]
easyink_version: "web"
last_reviewed: "2025-08-27"
related: ["../get-started/quickstart.md", "../how-to/create-and-send-document.md"]
---

# Roles and permissions

Use roles to control who can manage org settings and who can draft or start signing sessions.

## Overview
EasyInk includes two built-in roles:
- **Administrator** – full admin and sending capabilities.
- **Standard User** – sending capabilities without org-level administration.

**Note:** Your tenant may include more granular toggles. The tables below reflect the permissions visible in the current UI.

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
| Change signing session | ✅ | ⛔ |
| Start signing session | ✅ | ✅ |
| View organization signing sessions | ✅ | ⛔ |
| View signing sessions | ✅ | ✅ |
| Void signing session | ✅ | ✅* |

**Caution:** `Void signing session` appears enabled for **Standard User** in the screenshots. Confirm if this is intended in your org; many teams restrict voiding to admins.

## Default configuration (recommended)
- Assign **Administrator** to a small group of trusted users responsible for org configuration.
- Assign **Standard User** to most senders.
- Review **Bulk send access** and **Void signing session** before enabling for Standard Users.

## Manage roles (UI)
1. Go to **Security → Roles**.
2. Select a role (e.g., **Administrator** or **Standard User**).
3. Toggle capabilities as needed.
4. Click **Save**.

## Audit considerations
- Changes to roles should be limited to administrators.
- Record who changed role settings and when.
- Review role assignments quarterly.

**Related reading**
- See also: [Quickstart: send your first document](../get-started/quickstart.md)  
- See also: [Create and send a document](../how-to/create-and-send-document.md)
