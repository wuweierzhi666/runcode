# 🚀 RunCode — AI Agent 框架

<div align="center">

**一个功能完备的 AI 编程助手框架，支持多模型、多 Agent 协作、任务调度与 MCP 集成**

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green)]()

</div>

---

## 📋 项目简介

RunCode 是一个**开箱即用的 AI Agent 框架**，提供了一个功能完整、可扩展的 AI 编程助手。它不是一个简单的 API 调用封装，而是一个真正的 agent 运行时——拥有完整的工具调度、权限管理、多 Agent 协作、任务编排和自主决策能力。

核心部分：

| 部分 | 说明 |
|------|------|
| **`runcode/`** | Python CLI Agent 核心框架 |

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

---

## 🚀 快速开始

### 前置条件

- Python 3.10+

### 安装

```bash
# 1️⃣ 克隆或进入项目目录
cd runcode

# 2️⃣ 安装依赖
pip install -r requirements.txt

# 3️⃣ 安装 runcode 为全局命令（可选但推荐）
#    安装后可在任意终端直接输入 runcode 启动
pip install -e .

# 4️⃣ 配置 API Key（编辑 .env 文件）
#    支持：DeepSeek、Claude、GLM、Kimi、MiniMax
```

### 运行

```bash
# 方式一：全局命令（安装后可用，在任何目录下执行）
runcode

# 方式二：直接运行（无需安装，必须在项目目录下）
python runcode/code.py
```

> 💡 **提示**：推荐使用方式一（`pip install -e .`），这样在任何终端目录输入 `runcode` 即可启动，它会自动加载当前目录下的 `.env` 配置。如果遇到 `runcode` 命令找不到的情况，请确保 `%APPDATA%\Python\Python313\Scripts`（Windows）或 `~/.local/bin`（Linux/macOS）已添加到系统 PATH。

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
│   ├── code.py              # 主入口 Agent
│   ├── images/              # 架构图 SVG
│   └── README.md
├── skills/                  # 📚 运行时加载的技能
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
