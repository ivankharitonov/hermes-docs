---
title: "Glossary"
description: "Clear definitions of EasyInk terms used across the docs."
audience: ["senders", "admins", "developers", "signers"]
keywords: ["glossary", "terminology", "definitions"]
easyink_version: "web"
last_reviewed: "2025-08-28"
related: ["./get-started/quickstart.md", "./how-to/create-and-send-document.md", "./admin/roles-permissions.md"]
---

# Glossary

Short, precise definitions of words you’ll see in the UI and docs.

## Core objects
- **Signing session**  
  The container for documents, recipients, settings, and status. You create it, place fields, **Finalize**, and **Start**.

- **Document**  
  A file you upload to be signed (for example, a PDF).

- **Recipient / Participant**  
  A person asked to sign. You add their **First name**, **Last name**, **Email**, and (optionally) **Phone** and **Language**.  
  **Note:** The UI uses **Participant** in dialogs (e.g., **Add Participant**).

## Configuration
- **Template overlay**  
  A reusable set of fields pre-placed on a document layout. Overlays save time and reduce placement errors.

- **Notification sender**  
  The “From” identity shown on invitation emails. Admins set it so recipients recognize your organization.

- **Settings set**  
  A preset of sending options such as reminders and expiration. Apply it to a session for consistent behavior.

- **Signing order**  
  The sequence recipients must follow. If set, later signers can’t act until earlier signers finish.
  
  - **Settings set:** Org-level defaults for sending (time zone, expiry, sender, SMS rules, templates). Exactly **one** settings set per organization. One set can be **shared** by multiple orgs.
- **Template overlay:** A reusable layout of **participants** and **placed fields**. Created under **Manage templates** and **applied during session preparation** from **Uploaded documents → ⋯ → Apply template overlay**.


## Actions and states
- **Finalize**  
  Locks field placement and prepares the session to start.

- **Start now / Start later**  
  After you **Finalize**, choose **Start now** to send invitations immediately, or **Start later** to keep the session in **Ready to start**.

- **Resend**  
  Sends another invite to a recipient. Useful after email corrections or spam issues.

- **Void**  
  Cancels a session. Use when you must stop signing. Voided sessions can’t be restarted.

## Files and outputs
- **Uploaded documents**  
  The list of files attached to a session. You can add, remove, and reorder before finalizing.

- **Field**  
  A required input placed on a document page (for example, **Signature**, **Full name**, **Date**). Fields are placed for the **active participant**.

- **Download All**  
  Exports the completed, validated document bundle after a session reaches **Finished**.

- **Validation badge**  
  The indicator (e.g., *Validated by Entrust*) shown in the session view confirming cryptographic validation of the signed file.

## Session statuses

| Status | Meaning | What you usually do |
|---|---|---|
| **Draft** | Session created; fields not finalized. | Place fields → **Finalize**. |
| **Ready to start** | Finalized but not started. | Open the session → **Start**. |
| **In progress** | Invitations sent; waiting on recipients. | Monitor; **Resend** if needed. |
| **Finished** | All required recipients completed signing. | **Download All** and archive. |
| **Declined** | A recipient refused to sign. | Replace recipient or create a new session. |
| **Voided** | Session canceled by a user with permission. | Create a new session if needed. |
| **Expired** | Session ended due to expiration policy. | Start a new session; adjust policy via **Settings set** if required. |
| **Need to sign** | A personalized queue showing items where *you* are a recipient. | Open and complete signing. |

**Tip:** Status names match the filters on the **Home** dashboard.

**Related reading**
- See also: [Quickstart: send your first document](./get-started/quickstart.md)  
- See also: [Create and start a signing session](./how-to/create-and-send-document.md)  
- See also: [Roles and permissions](./admin/roles-permissions.md)
