---
title: "Environments (internal)"
description: "Policies and safe practices for Production, Staging (customer test), and Developer Test."
audience: ["admins", "developers"]
keywords: ["environments", "production", "staging", "test", "SSO", "allow-list"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["./roles-permissions.md", "./notification-senders.md", "./settings-sets.md", "../troubleshooting/sending.md", "../get-started/quickstart.md"]
---

# Environments (internal)

Use this page to choose the right environment, set up safe customer tests, and avoid leaking real data into non-production.

## Overview
EasyInk runs in three environment types:

- **Production** — real customer data and live notifications.
- **Staging (customer test)** — customer acceptance testing with controlled notifications.
- **Developer Test** — short-lived instances for internal QA and development.

> **Caution:** Never send test invitations to real external **participants** from non-production environments. Use an allow-listed domain or a mail sandbox.

## Environment matrix

| Environment | Primary use | Who uses it | Data policy | Email/SMS policy | Webhooks | SSO | Purge |
|---|---|---|---|---|---|---|---|
| **Production** | Live documents and signatures | Senders, Admins | Real data only | Enabled with verified **notification sender** | Enabled to prod endpoints | Enabled (prod IdP) | No automatic purge |
| **Staging (customer test)** | Customer UAT and demos | Admins, selected senders | Test data only | **TBD:** allow-list vs off by default | **TBD** (usually allowed to staging endpoints) | **TBD** (OneLogin test connector) | **TBD:** purge window |
| **Developer Test** | Internal QA/dev | Developers, QA | Synthetic data only | Off; or sent to sandbox/inbox catcher | Optional; local or stub | Optional; dev connector | Frequent purge (short) |

> **Tip:** If you must demonstrate email content in non-prod, use a sandbox inbox (e.g., MailHog/Mailtrap) or an allow-listed corporate domain.

## Safe testing checklist (non-prod)
1. **Accounts:** Use internal identities (you@company.com) and test phone numbers.
2. **Participants:** Use unique aliases per run (e.g., `alex+uat-2025-08-29@company.com`).
3. **Notification sender:** Use a clearly labeled non-prod sender (e.g., “Acme Test”).
4. **Settings set:** Set short expirations (e.g., 1 day) and quiet hours for SMS.
5. **Webhooks:** Point to staging/test endpoints; add environment headers to help consumers discard non-prod events.
6. **Audit:** Mark sessions and overlays with “TEST” in the subject/name for easy filtering.
7. **Data retention:** Confirm the purge policy before uploading any real customer content. If unsure, **do not** upload.

## Production
**When to use:** Real business operations.

**Defaults**
- **Email/SMS:** Enabled. Use a verified **notification sender**.
- **Webhooks:** Enabled. Point to production consumers only.
- **SSO:** Enabled (production IdP).

**Caution:** Configuration changes (e.g., **settings sets**, **notification senders**) affect future sessions immediately. Coordinate changes and announce to senders.

## Staging (customer test)
**When to use:** Customer UAT, demos, pre-production validation.

**Recommended policies**
- **Email:** Prefer **allow-list** (e.g., `*@company.com`) or a sandbox mailbox. External domains blocked by default.
- **SMS:** Disabled or limited to test numbers; enforce quiet hours.
- **Webhooks:** Enabled to **staging** endpoints only; include an `X-Environment: staging` header.
- **SSO:** Use a **test connector** with a small set of test users.
- **Data retention:** Short purge window to reduce risk.

**TBD — confirm and document**
- Staging **purge window** (e.g., 7/14/30 days): **TBD**
- **Email** policy (allow-list pattern, bounce domain, sandbox): **TBD**
- **SMS** policy (enabled?, test number range, quiet hours): **TBD**
- **Webhooks** availability and endpoint convention: **TBD**
- **SSO** connector name, metadata, and mapping rules: **TBD**
- **Owner(s)** responsible for updating this page when policies change: **TBD**

> **Note:** Once confirmed, replace **TBD** with exact values and update `last_reviewed`.

## Developer Test
**When to use:** Internal QA and development only.

**Defaults**
- **Email:** Off or routed to a sandbox/catcher.
- **SMS:** Off.
- **Webhooks:** Optional; often stubbed or pointed to localhost tunnels during testing.
- **SSO:** Optional; dev connector or local accounts.
- **Purge:** Frequent automatic cleanup to keep data small.

**Tip:** If you need to test invitations, explicitly enable the sandbox sender and confirm messages are not leaving your network.

## Troubleshooting

| Symptom | Likely cause | Fix | Time to verify |
|---|---|---|---|
| Participant didn’t get invite in **Staging** | Domain not on allow-list or email disabled | Add the domain to the allow-list or use a sandbox inbox; **Resend**. | 1–5 min |
| **Start now** succeeds but webhook consumer shows nothing | Webhooks disabled for the environment or wrong endpoint | Enable webhooks for Staging/Dev; point to staging consumer; verify with a test event. | 5–10 min |
| SSO works in Production but fails in Staging | Wrong connector or attribute mapping | Switch to the **test connector**; verify NameID/email mapping; retry. | 5–15 min |
| SMS never arrives in non-prod | SMS disabled or outside quiet hours | Enable for test range and widen allowed time window; retry. | Next SMS window |
| Sensitive data found in Staging | Real data uploaded by mistake | **Void** affected sessions; purge per policy; notify security; update allow-list rules. | Same day |

## Governance and reviews
- **Change control:** Treat environment policy changes like product changes. Announce, document, and review.
- **Quarterly review:** Validate allow-lists, purge jobs, webhook endpoints, and SSO connectors.
- **Monitoring:** Track non-prod mail volume and bounce rates to catch misconfigurations.

**Related reading**
- See also: [Roles and permissions](./roles-permissions.md)  
- See also: [Notification senders](./notification-senders.md)  
- See also: [Settings sets](./settings-sets.md)  
- See also: [Troubleshooting: sending and signing](../troubleshooting/sending.md)  
- See also: [Quickstart: send your first document](../get-started/quickstart.md)
