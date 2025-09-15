---
<!-- 项目标题 -->
![Banner](https://homarr.dev/)

<!-- 标志 -->
<p align="center">
<img src="https://img.shields.io/github/stars/ajnart/homarr?label=%E2%AD%90%20Stars&style=flat-square?branch=master&kill_cache=1%22">
<a href="https://github.com/ajnart/homarr/releases/latest">
  <img alt="最新发布 (Semver)" src="https://img.shields.io/github/v/release/ajnart/homarr?label=%F0%9F%9A%80%20发布">
</a>
<a href="https://github.com/ajnart/homarr/actions/workflows/docker.yml">
  <img title="Docker CI 状态" src="https://github.com/ajnart/homarr/actions/workflows/docker.yml/badge.svg" alt="CI 状态">
</a>
<a href=https://translate.homarr.dev/>
<img title="翻译" src="https://badges.crowdin.net/homarr/localized.svg" />
</a>
<a href="https://discord.gg/aCsmEV5RgA">
  <img title="Discord" src="https://discordapp.com/api/guilds/972958686051962910/widget.png?style=shield">
</a>
</p>

<!-- 链接 -->
<p align="center">
  <a href="https://demo.homarr.dev/">
    <strong>演示 ✨</strong>
  </a>
  •
  <a href="https://homarr.dev/docs/getting-started/">
    <strong>安装 💻</strong>
  </a> •
  <a href="https://translate.homarr.dev/">
    <strong>翻译 🈺</strong>
  </a> •
  <a href="https://discord.com/invite/aCsmEV5RgA">
    <strong>Discord 👋</strong>
  </a>
</p>

使用 Homarr 简化您的服务器管理 —— 一个简洁现代的仪表板，将您所有的应用程序和服务集中在一个触手可及的位置。通过 Homarr，您可以在一个便捷的位置访问和控制所有内容。Homarr 与您添加的应用程序无缝集成，为您提供有价值的信息并实现完全控制。安装简便，且支持广泛的部署方式。

<br/>
<br/>

> [!IMPORTANT]  
> # Homarr 仓库已迁移至 [HomarrLabs](https://github.com/homarr-labs/homarr)
> # 请在该仓库提交与 1.0 相关的问题。此仓库将在 1.0 完全完善后归档。
> # 1.0 是一次完全重写，迁移时需要修改您的 compose 文件。请参考 [迁移指南](https://homarr.dev/blog/2025/01/19/migration-guide-1.0) 并阅读 [重大变更说明](https://homarr.dev/blog/2024/09/23/version-1.0#breaking-changes)

![功能部分](https://homarr.dev/)

- 🖌️ 高度可定制，具备强大的拖放网格系统
- ✨ 与您喜爱的自托管应用无缝集成
- 📌 简单快速的应用管理 - 无需 YAML
- 🙊 增强安全性的高级密钥管理系统
- 📄 详细的文档和活跃的社区
- 🔍 即时搜索网页或支持的集成内容
- 🏴󠁧󠁢󠁮󠁩󠁲󠁿 内置状态监控系统，实时监测您的应用
- 🦞 内置图标选择器，包含超过 7000 个图标
- 🐳 使用 Docker、unRAID 和 Synology 轻松部署
- 🚀 兼容各种主流硬件（x86、树莓派、旧笔记本等）

<br/>
<br/>

![小组件与集成部分](https://homarr.dev/docs/category/widgets)

Homarr 提供了[内置的小组件和集成](https://homarr.dev/docs/category/integrations)，它们连接您的应用程序，使您能够直接从仪表板控制它们。每个小组件和集成都配有详尽的文档。Homarr 可与以下应用程序集成：

📥 种子客户端
- [Deluge](https://homarr.dev/docs/integrations/torrent#deluge)
- [Transmission](https://homarr.dev/docs/integrations/torrent#transmission)
- [qBittorent](https://homarr.dev/docs/integrations/torrent#qbittorrent-integration)

📥 Usenet 客户端
- [SABnzbd](https://homarr.dev/docs/integrations/usenet#sabnzbd)
- [NZBGet](https://homarr.dev/docs/integrations/usenet#nzbget)

📺 媒体服务器
- [Plex](https://homarr.dev/docs/integrations/media-server/#plex)
- [Jellyfin](https://homarr.dev/docs/integrations/media-server#jellyfin-and-emby)

📚 媒体收藏管理器
- [Sonarr](https://homarr.dev/docs/integrations/servarr#sonarr)
- [Radarr](https://homarr.dev/docs/integrations/servarr#radarr)
- [Lidarr](https://homarr.dev/docs/integrations/servarr#lidarr)
- [Readarr](https://homarr.dev/docs/integrations/servarr#readarr)
 
🎞️ 媒体请求管理器
- [Overseerr](https://homarr.dev/docs/integrations/media-requester)
- [Jellyseerr](https://homarr.dev/docs/integrations/media-requester)

🚫 DNS 广告拦截器
- [Pihole](https://homarr.dev/docs/integrations/dns#pihole)
- [AdGuard Home](https://homarr.dev/docs/integrations/dns#adguard-home)

其他集成
- [🔌 Dash.](https://homarr.dev/docs/integrations/hardware)
- [🐳 Docker](https://homarr.dev/docs/integrations/containers)  

我们正在不断添加新的集成和小组件，以进一步提升您的使用体验。

<br/>
<br/>

![预览部分](https://demo.homarr.dev/)

https://user-images.githubusercontent.com/30572287/217098893-5880e7de-13d0-42c5-b505-f7921593396f.mp4

<br/>
<br/>

![安装部分](https://homarr.dev/docs/category/installation-1)

由于我们频繁更新 Homarr，建议您阅读我们的官方安装指南：

<a href="https://homarr.dev/docs/category/installation-1">
  <img src="docs/installation-button.png" width="200" />
</a>

<br/>
<br/>

![贡献部分](https://github.com/ajnart/homarr/blob/dev/CONTRIBUTING.md)
Homarr 由一群充满热情的开发者在空闲时间维护。
我们出于兴趣和学习目的参与这个项目。

因此，我们非常欢迎任何形式的帮助与支持。
虽然我们感激您的捐赠，但您也可以通过其他方式来支持我们。

<a href="https://ko-fi.com/ajnart">
  <img src="https://cdn.ko-fi.com/cdn/kofi3.png?v=3" width="200" />
</a>

您也可以通过帮助我们将整个项目[翻译成尽可能多的语言](https://homarr.dev/docs/community/translations)，或直接参与代码或文档的编写来支持我们。

**请阅读我们的 贡献指南**

无论大小和范围，所有贡献都受到热烈欢迎和高度赞赏！谢谢 ❤️

![Alt](https://repobeats.axiom.co/api/embed/60a6f68f193faf831f64221bdf90782adec51c93.svg "Repobeats 分析图片")
[![由 Argos 视觉测试覆盖](https://argos-ci.com/badge-large.svg)](https://argos-ci.com?utm_source=%5Bhomarr%5D&utm_campaign=oss)