<div align="center">

# BLOG-V3 // 序栈博客引擎

**React + Rsbuild + MDX 的本地优先博客与 CMS**<br>
*An MDX publishing engine with a local content workbench.*

[![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=111111)](https://react.dev)
[![Rsbuild](https://img.shields.io/badge/Rsbuild-2-F59E0B?style=for-the-badge&logo=rsbuild)](https://rsbuild.dev)
[![MDX](https://img.shields.io/badge/Content-MDX-1B1F24?style=for-the-badge&logo=mdx)](https://mdxjs.com)
[![License](https://img.shields.io/badge/License-MIT%20%2F%20CC-555555?style=for-the-badge)](LICENSE)

</div>

---

## 01. THE PURPOSE // 项目本源

blog-v3 将 MDX 内容预编译为静态页面，同时提供本地 CMS、全文搜索、Atom/OPML 订阅和构建统计。

[Repository](https://github.com/kerntau/blog-v3)

## 02. CORE ARCHITECTURE // 核心架构

~~~mermaid
graph LR
  C[Markdown / MDX] --> P[Build scripts]
  P --> X[MDX + Shiki + KaTeX]
  X --> I[Search, stats, Atom, OPML]
  X --> R[React + Rsbuild pages]
  CMS[Local CMS] --> C
~~~

内容在构建期解析，浏览器消费生成的页面和索引；CMS 仅用于本地编辑与 Git 工作流。

## 03. TECHNICAL MATRIX // 技术矩阵

| 领域 | 技术 | 责任 |
| --- | --- | --- |
| UI | React 19、React Router 7 | 页面、主题和导航 |
| Build | Rsbuild/Rspack、TypeScript | 开发、编译和类型检查 |
| Content | MDX、gray-matter、Shiki、KaTeX | 解析、代码和公式 |
| Search | MiniSearch | 客户端全文搜索 |
| Feeds | Atom、OPML、JSON | 订阅与统计 |

## 04. REPOSITORY TOPOLOGY // 源码拓扑

~~~text
content/              # posts、previews、友链和主题页
remark-plugins/       # MDX Remark/Rehype 插件
scripts/              # build、dev、CMS、新建文章
src/                  # pages、components、hooks、stores、utils
public/               # 静态资源和生成索引
blog.config.ts        # 品牌与路由配置
rsbuild.config.ts     # 构建配置
~~~

## 05. CLONE & QUICK START // 极速开始

需要 Node.js 22.17.1+ 与 pnpm 10+。

~~~bash
git clone https://github.com/kerntau/blog-v3.git
cd blog-v3
pnpm install
pnpm dev
~~~

本地 CMS：

~~~bash
pnpm admin
~~~

## 06. DEPLOYMENT & VERIFICATION // 部署与验证

~~~bash
pnpm lint
pnpm tsc --noEmit
pnpm build
pnpm preview
~~~

将构建产物部署到静态托管。发布前验证 MDX 编译、搜索索引、Atom/OPML、草稿预览和 CMS 写入流程。

## 07. ENGINEERING CONTRACT // 工程契约

- 文章 front matter 必须可解析并包含必要字段。
- 生成的 public/api 数据应由脚本更新，不手工修改。
- CMS 操作必须保持 Git 可审计，避免提交敏感配置。
- 文章、图片和代码的许可证边界需在发布前确认。

## 08. ROADMAP // 演进路线

- [x] MDX、搜索、Atom/OPML 和本地 CMS
- [x] 主题、统计和预览工作流
- [ ] 增量构建与更快的内容索引
- [ ] 可选的远程草稿协作

## 09. LICENSE // 许可证

代码遵循 [MIT](LICENSE)。文章和原创内容遵循仓库中的 CC BY-NC-SA 声明。
