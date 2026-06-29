---
type: note
title: Hot Cache
description: Recent working context for the Bird Knowledge OKF bundle.
tags:
  - cache
  - working-context
timestamp: 2026-06-29T13:51:02+08:00
---

# Hot Cache

Bird Knowledge is now OKF-first. Codex should manage durable knowledge pages as markdown files with YAML frontmatter and a required `type` field.

## Recent Activity

- Initialized `obsidian-wiki` globally.
- Trimmed project-local agent folders.
- Reoriented repository conventions around OKF.
- Added [福格行为模型](/references/福格行为模型.md) as the first book reference.
- Added [How To Fix Your Entire Life In 1 Day](/references/Dan Koe - How To Fix Your Entire Life In 1 Day.md) and extracted identity-change concepts.
- Stored the user-provided Dan Koe X article original and capture notes in one [raw markdown source](/_raw/web/dan-koe-how-to-fix-your-entire-life-in-1-day.md).
- Added [如何在一天内修复整个人生](/references/Dan Koe - 如何在一天内修复整个人生.md) as the Chinese reading version.
- Consolidated the AI-era learning and growth series into one long-form synthesis: [AI时代，人成长的第一性原理](/synthesis/AI时代，人成长的第一性原理.md).
- Moved the Learn runtime skill to `/.codex/skills/learn/SKILL.md` in the repository as a project-local AI runtime asset.
- Added [什么是认知？——重新理解世界、判断与成长](/synthesis/什么是认知？——重新理解世界、判断与成长.md) as the next synthesis in the AI-era growth framework.
- Added [模型更新阅读法](/skills/模型更新阅读法.md) as a reusable reading method that uses AI to expose prediction errors and update the reader's explanation system.
- Updated `/.codex/skills/learn/SKILL.md` to include Model Update Reading as a dedicated reading mode.
- Began model-update reading of [认知觉醒](/references/认知觉醒.md); active chapter notes live under `/projects/认知觉醒/`, starting with [第一章 大脑——一切问题的起源](/projects/认知觉醒/第一章 大脑——一切问题的起源.md).
- Updated [README](/README.md) and [Codex OKF Management Rules](/AGENTS.md) with the reading project style.

## Active Threads

- Design a Karpathy-style personal knowledge base that remains plain-text, git-friendly, Codex-writable, and OKF-compatible.
- Read 《福格行为模型》 with the user and extract durable behavior-design concepts over time.
- Connect Dan Koe's identity-first behavior change lens with B.J. Fogg's behavior design model.
- Develop an AI-era growth framework that treats AI as an amplifier for practice, feedback, reflection, and self-update.
- Continue extracting reusable concepts from the AI-era growth framework, especially cognition, world model, judgment, and model update speed.
- TODO research question: 为什么好的认知模型具有预测能力？连接世界模型、抽象、第一性原理和科学理论。
- Consider folding Model Update Reading into the runtime `learn` skill as a dedicated reading mode.
- Continue [第一章 大脑——一切问题的起源](/projects/认知觉醒/第一章 大脑——一切问题的起源.md) from first-chapter recap, then move to Chapter 2.

## Key Takeaways

- OKF is the file contract.
- Obsidian is a reader.
- Codex is the main writer.
- `obsidian-wiki` is helper tooling, not the primary schema.
- For copyrighted books, keep concise notes and avoid copying long passages into the vault.
- For X articles, prefer user-provided exports/MHTML when public logged-out capture cannot access the full original.
- In the AI-era growth model, AI is an accelerator rather than the engine; the engine is inner drive.
- Growth speed depends more on model update velocity than on raw learning time.
- High-quality learning updates mental models through first-principles questions, practice, feedback, and transfer.
- AI's strongest learning role is cognitive partner, not answer machine.
- The article theme is human growth: learning is a mechanism, AI is a tool, and growth is the final purpose.
- The whole theory should resolve into one loop: reality, practice, feedback, model update, judgment, action, and back to reality.
- Slogan: Growth is the goal. Learning is the mechanism. AI is the accelerator.
- The article now uses a question-driven structure and adds the boundary: AI can help understanding and feedback, but should not replace reasoning, judgment, or practice.
- The article's durable main line is now explicit: human growth is continuous cognitive model updating; the seven questions are named as 第一性学习七问 / First-Principles Learning Framework.
- The `learn` skill operationalizes the article's method as Explore -> Essence -> Connect -> Challenge -> Practice -> Feedback -> Reflection -> Mental Model Update.
- Cognition is now defined as a self-correcting internal interpretation system that reduces environmental uncertainty, explains reality, predicts outcomes, and supports judgment and action.
- Judgment is defined as the choice made in a concrete situation through the joint action of cognition and values.
- The cognition essay now standardizes on “解释系统” as its core theoretical language and trims repeated “model update” claims.
- Explanation system is now explicitly defined as the internal rules a person uses to understand the world, predict the future, and guide action; cognition is framed as explanation, prediction, and correction.
- Rewrote the cognition synthesis around explanation, judgment, and feedback correction while preserving the core definition of cognition as a revisable explanation system.
- Model Update Reading reframes AI-assisted reading as old explanation system -> author's model -> AI challenge -> conflict exposure -> explanation system update.
- Runtime `learn` skill now applies Model Update Reading when the learning object is a book, paper, course, long article, or video.
- 《认知觉醒》第一节当前更新：真正的自律不是理智脑亲自干活，而是理智脑当设计师，让本能和情绪愿意出力。
- 《认知觉醒》第二节当前更新：学习只有真实提升能力、缩小欲望和能力差距时，才会缓解焦虑；求多求快会放大欲望并制造额外焦虑。
- 《认知觉醒》第三节当前更新：耐心不是硬靠毅力忍出来的，而是看清成长规律后形成的长远目光。
- 《认知觉醒》第一章笔记已从问答记录整理为正式读书笔记结构，并补足复利效应、舒适区边缘、成长权重对比、学习平台期、焦虑类型对应方法和行动原则。
- Runtime `learn` skill now distinguishes user reading notes from answers to prompts, identifies missing note content, and asks before AI fills gaps.
- Reading projects separate source records from learning-process notes: `references/` records the source, while `projects/<Book Title>/` stores chapter notes.
