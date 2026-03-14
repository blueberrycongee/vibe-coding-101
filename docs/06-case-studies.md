# 06 案例拆解

## 案例模板

每个案例应包含：
- **背景与目标**：为什么做这个、成功标准是什么
- **约束与风险**：技术栈、时间限制、质量要求
- **关键决策**：选择了什么方案、为什么
- **产出与验证**：最终交付了什么、如何验证成功
- **复盘与可复用结论**：学到了什么、可以模板化的部分

## 案例 1：Boris Cherny 的 Prototype-Discard-Retry

**背景**：在开发新功能时，Boris 经常面对需求不够明确的情况。

**做法**：
1. 让 Claude Code 快速生成一个粗糙原型
2. 审视原型，识别之前没想到的问题和约束
3. 丢弃原型，用新发现的认知重新引导 AI
4. 重复直到理解足够清晰，再正式实现

**关键决策**：选择"丢弃并重试"而非"在原型上修补"——因为带着新认知重新开始，往往比在错误基础上修补更高效。

**可复用结论**：
- 原型的价值不在于代码本身，而在于它帮你发现了什么
- 每轮丢弃前应至少提炼一条新认知
- 适用于探索性任务，不适用于需求已明确的任务

来源：[[prototype-discard-retry]]

## 案例 2：用并行会话加速大型迁移

**背景**：需要对代码库进行大规模 API 迁移。

**做法**：
1. 在 plan mode 中与 AI 对齐迁移方案
2. 将迁移任务按模块拆分
3. 用 git worktrees 创建 3-5 个独立工作目录
4. 每个工作目录启动一个 Claude Code 会话，处理一个模块
5. 用 subagents 对每个模块做代码审查
6. 逐步合并，解决冲突

**关键决策**：选择并行而非串行——因为模块间相对独立，并行可以大幅缩短总时间。

**可复用结论**：
- 并行工作的前提是任务之间没有强依赖
- 合并阶段仍需人工审查
- Subagent 审查的误报率较高，需要人工过滤

来源：[[parallel-sessions-worktrees]]、[[subagents-for-review]]

## 案例 3：Karpathy 的"纯 Vibe Coding"实验

**背景**：Andrej Karpathy 在 2025 年 2 月分享了他的 vibe coding 体验——完全信任 AI，不看代码，只看结果。

**做法**：
1. 用自然语言描述想要的功能
2. AI 生成代码后，不审查代码，直接运行看效果
3. 如果不对，继续用自然语言描述问题
4. "Accept All" — 接受所有改动

**关键决策**：刻意放弃代码审查，测试"纯信任 AI"的极限。

**可复用结论**：
- 对于个人项目和原型，这种方式确实可以极大提高产出速度
- 但对于生产代码和团队项目，这种方式风险太高
- Karpathy 自己也承认这主要适用于"throwaway weekend projects"
- Boris Cherny 的观点形成对比：vibecoding 是场景化的，生产代码仍需审查

来源：Andrej Karpathy X post (2025-02), [[vibecoding-is-situational]]

## 案例 4：Karpathy 的 MenuGen — 最后一公里问题

**背景**：2025 年 4 月，Karpathy 用 Cursor + Claude 3.7 构建 MenuGen（拍照菜单生成菜品图片），100% AI 生成代码。

**做法**：
1. 用 Cursor Composer 描述功能需求
2. AI 快速生成 React 前端 + 后端逻辑
3. 集成第三方服务：OpenAI (OCR)、Replicate (图像生成)、Vercel、Clerk、Stripe

**关键发现**：
- 本地原型阶段体验 "exhilarating"——UI 精美、动画流畅
- 部署阶段是 "painful slog"——AI 对第三方服务配置频繁幻觉
- **瓶颈不在写代码，而在基础设施配置**

**Karpathy 原话**：
> "I didn't even spend all that much work in the code editor itself. I spent most of it in the browser, moving between tabs and settings and configuring and gluing a monster."

**可复用结论**：
- Vibe coding 的真正瓶颈是"最后一公里"——认证、支付、部署、环境变量
- LLM 对第三方 API 的知识可能过时或幻觉，需要人工验证
- 选择服务时优先考虑配置简单的方案

来源：[[karpathy-menugen-last-mile]]

## 案例 5：Karpathy 的 Nanochat — Vibe Coding 的局限

**背景**：2025 年 10 月，Karpathy 发布 Nanochat（~8000 行代码的 ChatGPT 替代品），但代码几乎全部手写。

**做法**：
1. 尝试使用 Claude/Codex agent
2. 发现 agent 模式完全无法有效工作
3. 退回到手写代码 + tab 自动补全

**关键引用**：
> "I tried to use Claude/Codex agents a few times but they just didn't work well enough at all and net unhelpful, possibly the repo is too far off the data distribution."

**可复用结论**：
- **"数据分布"决定 AI 辅助效果**——项目越偏离常见模式，AI 越无力
- 标准 web app / CRUD → vibe coding 效果好
- 创新性/底层/非常规架构 → AI agent 基本无效，但 tab 补全仍有用
- **诚实评估适用性**比强行使用 AI 更重要

来源：[[karpathy-nanochat-failure]]

## 案例 6：Pieter Levels 的 AI 快速发布

**背景**：Pieter Levels 是独立开发者，用 AI 在极短时间内从想法到上线，验证商业可行性。

**做法**：
1. 用 Cursor 快速构建 MVP
2. 极简技术栈（PHP + SQLite）
3. 不追求代码质量，追求"有人用"
4. 快速发布、快速验证、快速迭代或放弃

**关键决策**：代码质量不重要，验证速度最重要。

**可复用结论**：
- Vibe coding 在**独立开发者快速验证**场景中价值最大
- 失败成本极低——如果产品没人用，丢弃成本几乎为零
- 这种方式不适合团队协作和需要高可靠性的产品
- 与 Boris 的"同一质量标准"形成光谱：从"完全不关注质量"到"严格审查"，根据场景选择

来源：[[pieter-levels-ship-fast]]
