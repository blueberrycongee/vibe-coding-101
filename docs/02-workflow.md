# 02 端到端流程

## 标准流程

一个完整的 vibecoding 工作流可以分为五个阶段。这个流程综合了 Boris Cherny 的 plan-mode 工作流和通用的软件工程实践。

### 1. 目标对齐

**做什么**：明确任务的成功标准，消除歧义。

- 用一句话描述目标和成功标准
- 识别关键约束（时间、范围、质量底线）
- 判断任务类型：探索性（→ prototype-discard-retry）还是明确性（→ plan mode）

**最小产物**：一句话目标 + 成功标准

Boris Cherny 的做法：对于不确定的任务，先让 AI 生成一个粗糙版本来发现未知问题，然后丢弃并重试。（参见：[[prototype-discard-retry]]）

### 2. 约束收集

**做什么**：界定范围，避免过度工程。

- 技术约束：语言、框架、兼容性要求
- 质量约束：是原型还是生产代码？需要测试吗？
- 时间约束：这是 30 分钟能完成的还是需要一天？

**最小产物**：范围边界 + 质量标准 + 时间预期

### 3. 方案草图

**做什么**：在写代码之前对齐实现路径。

- 在 Claude Code 中使用 **Plan Mode**（Shift+Tab）
- 让 AI 提出澄清问题，暴露你没想到的边界条件
- 把任务拆分为 3-5 个可验证的子任务
- 识别关键风险和技术选型

**最小产物**：任务拆分 + 关键风险清单

Boris Cherny 的做法："Plan mode improves success rate" — 明确推荐在复杂任务中使用 plan mode，并在偏离时重新 plan。（参见：[[plan-mode-workflow]]）

### 4. 迭代实现

**做什么**：按子任务逐步实现，每步验证。

- 每个子任务产出一个**可验证增量**
- 完成一个子任务后运行测试/预览
- 偏差较大时退回 plan mode 重新对齐
- 可以用**并行会话 + git worktrees** 同时推进多个独立子任务（参见：[[parallel-sessions-worktrees]]）

**最小产物**：可验证的代码增量

高效技巧：
- 使用 slash commands 标准化重复操作（参见：[[slash-commands-standardize]]）
- 用 subagents 处理代码审查和大规模迁移（参见：[[subagents-for-review]]）

### 5. 复盘沉淀

**做什么**：把本次经验转化为可复用的知识。

- 回答复盘三问：目标达成了吗？偏差在哪？有什么可复用的？
- 更新 CLAUDE.md：把本次学到的规则写入项目规则文件（参见：[[invest-in-claude-md]]）
- 如果发现了新的可复用模式，创建 slash command 或笔记

**最小产物**：可复用的原则、模板或规则更新

## 流程图

```mermaid
flowchart LR
    A[目标对齐] --> B[约束收集]
    B --> C[方案草图]
    C --> D[迭代实现]
    D --> E[复盘沉淀]
    D -- "偏差较大" --> B

    style A fill:#4dabf7,color:#fff
    style B fill:#4dabf7,color:#fff
    style C fill:#ffd43b,color:#333
    style D fill:#69db7c,color:#333
    style E fill:#cc5de8,color:#fff
```

## 不同场景的流程变体

| 场景 | 建议流程 |
|------|----------|
| 快速原型/POC | 跳过方案草图，直接 prototype-discard-retry |
| 复杂功能开发 | 完整五步流程，强调 plan mode |
| Bug 修复 | 简化为：定位 → 修复 → 验证 → 更新规则 |
| 大规模重构 | 并行会话 + subagents，每个处理一个模块 |
