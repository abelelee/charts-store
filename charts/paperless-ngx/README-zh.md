---
[![ci](https://github.com/paperless-ngx/paperless-ngx/workflows/ci/badge.svg)](https://github.com/paperless-ngx/paperless-ngx/actions)
[![Crowdin](https://badges.crowdin.net/paperless-ngx/localized.svg)](https://crowdin.com/project/paperless-ngx)
[![文档状态](https://img.shields.io/github/deployments/paperless-ngx/paperless-ngx/github-pages?label=docs)](https://docs.paperless-ngx.com)
[![codecov](https://codecov.io/gh/paperless-ngx/paperless-ngx/branch/main/graph/badge.svg?token=VK6OUPJ3TY)](https://codecov.io/gh/paperless-ngx/paperless-ngx)
[![在 Matrix 上聊天](https://matrix.to/img/matrix-badge.svg)](https://matrix.to/#/%23paperlessngx%3Amatrix.org)
[![演示](https://cronitor.io/badges/ve7ItY/production/W5E_B9jkelG9ZbDiNHUPQEVH3MY.svg)](https://demo.paperless-ngx.com)

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/paperless-ngx/paperless-ngx/blob/main/resources/logo/web/png/White%20logo%20-%20no%20background.png" width="50%">
    <source media="(prefers-color-scheme: light)" srcset="https://github.com/paperless-ngx/paperless-ngx/raw/main/resources/logo/web/png/Black%20logo%20-%20no%20background.png" width="50%">
    <img src="https://github.com/paperless-ngx/paperless-ngx/raw/main/resources/logo/web/png/Black%20logo%20-%20no%20background.png" width="50%">
  </picture>
</p>

<!-- omit in toc -->

# Paperless-ngx

Paperless-ngx 是一个文档管理系统，它可以将你的纸质文档转换为可搜索的在线档案，从而让你减少纸质文档的使用。

Paperless-ngx 是原始 [Paperless](https://github.com/the-paperless-project/paperless) 和 [Paperless-ng](https://github.com/jonaswinkler/paperless-ng) 项目的官方继任者，旨在将项目推进和支持的责任分担给一个团队。[欢迎加入我们！](#community-support)

感谢 [DigitalOcean](https://m.do.co/c/8d70b916d462) 的慷慨支持，我们提供了一个演示站点 [demo.paperless-ngx.com](https://demo.paperless-ngx.com)，登录用户名和密码均为 `demo`。_注意：演示内容会定期重置，请勿上传机密信息。_

- [功能](#功能)
- [入门指南](#入门指南)
- [贡献指南](#贡献指南)
  - [社区支持](#社区支持)
  - [翻译](#翻译)
  - [功能请求](#功能请求)
  - [缺陷报告](#缺陷报告)
- [相关项目](#相关项目)
- [重要提示](#重要提示)

<p align="right">本项目得到了以下支持：<br/>
  <a href="https://m.do.co/c/8d70b916d462" style="padding-top: 4px; display: block;">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://opensource.nyc3.cdn.digitaloceanspaces.com/attribution/assets/SVG/DO_Logo_horizontal_white.svg" width="140px">
      <source media="(prefers-color-scheme: light)" srcset="https://opensource.nyc3.cdn.digitaloceanspaces.com/attribution/assets/SVG/DO_Logo_horizontal_blue.svg" width="140px">
      <img src="https://opensource.nyc3.cdn.digitaloceanspaces.com/attribution/assets/SVG/DO_Logo_horizontal_black_.svg" width="140px">
    </picture>
  </a>
</p>

# 功能

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/paperless-ngx/paperless-ngx/main/docs/assets/screenshots/documents-smallcards-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/paperless-ngx/paperless-ngx/main/docs/assets/screenshots/documents-smallcards.png">
  <img src="https://raw.githubusercontent.com/paperless-ngx/paperless-ngx/main/docs/assets/screenshots/documents-smallcards.png">
</picture>

完整的 [功能列表](https://docs.paperless-ngx.com/#features) 和 [截图](https://docs.paperless-ngx.com/#screenshots) 可在 [文档](https://docs.paperless-ngx.com/) 中查看。

# 入门指南

部署 Paperless 最简单的方式是使用 `docker compose`。位于 [`/docker/compose` 目录](https://github.com/paperless-ngx/paperless-ngx/tree/main/docker/compose) 的文件已配置为从 GitHub 容器注册表拉取镜像。

如果你希望立即开始，可以使用我们的安装脚本来配置 `docker compose` 环境：

```bash
bash -c "$(curl -L https://raw.githubusercontent.com/paperless-ngx/paperless-ngx/main/install-paperless-ngx.sh)"
```

更多细节和替代安装方法的分步指南可在 [文档](https://docs.paperless-ngx.com/setup/#installation) 中找到。

从 Paperless-ng 迁移非常简单，只需使用新的 Docker 镜像即可！更多详细信息请参阅 [迁移文档](https://docs.paperless-ngx.com/setup/#migrating-to-paperless-ngx)。

<!-- omit in toc -->

### 文档

Paperless-ngx 的文档请访问 [https://docs.paperless-ngx.com](https://docs.paperless-ngx.com/)。

# 贡献指南

如果你有兴趣为本项目做贡献，请尽管参与！我们始终欢迎缺陷修复、功能增强、视觉优化等贡献。如果你打算实现较大的功能：请先发起讨论！[文档](https://docs.paperless-ngx.com/development/) 中提供了一些关于如何开始的基本信息。

## 社区支持

欢迎有兴趣继续开发 Paperless-ngx 的人员通过 GitHub 和 [Matrix 聊天室](https://matrix.to/#/#paperless:matrix.org) 与我们联系。如果你希望持续为项目做贡献，我们有多个 [团队](https://github.com/orgs/paperless-ngx/people)（前端、CI/CD 等）需要你的帮助，请与我们联系！

## 翻译

Paperless-ngx 支持多种语言，翻译工作是在 Crowdin 上协调进行的。如果你想帮助将 Paperless-ngx 翻译成你的语言，请访问 https://crowdin.com/project/paperless-ngx，非常感谢！更多细节请参见 [CONTRIBUTING.md](https://github.com/paperless-ngx/paperless-ngx/blob/main/CONTRIBUTING.md#translating-paperless-ngx)。

## 功能请求

功能请求可以通过 [GitHub Discussions](https://github.com/paperless-ngx/paperless-ngx/discussions/categories/feature-requests) 提交，你可以搜索已有的想法，添加你自己的想法，并为你关心的功能投票。

## 缺陷报告

如发现缺陷，请 [提交问题](https://github.com/paperless-ngx/paperless-ngx/issues)，如有疑问也可以 [发起讨论](https://github.com/paperless-ngx/paperless-ngx/discussions)。

# 相关项目

相关项目和与 Paperless-ngx 兼容的软件列表，请参见 [wiki 页面](https://github.com/paperless-ngx/paperless-ngx/wiki/Related-Projects)。

# 重要提示

> 文档扫描仪通常用于扫描敏感文档，例如你的社会保险号、税务记录、发票等。**Paperless-ngx 不应运行在不受信任的主机上**，因为信息是以明文形式存储且未加密的。我们不对安全性提供任何保证（但我们确实在努力），使用本应用需自担风险。
> **运行 Paperless-ngx 最安全的方式是在你家中的本地服务器上，并确保有备份机制**。