以下是你要求翻译的 Markdown 内容的中文版本，保留了原始格式和结构：

---

<div align="center">
  <img src="frontend/app/public/logo/logo.png" width="128" height="128">

  # Endurain

  <a title="Crowdin" target="_blank" href="https://crowdin.com/project/endurain"><img src="https://badges.crowdin.net/endurain/localized.svg"></a>
  ![License](https://img.shields.io/github/license/joaovitoriasilva/endurain)
  [![GitHub release](https://img.shields.io/github/v/release/joaovitoriasilva/endurain)](https://github.com/joaovitoriasilva/endurain/releases)
  [![GitHub stars](https://img.shields.io/github/stars/joaovitoriasilva/endurain.svg?style=social&label=Star)](https://github.com/joaovitoriasilva/endurain/stargazers)

  **一个自托管的健身追踪服务**  
  访问 Endurain 的 [Mastodon 主页](https://fosstodon.org/@endurain) 和 [Discord 服务器](https://discord.gg/6VUjUq2uZR)。

  <img src="screenshot_01.png" alt="Endurain 截图">
</div>

## 目录

- [Endurain 文档](https://docs.endurain.com)
- 什么是 Endurain？
- [Endurain 截图](https://docs.endurain.com/gallery/)
- 赞助者
- 贡献指南
- 协助翻译
- 许可证

## 什么是 Endurain？

Endurain 是一个自托管的健身追踪服务，旨在让用户完全掌控自己的数据和托管环境。它类似于 Strava，但更注重隐私和可定制性。使用以下技术构建：

- **前端：** Vue.js、Notivue 和 Bootstrap CSS
- **后端：** Python FastAPI、Alembic、SQLAlchemy、stravalib 和 python-garminconnect（用于集成 Strava 和 Garmin Connect）、gpxpy、tcxreader 和 fitdecode（分别用于导入 .gpx、.tcx 和 .fit 文件）
- **数据库：** MariaDB 或 PostgreSQL，用于高效的数据管理
- **可观测性：** Jaeger 用于基础的追踪和监控
- **集成支持：** 支持 Strava 和 Garmin Connect。也支持通过 .gpx、.tcx 和 .fit 文件手动上传活动

要部署 Endurain，可以使用提供的 Docker 镜像，在 "docker-compose.yml.example" 文件中可以找到完整的示例。配置通过环境变量进行，确保灵活性和易于定制。

更多信息请参阅 Endurain 的 [文档](https://docs.endurain.com)。

## 赞助者

非常感谢项目赞助者！你们的支持让这个项目得以持续进行。

欢迎通过 [GitHub 赞助 Endurain](https://github.com/sponsors/joaovitoriasilva) 来帮助项目持续开发。

## 贡献指南

我们欢迎任何形式的贡献！在提交 PR 之前，请先创建一个 issue 来讨论任何更改或改进。更多详情请查看 贡献指南。

## 协助翻译

Endurain 支持多语言，你可以通过 [Crowdin](https://crowdin.com/project/endurain) 帮助将其翻译成更多语言。

## 许可证

本项目采用 AGPL-3.0 许可证 —— 详见 LICENSE 文件。