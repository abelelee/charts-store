<p align="center">
  <a href="https://strapi.io/#gh-light-mode-only">
    <img src="https://strapi.io/assets/strapi-logo-dark.svg" width="318px" alt="Strapi logo" />
  </a>
  <a href="https://strapi.io/#gh-dark-mode-only">
    <img src="https://strapi.io/assets/strapi-logo-light.svg" width="318px" alt="Strapi logo" />
  </a>
</p>

<h3 align="center">开源无头CMS，可自托管或使用云端，一切由你掌控。</h3>
<p align="center">领先的开源无头CMS，100%基于JavaScript/TypeScript，灵活且完全可定制。</p>
<p align="center"><a href="https://cloud.strapi.io/signups?source=github1">云端</a> · <a href="https://strapi.io/demo?utm_campaign=Growth-Experiments&utm_source=strapi%2Fstrapi%20README.md">在线演示</a></p>
<br />

<p align="center">
  <a href="https://www.npmjs.org/package/@strapi/strapi">
    <img src="https://img.shields.io/npm/v/@strapi/strapi/latest.svg" alt="NPM 版本" />
  </a>
  <a href="https://github.com/strapi/strapi/actions/workflows/tests.yml">
    <img src="https://github.com/strapi/strapi/actions/workflows/tests.yml/badge.svg?branch=main" alt="测试" />
  </a>
  <a href="https://discord.strapi.io">
    <img src="https://img.shields.io/discord/811989166782021633?label=Discord" alt="Discord 上的 Strapi" />
  </a>
  <a href="https://github.com/strapi/strapi/actions/workflows/nightly.yml">
    <img src="https://github.com/strapi/strapi/actions/workflows/nightly.yml/badge.svg" alt="Strapi 夜间版本构建状态" />
  </a>
</p>

<br>

<p align="center">
  <a href="https://strapi.io">
    <img src="https://raw.githubusercontent.com/strapi/strapi/main/public/assets/admin-demo.gif" alt="管理面板" />
  </a>
</p>

<br>

Strapi 社区版是一个免费、开源的无头CMS，可帮助你在任何地方管理内容。

