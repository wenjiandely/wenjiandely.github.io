# stabilelee.me

基于 [Hugo](https://gohugo.io/) + [PaperMod](https://github.com/adityatelange/hugo-PaperMod) 的个人站点，
部署在 GitHub Pages，域名 `stabilelee.me`。

## 本地预览

```bash
hugo server -D          # 打开 http://localhost:1313
hugo --minify --gc      # 构建到 public/
```

需要 Hugo **extended ≥ 0.158**（当前验证版本 0.168.0）。
macOS：`brew install hugo`；其他平台见 https://gohugo.io/installation/

## 目录结构

```
.
├── hugo.yaml                     # 站点配置：个人信息、菜单、社交图标、搜索
├── content/
│   ├── about.md                  # /about/ 关于页
│   ├── posts/                    # /posts/ 文章
│   └── projects/                 # /projects/ 项目
├── assets/css/extended/custom.css # 自定义样式（只写覆盖项）
├── static/
│   └── avatar.svg                # 首页头像
├── themes/PaperMod/              # 主题（已内置，无需 submodule）
└── .github/workflows/hugo.yaml   # 推送到 main 自动构建并发布
```

## 写作

新建文章：

```bash
hugo new content posts/my-post.md
```

front matter 常用字段：

```yaml
---
title: "标题"
date: 2026-10-29
tags: ["标签"]
categories: ["分类"]
summary: "列表页显示的摘要"
draft: false
ShowToc: true
---
```

`draft: true` 的文章本地 `hugo server -D` 可见，线上不会发布。

## 部署

1. 仓库 Settings → Pages → **Source 选 GitHub Actions**
2. 推送到 `main` 分支，Actions 自动构建
3. 首次部署后，在 Pages 里把 Custom domain 设为 `stabilelee.me`，等证书就绪后勾选 **Enforce HTTPS**

工作流里固定了 Hugo `0.168.0`，如需升级只改 `.github/workflows/hugo.yaml` 里的 `HUGO_VERSION`。

## 修改个人信息

| 想改什么 | 改哪里 |
|---|---|
| 首页标题、副标题、按钮 | `hugo.yaml` → `params.profileMode` |
| 顶部导航 | `hugo.yaml` → `menu.main` |
| 社交图标 | `hugo.yaml` → `params.socialIcons` |
| 头像 | `static/avatar.svg` |
| 关于页正文 | `content/about.md` |
| 站点描述、关键词 | `hugo.yaml` → `params.description` / `params.keywords` |

## 主题升级

主题文件直接放在 `themes/PaperMod/`，升级时用新版覆盖即可：

```bash
git rm -r themes/PaperMod
curl -L https://github.com/adityatelange/hugo-PaperMod/archive/refs/heads/master.tar.gz | tar xz
mv hugo-PaperMod-master themes/PaperMod
```

升级后务必本地 `hugo` 构建一次，确认主题与 Hugo 版本仍兼容。

## 中英文内容

- 默认英文：站点根路径 /。
- 中文：/zh/。
- 默认的 .md 文件为英文；对应的 .zh.md 文件为中文，两个文件使用相同的基础文件名。
- 顶部语言入口切换到当前页面的另一语言版本。
- 内部正文链接使用 Hugo relref，使链接保持在当前语言下。
- 首页两种语言都只显示 🍐。论文简介与项目卡片简介按要求保留英文，关于和项目正文提供双语版本。

语言设置位于 hugo.yaml 的 languages 段。添加页面时，请同时添加对应的 .zh.md 文件。
