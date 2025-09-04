<p align="center">
  <img width="auto" src="https://cms.count.ly/uploads/countly_github_56791635fe.png?updated_at=2023-04-05T09:56:43.491Z"/>
</p>

![CI](https://github.com/countly/countly-server/actions/workflows/main.yml/badge.svg)
![CodeQL Analysis](https://github.com/countly/countly-server/actions/workflows/codeql-analysis.yml/badge.svg)

## 🔗 快速链接

* [Countly 官方网站](https://countly.com)
* [Countly 服务器安装指南](https://support.count.ly/hc/en-us/articles/360036862332-Installing-the-Countly-Server)
* [Countly SDK 下载与文档链接](https://support.count.ly/hc/en-us/articles/360037236571-Downloading-and-Installing-SDKs)
* [Countly 社区 Discord 频道](https://discord.gg/countly)
* [Countly 功能用户指南](https://support.count.ly/hc/en-us/sections/7039354168729-User-Guides-Countly-22-x)

## 🌟 Countly 是什么？

Countly 是一个产品分析平台，帮助团队追踪、分析并响应其移动应用、网页应用和桌面应用中的用户行为。

Countly 全球范围内通过 2,000 多台服务器为超过 16,000 个应用提供服务，追踪 15 亿个唯一用户身份。它每天在云端和本地安全地处理数十亿条数据，使各种规模的团队都能构建更优质的应用程序，打造更具吸引力的用户体验，同时完全掌控其产品分析数据流。

## 🚀 Countly 有哪些版本？

* **Countly Lite** — 基础插件/功能，免费、开源、非商业用途。仅支持自托管。适用于个人和小型组织。
* **Countly Enterprise** — 提供更广泛的插件/功能、更细粒度的数据、SLA 服务和直接支持。支持自托管或由 Countly 托管/管理。适用于中型和大型组织。
* **Countly Flex** — 我们的 SaaS 平台，将部分企业功能作为核心功能提供，其他功能作为附加模块。每位用户都可以在自己选择的区域中获得专属且完全托管的 Countly 服务器。适用于个人、小型和中型组织。

如需详细了解不同版本之间的差异，请[点击此处](https://countly.com/pricing)。如需试用 Countly Flex，请访问[此页面](https://countly.com/flex)。

请注意，所有版本使用的 SDK 是相同的。

## 📦 此仓库包含什么？

此仓库包含 Countly 的服务器端部分，支持以下功能：

* 会话、页面浏览和事件的收集与报告
* 支持 iOS、Android、React Native、Flutter、NodeJS、Unity、Java 和 JavaScript 的崩溃/错误报告
* 针对 iOS 和 Android 的丰富交互式推送通知
* 远程配置，可动态调整应用的逻辑、外观和行为
* 可自定义的小部件应用内评分
* 内置报告和可定制的仪表板
* 邮件报告与警报
* 钩子功能，可通过电子邮件或 Webhook 将数据发送到外部系统
* 数据管理器，用于规划和管理事件及事件细分
* 合规中心，用于管理用户同意和数据主体请求
* 用户、应用和权限管理
* 读写 API
* 插件化架构，便于定制

![content](https://count.ly/github/countly-highlights.png?v3)

## 📈 Countly 可以追踪什么？

Countly 可以从移动应用、网页应用和桌面应用中收集和可视化数据。通过写入 API，你可以从任何来源向 Countly 发送数据。更多信息请参考以下资源：

* [Countly SDK 列表、文档和下载信息](https://support.count.ly/hc/en-us/articles/360037236571-Downloading-and-Installing-SDKs)
* [构建你自己的 SDK 开发指南](https://support.count.ly/hc/en-us/articles/360037753291-SDK-development-guide)
* [Countly 服务器写入 API 文档](https://api.count.ly/reference/i)

## 🛠️ 安装和升级 Countly 服务器

Countly 安装脚本假设运行在一台全新的 Ubuntu/CentOS/RHEL Linux 系统上，且没有服务占用 80 或 443 端口（这些端口也应允许入站流量），并会自动安装 Countly 所需的所有库和软件。

有以下几种方式可以安装 Countly：

1. 以下命令将在你的 **Ubuntu** 或 **CentOS** 服务器上下载并安装 Countly：

   `wget -qO- https://c.ly/install | bash`

2. 对于喜欢使用 bash 的用户，我们在 countly-server 包中提供了一个漂亮的安装脚本 (`bin/countly.install.sh`)，它将安装运行 Countly Server 所需的一切。你需要从[这里](https://github.com/Countly/countly-server/releases) 获取该仓库的稳定版本。

3. Countly Lite 也支持 Docker — [请查看我们的官方 Docker 仓库](https://registry.hub.docker.com/r/countly/countly-server/) 和 [Docker 安装说明](https://support.count.ly/hc/en-us/articles/360036862332-Installing-the-Countly-Server)。

如需从旧版本升级 Countly，请参考[升级文档](https://support.count.ly/hc/en-us/articles/360037443652-Upgrading-the-Countly-Server)。

## 🧩 API、可扩展性与插件

Countly 提供了[清晰定义的 API](https://api.count.ly)，用于从后端读取和写入数据。Countly 的仪表板就是基于读取 API 构建的，因此你可以通过 API 获取仪表板上显示的任何信息。

Countly 使用插件架构实现可扩展性。如果你希望扩展或修改现有功能，或者添加全新的功能，可以修改现有插件或创建新的插件。如果你打算开始插件开发，我们建议你阅读[这篇文档](https://support.count.ly/hc/en-us/articles/360036862392-Introduction)。

## 💚 社区

我们有一个新的 Discord 社区（自 2023 年 4 月起）🎉 [欢迎加入我们](https://discord.gg/countly)，提出支持请求、分享功能想法、展示你正在开发的应用，也可以一起轻松交流 :)

## 🔒 安全性

我们非常重视安全性。如果你发现任何安全相关的问题，请通过发送邮件至 security@count.ly 来负责任地披露信息，**不要创建 GitHub issue**。

## 🏗️ 使用的技术栈

* **MongoDB** — 最受欢迎的 NoSQL 数据库之一
* **NodeJS** — 开源、跨平台的 JavaScript 运行环境
* **Linux** — 我们都热爱的操作系统 ;-)

以及大量[开源组件](https://support.count.ly/hc/en-us/articles/360037092232-Open-source-components)！

## 🤝 我能为你们做些什么？

1. Fork 此仓库
2. 创建你的功能分支 (`git checkout -b my-new-super-feature`)
3. 提交你的更改 (`git commit -am 'Add some cool feature'`)
4. 推送分支到远程 (`git push origin my-new-super-feature`)
5. 创建新的 Pull Request

我们也鼓励你阅读[如何为 Countly 做贡献](https://github.com/Countly/countly-server/blob/master/CONTRIBUTING.md)的完整说明。

## 👍 项目徽章

如果你喜欢 Countly，为什么不使用我们的徽章之一，并回链到我们网站呢？

<a href="https://countly.com/?utm_source=badge" rel="nofollow"><img style="width:145px;height:60px" src="https://count.ly/badges/dark.svg?v2" alt="Countly - Product Analytics" /></a>

    <a href="https://countly.com/?utm_source=badge" rel="nofollow"><img style="width:145px;height:60px" src="https://count.ly/badges/dark.svg" alt="Countly - Product Analytics" /></a>

<a href="https://countly.com/?utm_source=badge" rel="nofollow"><img style="width:145px;height:60px" src="https://count.ly/badges/light.svg?v2" alt="Countly - Product Analytics" /></a>

    <a href="https://countly.com/?utm_source=badge" rel="nofollow"><img style="width:145px;height:60px" src="https://count.ly/badges/light.svg" alt="Countly - Product Analytics" /></a>