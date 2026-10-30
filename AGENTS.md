# AGENTS.md — Operating rules for the Extra Brain vault

This vault is a second brain: `raw/` holds source material, `wiki/` holds curated knowledge.
Anyone (human or agent) working here must follow the rules below.

## 1. Project Structure

The vault is split into two domains: **sources** and **synthesis**.

- **`raw/` — source documents.** Original exports, downloads, and transcripts, exactly as
  received. This is the user's domain.
  - **Never modify, rename, reformat, or delete anything in `raw/`.** Add new files only.
  - Every claim in `wiki/` must be traceable to a file here or to a URL.
- **`wiki/` — curated knowledge.** Synthesized, linked, and maintained by the agent. This
  is the agent's domain.
  - **`index.md`** — master catalog. Every wiki page appears here with a one-line summary
    and a last-updated date. Update it whenever a page is created, renamed, or deleted.
  - **`log.md`** — append-only activity log, newest entries at the bottom. Record every
    create / update / merge / rename / delete, the pages affected, the sources used, and a
    short reason. Never rewrite or delete past entries; correct them with a new entry.
  - **`concepts/`** — topic and reference pages: `concept`, `entity`, `source-summary`,
    and `comparison` types.
  - **`projects/`** — `project` pages: status, decisions, next actions.
  - **`people/`** — `person` pages: context, conversations, commitments.

Supporting folders:

- **`journal/`** — daily notes, one file per day (`YYYY-MM-DD.md`). The user's free-form
  space. Do not rewrite existing entries; it is acceptable to append a recap when asked.
  Durable knowledge found here should be promoted into `wiki/`.
- **`content/`** — content pipeline for published/shared work (ideas, drafts, published).
- **`.obsidian/`** — editor configuration. Do not edit unless explicitly asked.

Each folder has a `README.md` describing what belongs there. Read it before adding files.

## 2. Page Conventions

### Frontmatter

Every wiki page (`wiki/**/*.md`, except `index.md` and `log.md`) starts with YAML
frontmatter containing exactly these fields:

```yaml
---
title: Attention Mechanisms
type: concept
sources:
  - raw/arxiv-papers/2017-1706.03762-attention-is-all-you-need.pdf
  - https://arxiv.org/abs/1706.03762
related:
  - "[[concepts/transformers]]"
  - "[[concepts/retrieval-augmented-generation]]"
created: 2026-10-28
last-updated: 2026-10-28
---
```

Field rules:

| Field | Rule |
| --- | --- |
| `title` | Human-readable title; must match the page's H1. |
| `type` | Exactly one of: `concept`, `entity`, `source-summary`, `comparison`, `project`, `person`. |
| `sources` | List of `raw/` paths or URLs. Use `[]` only if genuinely unsourced, and say why in the body. |
| `related` | List of wiki-links, quoted: `"[[concepts/other-page]]"`. |
| `created` | ISO date `YYYY-MM-DD`, set once. |
| `last-updated` | ISO date `YYYY-MM-DD`, bumped on every substantive edit. |

`type` determines placement: `project` → `projects/`, `person` → `people/`, everything else
→ `concepts/`. Do not add fields not listed above without asking.

### Linking and atomicity

- Use Obsidian **wiki-links** (`[[concepts/page-name]]`), never bare relative paths, for
  internal references. Link to `raw/` files as inline code or markdown links, since they
  are not wiki pages.
- **One idea per page.** If a page covers two distinct ideas, split it and link the pieces.
  Prefer updating and linking existing pages over creating near-duplicates; record aliases
  in the body instead.
- Every page must be reachable from at least one other page and listed in `index.md`.
- No orphan pages. When deleting or merging, fix inbound links and log the change.

### Heading structure

Use this order consistently; omit a section only if it would be empty.

```markdown
# Title

One- or two-sentence summary/definition.

## Details
## Contradictions and open questions   (only when applicable)
## Related
## Sources
```

- Exactly one H1, matching `title`.
- Do not skip heading levels.
- `## Related` lists wiki-links with a few words on why they connect.
- `## Sources` lists the raw files/URLs actually used, with the specific claim each supports
  when it is not obvious.

### Filenames

Lowercase, hyphenated, no spaces or dates (dates live in frontmatter):
`concepts/spaced-repetition.md`, `people/ada-lovelace.md`.

## 3. Style Guide

- Write clear, concise prose. Short sentences, plain language, no filler.
- Prefer bullet points over paragraphs for anything list-shaped: facts, steps, options,
  comparisons.
- **Attribute every claim to its source.** Name the source inline (e.g. "per the 2024
  export", "Kahneman, *Thinking, Fast and Slow*, ch. 1") and keep the full reference in
  `## Sources`.
- Separate what a source says from your own inference. Mark inference explicitly
  ("likely", "this suggests"), and never present it as sourced fact.
- **Note contradictions explicitly** in `## Contradictions and open questions`: state which
  sources disagree, how, and what would resolve it. Do not silently pick a winner.
- Preserve the user's own wording for their ideas and preferences; quote them rather than
  paraphrasing when the exact phrasing matters.
- No invented facts, dates, names, or citations. If something is unknown, write that it is
  unknown.
- Use ISO dates (`YYYY-MM-DD`) everywhere.

## 4. Domain Context

This vault belongs to someone whose conversations and notes mostly concern AI, software, and
tools; research and study; and personal life and health. Day to day, the focus is on tools and
systems they use or build and on named projects and research threads, though much of what gets
captured is still ideas rather than specific people or entities. The vault exists to remember
decisions and the reasoning behind them, so settled questions do not get re-litigated. It should
also build reusable knowledge out of scattered conversations and papers, track learning over
time, and surface patterns in habits, health, and personal life. Prefer pages that record the
reasoning, not just the conclusion. When in doubt, capture the idea and link it — most of the
value here comes from connections rather than from a complete filing system.
