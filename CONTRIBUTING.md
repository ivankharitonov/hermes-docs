# Contributing

Guidelines for proposing, drafting, and reviewing EasyInk documentation.

## Workflow

1. **Create a branch**
   - Name: `docs/<area>-<short-topic>` (e.g., `docs/how-to-bulk-send`).

2. **Draft**
   - Place files under `docs/` using the structure in the repo blueprint.
   - Follow the house style in `STYLE.md`.
   - Every page under `docs/` starts with **YAML frontmatter** and ends with a **Related reading** section.

3. **Self-review**
   - Run the **PR checklist** below before opening a pull request.

4. **Open a PR**
   - Title: concise action + page (e.g., “Add how-to: bulk send”).
   - Description: what changed, unresolved TBDs, screenshots if UI labels changed.

5. **Review & merge**
   - At least one reviewer signs off.
   - Resolve comments, update `last_reviewed`, and squash-merge.

---

## File conventions

- **Paths:** `docs/<section>/<page>.md` (lowercase, hyphens).
- **Headings:** sentence case; one `#` H1 per page.
- **Frontmatter (docs pages only):**
  ```yaml
  ---
  title: "<Concise page title>"
  description: "<One-sentence value statement>"
  audience: ["senders" | "admins" | "developers" | "signers"]
  keywords: ["e-sign", "signing sessions"]
  easyink_version: "web"
  last_reviewed: "YYYY-MM-DD"
  related: ["../path/to/other.md"]
  ---
  ```
- **Links:** use **relative paths** (e.g., `../admin/roles-permissions.md`).
- **Callouts:** start lines with **Note**, **Tip**, **Caution** (bold label).
- **Diagrams:** prefer Mermaid; place any images under `docs/_assets/diagrams/`.
- **Environments:** public pages mention **Production** only. Put staging/test details on `docs/admin/environments.md`.

---

## PR checklist (Definition of Done)

- [ ] Page uses YAML **frontmatter** and includes **Related reading**.
- [ ] Labels and click-paths match the **current UI**.
- [ ] Steps are **task-complete** (examples first, then explanations).
- [ ] Tables used for parameters, options, and **errors** where relevant.
- [ ] Internal **links are valid** and relative.
- [ ] **No staging/test URLs** on public pages.
- [ ] **last_reviewed** date updated.
- [ ] Spelling/grammar pass; short, active sentences; second-person voice.
- [ ] If placeholders/TBDs exist, they’re clearly marked and tracked.

---

## Optional quality checks

- **Markdown lint:** use your editor’s Markdownlint extension or a CI job.
- **Link check:** run a link checker locally or in CI for `docs/`.
- **Preview:** open the Markdown in GitHub (or a local preview) to verify anchors and tables.

---

## Page templates

See `STYLE.md` for “How-to” and “Concept” skeletons you can copy/paste.

---

## Versioning & changes

- Keep breaking UI terminology changes in a **separate PR** with screenshots.
- If you change terminology across the docs, include a short "Why" note in the PR and update the **Glossary**.
- Add user-visible product changes to `docs/release-notes/CHANGELOG.md` (create the file if it doesn't exist).

---

## Questions

Open a draft PR and add your questions in the description, or leave inline `<!-- comments -->` for reviewers.
