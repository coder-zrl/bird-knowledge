---
type: project
title: Bird Knowledge
description: 一个 Codex-first、OKF-first 的个人知识库。
tags:
  - pkm
  - okf
  - codex
timestamp: 2026-06-29T13:51:02+08:00
---

# Bird Knowledge

Bird Knowledge 是一个以 Codex 为主要写作者、以 Open Knowledge Format（OKF）为长期文件契约的个人知识库。

这个仓库保持纯文本、git-friendly、可长期迁移。Obsidian 可以作为阅读器，Codex 可以作为主要写作者，但真正持久的格式约束是 OKF：Markdown 文件必须带 YAML frontmatter，并且知识页必须有非空的 `type` 字段。

## 格式规则

- 每个知识型 Markdown 文件都要有 YAML frontmatter。
- 每个知识型 Markdown 文件都要有非空的 `type`。
- 优先使用标准 Markdown 链接，不使用 Obsidian wikilinks。
- 内部链接使用 bundle-relative 路径，例如 `[Open Knowledge Format](/references/Open Knowledge Format.md)`。
- `index.md` 和 `log.md` 是根目录保留文件。
- `.git/`、`.obsidian/` 等隐藏工具目录不是知识内容。
- `.codex/skills/` 是给 AI runtime 读取的 Skill 配置，不是普通知识页。

## 目录结构

```text
index.md           根索引。
log.md             追加式活动日志。
hot.md             当前工作上下文和下一步 TODO。
.manifest.json     来源、页面和同步状态追踪。
.codex/skills/     给 AI runtime 读取的 Skill 配置。
.env               本地工具配置。
.obsidian/         可选的 Obsidian 阅读器配置。
_meta/             本地约定、分类法和 schema 说明。
_raw/              原始材料和未处理捕获。
_staging/          待人工审阅的生成内容。
_archives/         归档、快照和退休材料。
concepts/          可复用概念、心智模型、判断和区分。
entities/          人、工具、项目、组织、具体对象。
references/        有来源边界的事实笔记、书籍、论文、文章。
skills/            知识库里的程序性知识和可复用方法。
synthesis/         跨来源综合、原创分析和长文。
journal/           时间性记录、会话笔记和阶段性反思。
projects/          持续推进的知识项目。
```

## 知识流

```text
_raw/
  -> references/ or entities/
  -> concepts/
  -> synthesis/
  -> projects/
  -> index.md, log.md, hot.md, .manifest.json
```

原始材料先进入 `_raw/`。Codex 在保留来源边界的前提下，把它们整理成 `references/` 或 `entities/`，再抽象成 `concepts/`，最后形成 `synthesis/` 或 `projects/`。

## 读书项目风格

读一本书时，不要把所有笔记都塞进 `references/`。

- `_raw/books/` 保存 EPUB、PDF 等原始书籍文件。
- `references/书名.md` 保存书籍来源信息、资源路径、出版信息和稳定的作者模型摘要。
- `projects/书名/` 保存正在进行的阅读项目。
- `projects/书名/第一章 章节标题.md` 这类文件保存分章节读书笔记。
- 每章笔记按小节逐步追加；尚未讨论的小节不要提前写满。
- 从章节讨论中提炼出的稳定概念，再进入 `concepts/`。
- 跨多本书或多来源形成的综合判断，再进入 `synthesis/`。

最小例子：

```text
_raw/books/认知觉醒.epub
references/认知觉醒.md
projects/认知觉醒/第一章 大脑——一切问题的起源.md
```

## `skills/` 和 `.codex/skills/` 的区别

`skills/` 是知识库内容目录，用来保存人和 AI 都能阅读的方法论笔记，例如“如何做深度阅读”“如何整理一本书”。

`.codex/skills/` 是 AI runtime 配置目录，用来保存 Codex / Agent 执行任务时读取的 Skill，例如 `learn`。

简单说：

```text
skills/         知识库里的方法论笔记
.codex/skills/  AI 执行任务时读取的运行指令
```

## 当前工具

`obsidian-wiki` 已经全局安装，可以作为 Codex 操作知识库时的辅助工具。但这个仓库仍然是 OKF-first：文件格式、目录语义和长期契约以本仓库的 OKF 规则为准。
