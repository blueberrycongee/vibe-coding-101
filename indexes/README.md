# 索引说明

索引页用于从不同维度聚合 `notes/` 条目。每个 note 通过 YAML front matter 中的 tag 归类，通过 `[[双链]]` 建立关联。

## 索引维度

- `people.md`：按人物（`person/*` 标签）
- `topics.md`：按主题（`topic/*` 标签）
- `tools.md`：按工具（`tool/*` 标签）
- `languages.md`：按语言（`language/*` 标签，计划中）

## Tag 体系

```
person/*        — 人物：boris-cherny, andrej-karpathy, simon-willison, ...
topic/*         — 主题：vibecoding, workflow, quality, planning, ...
tool/*          — 工具：claude-code, cursor, replit, git, ...
language/*      — 语言：typescript, python, rust, ... (计划中)
source/*        — 来源类型：x, blog, youtube, podcast, talk, ...
```

## 双链规范

- 使用 `[[文件名]]` 语法（不含 .md 后缀）
- **双向性**：如果 A 引用了 B，B 也应在"相关"部分链回 A
- 笔记末尾用 `相关：[[a]]、[[b]]` 格式列出关联笔记
- 与笔记软件（Obsidian、Logseq 等）兼容
