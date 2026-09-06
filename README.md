# FictionChina — 静态小说网站（英文主站）

> 目标域名：`fictionchina.com`（静态站，GitHub Pages 已上线 `fictionchina.com`）。
> 主语言：**英文**。当前上架小说《The Complete Tale of Yue Fei 说岳全传》（详情+简介，章节待填）。

## 目录结构
```
fictionchina/
  index.html                     # 首页（hero + 小说网格）
  novel/<slug>.html              # 小说详情页（封面/简介/章节目录）
  read/<slug>/<n>.html           # 章节阅读页（正文 + 上一章/下一章）
  css/style.css                  # 设计系统（好看的关键）
  sitemap.xml  robots.txt  favicon.svg
```

## 如何新增一本小说
以 `my-story` 为例（slug 用英文小写+连字符）：
1. **详情页**：复制 `novel/the-jade-phoenix-ascends.html` → `novel/my-story.html`，改 `<title>`、`<meta description>`、`<link rel="canonical">`、封面标题、作者、简介、章节列表。
2. **章节**：复制 `read/the-jade-phoenix-ascends/1.html` → `read/my-story/1.html`（每章一个文件，改 title/canonical/正文/上下章链接）。
3. **首页**：在 `index.html` 的 `.grid` 里加一张 `.card`（封面色用 `--c1/--c2`，标题/作者/简介）。
4. **sitemap.xml**：把新页面的 URL 加进去，并更新 `lastmod`；在 Google Search Console「网址检查」提交新 URL 请求收录。

## 设计说明
- 阅读页用衬线、宽行距，纸白背景，专注阅读；深色顶栏 + 金色点缀。
- 封面是 CSS 渐变色块 + 中文/英文标题字（无需图片，改 `--c1/--c2` 调色即可）。
- SEO：每页有 title/meta description/canonical/OG；整站 sitemap + robots。

## 部署（可选，等 `fictionchina.com` 注册/托管好）
- GitHub Pages：把本目录推到 GitHub 仓库，Settings → Pages → 部署；CNAME 指向 `fictionchina.com`。
- 或 Cloudflare Pages：连仓库一键部署，绑 `fictionchina.com`。
