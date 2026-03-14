---
title: "用 Subagents 做代码审查和迁移"
tags: [person/boris-cherny, topic/workflow, topic/code-review, tool/claude-code]
---
# 用 Subagents 做代码审查和迁移

## 方法
- 将大任务拆分成多个子块，**扇出（fan out）多个 subagent** 并行处理
- 典型用途：代码审查、大规模代码迁移
- 收集各 subagent 的结果后，**人工去重和过滤误报**
- 保持主上下文窗口干净，避免上下文膨胀

## 适用场景
- 代码库范围的审查（如安全审计、风格统一）
- 大规模重命名、API 迁移
- 需要从多个角度审视同一问题

## 边界
- Subagent 之间无法共享状态，任务必须独立
- 误报率可能较高，需要人工筛选
- 对 API 配额消耗较大

## 来源
- Boris Cherny, Every.to transcript (2025-10-29): "fans out multiple subagents, then dedupes false positives"
  https://every.to/podcast/transcript-how-to-use-claude-code-like-the-people-who-built-it
- Boris Cherny, X thread (2026-01-31): "Use subagents to throw more compute at problem chunks"
  https://threadreaderapp.com/thread/2017742741636321619.html

相关：[[parallel-sessions-worktrees]]、[[plan-mode-workflow]]、[[boris-cherny-vibecoding]]、[[human-review-essential]]
