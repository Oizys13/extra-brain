---
description: Append a timestamped note to wiki/log.md.
---

<!-- argument-hint: the thought or note to capture -->

# Capture a note

Append this to the activity log:

> $ARGUMENTS

If `$ARGUMENTS` is empty, ask what to capture and stop. Never write a placeholder entry.

## How to write the entry

1. Read `AGENTS.md` and the tail of `wiki/log.md` first. Match the existing entry format.
2. **Append only.** Add the entry at the bottom of `wiki/log.md`. Never edit, reorder, or
   delete earlier entries — not even to fix them. If a past entry was wrong, add a new one
   that corrects it.
3. Use a consistent, human-readable timestamp. Current local time, format:
   `### YYYY-MM-DD HH:MM — Short title`
   Keep it stable across the file; do not switch formats per entry.
4. Record the note faithfully. Preserve the user's own wording where the phrasing matters;
   do not embellish, interpret, or add facts that were not given. A short faithful entry
   beats a long invented one.
5. If the note is about an existing wiki page, name it in the entry so it can be traced.

## Updating pages

If the note clearly concerns a **project, person, or concept that already has a wiki page**,
update that page to reflect the note:

- Add the new information under the most fitting existing heading.
- Bump `last-updated` to today.
- Add or fix `related` links when the note connects to another page.
- Update that page's row in `wiki/index.md` only if its one-line summary is now wrong.

**Do not create new wiki pages from this command.** If the note belongs to something with
no page yet, capture it in the log and mention that a page might be worth creating later.
That is `/ingest`'s job.

## Hard rules

- Never modify, move, or delete anything in `raw/`.
- Do not rewrite earlier log entries or pages beyond the focused update above.
- Keep the log append-only and chronological.

Finish by quoting the entry you appended and naming any pages you updated.
