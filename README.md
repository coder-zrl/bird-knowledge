---
type: project
title: Bird Knowledge
description: A Codex-first personal knowledge base managed as an Open Knowledge Format bundle.
tags:
  - pkm
  - okf
  - codex
timestamp: 2026-06-23T01:02:26+08:00
---

# Bird Knowledge

Bird is a personal knowledge base managed as an Open Knowledge Format bundle.

The repository stays plain-text and git-friendly. Obsidian can be used as a reader, and Codex can be used as the main writer, but the durable file contract is OKF: markdown files with YAML frontmatter and a required `type` field.

## Format Rules

- Every knowledge markdown file has YAML frontmatter.
- Every knowledge markdown file has a non-empty `type`.
- Prefer standard markdown links over Obsidian wikilinks.
- Internal links should be bundle-relative, for example `[Open Knowledge Format](/references/Open Knowledge Format.md)`.
- `index.md` and `log.md` are reserved root files.
- Hidden tool directories are not part of the knowledge bundle.

## Layout

```text
index.md         Root OKF index.
log.md           Append-only activity log.
hot.md           Recent working context as an OKF note.
.manifest.json   Local ingest and sync tracking.
.env             Local tool configuration.
.obsidian/       Optional Obsidian reader configuration.
_meta/           Format notes, taxonomy, and local conventions.
_raw/            Unprocessed captures waiting for ingest.
_staging/        Human review queue for generated notes.
_archives/       Archived snapshots or retired material.
concepts/        Abstract ideas, mental models, claims, distinctions.
entities/        People, tools, projects, organizations, concrete objects.
references/      Source-backed factual notes, specs, papers, articles.
skills/          Procedural knowledge and reusable ways of working.
synthesis/       Cross-source analysis and higher-level essays.
journal/         Time-bound notes and session records.
projects/        Active knowledge projects.
```

## Knowledge Flow

```text
_raw/
  -> references/ or entities/
  -> concepts/
  -> synthesis/
  -> projects/
  -> index.md, log.md, hot.md, .manifest.json
```

Raw material starts in `_raw/`. Codex promotes it into OKF pages with source boundaries, then links related concepts, entities, references, and synthesis notes.

## Current Tooling

`obsidian-wiki` is installed globally for Codex-oriented operations, but this repository is intentionally OKF-first. Use `obsidian-wiki` as a helper, not as the source of truth for file format decisions.

