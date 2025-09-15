---
![Feature Flag, Remote Config and A/B Testing platform, Flagsmith](https://www.flagsmith.com/)

[![Stars](https://img.shields.io/github/stars/flagsmith/flagsmith)](https://github.com/Flagsmith/flagsmith/stargazers)
[![Docker Pulls](https://img.shields.io/docker/pulls/flagsmith/flagsmith)](https://hub.docker.com/u/flagsmith)
[![Docker Image Size](https://img.shields.io/docker/image-size/flagsmith/flagsmith)](https://hub.docker.com/r/flagsmith/flagsmith)
[![Join the Discord chat](https://img.shields.io/discord/517647859495993347)](https://discord.gg/hFhxNtXzgm)
[![Coverage](https://codecov.io/gh/Flagsmith/flagsmith/branch/main/graph/badge.svg?token=IyGii7VSdc)](https://codecov.io/gh/Flagsmith/flagsmith)
[![License](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
<a href="https://depot.dev?utm_source=Flagsmith"><img src="https://depot.dev/badges/built-with-depot.svg" alt="Built with Depot" height="20"></a>

<p align="center">
  <a href="https://www.flagsmith.com/demo">
  <img width="75%" height="75%" src="static-files/ReadMe_Demo.gif" alt="Try our interactive demo">
</p>
<p align="center">
  <a href="https://www.flagsmith.com/demo">Try our interactive demo </a>
</p>

# [Flagsmith](https://flagsmith.com/) 是一个开源的功能标记工具，帮助您更快发布并控制版本

改变您的团队发布软件的方式。通过精细的控制进行功能上线、细分和优化。通过私有部署和私有云托管保障安全性。

* 功能标记：在功能标记的安全保护下发布功能
* 远程修改：轻松切换各个功能的开关，无需重新部署代码即可进行修改
* A/B测试：使用细分功能对新功能进行A/B测试和多变量测试
* 用户细分：向测试用户发布功能，收集反馈并迭代改进
* 组织管理：通过组织、项目和成员角色保持团队有序管理
* SDKs和框架：支持15+种流行语言，如Typescript、.NET、Java等，可与React、Next.js等框架集成
* 集成能力：与您喜爱的工具配合使用

Flagsmith 可轻松帮助您在Web、移动端和服务器端应用程序中创建和管理功能标记。只需将代码段用标记包裹，然后使用Flagsmith为不同环境、用户或用户细分切换功能的开关。

## 一分钟内启动并运行：

```bash
curl -o docker-compose.yml https://raw.githubusercontent.com/Flagsmith/flagsmith/main/docker-compose.yml
docker-compose -f docker-compose.yml up
```

系统将自动为您创建管理员用户、组织和项目。您可以在Compose日志中找到设置密码的链接：

```txt
Superuser "admin@example.com" created successfully.
Please go to the following page and choose a password: http://localhost:8000/password-reset/confirm/.../...
```

![Flagsmith Screenshot](static-files/screenshot.png)

## Flagsmith 开源

Flagsmith 仓库包含两个核心组件 - [REST API](https://github.com/Flagsmith/flagsmith/tree/main/api) 和 [前端仪表板](https://github.com/Flagsmith/flagsmith/tree/main/frontend)。

更多文档请参考：

* [API](https://docs.flagsmith.com/deployment/hosting/locally-api)
* [前端](https://docs.flagsmith.com/deployment/hosting/locally-frontend)

## Flagsmith 托管SaaS版本

您可以免费试用我们的托管版本：https://flagsmith.com

## 社区资源和贡献指南

* [访问我们的文档](https://docs.flagsmith.com/)
* [在Discord上与其他开发者交流](https://discord.com/invite/hFhxNtXzgm)
* 如果需要帮助启动，请[联系我们](https://www.flagsmith.com/contact-us)

我们非常欢迎社区的贡献，并一直在努力改进！以下是我们的[贡献指南](https://docs.flagsmith.com/platform/contributing)。

## 开源理念

我们平台的大部分代码都采用[BSD-3-Clause许可证](https://github.com/Flagsmith/flagsmith?tab=BSD-3-Clause-1-ov-file#readme)开源。少数仓库采用MIT许可证。

我们开发Flagsmith的初衷，是打造一个我们自己需要但在GitHub上找不到的开源功能标记工具。我们的核心功能将始终保持开源。阅读我们的[致开发者的公开信](https://www.flagsmith.com/about-us)。

## 开源 vs 付费版本

由于我们的核心功能是开源的，无论您使用什么环境都可以使用我们的开源功能标记和远程配置管理平台。企业级治理和管理功能需要有效的Flagsmith企业许可证。

如需了解更多，请[联系我们](https://www.flagsmith.com/contact-us)或查看我们的[版本对比](https://docs.flagsmith.com/version-comparison)。

## 贡献者

感谢开源社区的贡献，让我们共同构建了这个项目！

<a href="https://github.com/flagsmith/flagsmith/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=flagsmith/flagsmith" />
</a>

由 [contrib.rocks](https://contrib.rocks) 提供支持。