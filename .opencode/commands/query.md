---
description: Synthesise an answer from the wiki.
---

<!-- argument-hint: the question to answer -->

# Query the wiki

Answer this question using only what the wiki documents:

> $ARGUMENTS

If `$ARGUMENTS` is empty, ask what the question is and stop.

## Method

1. Read `AGENTS.md` for page conventions and citation expectations.
2. Read `wiki/index.md` and pick the pages most likely to be relevant.
3. Read those pages in full, then follow their `related` links and `sources` where the
   question requires it. Read more pages rather than fewer; do not answer from titles alone.
4. Synthesise across pages into a direct answer. Connect ideas that the pages do not yet
   connect themselves.

## Answer rules

- **Cite every factual claim by wiki page name**, inline, using wiki-links:
  "…as described in [[concepts/example-page]]". A claim without a citation is a bug.
- Where pages disagree, say so plainly: which page says what, and why they might conflict.
  Do not average the disagreement away or silently pick a side.
- Clearly separate:
  - **Documented** — stated in wiki pages, with citations.
  - **Inference** — your reasoning across pages, explicitly labelled as such.
  - **Gaps** — where the wiki does not contain enough evidence to answer. Say what is
    missing and what source would settle it. "The wiki does not cover this" is a valid and
    preferred answer over speculation.
- Do not fill gaps with outside knowledge. If you use general knowledge to frame the answer,
  label it and keep it out of the cited claims.
- Be concise. Short paragraphs and bullets. Answer first, support second.

## Suggested shape

```markdown
## Answer
## Evidence
## Tensions between pages
## Gaps
```

Omit any section that would be empty.

## Wiki updates

If the synthesis reveals a connection, distinction, or contradiction worth keeping, propose
the concrete change — which page, what text, which links — and **ask before writing it**.
Do not edit the wiki, `index.md`, or `log.md` in this command without confirmation.
