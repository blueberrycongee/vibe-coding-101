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
5. `indexes/languages.md`
6. `tools/skills.md`
7. `tools/mcp.md`

## 内容结构
- `docs/`：线性教程主线
- `notes/`：原子化技巧条目（可双链、可按标签组织）
- `indexes/`：索引页（按人、语言、主题）
- `examples/`：可复现示例
- `tools/`：好用的 skills 与 MCP 归档

## 初期名人范围（调研）
- Boris Cherny：Anthropic 的 Claude Code 负责人，公开分享过 Claude Code 的实践与流程。（来源：[Anthropic Webinar](https://www.anthropic.com/events/claude-code-for-service-delivery)）
- Andrej Karpathy：公开提出“vibe coding”概念的来源人物。（来源：[Wikipedia](https://en.wikipedia.org/wiki/Vibe_coding)）

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

示例：
```md
---
tags: [person/boris, language/rust, topic/prompting]
---
# 标题
内容...
相关：[[vibe-workflow]]
```

## 链接规范
- 同目录内用相对链接
- 需要双链时使用 `[[文件名]]`，以兼容笔记软件

## 输出约束
- 不新增目录层级，除非明确要求
- 不移动现有文件，除非明确要求
- 内容必须可验证，外部观点必须有来源
