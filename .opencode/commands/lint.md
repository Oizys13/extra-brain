---
description: Run a health check on the wiki.
---

<!-- argument-hint: [optional scope, e.g. concepts/ or a page name] -->

# Lint the wiki

Inspect the wiki and report problems. **This command is read-only: do not modify, fix, or
delete anything.** Propose fixes and wait for explicit permission.

Read `AGENTS.md` first so you check against the real conventions. If `$ARGUMENTS` narrows
the scope (a folder or page), check only that; otherwise scan all of `wiki/`.

## Checks

1. **Broken wiki-links** — every `[[...]]` target that does not resolve to an existing file.
   Report the linking page, the broken target, and any obvious intended target.
2. **Orphan pages** — pages with no inbound wiki-links, and pages missing from
   `wiki/index.md`. `index.md` and `log.md` are exempt.
3. **Missing or invalid frontmatter** — required fields are `title`, `type`, `sources`,
   `related`, `created`, `last-updated`. Also flag:
   - a `type` outside `concept`, `entity`, `source-summary`, `comparison`, `project`,
     `person`;
   - an H1 that does not match `title`;
   - `sources` entries that point to files missing from `raw/`;
   - malformed dates (must be `YYYY-MM-DD`).
   `wiki/index.md`, `wiki/log.md`, and `README.md` files are exempt.
4. **Stale pages** — `last-updated` 30 or more days before today, or, where the field is
   missing, a file modification time that old. Report the age and what looks out of date.
5. **Contradictions between pages** — factual conflicts, the same term defined differently,
   or duplicated pages that disagree. Quote both sides and name the pages. Do not resolve
   them; flag them.
6. **Structural drift** — pages in the wrong folder for their `type`, duplicate or
   near-duplicate pages, empty sections, sources cited in the body but absent from the
   `sources` list, broken `## Sources` paths.

## Report

Group findings by check, most serious first. For each finding give:

- **Page** — exact path and, where relevant, the line or heading.
- **Issue** — what is wrong, in one or two sentences.
- **Proposed fix** — the specific change you would make.

End with a count per category and a short priority list. If a category is clean, say so
explicitly. Then ask which fixes to apply — make no changes until the user confirms, and if
they do confirm, follow the write rules in `AGENTS.md` and log the changes in `wiki/log.md`.
