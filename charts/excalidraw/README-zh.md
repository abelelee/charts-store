<a href="https://excalidraw.com/" target="_blank" rel="noopener">
  <picture>
    <source media="(prefers-color-scheme: dark)" alt="Excalidraw" srcset="https://excalidraw.nyc3.cdn.digitaloceanspaces.com/github/excalidraw_github_cover_2_dark.png" />
    <img alt="Excalidraw" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/excalidraw/image/excalidraw_github_cover_2.png" />
  </picture>
</a>

<h4 align="center">
  <a href="https://excalidraw.com">Excalidraw 编辑器</a> |
  <a href="https://plus.excalidraw.com/blog">博客</a> |
  <a href="https://docs.excalidraw.com">文档</a> |
  <a href="https://plus.excalidraw.com">Excalidraw+</a>
</h4>

<div align="center">
  <h2>
    一个开源的虚拟手绘风格白板。</br>
    支持协作和端到端加密。</br>
  <br />
  </h2>
</div>

<br />
<p align="center">
  <a href="https://github.com/excalidraw/excalidraw/blob/master/LICENSE">
    <img alt="Excalidraw 采用 MIT 协议发布。" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/excalidraw/image/license-MIT-blue.svg"  />
  </a>
  <a href="https://www.npmjs.com/package/@excalidraw/excalidraw">
    <img alt="npm 每月下载量" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/excalidraw/image/68747470733a2f2f696d672e736869656c64732e696f2f6e706d2f646d2f40657863616c69647261772f657863616c6964726177.svg"  />
  </a>
  <a href="https://docs.excalidraw.com/docs/introduction/contributing">
    <img alt="欢迎提交 PR！" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/excalidraw/image/PRs-welcome-brightgreen.svg"  />
  </a>
  <a href="https://discord.gg/UexuTaE">
    <img alt="在 Discord 上聊天" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/excalidraw/image/68747470733a2f2f696d672e736869656c64732e696f2f646973636f72642f3732333637323433303734343137343638323f636f6c6f723d373338616436266c6162656c3d436861742532306f6e253230446973636f7264266c6f676f3d646973636f7264266c6f676f436f6c6f723d6666666666662677.svg"/>
  </a>
  <a href="https://deepwiki.com/excalidraw/excalidraw">
    <img alt="向 DeepWiki 提问" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/excalidraw/image/badge.svg" />
  </a>
  <a href="https://twitter.com/excalidraw">
    <img alt="在 Twitter 上关注 Excalidraw" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/excalidraw/image/excalidraw.svg"/>
  </a>
</p>

<div align="center">
  <figure>
    <a href="https://excalidraw.com" target="_blank" rel="noopener">
      <img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/excalidraw/image/github_2Fproduct_showcase.png" alt="产品展示" />
    </a>
    <figcaption>
      <p align="center">
        创建美观的手绘风格图表、线框图，或任何你喜欢的内容。
      </p>
    </figcaption>
  </figure>
</div>

## 功能特性

Excalidraw 编辑器（npm 包）支持以下功能：

- 💯&nbsp;免费且开源。
- 🎨&nbsp;基于画布的无限白板。
- ✍️&nbsp;手绘风格。
- 🌓&nbsp;暗色模式。
- 🏗️&nbsp;可定制。
- 📷&nbsp;支持图片。
- 😀&nbsp;支持形状库。
- 🌐&nbsp;支持本地化（i18n）。
- 🖼️&nbsp;导出为 PNG、SVG 和剪贴板。
- 💾&nbsp;开放格式 - 可将绘图导出为 `.excalidraw` JSON 文件。
- ⚒️&nbsp;丰富的工具集 - 矩形、圆形、菱形、箭头、直线、自由绘制、橡皮擦等。
- ➡️&nbsp;箭头绑定和带标签的箭头。
- 🔙&nbsp;撤销 / 重做。
- 🔍&nbsp;支持缩放和平移。

## Excalidraw.com

托管在 [excalidraw.com](https://excalidraw.com) 的应用是使用 Excalidraw 构建功能的一个最小化展示。它的 [源代码](https://github.com/excalidraw/excalidraw/tree/master/excalidraw-app) 也包含在本仓库中，该应用包含以下功能：

- 📡&nbsp;PWA 支持（可离线使用）。
- 🤼&nbsp;实时协作。
- 🔒&nbsp;端到端加密。
- 💾&nbsp;本地优先支持（自动保存到浏览器）。
- 🔗&nbsp;可分享链接（导出为只读链接供他人查看）。

我们未来会将这些功能作为即插即用的插件提供给 npm 包使用。

## 快速开始

**注意：** 以下说明是关于如何将 Excalidraw 的 [npm 包](https://www.npmjs.com/package/@excalidraw/excalidraw) 集成到你自己的应用中。如需在本地运行本仓库用于开发，请参考我们的 [开发指南](https://docs.excalidraw.com/docs/introduction/development)。

使用 `npm` 或 `yarn` 安装包：

```bash
npm install react react-dom @excalidraw/excalidraw
# 或
yarn add react react-dom @excalidraw/excalidraw
```

更多细节请查看我们的 [文档](https://docs.excalidraw.com/docs/@excalidraw/excalidraw/installation)！

## 贡献

- 缺少某些功能或发现 bug？请 [提交报告](https://github.com/excalidraw/excalidraw/issues)。
- 想要贡献代码？请查看我们的 [贡献指南](https://docs.excalidraw.com/docs/introduction/contributing) 或加入 [Discord](https://discord.gg/UexuTaE) 与我们交流。
- 想帮助翻译？请参考 [翻译指南](https://docs.excalidraw.com/docs/introduction/contributing#translating)。

## 集成方式

- [VScode 插件](https://marketplace.visualstudio.com/items?itemName=pomdtr.excalidraw-editor)
- [npm 包](https://www.npmjs.com/package/@excalidraw/excalidraw)

## 使用 Excalidraw 的组织

[Google Cloud](https://googlecloudcheatsheet.withgoogle.com/architecture) • [Meta](https://meta.com/) • [CodeSandbox](https://codesandbox.io/) • [Obsidian Excalidraw](https://github.com/zsviczian/obsidian-excalidraw-plugin) • [Replit](https://replit.com/) • [Slite](https://slite.com/) • [Notion](https://notion.so/) • [HackerRank](https://www.hackerrank.com/) • 以及其他许多组织
