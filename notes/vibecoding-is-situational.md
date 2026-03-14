---
title: "Vibecoding 是场景化的"
tags: [person/boris-cherny, topic/vibecoding, topic/quality]
---
# Vibecoding 是场景化的

## 方法
- Vibecoding 主要适用于**一次性/原型**工作，不是所有代码都适合
- 对 AI 生成的代码保持**与人类代码相同的质量标准**——不好就不合并，迭代到达标
- 采用**配对模式（pairing）而非一次性生成**：对齐方案 → 审查输出 → 要求清理 → 迭代
- 对设计细节有强烈意见的关键部分，**手写**

## 适用场景
- 需要判断某个任务是否适合 vibecoding
- 建立团队 AI 代码质量标准
- 在效率和质量之间做权衡

## 边界
- "Vibecoding 一切"是危险的——核心业务逻辑、安全相关代码需要更高的审查标准
- 不同团队/项目的边界不同，需要根据实际情况调整

## 来源
- Boris Cherny, Peterman Pod (2025-12-15): "Vibecoding is situational, mainly for throwaway/prototype work"
  https://www.developing.dev/p/boris-cherny-creator-of-claude-code
- Boris Cherny, Peterman Pod (2025-12-15): "Same quality bar for AI and human code"
  https://www.developing.dev/p/boris-cherny-creator-of-claude-code

相关：[[prototype-discard-retry]]、[[human-review-essential]]、[[boris-cherny-vibecoding]]、[[karpathy-vibe-coding-origin]]、[[karpathy-nanochat-failure]]、[[karpathy-agentic-engineering]]、[[simon-willison-ai-coding]]、[[swyx-ai-engineer]]、[[pieter-levels-ship-fast]]
