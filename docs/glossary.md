---
title: "Glossary"
description: "Shared terms for EasyInk so everyone speaks the same language."
audience: ["senders", "admins", "developers", "signers"]
keywords: ["glossary", "terminology", "definitions"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["docs/get-started/quickstart.md", "docs/how-to/create-and-send-document.md", "docs/admin/roles-permissions.md", "docs/admin/template-overlays.md", "docs/admin/settings-sets.md", "docs/admin/notification-senders.md"]
---

# Glossary

Use these definitions across product, docs, and support. Terms match current UI labels.

## Core objects

- **Signing session**  
  Container that holds **documents**, **participants**, **fields**, and **status**. You prepare it, **Finalize**, then **Start now** (or **Start later**).

- **Participant** *(canonical; sometimes called “recipient”)*  
  A person who signs. You provide **First Name**, **Last Name**, **Email**, optional **Phone** and **Language**. Ordering is optional.

- **Document**  
  The PDF you upload to be signed.

- **Field**  
  A required or optional input placed on a page (for example, **Signature**, **Full name**, **Date**, **Initials**). Placed for the **active participant**.

- **Template overlay**  
  Reusable set of participants and pre-placed fields bound to page positions. Applied during session preparation.

- **Settings set**  
  Org-level defaults: **From** name/address (via notification sender), expiration, time zone, SMS rules, and notification templates. Exactly **one** settings set applies to each organization.

- **Notification sender**  
  The **From name** and **From email** used for invitations and reminders.

## Common actions

- **Finalize**  
  Lock preparation. Required before starting.

- **Start now** / **Start later**  
  Send invitations immediately, or keep the session in **Ready to start**.

- **Download All**  
  Download the signed PDF bundle and audit trail after the session is **Finished**.

- **Void**  
  Stop a session so it can’t be completed. Requires permission.

- **Change signing session**  
  Edit an **In progress** session (if enabled for your role/tenant).

## Session states

- **Draft** — In preparation; documents/fields editable.  
- **Ready to start** — Finalized; waiting for **Start now**.  
- **In progress** — Invitations sent; participants are signing.  
- **Finished** — All required participants completed signing.  
- **Declined** — A participant declined to sign.  
- **Voided** — An admin or authorized user cancelled the session.  
- **Expired** — Deadline passed (per settings set).

## Roles and access

- **Administrator**  
  Can manage org settings, **roles**, **users**, **settings sets**, **notification senders**, **template overlays**, and usually **Change/ Void signing session**.

- **Standard User**  
  Can create, finalize, and start signing sessions; apply template overlays.

> **Tip:** See the role matrix for precise capabilities in your tenant.

## Notifications and delivery

- **Email** / **SMS**  
  Invitation and reminder channels. SMS availability and quiet hours come from the **settings set**.

- **Allow-list**  
  In non-prod, domains permitted to receive email (e.g., `*@company.com`).

- **Quiet hours**  
  Time window when SMS will not be sent.

## Environment terms

- **Production** — Live environment for real participants and webhooks.  
- **Staging (customer test)** — Safe testing with allow-lists/sandboxes.  
- **Developer Test** — Internal QA/dev; data is short-lived.

## Security and compliance

- **Audit trail**  
  Time-stamped record of actions and events for a session (creation, finalize, start, signing steps, completion).

- **SSO**  
  Single sign-on via your identity provider (IdP). Separate connectors may exist for staging vs production.

## Other helpful terms

- **Signing link**  
  Secure URL sent to a participant to open the signing experience (availability/visibility depends on tenant settings).

- **Signing order**  
  Numeric order (1..n) that enforces sequence among participants.

- **Entrust validation**  
  Platform-level document validation shown post-completion (label may appear in the UI and download bundle).

- **Bulk send**  
  Capability that lets admins send many sessions at once (availability varies by tenant/role).

**Related reading**
- See also: [Quickstart: send your first document](docs/get-started/quickstart.md)  
- See also: [Create and start a signing session](docs/how-to/create-and-send-document.md)  
- See also: [Roles and permissions](docs/admin/roles-permissions.md)  
- See also: [Template overlays](docs/admin/template-overlays.md)  
- See also: [Settings sets](docs/admin/settings-sets.md)  
- See also: [Notification senders](docs/admin/notification-senders.md)
