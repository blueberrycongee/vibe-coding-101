# Skills

收纳好用的 skills（自定义命令/模板），并给出适用场景、输入输出、示例与注意事项。

---

## Claude Code Skills / Slash Commands

### /commit — 标准化提交

- **适用场景**：每次需要 git commit 时
- **输入**：当前 staged 的变更
- **输出**：规范化的 commit message + 提交
- **示例**：
  ```markdown
  # .claude/commands/commit.md
  请分析当前 staged 的变更，生成一个简洁的 commit message：
  - 第一行：类型(范围): 简述（不超过 70 字符）
  - 空行
  - 详细描述变更的"为什么"
  - 使用约定式提交格式（feat/fix/refactor/docs/test/chore）
  ```
- **注意事项**：Boris Cherny 推荐将此类命令提交到 git，团队共享

### /review — 代码审查

- **适用场景**：PR 创建前或合并前的代码审查
- **输入**：当前分支与目标分支的 diff
- **输出**：审查报告（问题列表 + 建议）
- **示例**：
  ```markdown
  # .claude/commands/review.md
  请审查当前分支的所有变更：
  1. 检查逻辑正确性和边界条件
  2. 检查安全问题（注入、泄露、未授权访问）
  3. 检查是否符合 CLAUDE.md 中的项目规范
  4. 给出具体改进建议
  ```
- **注意事项**：可以结合 subagents 对大范围变更做并行审查

### /feature — 功能开发流程

- **适用场景**：开始一个新功能开发时
- **输入**：功能描述
- **输出**：plan → 实现 → 测试 → 提交
- **示例**：
  ```markdown
  # .claude/commands/feature.md
  请按以下流程开发功能：
  1. 先进入 plan mode，列出实现方案
  2. 等我确认方案后，逐步实现
  3. 每个步骤完成后运行相关测试
  4. 全部完成后生成 commit
  ```
- **注意事项**：体现了 Boris 的 plan-mode-first 理念

---

## Cursor Skills

### .cursorrules — 项目规则

- **适用场景**：任何使用 Cursor 的项目
- **输入**：项目约束和规范
- **输出**：AI 在每次对话中自动遵守这些规则
- **示例**：
  ```markdown
  # .cursorrules
  You are working on a Next.js 14 project with:
  - App Router (not Pages Router)
  - TypeScript strict mode
  - Tailwind CSS + shadcn/ui
  - Prisma ORM with PostgreSQL

  Rules:
  - Always use server components by default
  - Use 'use client' only when needed
  - Error handling: use Result type pattern, not try/catch
  - Tests: use Vitest, co-locate test files
  ```
- **注意事项**：类似 Claude Code 的 CLAUDE.md，核心思想可迁移

### Cmd+K 编辑模式

- **适用场景**：对选中的代码做局部修改
- **输入**：选中代码 + 自然语言指令
- **输出**：修改后的代码
- **示例**：选中一个函数 → "添加错误处理和输入验证"
- **注意事项**：适合小范围修改，大范围修改用 Composer

---

## GitHub Copilot Skills

### copilot-instructions.md — 项目规则

- **适用场景**：任何使用 Copilot 的项目
- **输入**：项目约束
- **输出**：Copilot 在补全和 Chat 中遵守规则
- **示例**：
  ```markdown
  # .github/copilot-instructions.md
  - Use functional components with hooks
  - Prefer named exports over default exports
  - Use TypeScript generics for reusable functions
  ```
- **注意事项**：功能比 CLAUDE.md 和 .cursorrules 简单，但原理相同

---

## 通用 Vibecoding Skills

### 原型-丢弃-重试（Prototype-Discard-Retry）

- **适用场景**：需求不明确、探索性开发
- **输入**：模糊的需求描述
- **输出**：通过多轮迭代获得清晰的需求理解
- **做法**：让 AI 生成粗糙原型 → 审视发现未知 → 丢弃重来 → 直到理解足够清晰
- **注意事项**：每轮至少提炼一条新认知
- **详见**：[[prototype-discard-retry]]

### 并行多会话开发

- **适用场景**：多个独立子任务需要同时推进
- **输入**：任务拆分后的子任务列表
- **输出**：多个并行完成的代码分支
- **做法**：git worktree 创建独立工作目录 → 每个目录启动一个 AI 会话 → 逐步合并
- **注意事项**：任务间不能有强依赖；合并仍需人工
- **详见**：[[parallel-sessions-worktrees]]

