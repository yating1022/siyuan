---
title: 3.Claude Code
date: '2026-08-13 08:24:39'
head: []
outline: deep
sidebar: false
prev: false
next: false
---



# 3.Claude Code

# 1.安装与使用

> [!NOTE] 💡 两种方式的区别
> 两者业务代码完全同源、命令参数、配置格式、功能逻辑一模一样；差异集中在运行载体、依赖、更新机制、官方支持优先级。Anthropic 文档明确推荐【原生二进制 CLI】，npm 包是兼容过渡方案，长期维护优先级更低。

|对比维度|官方原生二进制 CLI|npm @anthropic-ai/claude-code（Node 版）|
| ----------| ----------------------------------------------| ----------------------------------------------------------------------------|
|**运行依赖**|✅​**不需要预装 Node.js**，自带运行时|❌ 强制依赖本地 Node.js ≥18；Node 版本不对直接报错、崩溃|
|**程序形态**|独立平台二进制（单文件可执行）|Node JS 脚本包，通过 node 解释器启动|
|**自动更新**|✅ 内置自更新`claude update`|❌​**没有内置自更新**​，必须手动`npm update -g @anthropic-ai/claude-code`|
|**官方推荐等级**|⭐⭐⭐⭐⭐ 文档首选推荐|⭐⭐⭐ 过渡兼容方案，不做优先推荐|
|**启动性能**|更快，启动开销小|更慢，额外加载 Node.js 虚拟机，冷启动明显延迟|
|**容器 / 无 Node 环境**|非常友好，只需要下载二进制|必须在镜像预装 Node，增加镜像体积|
|**版本分发节奏**|优先推送新版本；新功能先上线二进制|npm 包会延后同步，偶有版本滞后|
|**卸载方式**|`claude uninstall`/ 删除二进制文件|`npm uninstall -g @anthropic-ai/claude-code`|
|**已知坑点**|极少；平台权限（macOS 安全隔离）问题为主|容易受：Node 版本、npm 镜像、pnpm/yarn 全局路径冲突、node 全局权限污染影响|
|**IDE 插件联动**|和 VSCode/JetBrains Claude Code 插件完美互通|可用，但部分插件自动唤起逻辑优先识别原生二进制|

## 1.官方安装

```bash
# Mac/Linux/WSL
curl -fsSL https://claude.ai/install.sh | bash
# Windows PowerShell
irm https://claude.ai/install.ps1 | iex
```

## 2.nodejs安装

```bash
npm install -g @anthropic-ai/claude-code
```

## 3.nodejs版本迁移官方版

> 如果在已经安装nodejs版本的情况下，需要安装官方二进制版本，则直接运行如下命令

```bash
claude install
```

> [!CAUTION]
> 下载安装失败则可能需要代理，要么开启tun模式，要么在当前终端配置代理

```bash
$env:HTTP_PROXY="http://127.0.0.1:10808"
$env:HTTPS_PROXY="http://127.0.0.1:10808"
# 然后再次尝试安装
claude install
```

‍

安装完成后卸载npm版本

```bash
npm uninstall -g @anthropic-ai/claude-code
```

‍

‍

# 2.使用

‍
