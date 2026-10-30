# Extra Brain

A personal knowledge management vault built with [Obsidian](https://obsidian.md/), structured as a **second brain**: raw source material on one side, curated synthesis on the other.

---

## Structure

```
extra-brain/
├── raw/          # Original sources — never modified (exports, PDFs, transcripts)
├── wiki/         # Curated knowledge — maintained by the agent
│   ├── index.md          Master catalog of every wiki page
│   ├── log.md            Append-only activity log
│   ├── concepts/         Topic pages (concept, entity, source-summary, comparison)
│   ├── projects/         Project pages (status, decisions, next actions)
│   └── people/           Person pages (context, conversations, commitments)
├── journal/      # Daily notes (YYYY-MM-DD.md) — free-form capture
├── content/      # Content pipeline (ideas → drafts → published)
├── AGENTS.md     # Operating rules for AI agents working in this vault
└── README.md     # This file
```

---

## How It Works

| Zone | Owner | Rule |
|------|-------|------|
| `raw/` | User | Add only. Never edit or delete existing files. |
| `wiki/` | Agent | Synthesized, linked pages traceable to `raw/` or URLs. |
| `journal/` | User | Free-form daily notes. Agent may append recaps when asked. |
| `content/` | User | Drafts and published work in progress. |

### Wiki page lifecycle

1. **Capture** — drop source material into `raw/`.
2. **Synthesize** — agent creates or updates a `wiki/` page linked to the source.
3. **Log** — every change is recorded in `wiki/log.md`.
4. **Catalog** — `wiki/index.md` always reflects the current set of pages.

---

## Page Conventions

Every wiki page starts with YAML frontmatter:

```yaml
---
title: Page Title
type: concept          # concept | entity | source-summary | comparison | project | person
sources:
  - raw/path/to/source.pdf
  - https://example.com
related:
  - "[[concepts/related-page]]"
created: YYYY-MM-DD
last-updated: YYYY-MM-DD
---
```

Standard heading order: `# Title` → `## Details` → `## Contradictions and open questions` → `## Related` → `## Sources`.

---

## Topics

This vault covers the owner's areas of ongoing focus:

- **AI & software** — tools, systems, research papers, and personal projects
- **Research & study** — annotated reading and concept synthesis
- **Personal** — habits, health, and life decisions with reasoning preserved

---

## Getting Started (new machine)

```bash
git clone <repo-url>
# Open the cloned folder as a vault in Obsidian
```

> **Note:** `.obsidian/plugins/` and `.obsidian/themes/` are gitignored — re-enable your community plugins after cloning.

---

## Rules for AI Agents

See [`AGENTS.md`](./AGENTS.md) for the full operating specification: vault structure, frontmatter schema, linking conventions, style guide, and what agents are and are not allowed to do.
