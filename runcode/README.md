# RunCode Agent 框架 — 核心模块

> 一个统一的多机制 AI Agent 框架，集成 18 种核心机制于一个主循环中。

---

## 特性总览

| 特性 | 说明 |
|------|------|
| 智能调度 | 自动将任务路由到最合适的处理器 |
| 权限系统 | 细粒度的操作访问控制 |
| 钩子机制 | 灵活的生命周期钩子，支持扩展与监控 |
| 任务管理 | 内置任务追踪系统 |
| 子代理 | 创建和管理子 Agent，实现层级协作 |
| 技能系统 | 动态加载和使用各种技能 |
| 上下文压缩 | 自动压缩上下文，突破 Token 限制 |
| 记忆系统 | 跨会话的持久化上下文记忆 |
| 提示词组装 | 灵活的提示词模板组合 |
| 错误恢复 | 智能异常处理与自动重试 |
| 任务图 | 可视化任务依赖关系与执行流程 |
| 后台任务 | 异步执行长时间运行的操作 |
| 定时调度 | 基于 Cron 表达式的周期性任务调度 |
| 团队协作 | 多 Agent 通信与协作 |
| 协议系统 | 标准化协议支持，可扩展通信 |
| 自主 Agent | 自主决策与执行 |
| 工作树 | 隔离的工作环境，支持并发开发 |
| MCP 集成 | Model Context Protocol 支持 |

---

## 快速开始

```bash
# 安装依赖
pip install anthropic python-dotenv pyyaml

# 配置 .env（在项目根目录）
# 设置你的 API Key 和模型

# 运行
python runcode/code.py
```

---

## 项目结构

```
runcode/
├── code.py              # 主入口程序（综合 Agent）
├── images/              # 架构图
│   ├── system-architecture.svg
│   ├── system-architecture.en.svg
│   └── system-architecture.ja.svg
├── .tasks/              # 任务存储（自动生成）
├── .transcripts/        # 会话记录（自动生成）
├── .worktrees/          # 工作树目录（自动生成）
└── .mailboxes/          # 消息邮箱（自动生成）
```

---

## 架构

![系统架构图](images/system-architecture.svg)

七层架构设计：

1. **输入层** — 接收用户请求并解析指令
2. **调度层** — 根据任务特征路由到合适的处理器
3. **执行层** — 调用技能、子代理、后台任务等执行单元
4. **记忆层** — 管理短期和长期记忆，维护上下文
5. **监控层** — 权限检查、错误恢复、日志记录
6. **协作层** — 团队通信、协议交换、自主决策
7. **持久层** — 工作树隔离、定时任务、状态持久化

---

## 使用示例

```python
# 初始化 Agent
agent = ComprehensiveAgent()

# 执行任务
result = agent.run("你的指令")

# 创建子代理
sub = agent.create_subagent(
    name="analyzer",
    role="数据分析师",
    prompt="你擅长分析结构化数据。"
)
sub.run("分析这份报告")

# 设置定时任务
agent.schedule_cron(
    cron="0 9 * * *",        # 每天早上 9 点
    prompt="生成每日摘要"
)
```

---

## 配置

通过 `.env` 或环境变量配置：

| 变量 | 说明 | 默认值 |
|------|------|--------|
| ANTHROPIC_API_KEY | API Key | - |
| MODEL_ID | 模型名称 | deepseek-v4-flash |
| MAX_TOKENS | 最大 Token 数 | 8000 |
| TEMPERATURE | 生成温度 | 0.7 |

---

## 协议

MIT License