- **自托管或云端**：你可以按自己的方式托管和扩展 Strapi 项目。通过部署到 [Strapi Cloud](https://cloud.strapi.io/signups?source=github1) 可以节省时间，也可以部署到你选择的平台：AWS、Azure、Google Cloud、DigitalOcean。
- **现代管理面板**：优雅、完全可定制且高度可扩展的管理界面。
- **多数据库支持**：可选择你偏好的数据库：PostgreSQL、MySQL、MariaDB 和 SQLite。
- **高度可定制**：你可以快速构建自己的逻辑，完全自定义 API、路由或插件以完美契合你的需求。
- **极速且稳定**：基于 Node.js 和 TypeScript 构建，提供可靠且高性能的表现。
- **前端无关**：支持任何前端框架（React、Next.js、Vue、Angular 等）、移动应用甚至物联网设备。
- **默认安全**：提供可复用的策略、CORS、CSP、P3P、Xframe、XSS 等安全机制。
- **强大的 CLI 工具**：可即时生成项目和 API。

## 快速入门

<a href="https://docs.strapi.io/developer-docs/latest/getting-started/quick-start.html" target="_blank">阅读快速入门教程</a> 或按照以下步骤操作：

### ⏳ 安装

使用以下 **Quickstart** 命令立即创建一个 Strapi 项目：

- （推荐使用 **yarn** 安装 Strapi 项目。[点击此处安装 yarn](https://yarnpkg.com/lang/en/docs/install/)）

```bash
yarn create strapi
```

**或**

- （使用 npx 安装 Strapi 项目）

```bash
npx create-strapi@latest
```

该命令将生成一个包含默认功能（认证、权限、内容管理、内容类型构建器和文件上传）的新项目。

尽情享受吧 🎉

### 🖐 系统要求

完整的安装要求请参阅文档中的 <a href="https://docs.strapi.io/developer-docs/latest/setup-deployment-guides/deployment.html">安装要求</a>。

**支持的操作系统**：

| 操作系统         | 推荐版本 | 最低版本 |
|------------------|----------|----------|
| Ubuntu           | 24.04    | LTS      |
| Debian           | 11       | LTS      |
| RHEL             | 9        | LTS      |
| macOS            | 14       | 12       |
| Windows 桌面版   | 11       | 10       |
| Windows Server   | 不支持   | 不支持   |
| Docker           | N/A      | N/A      |

（请注意，Strapi 可能在其他操作系统上也能运行，但目前未经过测试，也不在官方支持范围内。）

**Node.js 要求**：

Strapi 仅支持 Node.js 的维护版本和 LTS 版本。更多信息请参阅 <a href="https://nodejs.org/en/about/releases/">Node.js 发布计划</a>。随 Node.js 默认安装的 NPM 版本也受支持。建议尽可能使用 yarn 而非 npm。

| Strapi 版本     | 推荐版本 | 最低版本 |
|------------------|----------|----------|
| 5.0.0 及以上     | 20.x     | 18.x     |
| 4.14.5 及以上    | 20.x     | 18.x     |
| 4.11.0 及以上    | 18.x     | 16.x     |
| 4.3.9 至 4.10.x  | 18.x     | 14.x     |
| 4.0.x 至 4.3.8   | 16.x     | 14.x     |

**数据库要求**：

| 数据库     | 推荐版本 | 最低版本 |
|------------|----------|----------|
| MySQL      | 8.0      | 8.0      |
| MariaDB    | 11.2     | 10.3     |
| PostgreSQL | 16.0     | 14.0     |
| SQLite     | 3        | 3        |

**我们建议始终使用最新的 Strapi 稳定版本来启动新项目。**

## 功能特性

- **内容类型构建器**：通过字段、组件和[动态区域](https://docs.strapi.io/user-docs/content-manager/writing-content#dynamic-zones)，为内容管理员提供最灵活的内容发布体验。
- **媒体库**：将图片、视频、音频或文档上传至媒体库，轻松查找、编辑和复用资源。
- **国际化**：国际化（i18n）插件允许用户创建、管理和分发多种语言的本地化内容。
- **基于角色的访问控制**：为管理员和终端用户创建无限数量的自定义角色和权限。
- **GraphQL 或 REST**：可通过 REST 或 GraphQL 消费 API。

你可以在 [Strapi Cloud](https://cloud.strapi.io/login?source=github1) 或 [Strapi Enterprise](https://strapi.io/enterprise?source=github1) 中解锁更多功能，如 SSO、审计日志、审核流程等。

**[在我们的官网了解更多](https://strapi.io/overview)**。

## 贡献

在提交 Pull Request 之前，请先阅读我们的 贡献指南。

## 社区支持

如需使用 Strapi 的一般帮助，请参考 [官方文档](https://docs.strapi.io)。如需进一步帮助，可通过以下渠道提问：

- [Discord](https://discord.strapi.io)（与社区和 Strapi 团队实时交流）
- [GitHub](https://github.com/strapi/strapi)（报告 Bug、提交贡献）
- [社区论坛](https://forum.strapi.io)（问题与讨论）
- [反馈页面](https://feedback.strapi.io)（路线图、功能请求）
- [Twitter](https://twitter.com/strapijs)（第一时间获取新闻）
- [Facebook](https://www.facebook.com/Strapi-616063331867161)
- [YouTube 频道](https://www.youtube.com/strapi)（观看视频教程）

## 迁移

请参考文档中的 [迁移指南](https://docs.strapi.io/developer-docs/latest/update-migration-guides/migration-guides.html) 来保持项目的更新。

## 路线图

访问我们的 [路线图页面](https://feedback.strapi.io) 获取最新发布功能和即将推出功能的信息，你也可以提供反馈并为某个功能投票。

## 文档

查看我们专门的 [文档仓库](https://github.com/strapi/documentation)，或在线浏览：

- [开发者文档](https://docs.strapi.io/developer-docs/latest/getting-started/introduction.html)
- [用户指南](https://docs.strapi.io/user-docs/latest/getting-started/introduction.html)
- [云端指南](https://docs.strapi.io/cloud/intro)

## 在线演示

点击访问一个包含示例数据的 [托管 Strapi 项目](https://strapi.io/demo)，亲自体验其内部功能。

## 许可协议

请查看 LICENSE 文件获取授权信息。