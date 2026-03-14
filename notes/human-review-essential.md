---
title: "人工审查不可省略"
tags: [person/boris-cherny, topic/quality, topic/code-review]
---
# 人工审查不可省略

## 方法
- 即使大部分代码由 AI 编写，**人工审查仍然是必要环节**
- AI 生成代码的审查标准与人类代码相同
- 复杂或关键部分，在审查后可能需要手工重写
- Claude Code 定位为"原始的高级用户工具"，而非取代审查的自动化工具

## 适用场景
- 任何 AI 辅助编程的工作流中
- 建立团队 AI 代码审查规范
- 关键路径上的代码质量把关

## 边界
- 不意味着每一行都需要逐字审查——可以分层：关键路径精读，辅助代码快速扫描
- 审查的深度应与代码的重要性成正比

## 来源
- Boris Cherny, Latent Space Podcast (2025-05-08): "Human review remains essential even when a large share of code is model-written"
  https://www.latent.space/p/claude-code
- Boris Cherny, Peterman Pod (2025-12-15): "Handwrites critical parts when he has strong opinions"
  https://www.developing.dev/p/boris-cherny-creator-of-claude-code

相关：[[vibecoding-is-situational]]、[[subagents-for-review]]、[[boris-cherny-vibecoding]]、[[simon-willison-ai-coding]]
