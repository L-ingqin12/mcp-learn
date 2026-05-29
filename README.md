# MCP (Model Context Protocol) 学习指南

MCP 是 Anthropic 推出的开放标准协议，为 AI 模型提供连接外部工具、数据和 API 的统一接口。类比：**MCP 之于 AI 工具集成，就像 USB-C 之于设备充电**——一个通用连接器。

## 目录结构

| 文件 | 内容 |
|------|------|
| [01-overview.md](01-overview.md) | MCP 核心概念、架构、协议基础 |
| [02-quickstart.md](02-quickstart.md) | 环境搭建、第一个 MCP 服务器 |
| [03-server-dev.md](03-server-dev.md) | 服务器开发详解 (Python SDK) |
| [04-client-dev.md](04-client-dev.md) | 客户端开发详解 |
| [05-tools-resources-prompts.md](05-tools-resources-prompts.md) | 三大核心原语: Tools/Resources/Prompts |
| [06-transports.md](06-transports.md) | 传输层: stdio/SSE/Streamable HTTP |
| [07-best-practices.md](07-best-practices.md) | 最佳实践与安全 |
| [references.md](references.md) | 官方文档、教程、社区资源链接 |
| [examples/](examples/) | 可运行的示例代码 |

## 快速开始

```bash
# 安装 Python SDK
pip install mcp

# 运行示例服务器
cd examples/
python simple_server.py
```

## 核心要点

1. **协议基础**: JSON-RPC 2.0，客户端-服务器架构
2. **三种原语**: Tools (模型控制的操作)、Resources (应用控制的只读数据)、Prompts (可复用交互模板)
3. **传输方式**: stdio (本地)、Streamable HTTP (远程)、SSE (已废弃)
4. **鉴权**: OAuth 2.0 + Client ID Metadata Documents
