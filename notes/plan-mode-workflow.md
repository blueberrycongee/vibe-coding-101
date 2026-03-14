---
title: "Plan Mode 工作流"
tags: [person/boris-cherny, topic/workflow, topic/planning, tool/claude-code]
---
# Plan Mode 工作流

## 方法
- 对于**较复杂的功能开发**，先进入 plan mode（Claude Code 中 Shift+Tab）对齐方案
- 在 plan 阶段让 AI **提出澄清问题**，确保双方理解一致
- Plan 通过后再进入实现阶段
- 当实现偏离时，**重新进入 plan mode** 而不是硬修

## 适用场景
- 功能开发涉及多个文件或模块
- 需求存在多种实现路径需要选择
- 团队协作中需要对齐方案

## 边界
- 简单修改（如改样式、修 typo）不需要 plan mode
- Plan mode 的边界随模型能力提升而变化——模型越强，可以直接实现的任务越多
- Plan 不是一次性的，需要在执行中持续校准

## 来源
- Boris Cherny, Every.to transcript (2025-10-29): "Plan mode improves success rate"
  https://every.to/podcast/transcript-how-to-use-claude-code-like-the-people-who-built-it
- Boris Cherny, X thread (2026-01-31): "Start complex tasks in plan mode; re-plan when things go sideways"
  https://threadreaderapp.com/thread/2017742741636321619.html

相关：[[prototype-discard-retry]]、[[parallel-sessions-worktrees]]、[[boris-cherny-vibecoding]]、[[invest-in-claude-md]]、[[slash-commands-standardize]]、[[subagents-for-review]]
