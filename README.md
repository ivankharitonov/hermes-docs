---
title: "EasyInk Docs"
description: "User-centric documentation for the EasyInk e-sign web tool."
audience: ["senders", "admins", "developers", "signers"]
keywords: ["EasyInk", "documentation", "e-sign", "signing", "web"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["docs/get-started/quickstart.md", "CONTRIBUTING.md", "STYLE.md"]
---

# EasyInk Documentation

This repository contains the GitHub-ready Markdown documentation for the **EasyInk web** product. The docs are task-first, concise, and aligned with the current UI.

> **Tip:** If you’re new, start with the [Quickstart](docs/get-started/quickstart.md).

---

## Quick links

- **Get started**
  - [Quickstart: send your first document](docs/get-started/quickstart.md)

- **How-to**
  - [Create and start a signing session](docs/how-to/create-and-send-document.md)

- **Admin**
  - [Roles and permissions](docs/admin/roles-permissions.md]  
  - [Settings sets](docs/admin/settings-sets.md)  
  - [Template overlays](docs/admin/template-overlays.md)  
  - [Notification senders](docs/admin/notification-senders.md)  
  - [Environments (internal)](docs/admin/environments.md)

- **Concepts**
  - [Signing sessions](docs/concepts/signing-sessions.md)  
  - [Templates and overlays](docs/concepts/templates.md)  
  - [Participants and roles](docs/concepts/participants-and-roles.md)

- **Troubleshooting**
  - [Sending and signing](docs/troubleshooting/sending.md)

- **Reference**
  - [Glossary](glossary.md)  
  - [Style guide](STYLE.md)  
  - [Contributing](CONTRIBUTING.md)

---

## Repository structure

```
docs/
  get-started/
    quickstart.md
  how-to/
    create-and-send-document.md
  admin/
    roles-permissions.md
    environments.md
    notification-senders.md
    settings-sets.md
    template-overlays.md
  troubleshooting/
    sending.md
  concepts/
    signing-sessions.md
    templates.md
    participants-and-roles.md
  release-notes/
    # (add CHANGELOG.md on first release note)
  _assets/diagrams/
  _includes/
glossary.md
CONTRIBUTING.md
STYLE.md
README.md
```

---

## How to contribute

1. Create a feature branch (`feature/<area>-<slug>`).  
2. Draft content using the templates in [STYLE.md](STYLE.md).  
3. Check terminology (Participant/Email/SMS) and UI labels (Finalize/Start now).  
4. Open a PR and request review.  
5. Update `last_reviewed` on any files you touched.

See the full guide: [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Writing rules (short version)

- **Examples first**, then explanations.  
- **Short, active, second person** (“You click **Finalize**…”).  
- **UI-true** labels and capitalization.  
- **Markdown only**; no HTML.  
- Every page ends with **Related reading** and uses **relative links**.

For details, see the [Style guide](STYLE.md).

---

## Terminology

Use these canonical terms across the repo:

- **Participant** (not “recipient”)  
- **Email** (not “e-mail”)  
- **SMS** (not “sms/text”)  
- **Finalize**, **Start now**, **Start later**, **Download All** (exact UI labels)

> **Note:** If UI labels change, update the style guide and sweep the repo.

---

## Issues & support

Found a gap or UI drift? Open an issue with screenshots and the page path. For urgent fixes, add a short **Note** in the doc and assign an owner to replace it.

---

## Versioning

A `docs/release-notes/CHANGELOG.md` will be added when the first user-visible release note lands. Reference it in PRs when you make notable changes.

**Related reading**
- See also: [Quickstart: send your first document](docs/get-started/quickstart.md)  
- See also: [Contributing](CONTRIBUTING.md)  
- See also: [Style guide](STYLE.md)
