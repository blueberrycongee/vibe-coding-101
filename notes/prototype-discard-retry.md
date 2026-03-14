---
tags: [person/boris-cherny, topic/workflow, topic/prototyping]
---
# 原型-丢弃-重试（Prototype-Discard-Retry）

## 方法
- 先让 AI 生成一个粗糙版本（prototype），目的不是得到最终代码，而是**发现未知问题**
- 审视原型后，**丢弃并重试**，用新发现的认知重新引导 AI
- 反复迭代，每轮都带着更清晰的理解重新开始

## 适用场景
- 需求模糊、不确定要构建什么时
- 新技术/新领域的探索性开发
- 快速验证可行性（POC）

## 边界
- 不适合需求已经非常明确的任务（直接实现更高效）
- 要注意控制迭代轮数，避免无限丢弃
- 每轮丢弃前应提炼出至少一条新认知

## 来源
- Boris Cherny, Every.to "How to Use Claude Code Like the People Who Built It" (2025-10-29)
  https://every.to/podcast/transcript-how-to-use-claude-code-like-the-people-who-built-it

相关：[[plan-mode-workflow]]、[[boris-cherny-vibecoding]]
