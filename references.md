# 参考资源汇总

## 官方资源

- [MCP 官方网站/规范](https://modelcontextprotocol.io)
- [MCP GitHub (规范)](https://github.com/modelcontextprotocol/modelcontextprotocol)
- [Python SDK](https://github.com/modelcontextprotocol/python-sdk) — `pip install mcp`
- [TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk) — `npm install @modelcontextprotocol/sdk`
- [C# SDK](https://github.com/modelcontextprotocol/csharp-sdk)
- [MCP Inspector](https://modelcontextprotocol.io/docs/tools/inspector)
- [MCP Registry](https://registry.modelcontextprotocol.io) — 社区服务器市场
- [MCP 官方博客](https://blog.modelcontextprotocol.io)

## 教程

- [MCP 官方 Quickstart](https://modelcontextprotocol.io/quickstart)
- [DazzleML Python MCP Tutorial (GitHub)](https://github.com/DazzleML/MCP-Server-Tutorial) — 9 章完整教程
- [IBM MCP Context Forge](https://ibm.github.io/mcp-context-forge/1.0.0/best-practices/developing-your-mcp-server-python/)
- [SitePoint — 全栈 MCP 开发指南](https://www.sitepoint.com/mcp-model-context-protocol-complete-developer-integration-guide/)
- [Microsoft Azure — Web App 作为 MCP Server](https://learn.microsoft.com/en-us/azure/app-service/tutorial-ai-model-context-protocol-server-node)
- [LinkedIn Learning — MCP 入门课程 (Anthropic 官方)](https://www.linkedin.com/learning/introduction-to-model-context-protocol-by-anthropic)

## SDK 对比

| SDK | 语言 | 安装 | 特点 |
|-----|------|------|------|
| python-sdk | Python | `pip install mcp` | 官方维护, FastMCP 装饰器风格 |
| typescript-sdk | TypeScript | `npm i @modelcontextprotocol/sdk` | 官方维护 |
| csharp-sdk | C# | `dotnet add package ModelContextProtocol` | Microsoft 官方, v1.0 (2026.03) |
| mcp-go | Go | `go get github.com/mark3labs/mcp-go` | 社区维护 |
| java-sdk | Java/Kotlin | Maven/Gradle | Spring AI 集成 |

## 关键 SEP (规范增强提案)

| 编号 | 内容 | 状态 |
|------|------|------|
| SEP-2575 | 移除 initialize 握手, 无状态协议 | 2026-07-28 RC |
| SEP-2322 | 多轮请求 (InputRequiredResult) | 2026-07-28 RC |
| SEP-1865 | MCP Apps (沙盒 UI) | 2026-07-28 RC |
| SEP-1686 | Tasks (异步任务) | 2025-11-25 实验 / 2026-07-28 正式扩展 |
| SEP-973 | Icon 元数据 | 2025-11-25 稳定 |
| SEP-835 | OAuth 增量范围同意 | 2025-11-25 稳定 |
| SEP-2106 | JSON Schema 2020-12 完整支持 | 2026-07-28 RC |
| SEP-2549 | 缓存控制 (ttlMs, cacheScope) | 2026-07-28 RC |

## 社区服务器示例

- [server-filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) — 文件系统访问
- [server-github](https://github.com/modelcontextprotocol/servers/tree/main/src/github) — GitHub API
- [server-postgres](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) — PostgreSQL 数据库
- [server-slack](https://github.com/modelcontextprotocol/servers/tree/main/src/slack) — Slack 集成
- [server-brave-search](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search) — Web 搜索

## 调试工具

```bash
# MCP Inspector — 浏览器可视化调试
npx @modelcontextprotocol/inspector python my_server.py

# mcp-cli — 命令行测试
pip install mcp-cli
mcp-cli --server "python my_server.py" tools list

# curl — 测试 HTTP 服务器
curl -X POST http://localhost:8000/mcp \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list","params":{}}'
```

## 推荐学习路径

1. **第 1 天**: 阅读 01-overview.md, 理解核心概念
2. **第 2 天**: 按 02-quickstart.md 搭建第一个服务器
3. **第 3 天**: 深入学习 03-server-dev.md, 实现 Tools/Resources/Prompts
4. **第 4 天**: 学习 04-client-dev.md, 编写客户端连接服务器
5. **第 5 天**: 研究 06-transports.md, 了解不同传输方式
6. **第 6 天**: 阅读 07-best-practices.md, 学习安全和性能优化
7. **第 7 天**: 阅读 08-mcp-vs-skill.md, 掌握架构选型决策方法
8. **第 8 天**: 阅读 09-cross-platform.md, 将服务器部署到 OpenCode/Cursor/Copilot 等多平台
9. **之后**: 阅读官方规范, 浏览社区服务器源码, 动手做项目
