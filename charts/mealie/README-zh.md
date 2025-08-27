[![最新版本][latest-release-shield]][latest-release-url]
[![贡献者][contributors-shield]][contributors-url]
[![关注数][stars-shield]][stars-url]
[![问题][issues-shield]][issues-url]
[![AGPL 许可证][license-shield]][license-url]
[![Docker 下载量][docker-pull]][docker-url]
[![GHCR 下载量][ghcr-pulls]][ghcr-url]

<!-- 项目LOGO -->
<br />
<p align="center">
  <a href="https://github.com/mealie-recipes/mealie">
<svg style="width:100px;height:100px" viewBox="0 0 24 24">
    <path fill="currentColor" d="M8.1,13.34L3.91,9.16C2.35,7.59 2.35,5.06 3.91,3.5L10.93,10.5L8.1,13.34M13.41,13L20.29,19.88L18.88,21.29L12,14.41L5.12,21.29L3.71,19.88L13.36,10.22L13.16,10C12.38,9.23 12.38,7.97 13.16,7.19L17.5,2.82L18.43,3.74L15.19,7L16.15,7.94L19.39,4.69L20.31,5.61L17.06,8.85L18,9.81L21.26,6.56L22.18,7.5L17.81,11.84C17.03,12.62 15.77,12.62 15,11.84L14.78,11.64L13.41,13Z" />
</svg>
  </a>

  <h3 align="center">Mealie</h3>

  <p align="center">
    所有食谱的集中地
    <br />
    <a href="https://docs.mealie.io/"><strong>探索文档 »</strong></a>
  <a href="https://github.com/mealie-recipes/mealie">
  </a>
    <br />
    <a href="https://demo.mealie.io/">查看演示</a>
    ·
    <a href="https://github.com/mealie-recipes/mealie/issues">报告问题</a>
    ·
    <a href="https://github.com/mealie-recipes/mealie/pkgs/container/mealie">GitHub 容器仓库</a>
</p>

[![产品名称截图][product-screenshot]](https://docs.mealie.io)

# 关于本项目

Mealie 是一个自托管的食谱管理器、膳食计划工具和购物清单工具，后端采用 REST API，前端使用 Vue 构建，具有响应式设计，为全家人提供愉悦的用户体验。您只需提供 URL，Mealie 就能自动导入相关数据，轻松地将食谱添加到数据库中，也可以通过 UI 编辑器添加家庭食谱。此外，Mealie 还提供了 API，供第三方应用程序进行交互。

- [记得加入 Discord 群组](https://discord.gg/QuStdQGSGK)!
- [文档](https://docs.mealie.io/)

## 主要特性
- 食谱导入：通过**导入 URL** 或手动输入数据创建食谱
- 膳食计划：使用 **膳食计划** 功能规划接下来一周的饮食安排
- 购物清单：将所需食材添加到**购物清单**，并按本地超市的区域分类整理
- 食谱集：根据您自定义的标准将食谱分组到不同的 **食谱集**
- Docker：支持便捷的 **Docker** 部署
- 多语言支持：提供 **35+ 种语言** 的翻译

<!-- 贡献 -->
## 贡献

开源社区之所以成为一个学习、启发和创造的精彩地方，正是因为有像您这样的贡献者。我们非常感谢您的任何贡献。如果您打算参与代码开发，请务必查阅夜间构建文档，以获取最新的信息。

- 参考 [贡献者指南](https://nightly.mealie.io/contributors/developers-guide/code-contributions/) 获取入门帮助。
- 我们使用 [VSCode Dev Containers](https://code.visualstudio.com/docs/remote/containers) 来帮助贡献者快速上手！

如果您不是开发者，也可以通过财务支持来贡献本项目。资金支持可以帮助我优先投入更多时间到本项目，并让我知道社区对该项目有真实的需求。

<a href="https://www.buymeacoffee.com/haykot" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-green.png" alt="Buy Me A Coffee" style="height: 30px !important;width: 107px !important;" ></a>

### 翻译

对于**非开发者**来说，参与翻译是贡献项目的一种绝佳方式。我们使用 [Crowdin](https://crowdin.com/project/mealie) 平台，允许多位贡献者共同参与 Mealie 的翻译工作。您可以简单地通过为喜欢的翻译投票，甚至可以完整地将 Mealie 翻译成一种新语言。

更多信息请查看 [贡献者指南中的翻译页面](https://nightly.mealie.io/contributors/translating/)。

<!-- 许可证 -->
## 许可证
本项目采用 AGPL 许可证发布。详情请参阅 `LICENSE` 文件。

## 赞助商

衷心感谢所有通过 [Github Sponsors](https://github.com/sponsors/hay-kot) 和 Buy Me a Coffee 赞助本项目的赞助者。没有你们的支持，这个项目将无法实现。

感谢 Depot 为我们提供 Docker 镜像构建实例。

[![使用 Depot 构建](https://depot.dev/badges/built-with-depot.svg)](https://depot.dev?utm_source=Mealie)

<!-- Markdown 链接与图片 -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/mealie-recipes/mealie.svg?style=flat-square
[docker-pull]: https://img.shields.io/docker/pulls/hkotel/mealie?style=flat-square
[docker-url]: https://hub.docker.com/r/hkotel/mealie
[ghcr-pulls]: https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fipitio.github.io%2Fbackage%2Fmealie-recipes%2Fmealie%2Fmealie.json&query=%24.downloads&style=flat-square&label=ghcr%20pulls
[ghcr-url]: https://github.com/mealie-recipes/mealie/pkgs/container/mealie
[contributors-url]: https://github.com/mealie-recipes/mealie/graphs/contributors
[stars-shield]: https://img.shields.io/github/stars/mealie-recipes/mealie.svg?style=flat-square
[stars-url]: https://github.com/mealie-recipes/mealie/stargazers
[issues-shield]: https://img.shields.io/github/issues/mealie-recipes/mealie.svg?style=flat-square
[issues-url]: https://github.com/mealie-recipes/mealie/issues
[latest-release-shield]: https://img.shields.io/github/v/release/mealie-recipes/mealie?style=flat-square&label=latest%20release
[latest-release-url]: https://github.com/mealie-recipes/mealie/releases
[license-shield]: https://img.shields.io/github/license/mealie-recipes/mealie.svg?style=flat-square
[license-url]: https://github.com/mealie-recipes/mealie/blob/mealie-next/LICENSE
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/hay-kot
[product-screenshot]: docs/docs/assets/img/home_screenshot.png