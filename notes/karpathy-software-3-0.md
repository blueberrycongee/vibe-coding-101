---
tags: [person/andrej-karpathy, topic/architecture, topic/software-evolution, source/talk]
---
# Karpathy: Software 三个时代（Software 3.0）

## 核心框架

Karpathy 在 2025 年 YC AI Startup School 演讲中提出了软件的三个时代：

| 时代 | 编程方式 | 核心范式 |
|------|---------|---------|
| Software 1.0 | 人写代码（C++/Python） | 显式指令 |
| Software 2.0 | 数据+训练（神经网络权重） | 学习到的权重 |
| Software 3.0 | 自然语言提示（English） | LLM 执行 |

## 关键观点

### "Iron Man Suit" 方法
- LLM 应用应该是**增强人类能力的工具**，而非完全自主的 agent
- 理想工作流是紧密的 "生成-验证循环"（generate-and-verify cycle）
- 配有"自主性滑块"（autonomy slider）：从完全人控到完全自主的光谱

### Vibe Coding 民主化
- 领域专家（医生、律师、艺术家）可以用自然语言描述需求，无需传统编程背景
- "Vibe coding will disproportionately benefit regular people rather than experts"

### 为 Agent 构建基础设施
- 提议 `llms.txt` 文件（类似 `robots.txt`），为 AI agent 提供项目导航
- 文档应为 **Markdown 格式**，方便 LLM 消费
- API 文档应可执行，而非 "点击这里" 式指引

## 适用场景
- 理解 vibecoding 在更大的软件演进趋势中的位置
- 设计 AI 友好的文档和基础设施
- 思考 AI 辅助编程的产品策略

## 来源
- Andrej Karpathy, "Software Is Changing (Again)" at YC AI Startup School (2025)
- X announcement: https://x.com/karpathy/status/1935518272667217925

相关：[[karpathy-vibe-coding-origin]]、[[karpathy-agentic-engineering]]、[[karpathy-llm-os]]、[[karpathy-menugen-last-mile]]、[[karpathy-nanochat-failure]]
