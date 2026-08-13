---
title: 2.GitNexus
date: '2026-08-11 16:48:47'
head:
  - name: keywords
    content: AI
outline: deep
sidebar: false
prev: false
next: false
---



![image](./images)

# 2.GitNexus

> [!NOTE] ✏️ 说明
> GitNexus是一个代码知识图谱工具，它的核心功能是将任意代码仓库（支持 GitHub、GitLab、Azure、本地仓库或 ZIP 文件）转换成一个交互式的**知识图谱**，并内置了一个基于图谱的 RAG（检索增强生成）代理，非常适合用于代码探索和分析。

- analyze一Tree-sitter AST全量索引
- impact一Blast Radius变更影响分析
- context-360°符号视图（callers/,callees)
- detect-changes一Git diff→受影响符号映射
- mcp一MCP服务器供AI直接查询

# 一、安装

```bash
# 1. 安装与索引
npm install -g gitnexus
cd your-project
gitnexus analyze              # 全量索引（AST + 依赖 + 调用链）
gitnexus analyze --force      # 大重构后强制重建

# 2. 接入 AI 编码工具（MCP）
claude mcp add gitnexus -- gitnexus mcp   # Claude Code
codex mcp add gitnexus -- gitnexus mcp    # Codex

# 3. Trellis 初始化
trellis init -u junsen --claude
# AI 描述重构需求 → brainstorm → PRD

# 4. AI 在实现过程中自动调用 GitNexus
# gitnexus impact <symbol>        → 变更影响范围
# gitnexus context <symbol>       → 360° 调用方/被调用方
# gitnexus detect-changes         → 提交前 diff 影响分析
# trellis-check 对照 Spec + blast radius 验证
```

‍
