---
type: reference
title: Matt Pocock - Writing Great Skills
description: Matt Pocock 关于如何设计可预测、可维护的 Agent Skill 的原始方法说明。
resource: "https://github.com/mattpocock/skills/tree/main/skills/productivity/writing-great-skills"
author: Matt Pocock
language: en
tags:
  - agent-skills
  - prompt-engineering
  - context-engineering
  - ai-learning
timestamp: 2026-07-13T04:34:09+08:00
---

# Matt Pocock - Writing Great Skills

这是一份来源笔记，记录 Matt Pocock 对「优秀 Agent Skill」的设计原则。正文依据其公开仓库中的 `writing-great-skills/SKILL.md` 与 `GLOSSARY.md`；相关演讲视频为《Building Great Agent Skills: The Missing Manual》。

## Source

- Author: Matt Pocock
- Primary document: [writing-great-skills/SKILL.md](https://github.com/mattpocock/skills/blob/main/skills/productivity/writing-great-skills/SKILL.md)
- Glossary: [GLOSSARY.md](https://github.com/mattpocock/skills/blob/main/skills/productivity/writing-great-skills/GLOSSARY.md)
- Related video: [Building Great Agent Skills: The Missing Manual](https://www.youtube.com/watch?v=UNzCG3lw6O0)
- Related announcement: [AI Engineer X post](https://x.com/aiDotEngineer/status/2071670308642414953)

## Core Problem

【原文内容】Skill 的根本作用是从随机系统中争取确定性：不是要求每次输出相同，而是让 Agent 每次采用更一致、可预期的工作过程。

## Author Model

### 1. Invocation：谁来触发

【原文内容】模型自动触发的 Skill 能被 Agent 与其他 Skill 发现，但其描述会常驻上下文，产生 context load。用户手动触发的 Skill 没有这项上下文负担，但用户必须记住它何时可用，产生 cognitive load。

- 只有必须让模型自行发现、或需要被其他 Skill 调用时，才选择自动触发。
- 若只有用户会主动启动，选择手动触发。
- 手动 Skill 太多时，用一个 router skill 帮用户记住有哪些 Skill 以及各自适用时机。

### 2. Information Hierarchy：把步骤与资料分层

【原文内容】Skill 由步骤（steps）和参考资料（reference）构成。信息按“Agent 现在有多迫切需要它”分层：主文件中的步骤、主文件中的参考资料、通过 context pointer 按需加载的外置参考资料。

- 每条执行路径都需要的内容留在主文件。
- 只在特定分支需要的内容放到链接文件中，按需披露。
- 把同一概念的定义、规则与例外放在一起，避免分散。

### 3. Steering：稳定执行行为

【原文内容】每一步应有完成标准（completion criterion）。强标准既可检查，又要求足够的覆盖范围；它能减少 Agent 在步骤尚未完成时急于进入下一步。

【原文内容】leading word 是模型预训练中已有的紧凑概念，如 `red`、`tracer bullets`。它可以用少量 token 锚定一组行为，并同时帮助触发与执行。

- 优先正向描述目标行为；负向禁令容易让被禁止的模式反而进入注意力中心。
- 不要用“仔细”“高质量”之类本身不改变默认行为的弱要求；换成可观察的目标或更有区分度的词。

### 4. Pruning：持续删减

【原文内容】每个含义应只有一个权威位置。逐句检查相关性，并删除不会改变模型行为的 no-op。

需要识别的常见问题：

- `duplication`：同一含义在多处重复，增加维护成本并错误抬高其权重。
- `sediment`：随着时间堆积的过期、无关内容。
- `sprawl`：即使每句都有效，主文件仍过长，导致注意力被稀释。
- `no-op`：模型默认就会做，写了也不改变行为的指令。
- `premature completion`：后续步骤吸引注意力，导致当前步骤过早结束。

## Practical Writing Loop

【基于原文整理】

1. 先定义要稳定的工作过程与完成标准。
2. 决定手动还是自动触发，并为自动触发写简短、分支明确的描述。
3. 写出每次都必经的步骤；每步写可检查的完成标准。
4. 将仅特定情况需要的资料移至外置参考文件。
5. 只因独立触发需求或“后续步骤导致抢跑”而拆分 Skill。
6. 在真实任务中运行，观察失败模式后再补充或删减。
7. 定期移除重复、沉积、冗长与无效指令。

## My Learning Notes

【AI 推导】可以把 Skill 视为 Agent 的“注意力架构”：触发机制决定何时注意，信息层级决定看见什么，完成标准决定何时停止，剪枝决定长期是否仍清晰。

一个实用检验式：

> 好 Skill = 正确触发 × 恰当上下文 × 明确完成标准 × 持续剪枝。

## Links

- [模型更新阅读法](/skills/模型更新阅读法.md)
- [如何写出优秀的 Skill](/projects/智能体技能学习/如何写出优秀的 Skill.md)
- [Bird Knowledge Index](/index.md)
