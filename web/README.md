# RunCode Web — Agent 框架展示平台

> 基于 Next.js 16 的互动展示网站，用于呈现 RunCode Agent 框架的各个版本与核心机制。

---

## 技术栈

- **框架**: Next.js 16 (App Router)
- **UI**: React 19 + Tailwind CSS v4 + Framer Motion
- **语言**: TypeScript
- **国际化**: 内置英文、中文、日文支持

## 功能

- 20 个渐进式版本展示（s01 → s20）
- 代码差异对比查看器
- 交互式 Agent 循环模拟器
- 架构动画与可视化组件
- 版本时间线

## 运行

```bash
npm install
npm run dev
```

打开 `http://localhost:3000`。

## 构建

```bash
npm run build
```

静态文件输出到 `out/` 目录，可部署到任意静态托管服务。

## 部署

本项目配置了 Vercel 部署：

```bash
npm i -g vercel
vercel --prod
```
