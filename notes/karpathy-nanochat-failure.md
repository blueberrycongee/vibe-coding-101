---
tags: [person/andrej-karpathy, topic/vibecoding, topic/limitations, source/github]
---
# Karpathy 的 Nanochat：承认 Vibe Coding 不适用

## 背景
- 2025 年 10 月，Karpathy 发布 Nanochat（约 8000 行代码的 ChatGPT 替代品）
- 代码**几乎全部手写**（仅使用了 tab 自动补全），而非 vibe coded

## 关键引用

> [!quote] Andrej Karpathy, 2025-10
> It's basically entirely hand-written (with tab autocomplete). I tried to use Claude/Codex agents a few times but they just didn't work well enough at all and net unhelpful, possibly the repo is too far off the data distribution.

## 为什么 AI Agent 失败
- 项目**太偏离训练数据分布**（"off the data distribution"）
- 当代码库的架构和模式不是 LLM 常见的模式时，AI 的辅助效果急剧下降
- Tab 级自动补全仍有用，但完整的 agent 模式无法胜任

## 可提炼的技巧
1. **"数据分布"是关键因素**——项目越偏离 LLM 训练数据中的常见模式，AI 辅助效果越差
2. **Vibe coding 在 "on-distribution" 的项目上效果好**（标准 web app、CRUD），在创新性/底层项目上会失败
3. **不同 AI 辅助层级有不同适用范围**：
   - Tab 自动补全：几乎任何场景都有用
   - AI Chat 讨论：大部分场景有用
   - Full Agent 模式：仅在常见模式的项目上有效
4. 即使是 vibe coding 的提出者，也要**诚实面对 AI 的局限性**

## 来源
- Karpathy, Nanochat GitHub: https://github.com/karpathy/nanochat
- Futurism report: https://futurism.com/artificial-intelligence/inventor-vibe-coding-doesnt-work

相关：[[karpathy-vibe-coding-origin]]、[[karpathy-agentic-engineering]]、[[vibecoding-is-situational]]、[[karpathy-menugen-last-mile]]、[[karpathy-software-3-0]]、[[fireship-vibe-coding]]
