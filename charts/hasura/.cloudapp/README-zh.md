![Hasura 标志](./assets/hasura_logo_primary_darkbg.png#gh-dark-mode-only)
![Hasura 标志](./assets/hasura_logo_primary_lightbg.png#gh-light-mode-only)

# Hasura GraphQL 引擎

Hasura 引擎是一个开源项目，通过提供一个单一、可组合、安全的 API 端点来访问数据，从而加速现代应用程序的构建。

<a href="https://hasura.io/"><img src="https://img.shields.io/badge/🏠_访问-Hasura_官网-blue.svg?style=flat"></a>
<a href="https://hasura.io/community/"><img src="https://img.shields.io/badge/😊_加入-社区-blue.svg?style=flat"></a>

## Hasura V3

[![文档](https://img.shields.io/badge/文档-v3-yellow.svg?style=flat)](https://hasura.io/docs/3.0/getting-started/quickstart/)

数据交付网络（DDN）的未来已正式发布：支持 PostgreSQL（及其变体）、MongoDB、ClickHouse 和 MS SQL Server。还支持使用 Typescript、Python 和 Go Connector SDK 编写自定义业务逻辑。以下是推荐的 [快速入门指南](https://hasura.io/docs/3.0/getting-started/quickstart/)。

Hasura V3 引擎代码（驱动 Hasura DDN 的核心）位于此仓库的 `v3` 文件夹中。你可以在 [v3 README](/v3/README.md) 中找到更详细的说明。

Hasura DDN 架构包括用于连接数据源的 数据连接器。所有 Hasura 连接器也完全开源。请查看 [连接器中心](https://hasura.io/connectors/)，其中列出了所有可用的连接器。

## Hasura V2

[![最新版本](https://img.shields.io/github/v/release/hasura/graphql-engine)](https://github.com/hasura/graphql-engine/releases/latest)
[![文档](https://img.shields.io/badge/文档-v2.x-yellow.svg?style=flat)](https://hasura.io/docs)

Hasura V2 是当前稳定的版本。请在 `v2` 文件夹和此 [README](V2-README.md) 中找到关于 V2 版本的更详细信息。

## 克隆仓库

本仓库是一个大型且活跃的单体仓库，包含 Hasura 生态系统的多个部分以及较长的 Git 历史记录，首次克隆可能会较慢并占用大量磁盘空间。如果你遇到克隆问题，建议参考以下方法。

### 浅层克隆

这将仅克隆最新的提交，忽略所有历史提交。

```
git clone https://github.com/hasura/graphql-engine.git --depth 1
```

### 仅检出 Hasura V3 引擎代码

```
git clone --no-checkout https://github.com/hasura/graphql-engine.git --depth 1
cd graphql-engine
git sparse-checkout init --cone
git sparse-checkout set v3
git checkout @
```

这将检出顶层文件和仅包含 Hasura V3 引擎代码的 `v3` 文件夹。

## 支持与故障排查

要解决大多数问题，请查看我们的文档和社区资源。如果你遇到了 bug 或需要联系我们，请通过以下渠道之一与我们联系：

- Hasura DDN 文档：[DDN 文档](https://hasura.io/docs/3.0/)
- Hasura V2 文档：[V2 文档](https://hasura.io/docs/)
- 支持与反馈：[Discord](https://discord.gg/hasura)
- 问题与 bug 跟踪：[GitHub issues](https://github.com/hasura/graphql-engine/issues)
- 关注产品更新：[@HasuraHQ](https://twitter.com/hasurahq)
- 通过我们的 [网站聊天](https://hasura.io) 与我们交谈

## 行为准则

我们致力于在社区中营造开放和欢迎的环境。请参阅 [行为准则](code-of-conduct.md)。

## 安全

如需报告安全问题，请 [阅读此处](SECURITY.md)。

## 保持更新

加入我们的社区以获取最新公告、活动、产品更新和技术博客：
[https://hasura.io/community/](https://hasura.io/community/)

## 贡献

更多详细信息，请参阅我们的 [贡献指南](CONTRIBUTING.md)。

## 品牌资源

Hasura 品牌资源（标志、Hasura 吉祥物、Powered by 徽章等）可在 [v2/assets/brand](assets/brand) 文件夹中找到。欢迎在你的应用/网站中使用它们。如果你在使用 Hasura 构建的应用中添加 "Powered by Hasura" 徽章，我们会非常高兴。❤️

## 许可证

### V3

所有 [数据连接器](https://github.com/hasura/ndc-hub) 均采用 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) 发布。

核心 [V3 GraphQL 引擎](v3/) 也采用 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)（Apache-2.0）发布。

### V2

V2 核心 GraphQL 引擎采用 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)（Apache-2.0）发布。

`v2` 文件夹中的所有 **其他内容**（`server`、`cli` 和 `console` 目录中的内容除外）均采用 [MIT License](LICENSE-community) 发布。这包括 `docs` 和 `community` 目录中的所有内容。