---
title: "Environments (internal)"
description: "Internal guide to Production, Staging (customer test), and developer test environments."
audience: ["admins", "developers"]
keywords: ["environments", "production", "staging", "test", "SSO"]
easyink_version: "web"
last_reviewed: "2025-08-28"
related: ["./roles-permissions.md", "../get-started/quickstart.md", "../how-to/create-and-send-document.md"]
---

# Environments (internal)

Use this page to choose the right environment, set up safe customer tests, and avoid leaking real data into non-production.

## Quick reference

| Environment | Purpose | Base URL | Who uses it | Data policy | Email/SMS | Webhooks | SSO | Notes |
|---|---|---|---|---|---|---|---|---|
| **Production** | Live customer traffic | `https://easyink.io` | All customers and org users | Production data; org retention policies apply | Enabled | Enabled | OneLogin (prod) | Change-managed; monitored. |
| **Staging (customer test)** | Customer UAT and internal QA | `https://staging.easyink.io` | Customers invited for testing; EasyInk staff | **Non-production.** Use synthetic data only. Purge window: **TBD** | **TBD** (recommend allow-list only) | **TBD** (use test endpoints) | OneLogin (test connector) **TBD** | Feature flags may differ from prod. |
| **Developer Test N** | Engineering tests and feature work | **TBD** (e.g., `https://dev-<name>.easyink.internal`) | Engineering only | Non-production; synthetic data only; can reset anytime | Usually disabled/sandboxed | Use test endpoints only | Usually disabled or test IdP | No customer access. |

**Caution:** Never upload real customer or employee PII to Staging or Developer Test environments.

## When to use which

- Use **Production** for all real sending and signing.
- Use **Staging** for **customer acceptance testing** and internal demos that must mirror production UX.
- Use **Developer Test** environments for engineering work, experiments, and unstable features.

**Tip:** If a customer needs hands-on testing, create a **customer test tenant** on **Staging** (see checklist below).

## Customer test setup (Staging) — checklist

1. **Create or select the organization**
   - As an **Administrator**, go to **Security → Organizations** (or your org management area).
   - Create a dedicated **customer test org** or verify an existing one.

2. **Invite users**
   - Add the customer’s test users as **Standard User** (or as needed).
   - If your tenant uses SSO, configure the **OneLogin test connector** (test IdP) and map roles.

3. **Configure sending defaults**
   - **Notification sender:** set a recognizable From name and address for test emails.
   - **Settings set:** define reminders and expiration suitable for short test cycles (e.g., 7–14 days).

4. **Guard outbound channels**
   - Email/SMS in Staging should be **allow-listed** to specific domains/phones if possible (**TBD** per tenant).
   - Clearly label messages as **TEST** in the Notification sender if supported.

5. **Prepare test data**
   - Use fake names, emails under an allow-listed domain, and placeholder phone numbers.
   - Upload only **synthetic** or scrubbed documents.

6. **(Optional) Webhooks**
   - Register a test endpoint (e.g., a request bin) instead of a production system.
   - Store secrets in your test vault/tooling; never reuse production secrets.

7. **Communicate limits**
   - Share known differences vs Production (feature flags, email throttling, purge window).
   - Provide the **Staging URL** and the intended **test window**.

**Note:** If Staging email delivery is disabled by default, plan for **link-based signing** testing or use an internal mail catcher.

## Data and retention

- **Production:** follows your org’s retention policies for documents, audit trail, and logs.
- **Staging/Developer Test:** non-production; expected shorter retention and possible resets.  
  - Document retention (Staging): **TBD**  
  - Audit trail retention (Staging): **TBD**  
  - Webhook/log retention (Staging): **TBD**

**Caution:** If a customer requires longer retention during UAT, document an exception and its expiry date.

## Outbound integrations in non-prod

- **Email:** Prefer allow-listing or a mail sandbox. Avoid sending to real external recipients.
- **SMS:** Use test numbers or a provider sandbox; confirm billing behavior in non-prod.
- **Webhooks:** Send to **test endpoints** only. Rotate secrets before promotion to Production.

## SSO and access

- **Production:** OneLogin (prod) with full controls.  
- **Staging/Developer Test:** use a **test IdP/connector**. Confirm role mappings mirror Production.

**Tip:** Keep a break-glass local admin account in every environment for lockout recovery.

## Promotion flow (high level)

1. **Dev Test → Staging:** feature behind a flag; verify flows end-to-end with synthetic data.  
2. **Staging → Limited customer UAT:** add allow-listed emails/phones; run acceptance scripts.  
3. **Enable in Production:** remove the flag or roll out gradually; monitor and roll back if needed.

**Note:** Track promotion readiness with a short checklist (tests passing, docs updated, support briefed).

## Fill me in (placeholders to update)

- Staging purge window: **TBD**  
- Email policy on Staging (enabled/allow-list/off): **TBD**  
- SMS policy on Staging: **TBD**  
- Webhook availability on Staging: **TBD**  
- OneLogin test connector details: **TBD**  
- Developer Test environment URLs and owners: **TBD**

**Tip:** Update this page when any environment policy changes. Set a calendar reminder for quarterly review.

**Related reading**
- See also: [Roles and permissions](./roles-permissions.md)  
- See also: [Quickstart: send your first document](../get-started/quickstart.md)  
- See also: [Create and start a signing session](../how-to/create-and-send-document.md)
