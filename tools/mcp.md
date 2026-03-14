# MCP

收纳好用的 MCP（Model Context Protocol）服务器与配置方法，并给出用途与使用示例。

MCP 是 Anthropic 提出的协议，让 AI 工具（如 Claude Code、Cursor）能够通过标准化接口调用外部工具。在 vibecoding 中，MCP 扩展了 AI 的能力边界。

---

## 常用 MCP 服务器

### filesystem — 文件系统操作

- **用途**：让 AI 读写文件、搜索目录、管理文件结构
- **接入方式**：
  ```json
  {
    "mcpServers": {
      "filesystem": {
        "command": "npx",
        "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/project"]
      }
    }
  }
  ```
- **示例**：AI 可以浏览项目结构、读取配置文件、创建新文件
- **注意事项**：注意限制 AI 可访问的目录范围，避免误操作敏感文件

### git — Git 操作

- **用途**：让 AI 执行 git 命令（status、diff、log、commit 等）
- **接入方式**：
  ```json
  {
    "mcpServers": {
      "git": {
        "command": "uvx",
        "args": ["mcp-server-git", "--repository", "/path/to/repo"]
      }
    }
  }
  ```
- **示例**：AI 可以查看变更历史、分析 diff、辅助 code review
- **注意事项**：建议限制为只读操作，或仅允许 commit（不允许 push）

### fetch / browser — 网络访问

- **用途**：让 AI 访问网页、API，获取外部信息
- **接入方式**：
  ```json
  {
    "mcpServers": {
      "fetch": {
        "command": "uvx",
        "args": ["mcp-server-fetch"]
      }
    }
  }
  ```
- **示例**：AI 可以查阅文档、获取 API 响应、爬取参考资料
- **注意事项**：注意网络安全，不要让 AI 访问内网敏感服务

### sqlite / postgres — 数据库操作

- **用途**：让 AI 查询和操作数据库
- **接入方式**：
  ```json
  {
    "mcpServers": {
      "sqlite": {
        "command": "uvx",
        "args": ["mcp-server-sqlite", "--db-path", "/path/to/db.sqlite"]
      }
    }
  }
  ```
- **示例**：AI 可以查询数据、分析表结构、生成迁移脚本
- **注意事项**：生产数据库应使用只读连接；建议使用开发/测试数据库

### playwright — 浏览器自动化

- **用途**：让 AI 操控浏览器进行测试、截图、页面交互
- **接入方式**：
  ```json
  {
    "mcpServers": {
      "playwright": {
        "command": "npx",
        "args": ["-y", "@anthropic-ai/mcp-server-playwright"]
      }
    }
  }
  ```
- **示例**：AI 可以打开页面、点击元素、截图验证 UI、运行 E2E 测试
- **注意事项**：注意浏览器实例的资源消耗

---

## MCP 在 Vibecoding 中的价值

1. **扩展上下文**：AI 可以主动查阅文档、读取配置，而不需要人工粘贴
2. **闭环验证**：AI 可以运行测试、查看数据库、打开浏览器，自己验证输出
3. **减少来回**：减少"AI 生成 → 人工验证 → 反馈 → AI 修正"的循环次数

## 配置位置

| 工具 | 配置文件 |
|------|----------|
| Claude Code | `~/.claude/settings.json` 或项目级 `.claude/settings.json` |
| Cursor | `.cursor/mcp.json` |
| VS Code + Continue | `.continue/config.json` |

## 安全原则

- **最小权限**：只给 AI 需要的权限（只读 vs 读写）
- **沙箱隔离**：使用开发环境的数据库和服务，不连接生产
- **审计日志**：记录 AI 通过 MCP 做了什么操作
- **敏感信息**：不要在 MCP 配置中硬编码密码和 token
