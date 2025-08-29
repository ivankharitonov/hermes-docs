---
title: "Contributing to EasyInk Docs"
description: "How to plan, draft, review, and ship updates to the EasyInk documentation."
audience: ["developers", "admins"]
keywords: ["docs", "contributing", "definition of done", "style", "review"]
easyink_version: "web"
last_reviewed: "2025-08-29"
related: ["STYLE.md", "docs/glossary.md", "docs/get-started/quickstart.md"]
---

# Contributing to EasyInk Docs

This repo contains user-facing documentation for the **EasyInk web** product. Use this guide to add or revise pages with a consistent structure, tone, and quality.

> **Tip:** When in doubt, follow the examples in `docs/get-started/quickstart.md` and `docs/how-to/create-and-send-document.md`.

---

## Workflow at a glance

1. **Create a branch** for your change.  
   `feature/<area>-<short-slug>` (e.g., `feature/admin-settings-sets-expiry`)
2. **Draft the page** using our templates in [STYLE.md](STYLE.md). Keep sentences short, voice active, second person.
3. **Run checks** locally (lint + link-check if available). Fix any warnings.
4. **Open a PR** with a clear title and short description. Add screenshots if UI changes are referenced.
5. **Peer review**: at least one reviewer. Resolve comments; re-run checks.
6. **Merge** when the **Definition of Done** is met. Bump `last_reviewed` in pages you touched.

---

## Definition of Done (DOD)

A page is **Done** when all of the following are true:

- **Frontmatter** is present and valid:
  - `title`, `description`, `audience`, `keywords`, `easyink_version: "web"`, `last_reviewed`, `related` (relative paths).
- **Examples first**, then explanations.
- **Terminology aligned**:
  - Use **Participant** (not recipient), **Email** (not e-mail), **SMS** (not sms/text).
  - Use UI labels exactly: **Finalize**, **Start now**, **Start later**, **Download All**.
- **Links** are relative and work; no dead ends.
- **Callouts** use our format: **Note:**, **Tip:**, **Caution:**.
- **No HTML** in body (Markdown only). Mermaid diagrams are allowed.
- **Screens and labels** match current UI.
- **Related reading** section exists and points to the next likely task/page.
- **last_reviewed** date is current for all edited pages.
- **No secrets** or proprietary details beyond what’s safe to publish.

> **Caution:** If you add a **TBD**, include an owner and target date (e.g., `**TBD (Owner: @alex, by 2025-09-15):** staging purge window.`).

---

## Repository layout (current)

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
    # add: CHANGELOG.md
  _assets/diagrams/
  _includes/
glossary.md
CONTRIBUTING.md
STYLE.md
```

---

## Adding or updating a page

### 1) Pick the right section
- **Get started** for quick wins and first-run success.
- **How-to** for task-focused guides.
- **Admin** for org-level configuration.
- **Concepts** for models and lifecycle explanations.
- **Troubleshooting** for symptoms, causes, and fixes.

### 2) Start with a template
Copy the appropriate skeleton from [STYLE.md](STYLE.md) and fill it in.

```yaml
---
title: "<Concise page title>"
description: "<One-sentence value statement>"
audience: ["senders" | "admins" | "developers" | "signers"]
keywords: ["e-sign", "signing sessions"]
easyink_version: "web"
last_reviewed: "YYYY-MM-DD"
related: ["../path/to/related-one.md", "../path/to/related-two.md"]
---
```

### 3) Write the page
- Put **examples first**.
- Use **short sentences** and **active voice** (“You create…”, “Click **Finalize**…”).
- Keep **UI labels** exact.
- Use **relative links** only.
- Add a **Related reading** section at the end.

### 4) Validate
- Click every link you added.
- Skim for terms to standardize:
  - `recipient|recipients → participant|participants`
  - `e-mail → email`
  - `sms|sms/text → SMS`
- Confirm `last_reviewed` is today’s date for edited files.

---

## PR checklist (copy into your PR)

- [ ] Frontmatter complete (`easyink_version: "web"`, `last_reviewed` updated)
- [ ] Examples first, then explanations
- [ ] Terminology aligned (Participant/Email/SMS; UI labels exact)
- [ ] Relative links valid (no dead ends)
- [ ] Callouts used correctly (**Note/Tip/Caution**)
- [ ] Related reading section added/updated
- [ ] Screens/labels match current UI
- [ ] No HTML; Markdown only
- [ ] Changelog touched if user-visible (see below)

---

## Changelog & versioning

- Create `docs/release-notes/CHANGELOG.md` on the first user-visible change.
- Add a dated entry for noteworthy additions, renames, or removals.
- Link the changelog entry in your PR description when appropriate.

---

## Screenshots and diagrams

- Store diagrams under `docs/_assets/diagrams/`.
- Use **Mermaid** for simple data models and flows.
- Keep filenames descriptive (e.g., `settings-sets-lifecycle.mmd`).

> **Tip:** Prefer numbered steps over annotated screenshots to reduce UI drift.

---

## Security and data hygiene

- No secrets, tokens, or internal-only endpoints.
- Use fake data in examples (`alex@example.com`).
- If referencing **Staging/Developer** environments, follow policies in `docs/admin/environments.md`.

---

## Optional automation (CI examples)

Add GitHub Actions to enforce link health and style.

**Markdown lint**

```yaml
name: markdownlint
on: [push, pull_request]
jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: DavidAnson/markdownlint-cli2-action@v16
```

**Link check (external + relative)**

```yaml
name: link-check
on: [push, pull_request]
jobs:
  lychee:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: lycheeverse/lychee-action@v1
        with:
          args: --verbose --no-progress --exclude-mail --accept 200,206,429 "docs/**/*.md" "glossary.md" "STYLE.md" "CONTRIBUTING.md"
```

---

## Reporting UI drift or gaps

If you find labels or flows that differ from the product:
1. File an issue with screenshots and the page path.
2. Add a **temporary Note** in the doc only if it blocks task completion.
3. Assign an owner and a due date to replace or remove the note.

---

**Related reading**
- See also: [STYLE.md](STYLE.md)  
- See also: [Glossary](docs/glossary.md)  
- See also: [Quickstart: send your first document](docs/get-started/quickstart.md)
