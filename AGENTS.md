---
type: instruction
title: Codex OKF Management Rules
description: Agent rules for maintaining Bird Knowledge as an Open Knowledge Format bundle.
tags:
  - codex
  - okf
timestamp: 2026-06-29T13:51:02+08:00
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

## Reading Project Style

When reading a book, keep source notes and learning-process notes separate.

- Store source files such as EPUB or PDF under `_raw/books/`.
- Create or update `references/<Book Title>.md` for the source record: bibliographic facts, resource path, source boundary, and stable author-model summaries.
- Do not put all chapter discussion, user answers, practice logs, or learning state into `references/`.
- Put active reading notes under `projects/<Book Title>/`.
- Use one markdown file per chapter, named with chapter number and title, for example `projects/认知觉醒/第一章 大脑——一切问题的起源.md`.
- Append only the sections that have actually been discussed. Do not prefill later sections just because they exist in the table of contents.
- Extract durable abstractions from chapter notes into `concepts/` only after they become reusable beyond the book.
- Put cross-book interpretation or higher-level synthesis into `synthesis/`.

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
