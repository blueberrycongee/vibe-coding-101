---
tags: [person/boris-cherny, topic/workflow, topic/automation, tool/claude-code]
---
# 用 Slash Commands 标准化工作流

## 方法
- 为重复性任务创建 **slash commands（自定义命令）**
- 典型用途：commit、PR 创建、功能开发流程、代码审查
- 在命令中预设权限允许，减少交互摩擦
- 将命令提交到 git，团队共享

## 适用场景
- 团队中有固定的开发流程需要标准化
- 经常重复的操作（提交、部署、测试）
- 需要降低新成员上手门槛

## 边界
- 命令应保持简洁，避免过度封装
- 不适合一次性或探索性任务
- 需要定期审查和更新命令内容

## 来源
- Boris Cherny, Every.to transcript (2025-10-29): "used to standardize workflows (commit/PR/feature dev)"
  https://every.to/podcast/transcript-how-to-use-claude-code-like-the-people-who-built-it
- Boris Cherny, X thread (2026-01-31): "Create skills/commands for repeated tasks; commit them to git"
  https://threadreaderapp.com/thread/2017742741636321619.html

相关：[[invest-in-claude-md]]、[[plan-mode-workflow]]
