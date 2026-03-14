---
title: "Boris Cherny 的 vibecoding 实践时间线"
tags: [person/boris-cherny, topic/vibecoding, tool/claude-code, topic/workflow, source/transcript, source/x]
---
# Boris Cherny 的 vibecoding 实践时间线

基于公开来源整理的 **Boris Cherny 关于 vibecoding 和 Claude Code 的公开发言**时间线。不保证穷尽所有来源。

## 2025-05-08 — Latent Space Podcast (Claude Code: Anthropic's Agent in Your Terminal)
Source: Latent Space transcript.

Key points (tool philosophy):
- Claude Code is positioned as a **raw, power-user tool** for big workloads, closer to a Unix utility than a polished IDE UI.
- **Human review remains essential** even when a large share of code is model-written; some intricate parts are still handwritten when the author has strong opinions.
- MCP and custom commands are optional layers; users should not be locked into a single technology choice.

Sources:
- https://www.latent.space/p/claude-code

## 2025-10-29 (updated 2026-01-28) — Every.to AI & I transcript
Source: “How to Use Claude Code Like the People Who Built It.”

Key points (workflow and modes):
- **Prototyping mode**: Boris often lets Claude build a rough version to discover unknowns, then discards and retries to refine understanding.
- **Plan mode**: for harder feature work, he aligns on a plan first (Shift+Tab in Claude Code), then proceeds to implementation; the boundary of when to plan shifts with model capability.
- **Plan mode improves success rate**; he explicitly recommends using it more and asks Claude to ask clarifying questions during planning.
- **Subagents**: used for code review and large migrations; he fans out multiple subagents, then dedupes false positives.
- **Slash commands**: used to standardize workflows (commit/PR/feature dev), pre-allow permissions, and speed up common tasks.
- **Stop hooks**: can be used to auto-continue (e.g., re-run until tests pass).

Sources:
- https://every.to/podcast/transcript-how-to-use-claude-code-like-the-people-who-built-it

## 2025-12-15 — The Peterman Pod transcript (Developing Dev)
Source: “Boris Cherny (Creator of Claude Code) On How His Career Grew.”

Key points (vibecoding stance):
- **Vibecoding is situational**, mainly useful for **throwaway/prototype** work, not for all code paths.
- **Same quality bar** for AI and human code; if it’s bad, don’t merge, iterate until it meets the standard.
- **Pairing over one-shot**: typically aligns on a plan, reviews the output, asks for cleanup, and iterates.
- **Handwrites critical parts** when he has strong opinions on design details.

Sources:
- https://www.developing.dev/p/boris-cherny-creator-of-claude-code

## 2026-01-31 — X thread (workflow tips)
Source: @bcherny thread (Thread Reader App mirror).

Highlights:
- **Parallelism**: run 3–5 Claude sessions in parallel using git worktrees/checkouts.
- **Start complex tasks in plan mode**; re-plan when things go sideways.
- **Invest in CLAUDE.md** (project rules) and keep it updated after mistakes.
- **Create skills/commands** for repeated tasks; commit them to git.
- **Use subagents** to throw more compute at problem chunks and keep context clean.

Sources:
- https://threadreaderapp.com/thread/2017742741636321619.html

## Coverage notes
- Boris’s personal blog lists posts through 2024; there are **no vibecoding-specific posts** there as of 2026-03-14.
- There are additional interviews (e.g., newsletters, podcasts) behind paywalls or not fully transcribed. If you provide links, I can extend this timeline.

Sources:
- https://borischerny.com/

相关：[[prototype-discard-retry]]、[[plan-mode-workflow]]、[[parallel-sessions-worktrees]]、[[subagents-for-review]]、[[invest-in-claude-md]]、[[slash-commands-standardize]]、[[vibecoding-is-situational]]、[[human-review-essential]]
