---
title: "Groups and users"
description: "Create and manage users and groups; assign roles and the organization each user belongs to."
audience: ["admins"]
keywords: ["groups", "users", "roles", "organizations", "access control"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["./roles-permissions.md", "./settings-sets.md", "./notification-senders.md", "./environments.md", "../get-started/quickstart.md"]
---

# Create and manage groups and users
**Applies to:** admins

## Overview
Use this page to:
- Add or deactivate **users** who can prepare and start signing sessions.
- Place users into **one organization** (required).
- Assign a **role** (**Administrator** or **Standard User**).
- Organize users with **groups** for easier management.

**Note:** Each user belongs to **exactly one** organization. Each organization uses **one** applied **settings set** (shared across orgs if needed). Sender identity and expirations come from that settings set.

## Before you begin
- **Role:** Administrator.
- **Access:** **Security → Users** and **Security → Groups** in the left navigation.
- **Inputs:** User’s **First Name**, **Last Name**, **Email**, **Role**, and **Organization**.
- **Environment:** In non-prod, prefer test accounts (e.g., `alex+uat-2025-08-29@company.com`). See [Environments](./environments.md).

## Users

### Create a user
1. Go to **Security → Users**.
2. Click **Add User**.
3. Fill:
   - **First Name**, **Last Name**
   - **Email**
   - **Organization** *(required; one per user)*
   - **Role** *(Administrator or Standard User)*
   - (Optional) **Phone**, **Language**
4. Click **Save**.

> **Caution:** Changing a user’s **Organization** later changes their default **notification sender** and **expiration rules** for **future** sessions (via the org’s settings set). Existing started sessions are not retroactively changed.

### Edit a user
1. Open **Security → Users**.
2. Click a user → **Edit**.
3. Update **Role**, **Organization**, or profile fields.
4. Click **Save**.

**Tip:** For least disruption, change **Organization** and **Role** during off-hours.

### Deactivate or reactivate a user
- **Deactivate:** Open the user → **Deactivate**. The user can’t sign in or create/edit sessions.
- **Reactivate:** Open the user → **Reactivate** to restore access.

**Note:** Deactivation does **not** delete data or completed sessions. Ownership and audit trail remain intact.

## Groups

### Create a group
1. Go to **Security → Groups**.
2. Click **Add Group**.
3. Enter **Group Name** and optional **Description**.
4. Click **Save**.

### Add or remove members
1. Open **Security → Groups** → select a group.
2. **Add members** or **Remove** selected members.
3. Click **Save**.

**Tip:** Use groups to mirror real teams (e.g., “HR Tallinn”, “Sales EMEA”). This makes access reviews and feature rollouts easier.

### Rename or archive a group
- **Rename:** Open the group → edit **Group Name** → **Save**.
- **Archive:** If supported, archiving hides a group from pickers without removing historical membership.

> **Note:** Groups do not change a user’s **Organization**. They are an organizational convenience for admins.

## Troubleshooting

| Symptom | Likely cause | Fix | Time to verify |
|---|---|---|---|
| User can’t start sessions | User has **Standard User** role but is not in any **Organization** | Edit the user; assign the correct **Organization**; save. | Immediate |
| User sees the “wrong” From address | User’s **Organization** uses another **settings set** | Verify the org’s **settings set**; update **Send from** fields or move the user to the correct org. | Next email |
| Can’t deactivate last admin | At least one **Administrator** is required | Assign another user as **Administrator**, then deactivate. | Immediate |
| Email “already exists” when creating user | Duplicate account or typo | Search users for the address; edit existing user instead of creating a new one. | Immediate |
| Group changes don’t show up | Cached view or stale session | Refresh the page or sign out/in; verify group membership again. | 1–2 min |

## Governance
- **Least privilege:** Grant **Administrator** only to those who manage org-level settings.
- **Quarterly review:** Audit user lists, group membership, and role assignments.
- **Joiner/Mover/Leaver (JML):** Establish a process to update **Organization** and **Role** when employees move teams.

## FAQs
**Can a user belong to multiple organizations?**  
No. Exactly **one** organization per user.

**Do groups affect permissions?**  
Not directly. Permissions come from **roles**. Groups are for organization and (where supported) feature targeting.

**Does deactivating a user affect active sessions they created?**  
No. Sessions continue. Deactivation only blocks the user’s access.

**Can I bulk-import users?**  
If your tenant supports it, use the import option under **Security → Users**. Otherwise, add users individually.

## API
Not applicable today. *(Add cURL/Node/Python once API is public.)*

**Related reading**
- See also: [Roles and permissions](./roles-permissions.md)  
- See also: [Settings sets](./settings-sets.md)  
- See also: [Notification senders](./notification-senders.md)  
- See also: [Environments (internal)](./environments.md)  
- See also: [Quickstart: send your first document](../get-started/quickstart.md)