---

## Claude Code 高级技巧（来自 Boris Cherny 工作流研究）

### Hooks 自动化

- **PostToolUse hook**：代码生成后自动格式化，解决最后 10% 的格式问题，防止 CI 失败
- **PreToolUse hook**：工具执行前验证，用于安全检查
- **PostCompact hook**：压缩上下文后重新注入关键指令
- 来源：https://howborisusesclaudecode.com/

### Boris 的 Plan → Auto-accept 工作流

1. 先在 **Plan Mode**（Shift+Tab 两次）反复迭代直到满意
2. 切换到 **auto-accept 模式** 让 Claude 一次性实现
3. 复杂任务可以把计划写到 `plan.md` 文件中，作为跨 session 的持久化工作记忆
4. 如果执行中卡住，重新回到 Plan Mode

### CLAUDE.md 最佳实践

- 保持在 **200 行 / 2.5k tokens 以内**；过长会导致重要规则被忽略
- 不要写成文档手册，而是写 **guardrails**（什么该做、什么不该做，并提供替代方案）
- 团队每次发现 Claude 犯错就把纠正加入 CLAUDE.md，形成"持续学习"机制
- PR 上用 `@.claude` tag 将代码审查中的经验同步回 CLAUDE.md
- 来源：https://code.claude.com/docs/en/best-practices

### 小 Diff 原则

- 一个行为改动 = 一个 PR 大小的 diff = 一条验证路径
- 给 Claude 反馈回路（测试套件、浏览器测试、模拟器）可提升 2-3x 质量

---

## Cursor 高级技巧

### .cursor/*.mdc 规则文件（推荐替代 .cursorrules）

- 更灵活且按需加载，减少 token 消耗
- 规则应覆盖：安全防护、编码规范、错误处理、测试要求、commit 规范
- 可用"人格驱动"规则：如 Test Guru（确保每个函数有测试）
- 预置规则来源：[cursor.directory](https://cursor.directory)
- 来源：https://medium.com/@saket_kmr/cursor-rules-and-their-applications-for-vibe-coders-11a7221bbcbd

### Agent Mode 最佳实践

- 先给测试再给实现目标（"Write failing tests for X, then implement"）
- 提供明确的文件范围（"Limit changes to these files unless you propose a plan"）
- Agent session 保持在 2 小时以内
- 用 Ask Mode 做规划（可用高推理模型），用 Agent Mode 做执行

### 已知问题 (2026-03)

- Agent Review Tab 与编辑器存在文件锁冲突，可能导致代码静默回滚
- 临时方案：关闭 Agent Review Tab、禁用 Format On Save

---

## GitHub Copilot 高级技巧

### Agent Mode (2025-02 推出)

- 不仅写代码还能：读文件、运行代码、检查输出、修复 lint 错误、安装包
- 支持 MCP 协议连接外部工具
- 多模型选择：GPT-4o、Claude Opus 4.5、Gemini 2.0 Flash
- 来源：https://github.blog/news-insights/product-news/github-copilot-agent-mode-activated/

### 官方推荐 Vibe Coding 工作流

1. **Research**：空项目中用 Ask Mode 探索需求
2. **Plan**：切换到 Plan Mode 细化方案
3. **Implementation**：点 Start Implementation 进入 Agent Mode
4. **迭代**：每次只修 2-3 个最关键问题，每次成功后 git commit
5. **完善**：添加测试、更新 README、创建 `.github/copilot-instructions.md`
- 来源：https://docs.github.com/en/copilot/tutorials/vibe-coding

---

## 跨工具总结

| 工具 | 定位 | 最适合场景 | 规则文件 |
|------|------|-----------|----------|
| Claude Code | 终端 Agent | 大规模重构、架构级任务 | CLAUDE.md |
| Cursor | AI IDE | 日常开发、多文件编辑 | .cursor/*.mdc |
| GitHub Copilot | VS Code 集成 | 已有 VS Code 工作流的团队 | .github/copilot-instructions.md |
| Windsurf | AI IDE | 预算敏感、初学者 | 内置配置 |
| Replit Agent | 在线平台 | MVP/原型、非技术用户 | 无 |

**核心原则**：无论用哪个工具，最佳实践都收敛于——先规划再执行、小 diff 迭代、给 agent 验证反馈回路、用规则文件约束行为、保持 context 清洁。
