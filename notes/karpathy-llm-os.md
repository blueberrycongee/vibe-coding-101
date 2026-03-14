---
tags: [person/andrej-karpathy, topic/architecture, topic/llm, source/youtube]
---
# Karpathy 的 LLM OS 愿景

## 方法
- Karpathy 提出将 LLM 视为一种新的"操作系统"的比喻
- LLM 是"CPU"，context window 是"RAM"，工具调用是"系统调用"
- 这个框架影响了 AI 编程工具的设计思路：
  - **上下文管理**就像内存管理——要把最相关的信息放入有限的 context window
  - **工具使用**就像系统调用——AI 通过工具（文件读写、搜索、运行命令）扩展能力
  - **Prompt** 就像"编程语言"——用自然语言给 LLM 下达指令

## 适用场景
- 理解 AI 编程工具的设计哲学
- 设计 MCP 服务器和工具集成
- 理解 context window 大小对 vibecoding 工作流的影响

## 边界
- 这是一个类比，不是精确描述——LLM 与传统 OS 有本质区别
- LLM 没有真正的"持久化状态"（每次对话都从零开始，除非有外部记忆）
- 类比可能过度简化 AI 的局限性

## 来源
- Andrej Karpathy, "Intro to Large Language Models" YouTube talk (2023-11)
  https://www.youtube.com/watch?v=zjkBMFhNj_g
- Andrej Karpathy, various talks on LLM OS concept (2024)

相关：[[karpathy-vibe-coding-origin]]、[[karpathy-software-3-0]]
