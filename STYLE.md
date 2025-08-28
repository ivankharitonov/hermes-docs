# Style Guide

A shared set of rules to keep EasyInk docs clear, consistent, and fast to use.

## 1) Voice & tone
- **Direct, second person.** Speak to the reader: “you,” “your team.”
- **Active voice.** “Click **Finalize**,” not “Finalization is performed.”
- **Present tense.** Describe the current UI.
- **Short sentences.** Prefer 10–18 words.
- **No fluff.** Remove marketing language. Prefer facts and steps.

## 2) Information design
- **Examples first, then explanations.**
- **Task-oriented.** Prioritize what the user can do next.
- **One H1 per page.** Sentence case: “Create and start a signing session.”
- **Scannable sections.** Use concise headings and tables for params/errors.

## 3) File & heading conventions
- **Paths:** `docs/<section>/<page>.md` (lowercase, hyphenated filenames).
- **Headings:** sentence case (`## Before you begin`), not Title Case.
- **Anchors:** rely on GitHub’s auto-generated anchors; avoid custom IDs.

## 4) Frontmatter (docs pages only)
Every file under `docs/` starts with YAML frontmatter and ends with **Related reading**.

```yaml
---
title: "Create and start a signing session"
description: "Upload a document, add participants, place fields, finalize, and start a signing session."
audience: ["senders", "admins"]
keywords: ["signing session", "fields", "participants"]
easyink_version: "web"
last_reviewed: "YYYY-MM-DD"
related: ["../get-started/quickstart.md", "../admin/roles-permissions.md"]
---
```

**Tip:** Update `last_reviewed` whenever you touch the page.

## 5) UI text & formatting
- **UI labels:** bold (**Add Participant**, **Finalize**, **Start now**).
- **Navigation paths:** `Home → New signing session` (use `→`).
- **Fields:** capitalize as in UI (First Name, Email).  
- **Keyboard:** `Ctrl+K`, `Cmd+K` (inline code).
- **Code blocks:** use fenced code with language (```bash, ```json, ```mermaid).
- **Callouts:** start with bold label on its own line.  
  - **Note:** context or nuance.  
  - **Tip:** productivity win.  
  - **Caution:** risks or irreversible actions.

## 6) Environments
- **Public docs:** mention **Production** only (`https://easyink.io`).  
- If a customer-safe **test environment** exists, say “use the URL provided by your administrator” (do **not** print staging URLs).
- **Internal pages** (under `docs/admin/`): it’s fine to document Staging/Test with clear data-safety warnings.

**Caution:** Never instruct readers to upload real PII to non-production.

## 7) Tables (preferred patterns)

**Parameters / options**

| Name | Type | Required | Default | Description | Example | Notes |
|---|---|---|---|---|---|---|
| Language | string | No | org default | Language used in the signing session. | `en` | Affects invitation and UI text. |

**Errors**

| Status | Error code | Message | When it happens | How to fix |
|---|---|---|---|---|
| 400 | missing_fields | Required fields not placed for a participant. | User finalized without all fields. | Place required fields, then finalize. |

**Troubleshooting**

| Symptom | Likely cause | Fix | Time to verify |
|---|---|---|---|
| **Finalize** disabled | Missing fields | Place required fields per participant. | Immediate |

## 8) Code & examples
- **Minimal and runnable.** Prefer a single end-to-end example per page.
- **Secrets:** never hard-code. Use placeholders (`YOUR_ORG_SENDER`).
- **Multi-language:** If/when API exists, show **cURL**, **Node**, **Python** tabs; keep parity.
- **JSON:** compact but readable; include only necessary fields.

## 9) Diagrams & media
- **Mermaid diagrams** for models and flows.
- **Alt text** or a caption explaining purpose.
- Avoid screenshots that show non-prod URLs in public docs. If unavoidable, add “Screenshot from a test environment.”

## 10) Accessibility & inclusivity
- Don’t rely on color alone to convey meaning.
- Write clear link text (“See also: Roles and permissions”), not “click here.”
- Avoid idioms and culture-specific slang.

## 11) Dates, times, numbers
- **Dates:** `2025-08-28` (ISO-like) or “August 28, 2025.”
- **Timezones:** specify explicitly if relevant (org default is Europe/Tallinn).
- **Numbers:** use digits; include units (MB, pages).

## 12) Page skeletons

**How-to page**
```markdown
# <Action>: <object>

**Applies to:** roles

## Overview
One-paragraph purpose.

## Before you begin
- Roles
- Access
- Inputs/files

## Steps
1. ...
2. ...

## Troubleshooting
| Symptom | Cause | Fix | Time to verify |
|---|---|---|---|

## API
Not applicable. (Or: cURL/Node/Python tabs)

**Related reading**
- See also: ...
```

**Concept page**
```markdown
# Concept: <name>

## Example first
Short example steps.

## How it works
- Entities
- States

## Data model
```mermaid
classDiagram
...
```

**Related reading**
- See also: ...
```

## 13) Review checklist (Definition of Done)
- Screens and labels match the current product.
- Steps are task-complete and tested.
- Internal links work; no dead ends.
- “Examples first” pattern followed.
- Tables for parameters and errors present when relevant.
- **Related reading** section exists and is populated.
- `last_reviewed` updated.
- Sensitive env details removed from public pages.

## 14) Terminology (canonical)
- Signing session, Document, Participant (Recipient), Template overlay, Notification sender, Settings set, Finalize, Start now, Void, Download All.

**Related reading**
- See also: `docs/get-started/quickstart.md`  
- See also: `docs/how-to/create-and-send-document.md`  
- See also: `docs/admin/environments.md`  
- See also: `docs/admin/roles-permissions.md`
