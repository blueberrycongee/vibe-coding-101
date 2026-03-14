---
tags: [person/andrej-karpathy, topic/vibecoding, topic/deployment, source/blog]
---
# Karpathy 的 MenuGen 实践：最后一公里问题

## 方法
- 2025 年 4 月，Karpathy 用 Cursor + Claude 3.7 构建了 MenuGen（拍照菜单自动生成菜品图片）
- **100% AI 生成代码**，Karpathy 没有手写任何一行
- 技术栈：React 前端, OpenAI (OCR), Replicate (图像生成), Vercel 部署, Clerk 认证, Stripe 支付

## 关键发现

### 什么可行
- 初始本地原型极快成型
- UI 精美，动画和响应式设计快速就绪
- 本地开发阶段体验 "exhilarating"（令人兴奋）

### 什么不可行（"最后一公里问题"）
- API 速率限制和新账号限制让调试困难
- Claude 频繁幻觉出**已弃用的 API 规格**
- `.env.local` 因 `.gitignore` 不会推送到 Vercel，需手动配置
- Clerk 认证需要在 Vercel、Google Cloud Console、Clerk 之间来回配置
- 数据库和工作队列（Supabase、Upstash）需要额外服务配置

### Karpathy 的总结
> "I didn't even spend all that much work in the code editor itself. I spent most of it in the browser, moving between tabs and settings and configuring and gluing a monster."
> "Vibe coding full web apps today is kind of messy and not a good idea for anything of actual importance."

## 适用场景
- 理解 vibe coding 的实际瓶颈在哪里
- 规划 vibe coding 项目时评估部署复杂度

## 边界
- Vibe coding 的瓶颈**不在写代码，而在基础设施配置**（认证、支付、部署、环境变量）
- LLM 对第三方服务的 API 文档经常幻觉——需要人工验证
- 本地原型阶段体验极好，部署阶段是 "painful slog"

## 来源
- Andrej Karpathy, "Vibe Coding MenuGen" (2025-04-27): https://karpathy.bearblog.dev/vibe-coding-menugen/

相关：[[karpathy-vibe-coding-origin]]、[[karpathy-nanochat-failure]]、[[karpathy-software-3-0]]、[[pieter-levels-ship-fast]]
