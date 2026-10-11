# 序栈 Blog Engine

基于 React 19、Rsbuild 和 MDX 的现代化技术博客引擎，同时提供本地可视化 CMS。文章、友链、主题配置和构建索引都在仓库内维护，可输出静态站点。

## 特性

- MDX 离线预编译、Shiki 代码高亮、KaTeX 数学公式
- ABCjs 音乐简谱/五线谱与阅读耗时统计
- 明暗主题、响应式侧栏、图片灯箱和 Ctrl+K 全文搜索
- Atom、OPML、搜索索引和统计 JSON 自动生成
- 本地 CMS：文章编辑、SEO/品牌配置、Git 状态与统计面板
- TypeScript 严格检查、ESLint 和 Sass 模块化样式

## 技术栈

React 19 · React Router DOM 7 · Rsbuild/Rspack · TypeScript · MDX · Shiki · KaTeX · Zustand · Framer Motion。

## 快速开始

需要 Node.js 22.17.1+ 与 pnpm 10+。

~~~bash
pnpm install
pnpm dev       # 前台开发
pnpm admin     # 本地 CMS，默认 http://localhost:4000
pnpm build
pnpm preview
~~~

新建文章：

~~~bash
pnpm new
pnpm new my-first-article
~~~

文章会按年份写入 content/posts/<年份>/。

## 目录

~~~text
content/          # Markdown/MDX 文章、草稿、友链和主题页
public/            # favicon、静态资源、RSS/搜索索引产物
remark-plugins/   # MDX Remark/Rehype 插件
scripts/           # 构建、开发、CMS 与新建文章脚本
src/               # 页面、组件、hooks、stores 和工具
blog.config.ts    # 品牌、导航和站点默认配置
rsbuild.config.ts # Rsbuild 配置
~~~

## 配置和检查

站点标题、作者和导航配置在 blog.config.ts；前台组件配置在 src/app.config.ts。提交前建议运行：

~~~bash
pnpm lint
pnpm tsc --noEmit
pnpm build
~~~

## 许可证

代码遵循 MIT（LICENSE）。文章和原创内容遵循仓库中的 CC BY-NC-SA 声明。
