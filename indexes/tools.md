# Tools Index

按工具整理的技巧索引。基于 notes/ 中的 `tool/*` 标签自动聚合。

详细的工具配置和用法参见 `../tools/skills.md` 和 `../tools/mcp.md`。

---

## Claude Code (`tool/claude-code`)

Anthropic 的终端 AI Agent，定位为"原始的高级用户工具"。

- [[boris-cherny-vibecoding]] — Boris Cherny 的完整工作流时间线
- [[plan-mode-workflow]] — Plan Mode（Shift+Tab）先对齐方案
- [[parallel-sessions-worktrees]] — 并行会话 + Git Worktrees
- [[subagents-for-review]] — Subagents 做代码审查和迁移
- [[invest-in-claude-md]] — 持续投资 CLAUDE.md 项目规则
- [[slash-commands-standardize]] — Slash Commands 标准化工作流
- [[simon-willison-ai-coding]] — Willison 的 Claude Code 使用实践

## Cursor (`tool/cursor`)

AI IDE，Composer 多文件编辑 + .cursorrules 项目规则。

- [[riley-brown-voice-first]] — 语音 + Cursor Composer 零代码构建
- [[karpathy-vibe-coding-origin]] — Karpathy 用 Cursor Composer + Sonnet 提出 vibe coding
- [[karpathy-menugen-last-mile]] — Karpathy 用 Cursor 构建 MenuGen
- [[pieter-levels-ship-fast]] — Levels 用 Cursor 3 小时构建飞行模拟器

## Replit (`tool/replit`)

在线 AI 编程平台，从自然语言到完整应用。

- [[amjad-masad-replit]] — Replit CEO 的愿景和产品演进

## Git (`tool/git`)

版本控制——vibe coding 中的安全网。

- [[parallel-sessions-worktrees]] — Git Worktrees 支持并行开发
- [[fireship-vibe-coding]] — Fireship: "必须掌握 Git，AI 可能删除可用代码"

## ChatGPT (`tool/chatgpt`)

OpenAI 的对话式 AI，用于规划和研究。

- [[simon-willison-ai-coding]] — Willison 用 ChatGPT Code Interpreter 做沙箱测试

---

## 工具选型光谱

```
                控制力高                              控制力低
                  |                                    |
  Claude Code ----+---- Cursor ---- Copilot ---- Windsurf ---- Replit Agent
  (终端 CLI)       (AI IDE)    (VS Code 插件)   (AI IDE)    (全托管)
```

选型建议：
- **大规模重构 / 架构级**：Claude Code（1M context、subagents、worktree）
- **日常开发**：Cursor（Composer 多文件、IDE 体验）
- **已有 VS Code 工作流**：GitHub Copilot（无需切换工具）
- **预算敏感 / 初学者**：Windsurf（$15/月、持久上下文）
- **非技术用户 / MVP**：Replit Agent（零配置、端到端）
