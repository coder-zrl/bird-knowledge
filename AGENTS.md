---
type: instruction
title: Codex OKF Management Rules
description: Agent rules for maintaining Bird Knowledge as an Open Knowledge Format bundle.
tags:
  - codex
  - okf
timestamp: 2026-06-23T01:02:26+08:00
---

# Codex OKF Management Rules

This repository is an Open Knowledge Format-first personal knowledge base.

Use `obsidian-wiki` skills as helpful operations when useful, but do not let their native frontmatter model override OKF conventions.

## Primary Contract

- The durable knowledge format is OKF.
- Every non-reserved markdown knowledge page must include YAML frontmatter with a non-empty `type`.
- Recommended frontmatter fields are `type`, `title`, `description`, `resource`, `tags`, and `timestamp`.
- Additional fields are allowed when they are useful.
- Keep markdown human-readable and git-diffable.
- Prefer standard markdown links over Obsidian wikilinks.
- Use bundle-relative internal links, for example `[Karpathy](/entities/Andrej Karpathy.md)`.

## Reserved Files

- `index.md` is the root OKF index.
- `log.md` is the append-only activity log.
- Hidden directories such as `.git/` and `.obsidian/` are local tooling, not knowledge content.

## Directory Semantics

- `_raw/`: unprocessed captures and source drops.
- `_staging/`: generated notes awaiting human review.
- `_archives/`: retired notes and snapshots.
- `_meta/`: local conventions, taxonomy, and schema notes.
- `concepts/`: abstract ideas, models, claims, distinctions.
- `entities/`: concrete people, tools, projects, organizations, artifacts.
- `references/`: source-backed factual notes, specs, papers, articles, posts.
- `skills/`: procedural knowledge and reusable practices.
- `synthesis/`: higher-level analysis connecting multiple notes.
- `journal/`: time-bound records and session notes.
- `projects/`: active knowledge projects.

## Write Behavior

- Prefer updating an existing page over creating a duplicate.
- Preserve source boundaries: do not mix quoted/source material with personal synthesis without labeling it.
- Do not invent citations, quotes, URLs, or publication facts.
- When ingesting external material, create or update a `references/` page first.
- Extract durable abstractions into `concepts/`.
- Link concrete people, tools, and projects through `entities/`.
- Put cross-source interpretation in `synthesis/`.
- Update `index.md`, `log.md`, `hot.md`, and `.manifest.json` after meaningful writes.

## Page Template

```markdown
---
type: concept
title: Example Concept
description: One-sentence summary of the page.
resource: ""
tags:
  - example
timestamp: YYYY-MM-DDTHH:MM:SS+08:00
---

# Example Concept

Write the page in clear markdown.

## Links

- [Related Page](/concepts/Related Page.md)
```

