---
title: "并行会话与 Git Worktrees"
tags: [person/boris-cherny, topic/workflow, topic/parallelism, tool/claude-code, tool/git]
---
# 并行会话 + Git Worktrees

## 方法
- 同时运行 **3-5 个 Claude Code 会话**，每个在独立的 git worktree 或 checkout 中工作
- 每个会话处理一个独立任务，互不干扰
- 利用 AI 的并行能力最大化产出

## 适用场景
- 有多个独立的子任务可以同时推进
- 大型重构或迁移项目
- 需要快速推进多个功能分支

## 边界
- 任务之间不能有强依赖（否则会产生合并冲突）
- 需要足够的机器资源（内存、API 配额）
- 合并阶段仍需人工审查和冲突解决

## 来源
- Boris Cherny, X thread (2026-01-31): "Run 3-5 Claude sessions in parallel using git worktrees/checkouts"
  https://threadreaderapp.com/thread/2017742741636321619.html

相关：[[plan-mode-workflow]]、[[subagents-for-review]]
