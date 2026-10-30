---
description: Ingest new files from raw/ into wiki/.
---

<!-- argument-hint: [optional number of sources, 5-10] -->

# Ingest raw sources

Turn unprocessed files in `raw/` into a linked, sourced wiki.

**Work on 5–10 sources in this run.** If `$ARGUMENTS` contains a number, use that as the
batch size instead. If `$ARGUMENTS` contains anything else (a path, folder, or keyword),
treat it as a filter on which sources to consider, with the default batch size.

## Before you start

1. Read `AGENTS.md` and follow it exactly — frontmatter fields, page types, heading order,
   linking, style, and the split between `raw/` (never touched) and `wiki/` (yours).
2. Read `wiki/index.md` and `wiki/log.md` to see what already exists.
3. Build an inventory: every file under `raw/`, excluding `README.md` files, is **unread**
   unless a source-summary page already lists it in `sources`, or an entry in `wiki/log.md`
   records it as ingested. When in doubt, treat it as unread.
4. Select up to the batch size, oldest or most recently added first — your choice, but say
   which order you used.

If nothing is unread, say so and stop. Do not invent work.

## For each selected source

1. **Read the whole source**, not just the beginning. For PDFs, transcripts, and exports,
   extract the actual text. If a file is unreadable, binary-only, empty, or corrupted, record
   that and skip it — never guess at its contents.
2. **Write one source-summary page** in `wiki/concepts/` (type `source-summary`), named after
   the source with a short descriptive slug. It must contain:
   - `title`, `type: source-summary`, `sources` with the exact `raw/` path, `related`,
     `created`, `last-updated`.
   - What the source is, who made it, and when.
   - Its key claims and findings, attributed to it.
   - Anything it contradicts elsewhere in the wiki (check related pages first).
   - Open questions it raises.
3. **Create or update related pages** as the content warrants:
   - `concept` (and `entity` / `comparison`) pages in `wiki/concepts/`.
   - `project` pages in `wiki/projects/` when the source bears on a named project.
   - `person` pages in `wiki/people/` when a person recurs and there is enough substance.
   Keep pages atomic — one idea each. Reuse and extend existing pages instead of creating
   near-duplicates; check `wiki/index.md` before adding anything new.
4. **Cross-link both directions.** New pages link back to the source summary and to related
   pages; add the reverse link to pages you touched. No orphans.

## After the batch

- Update `wiki/index.md` with an entry for every page created or materially changed.
- Append a timestamped entry to `wiki/log.md` for **each** source, following the existing
  entry format there: what was ingested, which pages were created or updated, and any issues.
  Append only — never rewrite earlier entries.
- Bump `last-updated` on every page you touched.

## Hard rules

- **Never modify, move, rename, or delete anything in `raw/`.** It is read-only input.
- Do not create pages for sources you did not actually read.
- Do not add frontmatter fields or folders beyond what `AGENTS.md` defines.
- Do not report a source as ingested unless its summary page exists and is linked from
  `wiki/index.md`.
- If you run out of context or time mid-batch, finish the current source, log what remains,
  and stop cleanly.

## Report

Finish with a short summary: how many sources were ingested, the pages created and updated,
anything skipped and why, and what remains unread.
