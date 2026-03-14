---
title: "McKay Wrigley：Cursor Vibe Coding 工作流"
tags: [person/mckay-wrigley, topic/vibecoding, topic/workflow, tool/cursor, source/x, source/course]
---
# McKay Wrigley：Cursor Vibe Coding 工作流

## 人物

McKay Wrigley，Cursor AI 编程教育领域最知名的内容创作者之一。推出 "Complete Cursor" 和 "Building Full-Stack Apps with AI" 课程，教小白用 Cursor 从零构建应用。

## 核心方法

### 速度演示
- 用 Cursor 在 **8 分钟**内克隆了一个 Perplexity（AI 搜索引擎），不到 14 次交互
- 用 Cursor 在 **20 分钟**内构建了 AI 客服 Agent（OpenAI + Slack），Composer 写了 95% 的代码
- 用 o1 pro 一次性完成 todo list 上的 6 个任务，修改 14 个文件，全部正确，省了 2 小时

### 小白友好的核心技巧

1. **Rules for AI（项目规则）**：在 Cursor 设置中配置 "Rules for AI"，可以把 AI 变成个人编程导师，边写边教
2. **User Rules vs Project Rules**：User Rules 全局生效，Project Rules 针对具体项目——大部分价值在 Project Rules
3. **Ask Mode 先规划**：用 Ask Mode（搭配 o3 等推理模型）生成步骤计划，再切 Agent Mode 执行
4. **小步迭代**：从 PRD 生成 tasks.json，逐个喂给 Cursor，保持动量和代码质量
5. **频繁提交**：每完成一个小功能就 git commit，方便定位哪个提交引入了 bug
6. **提供错误上下文**：别只说"不工作"——贴错误信息，UI 问题贴截图

## 适用场景

- **完全没有编程经验的人**想用 Cursor 构建第一个应用
- 想系统学习 AI 辅助编程工作流的人
- 需要快速原型演示给投资人/客户的场景

## 来源

- X: https://x.com/mckaywrigley
- "Rules for AI" 提示词: https://x.com/mckaywrigley/status/1833941831253696690
- Cursor 课程: https://www.youware.com/blog/cursor-vibe-coding-complete-guide

相关：[[pieter-levels-ship-fast]]、[[riley-brown-voice-first]]、[[plan-mode-workflow]]
