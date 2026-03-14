# Agent Guide (Read This First)

目标：让本机 Claude Code / Codex 在阅读本仓库后，能够按统一规范理解内容并持续协作。

## 仓库用途
- 系统化 vibecoding 教程
- 收集名人分享的可验证技巧，并沉淀为可复用方法
- 结合我们自己的流程，形成稳定可执行的实践路径
- 维护可索引的技巧库、示例库、技能清单与 MCP 清单

## 读取顺序
1. 本文件 `AGENTS.md`
2. `README.md`
3. `docs/README.md`
4. `indexes/people.md`
5. `indexes/topics.md`
6. `indexes/tools.md`
7. `indexes/languages.md`
8. `tools/skills.md`
9. `tools/mcp.md`

## 内容结构
- `docs/`：线性教程主线
- `notes/`：原子化技巧条目（可双链、可按标签组织）
- `indexes/`：索引页（按人、语言、主题）
- `examples/`：可复现示例
- `tools/`：好用的 skills 与 MCP 归档

## 已收录人物
- **Boris Cherny**：Anthropic 的 Claude Code 负责人，公开分享过 Claude Code 的实践与流程。（来源：Latent Space, Every.to, Peterman Pod）
- **Andrej Karpathy**：公开提出”vibe coding”概念的来源人物。（来源：[X post](https://x.com/karpathy/status/1886192184808149383)）
- **Simon Willison**：Django 联合创始人，AI 编程实践者和博主。（来源：[simonwillison.net](https://simonwillison.net)）
- **Swyx (Shawn Wang)**：AI 工程师，Latent Space 播客主持人。（来源：[latent.space](https://www.latent.space)）
- **Fireship (Jeff Delaney)**：YouTube 技术内容创作者。（来源：[YouTube](https://www.youtube.com/@Fireship)）
- **Pieter Levels**：独立开发者，AI 快速发布实践者。（来源：[X](https://x.com/levelsio)）
- **Amjad Masad**：Replit CEO，AI 编程工具推动者。（来源：[X](https://x.com/amasad)）
- **Riley Brown**：AI Coding 内容创作者，语音优先 vibe coding 实践者。（来源：[X](https://x.com/rileybrown_ai)）

## 语言范围（计划收纳）
- TypeScript / JavaScript
- Python
- Go
- Rust
- Java
- C#
- Swift
- Kotlin
- SQL
- Bash / PowerShell

## notes 规范
- 每条技巧一个文件
- 文件名用短横线小写英文，避免空格
- 必须包含 YAML front matter，用于标签
- 末尾必须包含 `相关：` 双链列表

### Tag 体系
```
person/*   — 人物名（如 boris-cherny, andrej-karpathy）
topic/*    — 主题（如 vibecoding, workflow, quality, planning）
tool/*     — 工具（如 claude-code, cursor, replit, git）
language/* — 语言（如 typescript, python, rust）
source/*   — 来源类型（如 x, blog, youtube, podcast, talk）
```

### 示例
```md
---
tags: [person/boris-cherny, topic/workflow, tool/claude-code, source/podcast]
---
# Plan Mode 工作流

## 方法
- ...

## 适用场景
- ...

## 边界
- ...

## 来源
- Boris Cherny, Every.to transcript (2025-10-29): https://...

相关：[[prototype-discard-retry]]、[[parallel-sessions-worktrees]]
```

## 双链规范
- 使用 `[[文件名]]` 语法（不含路径和 .md 后缀）
- **双向性要求**：如果 A 引用了 B，B 也应在"相关"部分链回 A
- 同目录内非双链引用用相对路径
- 兼容 Obsidian、Logseq 等笔记软件

## 输出约束
- 不新增目录层级，除非明确要求
- 不移动现有文件，除非明确要求
- 内容必须可验证，外部观点必须有来源
