---
title: "零代码应用构建器：Lovable / Bolt.new / v0 / Replit Agent"
tags: [topic/vibecoding, topic/prototyping, topic/shipping, tool/lovable, tool/bolt, tool/v0, tool/replit]
---
# 零代码应用构建器：Lovable / Bolt.new / v0 / Replit Agent

## 概述

如果终端 Agent（Claude Code、Codex CLI）面向的是开发者，那这四个平台面向的是**完全不会写代码的人**。用自然语言描述你想要什么，平台自动生成完整应用。

## 工具对比

| 平台 | 最适合 | 全栈？ | 小白友好度 | 部署 | 起步价 |
|------|--------|--------|-----------|------|--------|
| **Lovable** | 非技术创始人 | 全栈 | 最高 | 一键部署 | $25/月 |
| **Bolt.new** | 有一点基础的人 | 全栈 | 中等 | 需手动（Netlify/Vercel） | 免费 1M token/月 |
| **v0 (Vercel)** | UI/前端 | 仅前端 | 中等 | Vercel 集成 | 免费有限额度 |
| **Replit Agent** | 零基础完全小白 | 全栈 | 非常高 | 内置托管 | 需付费订阅 |

## 各平台详解

### Lovable — 最适合非技术创始人
- 欧洲 startup 历史上增长最快的公司之一，2 个月达到 $20M ARR
- 输入："我要一个带登录、到期日和可分享任务的 todo app"
- 输出：完整应用（前端 + 后端 + 数据库 + 用户认证 + 支付）
- Agent Mode 能从纯英语描述生成完整应用

### Bolt.new — 最灵活的免费选项
- 由 StackBlitz 构建，2025 年 3 月达 $40M ARR
- 免费层给 1M token/月，够做好几个原型
- 支持多种框架（React、Vue、Svelte 等）
- 缺点：部署需要自己配置 Netlify/Vercel

### v0 by Vercel — UI 组件专家
- 专注生成 **React + Tailwind + shadcn/ui** 组件
- 可以从图片/截图生成 UI 代码
- 仅前端——后端需要自己搭配（Supabase、Firebase 等）
- 适合在已有项目中快速生成 UI 片段

### Replit Agent — 最无摩擦的体验
- 从自然语言到完整应用，**零配置**
- 内置认证、数据库、托管、监控
- Agent 3（2026）让零编程经验的产品经理 20 分钟构建带 Mailchimp 集成的落地页
- 适合"我有个想法，10 分钟后想看到它在浏览器里运行"

## 使用建议

1. **验证想法用** Lovable 或 Replit Agent——最快看到结果
2. **需要灵活性**用 Bolt.new——免费额度大，框架选择多
3. **只需 UI 组件**用 v0——生成的代码可直接嵌入现有项目
4. **组合使用**：v0 生成 UI + Lovable 生成后端，并不冲突

## 共同局限

- 都能帮你走完前 70% 的路，最后 30% 需要人工调整
- 安全审查仍然重要——生成的代码需要检查
- 复杂业务逻辑（支付、权限、数据迁移）仍需人工介入

## 来源

- Lovable vs Bolt vs v0 对比: https://lovable.dev/guides/lovable-vs-bolt-vs-v0
- Replit Agent 文档: https://docs.replit.com/replitai/agent
- Lovable 初学者指南: https://lovable.dev/guides/vibe-coding-apps-8-options-for-beginners

相关：[[amjad-masad-replit]]、[[kevin-roose-software-for-one]]、[[pieter-levels-ship-fast]]、[[prototype-discard-retry]]
