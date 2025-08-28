---
title: "TBD register — Settings sets"
description: "Open questions and decisions to confirm before finalizing the Settings sets page."
audience: ["admins"]
keywords: ["tbd", "open questions", "settings sets"]
easyink_version: "web"
last_reviewed: "2025-08-28"
related: ["../admin/settings-sets.md", "../admin/environments.md", "../admin/notification-senders.md", "../admin/roles-permissions.md"]
---

# Settings sets — Open questions (to confirm)

Use this checklist to close gaps before marking the page as final. Keep answers short and cite the internal source.

## 1) Expiration & time calculations
- [ ] **Anchor time** for expiry: is it the session **Start**, **Finalize**, or creation timestamp?
- [ ] **Max/min** for **Add days to sign by date** (e.g., 0–365?) and **Add hours to sign by time** (0–23? minute granularity?).
- [ ] **Rounding rules:** what happens if the target time has already passed on the target day?
- [ ] **Time zone** used for deadlines: the set’s TZ vs org default vs sender’s profile?
- [ ] Can admins **extend or shorten** the expiry of a **live** session? Where?

## 2) Lifecycle & state
- [ ] What does **Finalize** do? Does it lock the set or can it still be edited?
- [ ] If a **finalized set is edited**, do changes affect **future sends only**, or also **in-flight** sessions and **queued reminders**?
- [ ] **Archive** behavior: visibility in pickers; impact on live sessions that referenced the set.
- [ ] **Associated organizations**: are they required? Can a set be shared across orgs/tenants?

## 3) Notifications (email & SMS)
- [ ] **Email reminders**: where is cadence configured (per set or elsewhere)? Any defaults/limits?
- [ ] **SMS**: default **Allowed time** window; which **time zone** governs quiet hours?
- [ ] Are **email quiet hours** supported, or only SMS?
- [ ] **Attachments**: if “Send documents in e-mail attachments” is enabled, what file **size/type limits** apply?

## 4) Senders & verification
- [ ] Scope of **sender verification**: per **workspace** or **org-wide**? Any approval workflow?
- [ ] Are there domain requirements (SPF/DKIM/DMARC) that must be met before a sender can be used here?

## 5) Locale & language
- [ ] Where is **locale** set: per **settings set**, per **recipient**, or elsewhere?
- [ ] **Supported locales** list to publish (requested: `en-US`, `es-MX`).
- [ ] Fallback behavior if a template isn’t localized: which language is used?

## 6) Integrations with Templates/Overlays
- [ ] Can a settings set be attached as the **default** to a **Template** or **Overlay**?
- [ ] Exact **UI path** to do so (click-path/screens).

## 7) Limits & quotas
- [ ] Max number of **settings sets** per org/workspace.
- [ ] Any rate limits on edits or usage that matter for admins?

## 8) Environments & audit
- [ ] **Staging/Test** specifics: email/SMS policy (disabled, allow-list, throttled), purge windows, webhook behavior.
- [ ] **Audit log** events for **create / edit / archive**: event names and fields; who can view.

---

## Decision log (fill as you answer)
| Date | Decision | Source/link | PR |
|---|---|---|---|
| YYYY-MM-DD |  |  |  |

**Related reading**
- See also: [Settings sets](../admin/settings-sets.md), [Notification senders](../admin/notification-senders.md), [Environments](../admin/environments.md), [Roles & permissions](../admin/roles-permissions.md)
