---
tags: [person/boris-cherny, topic/prompting, topic/project-rules, tool/claude-code]
---
# 持续投资 CLAUDE.md

## 方法
- 在项目根目录维护 `CLAUDE.md` 文件，记录项目规范、约束和 AI 应遵守的规则
- **每次 AI 犯错后更新 CLAUDE.md**，把教训转化为规则
- 将 CLAUDE.md 视为项目的"AI 记忆"，持续迭代

## 适用场景
- 任何使用 Claude Code 的项目
- 团队协作中需要统一 AI 行为
- 项目有特定的代码规范或架构约束

## 边界
- CLAUDE.md 不宜过长（建议控制在 200 行以内），否则会稀释关键信息
- 不要放入临时性指令，只记录稳定的规则
- 类似概念在 Cursor 中是 `.cursorrules`，在 Copilot 中是 `.github/copilot-instructions.md`

## 来源
- Boris Cherny, X thread (2026-01-31): "Invest in CLAUDE.md (project rules) and keep it updated after mistakes"
  https://threadreaderapp.com/thread/2017742741636321619.html

相关：[[slash-commands-standardize]]、[[plan-mode-workflow]]、[[boris-cherny-vibecoding]]
