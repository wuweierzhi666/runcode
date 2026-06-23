# 🚀 RunCode — AI Agent 框架

<div align="center">

**一个功能完备的 AI 编程助手框架，支持多模型、多 Agent 协作、任务调度与 MCP 集成**

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://python.org)
[![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)](https://nextjs.org)
[![License](https://img.shields.io/badge/License-MIT-green)]()

</div>

---

## 📋 项目简介

RunCode 是一个**开箱即用的 AI Agent 框架**，提供了一个功能完整、可扩展的 AI 编程助手。它不是一个简单的 API 调用封装，而是一个真正的 agent 运行时——拥有完整的工具调度、权限管理、多 Agent 协作、任务编排和自主决策能力。

项目包含两大部分：

| 部分 | 说明 |
|------|------|
| **`runcode/`** | Python CLI Agent 核心框架 |
| **`web/`** | Next.js 互动学习/展示网站 |

---

## ✨ 核心特性

### Agent 运行时（Python CLI）

| 特性 | 说明 |
|------|------|
| 🧠 **智能调度** | 自动将任务路由到最合适的处理器 |
| 🔒 **权限系统** | 细粒度的操作访问控制 |
| 🔗 **钩子机制** | 灵活的生命周期钩子，支持扩展与监控 |
| 📋 **任务管理** | 内置任务追踪系统 |
| 👷 **子代理** | 创建和管理子 Agent，实现层级协作 |
| 🎯 **技能系统** | 动态加载和使用各种技能 |
| 💾 **上下文压缩** | 自动压缩上下文，突破 Token 限制 |
| 🧠 **记忆系统** | 跨会话的持久化上下文记忆 |
| 🔧 **提示词组装** | 灵活的提示词模板组合 |
| 🔄 **错误恢复** | 智能异常处理与自动重试 |
| 📊 **任务图** | 可视化任务依赖关系与执行流程 |
| ⚡ **后台任务** | 异步执行长时间运行的操作 |
| ⏰ **定时调度** | 基于 Cron 表达式的周期性任务调度 |
| 👥 **团队协作** | 多 Agent 通信与协作 |
| 📡 **协议系统** | 标准化协议支持，可扩展通信 |
| 🤖 **自主 Agent** | 自主决策与执行 |
| 🌲 **工作树** | 隔离的工作环境，支持并发开发 |
| 🔌 **MCP 集成** | Model Context Protocol 支持 |

### Web 展示平台

- 20 个渐进式版本展示
- 代码差异对比查看器
- 交互式 Agent 循环模拟器
- 架构图与可视化组件
- 多语言支持（中文/英文/日文）

---

## 🚀 快速开始

### 前置条件

- Python 3.10+
- Node.js 18+（运行 Web 需要）

### 1️⃣ 配置与运行 Python Agent

```bash
# 安装依赖
pip install anthropic python-dotenv pyyaml pyreadline3 websockets sseclient-py aiohttp

# 配置 API Key（编辑 .env 文件）
# 支持：DeepSeek、Claude、GLM、Kimi、MiniMax

# 运行 Agent
python runcode/code.py
```

### 2️⃣ 运行 Web 前端

```bash
cd web
npm install
npm run dev
```

打开 `http://localhost:3000` 查看。

---

## 🔧 配置说明

通过 `.env` 文件配置：

```env
# 你的 API Key
ANTHROPIC_API_KEY=sk-your-key-here

# 模型 ID
MODEL_ID=deepseek-chat

# API 代理地址（可选）
ANTHROPIC_BASE_URL=https://api.deepseek.com/anthropic
```

支持多模型切换：DeepSeek V3/V4、Claude Sonnet/Opus、GLM-5、Kimi K2.5、MiniMax M2.5。

---

## 📁 项目结构

```
runcode/
├── runcode/                 # 🎯 Python Agent 核心框架
│   ├── code.py              # 主入口（综合 Agent）
│   ├── images/              # 架构图 SVG
│   └── README.md
├── agents/                  # 📖 独立可运行的教学/参考脚本
│   ├── s01_agent_loop.py
│   ├── s02_tool_use.py
│   ├── ...
│   └── s_full.py            # 完整参考实现
├── web/                     # 🌐 Next.js 展示网站
│   ├── src/                 # React 组件、页面、数据
│   ├── public/              # 静态资源
│   └── package.json
├── skills/                  # 📚 技能参考文档
│   ├── agent-builder/
│   ├── code-review/
│   ├── mcp-builder/
│   └── pdf/
├── .env                     # 配置文件（不提交到 Git）
├── .gitignore
├── requirements.txt
└── README.md
```

---

## 🧪 运行教学脚本

想了解每个机制的工作原理？可以单独运行教学脚本：

```bash
# 运行基础 Agent 循环
python agents/s01_agent_loop.py

# 运行工具调度
python agents/s02_tool_use.py

# 运行完整参考实现（集成所有机制）
python agents/s_full.py
```

每个脚本都是自包含的，可以直接运行体验。

---

## 🌐 多模型支持

预配置了多种模型，快速切换：

| 模型 | MODEL_ID | Base URL |
|------|----------|----------|
| DeepSeek V4 Flash | `deepseek-v4-flash` | `https://api.deepseek.com/anthropic` |
| DeepSeek Chat | `deepseek-chat` | `https://api.deepseek.com/anthropic` |
| Claude Sonnet 4.6 | `claude-sonnet-4-6` | 默认（无需设置） |
| GLM-5 | `glm-5` | `https://open.bigmodel.cn/api/anthropic` |
| Kimi K2.5 | `kimi-k2.5` | `https://api.moonshot.cn/anthropic` |
| MiniMax M2.5 | `MiniMax-M2.5` | `https://api.minimaxi.com/anthropic` |

---

## 📄 许可

本项目基于 MIT 协议开源。

---

## 🙌 致谢

感谢所有为 Agent 技术和 AI 框架发展做出贡献的开发者与研究者。
