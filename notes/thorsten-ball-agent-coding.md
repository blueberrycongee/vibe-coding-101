---
title: "Thorsten Ball：从手写代码到 Agent 编程的转变"
tags: [person/thorsten-ball, topic/vibecoding, topic/workflow, tool/claude-code, source/substack]
---
# Thorsten Ball：从手写代码到 Agent 编程的转变

## 人物

Thorsten Ball，Amp（AI 编程工具）开发者，《Writing An Interpreter In Go》作者，Register Spill 博客作者。一个从传统手写代码转向 agent 编程的实践者。

## 核心观点

### Agent 编程的真实体验
- 手写代码与 AI 生成代码的比例已经**翻转**——大部分代码现在由 agent 生成
- 在 Amp，他们甚至**移除了 Tab 自动补全**功能，全面转向 agent 模式
- 这代表了一种判断：**agent 模式比行内补全更有生产力**

### 渐进式信任实验
Ball 建议用以下步骤体验 vibe coding：
1. 拿一个简单文件，让 agent 写测试
2. 让 agent 运行测试，**不看代码**
3. 让 agent 修改代码并重新运行测试
4. 逐步扩大范围，观察边界在哪里

### 实际使用案例
- 用 Claude 创建 50 行 Python 脚本
- 用 AI 构建 HTML/JS/CSS 的 diff 查看器
- 用 AI 构建本地文件夹浏览的 Python Web App
- 这些都是**小工具类任务**——正是 vibe coding 最擅长的领域

### "不是所有代码都值得手写"
- 核心洞察：大量代码是**胶水代码、样板代码、一次性脚本**
- 这些代码不值得人类花时间手写
- Agent 在这类任务上已经足够好

## 边界

- Ball 来自编译器/解释器背景，深度理解代码
- 他的实践建立在**能审查和判断 AI 输出**的基础上
- 这与 Karpathy 最初"不看代码"的极端定义不同

## 来源

- Register Spill (Substack) 多期 Joy & Curiosity 通讯: https://registerspill.thorstenball.com/
- Joy & Curiosity #46 (2025-07): https://registerspill.thorstenball.com/p/joy-and-curiosity-46
- "Surely not all code's worth it": https://registerspill.thorstenball.com/p/surely-not-all-codes-worth-it

相关：[[karpathy-agentic-engineering]]、[[boris-cherny-vibecoding]]、[[prototype-discard-retry]]
