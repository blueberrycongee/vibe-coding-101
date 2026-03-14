---
title: "Simon Willison 的 AI 编程实践"
tags: [person/simon-willison, topic/vibecoding, topic/workflow, topic/vibe-engineering, tool/claude-code, tool/chatgpt, source/blog]
---
# Simon Willison 的 AI 编程实践

## 人物简介
Simon Willison 是 Django 联合创始人、Datasette 作者，活跃的 AI 工具使用者和技术博主（simonwillison.net）。他大量使用 LLM 辅助编程，同时保持清醒的批判视角。

## 核心立场：严格区分 vibe coding 与 AI 辅助编程

Willison 自称这是 "a hill I am willing to die on"（愿意为之死守的山头）：

- **Vibe coding** = 用 AI 生成代码，但**完全不关心**生成出来的代码是什么（Karpathy 原始定义）
- **AI 辅助编程** ≠ vibe coding。如果 LLM 写了所有代码但你逐行审查、测试并理解了它，那不是 vibe coding

> [!important] Simon Willison 的黄金法则
> I won't commit any code if I couldn't explain exactly what it does to somebody else.

## 关键文章时间线

### "Will the future of software development run on vibes?" (2025-03-06)
- Vibe coding 是探索模型极限的有趣方式，对原型制作有用
- 但用 vibe coding 构建生产代码库"显然是个糟糕的主意"
- 来源：https://simonwillison.net/2025/Mar/6/vibe-coding/

### "Not all AI-assisted programming is vibe coding" (2025-03-19)
- Vibe coding 极大降低了编程入门门槛，让数百万新人能构建自定义工具
- 安全边界：涉及密钥/API key 时不要 vibe code；不要对有不可控账单的 API vibe code；使用沙箱环境
- 来源：https://simonwillison.net/2025/Mar/19/vibe-coding/

### 批评 "Vibe Coding" 书名滥用 (2025-05-01)
- 批评《Vibe Coding: Building Production-Grade Software》——"连 Karpathy 的推文都没读完"
- 生产级软件恰恰是 vibe coding 的反面，术语遭遇"语义扩散"
- 来源：https://simonwillison.net/2025/May/1/not-vibe-coding/

### 提出 "Vibe Engineering" 概念 (2025-10-07)
- 定义：专业人士负责任地使用 LLM 加速工作，"在使用 LLM 加速工作的同时，自豪而自信地对产出负责"
- **核心洞见**："AI 工具放大现有专业能力。你作为软件工程师的技能和经验越丰富，使用 LLM 获得的结果就越快越好。"
- **LLM 奖励的实践**：TDD、提前规划、全面文档、Git 熟练度、CI/CD、代码审查文化、手动 QA
- 来源：https://simonwillison.net/2025/Oct/7/vibe-engineering/

### 演化为 "Agentic Engineering Patterns" (2026-02-23)
- 从 vibe engineering 演化为 agentic engineering
- 核心区别：coding agent 能"同时生成和执行代码"
- 最大挑战是"适应代码编写成本几乎为零的后果"
- **Red/Green TDD** 帮助 agent 产出更简洁可靠的代码
- 来源：https://simonwillison.net/2026/Feb/23/agentic-engineering-patterns/

## 实用技巧

| 技巧 | 说明 |
|------|------|
| 先简后繁 | 让 LLM 先写简单版本，验证可行后再迭代 |
| 先写计划 | 对长变更先让 LLM 写计划，反复迭代到合理 |
| Red/Green TDD | 测试驱动开发与 coding agent 配合效果极佳 |
| 使用沙箱 | ChatGPT Code Interpreter、Claude Artifacts |
| 异步 agent 研究 | 创建 GitHub 仓库，让 agent 自由工作 |
| CLI 优于 REST API | 让 agent 使用 CLI 工具而非 REST API，节省上下文 |
| 示例驱动提示 | 从冗长描述性提示转向简洁的、基于示例的提示 |

## 来源
- Simon Willison's blog: https://simonwillison.net
- Tag: vibe-coding: https://simonwillison.net/tags/vibe-coding/
- Tag: ai-assisted-programming: https://simonwillison.net/tags/ai-assisted-programming/
- Pragmatic Engineer Podcast (2024-09-25)
- TWIML AI Podcast #701 (2024-09-16)

相关：[[human-review-essential]]、[[vibecoding-is-situational]]、[[karpathy-agentic-engineering]]
