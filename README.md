# 🍎 Fruits Blog

基于 [VitePress](https://vitepress.dev) 构建的个人博客，使用 [easy-vitepress-blog](https://github.com/ZbWeR/easy-vitepress-blog) 主题。

## ✨ 特性

- **📝 自动化路由**：在 `docs/src/Notes/` 下新增 Markdown 文件即可发布文章，无需手动配置路由。
- **🌹 定制的 Friends 页面**：在 `docs/.vitepress/userConfig/friendsInfo.ts` 中配置友情链接。
- **🦄 定制的 Projects 页面**：在 `docs/.vitepress/userConfig/projectsInfo.ts` 中配置开源项目。
- **🎨 美观的 PDF 导出**：打印样式已优化，可导出精美的 PDF 文件。

## 🚀 本地开发

```bash
npm install
npm run docs:dev
```

## 📦 构建

```bash
npm run docs:build
```

## 📁 目录结构

```
docs
├─ .vitepress
│  ├─ components  # 自定义组件
│  ├─ userConfig  # 用户数据：友链、项目
│  └─ config.mjs  # VitePress 配置入口
└─ src            # 站点内容
   ├─ public      # 静态资源
   ├─ Notes       # 博客文章（Markdown）
   ├─ index.md    # 首页
   ├─ AboutMe.md  # 关于页
   ├─ Friends.md  # 友链页
   └─ Projects.md # 项目页
```
