---
<p align="center">
  <a href="https://cube.dev?ref=github-readme"><img src="https://raw.githubusercontent.com/cube-js/cube/master/docs/content/cube-logo-with-bg.png" alt="Cube — 数据应用的语义层" width="300px"></a>
</p>
<br/>

[官网](https://cube.dev?ref=github-readme) • [快速开始](https://cube.dev/docs/getting-started?ref=github-readme) • [文档](https://cube.dev/docs?ref=github-readme) • [示例](https://cube.dev/docs/examples?ref=github-readme) • [博客](https://cube.dev/blog?ref=github-readme) • [Slack](https://slack.cube.dev?ref=github-readme) • [X](https://twitter.com/the_cube_dev)

[![npm 版本](https://badge.fury.io/js/%40cubejs-backend%2Fserver.svg)](https://badge.fury.io/js/%40cubejs-backend%2Fserver)
[![GitHub Actions](https://github.com/cube-js/cube/workflows/Build/badge.svg)](https://github.com/cube-js/cube/actions?query=workflow%3ABuild+branch%3Amaster)
[![FOSSA 状态](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fcube-js%2Fcube.js.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fcube-js%2Fcube.js?ref=badge_shield)

__Cube 是现代数据应用的通用语义层。__ 它诞生于云时代，代表了 OLAP 技术的下一次演进，帮助数据工程师和应用开发者从现代数据存储中访问数据，将其组织为一致的定义，并交付给每一个应用。

<img
  src="https://ucarecdn.com/8d945f29-e9eb-4e7f-9e9e-29ae7074e195/"
  style="border: none"
  width="100%"
/>

<p align="center">
  <i>了解更多关于将 Cube 连接到 <a href="https://cube.dev/docs/config/databases?ref=github-readme" target="_blank">数据源</a> 和 <a href="https://cube.dev/docs/config/downstream?ref=github-readme" target="_blank">分析与可视化工具</a> 的信息。</i>
</p>

Cube 被设计为支持所有支持 SQL 的数据源，包括 Snowflake 或 Google BigQuery 等云数据仓库、Presto 或 Amazon Athena 等查询引擎，以及 Postgres 等应用数据库。Cube 内置了一个关系型缓存引擎，为 API 请求提供亚秒级延迟和高并发能力。

如需更多细节，请参阅我们的文档中的 [介绍](https://cube.dev/docs/cubejs-introduction?ref=github-readme) 页面。

## 为什么选择 Cube？

随着数据基础设施从传统关系型数据库演进到云数据平台，曾经存在于 SQL Server Analysis Services 和 Oracle Essbase 等专用服务器中的 OLAP 功能逐渐被遗弃。如今的组织面临以下几个挑战：

1. __分析建模与多维性。__ 现代云数据平台在处理大量数据方面表现出色，但缺乏对多维分析和建模的原生支持。Cube 将 OLAP 风格的分析引入这些平台，实现一致的指标定义和多维分析。

2. __性能优化。__ 尽管云数据仓库通过列式存储和分布式处理提升了查询性能，但在复杂的分析工作负载下仍然表现不佳。Cube 提供智能缓存和预聚合策略，显著提升查询响应速度。

3. __访问控制与治理。__ 在所有消费类应用中保障数据访问的安全性和治理仍然是关键。Cube 提供强大的访问控制，确保整个数据生态系统中的安全性一致。

4. __API 灵活性。__ 传统 OLAP 工具在数据暴露方式上存在局限。Cube 提供现代的 REST、GraphQL 和 SQL API，同时支持传统的 MDX 和 DAX 接口，使其成为真正通用的语义层。

Cube 是云数据平台时代缺失的 OLAP 引擎，它提供了必要的基础设施和功能，能够在不重复分析建模、数据或安全权限的情况下，实现高效的数据建模、访问控制和性能优化。

![](https://raw.githubusercontent.com/cube-js/cube.js/master/docs/content/old-was-vs-cubejs-way.png)

## 快速开始 🚀

### Cube Cloud

[Cube Cloud](https://cube.dev/cloud?ref=github-readme) 是使用 Cube 的最快方式。它提供托管基础设施，以及对开发项目和概念验证的即时免费访问。

<a href="https://cubecloud.dev/auth/signup?ref=github-readme"><img src="https://cubedev-blog-images.s3.us-east-2.amazonaws.com/f1f1eac0-0b44-4c47-936e-33b5c06eedf0.png" alt="立即开始" width="200px"></a>

关于 Cube Cloud 的逐步指南，[请参阅文档](https://cube.dev/docs/getting-started/cloud/overview?ref=github-readme)。

### Docker

或者，您可以使用 [Docker](https://www.docker.com/) 在本地启动 Cube 或自行托管。

安装 Docker 后，在新建的项目文件夹中运行以下命令：

```bash
docker run -p 4000:4000 \
  -p 15432:15432 \
  -v ${PWD}:/cube/conf \
  -e CUBEJS_DEV_MODE=true \
  cubejs/cube
```

然后，在浏览器中打开 http://localhost:4000 继续设置。

关于 Docker 的逐步指南，[请参阅文档](https://cube.dev/docs/getting-started-docker?ref=github-readme)。

## 资源

- [文档](https://cube.dev/docs?ref=github-readme)
- [快速开始](https://cube.dev/docs/getting-started?ref=github-readme)
- [示例与教程](https://cube.dev/docs/examples?ref=github-readme)
- [架构](https://cube.dev/docs/product/introduction#four-layers-of-semantic-layer)

## 贡献

您可以以多种方式为 Cube 做出贡献！以下是一些可能的方式：

* 为本仓库加星标，并在 [X](https://twitter.com/the_cube_dev) 上关注我们。
* 在 [Stackshare](https://stackshare.io/cube-js) 上将 Cube 添加到您的技术栈中。
* 为问题添加 👍 表情，让我们知道哪些问题有需求，以便在路线图中优先处理。
* 每当您觉得某些功能缺失或存在问题时，请创建问题。
* 如果其他人也可能遇到这些问题，请在 [Stack Overflow 的 cube.js 标签下](https://stackoverflow.com/questions/tagged/cube.js) 提问。
* 对所有开放问题提供 Pull Request，尤其是那些标记为 [help wanted](https://github.com/cube-js/cube/issues?q=is%3Aissue+is%3Aopen+label%3A"help+wanted") 和 [good first issue](https://github.com/cube-js/cube/issues?q=is%3Aissue+is%3Aopen+label%3A"good+first+issue") 的问题。

所有类型的贡献都**受到欢迎并极其有帮助** 🙌 有关更多信息，请参阅 [贡献指南](https://github.com/cube-js/cube/blob/master/CONTRIBUTING.md)。

## 许可证

Cube 客户端采用 MIT 许可证。

Cube 后端采用 Apache 2.0 许可证。


[![FOSSA 状态](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fcube-js%2Fcube.js.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fcube-js%2Fcube.js?ref=badge_large)