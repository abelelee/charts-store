# Radarr

[![构建状态](https://dev.azure.com/Radarr/Radarr/_apis/build/status/Radarr.Radarr?branchName=develop)](https://dev.azure.com/Radarr/Radarr/_build/latest?definitionId=1&branchName=develop)
[![翻译状态](https://translate.servarr.com/widget/servarr/radarr/svg-badge.svg)](https://translate.servarr.com/engage/servarr/?utm_source=widget)
[![Docker 下载量](https://img.shields.io/docker/pulls/linuxserver/radarr.svg)](https://wiki.servarr.com/radarr/installation/docker)
![GitHub 下载量](https://img.shields.io/github/downloads/Radarr/Radarr/total.svg)
[![Open Collective 支持者](https://opencollective.com/Radarr/backers/badge.svg)](#backers)
[![Open Collective 赞助商](https://opencollective.com/Radarr/sponsors/badge.svg)](#sponsors)
[![Open Collective 超级赞助商](https://opencollective.com/Radarr/megasponsors/badge.svg)](#mega-sponsors)

Radarr 是一个面向 Usenet 和 BitTorrent 用户的电影收藏管理工具。它可以监控多个 RSS 源以获取新电影，并与客户端和索引器交互来抓取、整理和重命名文件。当更好的格式质量可用时，Radarr 还可以配置为自动升级库中现有文件的质量。

请注意，Radarr 仅支持每部电影的一个版本。如果您希望同时拥有某部电影的 4K 版本和 1080p 版本，则需要运行多个实例。

## 主要功能包括

* 添加新电影时可获取大量信息，例如预告片、评分等。
* 支持主流平台：Windows、Linux、macOS、Raspberry Pi 等。
* 可以监控您已拥有的电影是否有更高质量版本，并自动升级。_例如，从 DVD 升级到蓝光_
* 自动失败下载处理，如果一次下载失败会尝试另一个发布版本。
* 手动搜索功能，您可以手动选择任意发布版本，或查看为何某个版本未被自动下载。
* 完全集成 SABnzbd 和 NZBGet。
* 自动搜索发布版本以及 RSS 同步。
* 自动导入已下载的电影。
* 识别特别版、导演剪辑版等。
* 识别带有硬编码字幕的发布版本。
* 识别使用别名发布的电影。
* 支持并集成 SABnzbd、NZBGet、QBittorrent、Deluge、rTorrent、Transmission、uTorrent 以及其他下载客户端。
* 完全集成 Kodi 和 Plex（通知、媒体库更新）。
* 导入元数据，例如预告片或字幕。
* 添加海报和信息等元数据供 Kodi 等使用。
* 高级配置文件自定义功能，确保 Radarr 始终下载您想要的版本。
* 精美的用户界面。

## 支持

[![Wiki](https://img.shields.io/badge/servarr-wiki-181717.svg?maxAge=60)](https://wiki.servarr.com/radarr)
[![Discord](https://img.shields.io/badge/discord-chat-7289DA.svg?maxAge=60)](https://radarr.video/discord)

注意：GitHub Issues 仅用于报告 Bug 和提出功能请求。

[![GitHub - 仅限 Bug 和功能请求](https://img.shields.io/badge/github-issues-red.svg?maxAge=60)](https://github.com/Radarr/Radarr/issues)

## 贡献者与开发者

[API 文档](https://radarr.video/docs/api/)

本项目感谢所有贡献者的支持。
- [参与贡献 (GitHub)](CONTRIBUTING.md)
- [贡献指南 (Wiki 文章)](https://wiki.servarr.com/radarr/contributing)

[![贡献者列表](https://opencollective.com/Radarr/contributors.svg?width=890&button=false)](https://github.com/Radarr/Radarr/graphs/contributors)

## 支持者

感谢所有支持者！🙏 [成为支持者](https://opencollective.com/Radarr#backer)

[![支持者列表](https://opencollective.com/Radarr/backers.svg?width=890)](https://opencollective.com/Radarr#backer)

## 赞助商

通过成为赞助商来支持本项目。您的标志将显示在此处并附带指向您网站的链接。[成为赞助商](https://opencollective.com/Radarr#sponsor)

[![赞助商列表](https://opencollective.com/Radarr/sponsors.svg?width=890)](https://opencollective.com/Radarr#sponsor)

## 超级赞助商

[![超级赞助商列表](https://opencollective.com/Radarr/tiers/mega-sponsor.svg?width=890)](https://opencollective.com/Radarr#mega-sponsor)

## JetBrains

感谢 [<img src="https://resources.jetbrains.com/storage/products/company/brand/logos/jetbrains.png" alt="JetBrains" width="96">](http://www.jetbrains.com/) 为我们提供其优秀工具的免费授权。

* [<img src="https://resources.jetbrains.com/storage/products/company/brand/logos/ReSharper_icon.png" alt="ReSharper" width="32"> ReSharper](http://www.jetbrains.com/resharper/)
* [<img src="https://resources.jetbrains.com/storage/products/company/brand/logos/WebStorm_icon.png" alt="WebStorm" width="32"> WebStorm](http://www.jetbrains.com/webstorm/)
* [<img src="https://resources.jetbrains.com/storage/products/company/brand/logos/Rider_icon.png" alt="Rider" width="32"> Rider](http://www.jetbrains.com/rider/)
* [<img src="https://resources.jetbrains.com/storage/products/company/brand/logos/dotTrace_icon.png" alt="dotTrace" width="32"> dotTrace](http://www.jetbrains.com/dottrace/)

## DigitalOcean

本项目也得到了 DigitalOcean 的支持
<p>
  <a href="https://www.digitalocean.com/">
    <img src="https://opensource.nyc3.cdn.digitaloceanspaces.com/attribution/assets/SVG/DO_Logo_horizontal_blue.svg" width="201px">
  </a>
</p>

### 许可证

* [GNU GPL v3](http://www.gnu.org/licenses/gpl.html)
* 版权所有 © 2010-2025