---
title: "Shrivu Shankar：Claude Code 全功能实战指南"
tags: [person/shrivu-shankar, topic/workflow, tool/claude-code, source/substack]
---
# Shrivu Shankar：Claude Code 全功能实战指南

## 人物

Shrivu Shankar，Claude Code 深度用户。个人项目在 VM 中跑 Claude Code，专业团队每月消耗数十亿 token 用于代码生成。发表的 "How I Use Every Claude Code Feature" 被 Simon Willison 转发推荐。

## 核心技巧

### 1. CLAUDE.md 是你的"宪法"
- 项目根目录的 CLAUDE.md 是 Agent 的首要信息源
- 不要试图写成完整手册——写成**高层次的护栏和指引**
- 用它来指向更详细的文档，而非替代文档

### 2. 上下文窗口管理
- 用 `/context` 命令查看上下文使用情况
- 200K token 窗口中，monorepo 基线占 ~20K（10%），剩余 180K 用于工作
- 把上下文想象成硬盘空间——工作一段时间后需要清理消息腾出空间

### 3. Plan Mode 的正确用法
- **复杂变更前必须用 plan mode** 对齐方案
- 可以基于 Claude Code SDK 构建**自定义 planning 工具**，对齐团队的技术设计格式
- Plan mode 不只是给 AI 看的——也是给你自己理清思路的

### 4. Subagents 的真实体验
- 理论上最强大的上下文管理功能：把复杂任务拆给专门的子 agent
- **实际陷阱**：子 agent 会"门卫化"上下文——主 agent 看不到测试上下文，无法整体推理
- 建议：简单场景用 subagent，复杂场景谨慎

### 5. Skills > MCP
- Skills（自定义命令）比 MCP 更实用
- 原因：教 AI 用一个**简单、定义清晰的工具**，比教它读一大段说明文档容易得多
- 建议：把常用操作做成 CLI 工具，而非 MCP 服务器

### 6. 并行 Agent
- 通过 bash 脚本启动并行 agent
- 在提示词中指定文件夹范围，信任 agent 会待在自己的区域
- 适合大型代码库的并行开发

## 适用场景

- 已经在用 Claude Code 的人想提升到进阶水平
- 团队想在工程实践中引入 Claude Code
- 想理解 Claude Code 各功能实际效果（而非官方宣传）

## 来源

- "How I Use Every Claude Code Feature": https://blog.sshh.io/p/how-i-use-every-claude-code-feature
- Simon Willison 转发: https://simonwillison.net/2025/Nov/2/how-i-use-every-claude-code-feature/

相关：[[boris-cherny-vibecoding]]、[[invest-in-claude-md]]、[[plan-mode-workflow]]、[[subagents-for-review]]、[[slash-commands-standardize]]
