<p align="right"><a href="#gitpod"><img alt="在 Gitpod 中打开" src="https://gitpod.io/button/open-in-gitpod.svg"></a></p>

# Collabora Online
<!--
[![Master: Pull request policy](https://img.shields.io/badge/Master-PRs%20can%20be%20merge%20without%20approval-42BC00?logoColor=42BC00&logo=git "Main release is still distant. Thanks for your support and contributions! :)")](https://github.com/CollaboraOnline/online/blob/master/CONTRIBUTING.md#contributing-to-source-code)
-->
[![Master: Pull request policy](https://img.shields.io/badge/Master-受保护的%2C%20PRs%20需要审核-red?logoColor=lightred&logo=git "Collabora 团队正在准备下一次发布，因此 'master' 分支目前受保护，PR 需要 1 次审核后才能合并。感谢您的支持和贡献！:)")](https://github.com/CollaboraOnline/online/blob/master/CONTRIBUTING.md#contributing-to-source-code)


[![Matrix](https://img.shields.io/badge/Matrix-%23cool--dev-turquoise.svg)](https://matrix.to/#/#cool-dev:matrix.org)
[![Telegram](https://img.shields.io/badge/Telegram-Collabora%20Online-green.svg)](https://t.me/CollaboraOnline)
[![Forum](https://img.shields.io/badge/Forum-Discourse-blue.svg)](https://forum.collaboraonline.com/)
[![Website](https://img.shields.io/badge/Website-collaboraonline.github.io-blueviolet.svg)](https://collaboraonline.github.io/)
[![L10n](https://img.shields.io/badge/L10n-Weblate-lightgrey.svg)](https://hosted.weblate.org/projects/collabora-online/)
[![Gitpod Ready-to-Code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/CollaboraOnline/online)


**安全的文档协作。由您掌控。**

![](https://www.collaboraonline.com/wp-content/uploads/2024/02/Website_COOL_2305_Home-1024x366.png)

## 了解更多 💡
* [Collabora Online 开发版 (CODE)](https://www.collaboraonline.com/code/)
* [Collabora Online](https://www.collaboraonline.com/collabora-online/)
* [Collabora Office](https://www.collaboraonline.com/collabora-office/)
* [适用于 iOS 和 Android 的 Collabora Office](https://www.collaboraonline.com/collabora-office-android-ios/)
* 有关更多细节、构建说明、下载等内容，请访问 [collaboraonline.github.io](https://collaboraonline.github.io/)。您还可以查看 [SDK 文档](https://sdk.collaboraonline.com/)。

## 主要功能
* 查看和编辑文本文档、电子表格、演示文稿等
* 协同编辑功能
* 在任何现代浏览器中运行——无需插件
* [集成、扩展和自定义](https://www.collaboraonline.com/integrations/)
* 开源 —— 主要采用 [MPLv2](http://mozilla.org/MPL/2.0/) 许可证。部分组件采用其他开源许可证，请参阅 [browser/LICENSE](https://github.com/CollaboraOnline/online/blob/master/browser/LICENSE)。

## 联系我们 💬

* [📋 论坛](https://forum.collaboraonline.com/)
* [👥 Facebook](https://www.facebook.com/collaboraoffice/)
* [🅾 Instagram](https://www.instagram.com/collaboraoffice/)
* [🐣 𝕏(Twitter)](https://twitter.com/CollaboraOffice)
* [🦋 Bluesky](https://bsky.app/profile/collaboraonline.com)
* [🐘 Mastodon](https://mastodon.social/@CollaboraOffice)
* [💼 LinkedIn](https://www.linkedin.com/products/collaboraproductivity-collabora-online/)
* [🎥 YouTube](https://www.youtube.com/@CollaboraOnline)

## 集成

要将 [Collabora Online](https://sdk.collaboraonline.com/docs/why_integrate.html) 集成到您自己的解决方案中，您可以查看我们的[分步教程](https://sdk.collaboraonline.com/docs/Step_by_step_tutorial.html)，查看[可用的集成方案](https://sdk.collaboraonline.com/docs/available_integrations.html)，了解用于自定义和与 Collabora Online 交互的[post message API](https://sdk.collaboraonline.com/docs/postmessage_api.html)，以及更多内容。

### 开发人员测试运行集成

在本地主机上设置 Nextcloud 或 ownCloud，并安装 richdocuments 应用，或者探索其他可用于测试 Collabora Online 的集成方式，请访问 https://www.collaboraonline.com/integrations/。

关于如何安装 ownCloud 或 Nextcloud，已有许多优秀的教程，我们在此不再赘述。richdocuments 在相应的应用商店 / 市场平台中被称为 Collabora Online。

当您在 http://localhost/nextcloud 或 http://localhost/owncloud 上运行了 Nextcloud 或 ownCloud 实例后，请进入 Collabora Online 设置，将 WOPI URL 设置为 http://localhost:9980。

然后在构建目录中，编辑生成的 coolwsd.xml 文件并将 ssl 设置为 false。您可以运行 make run，使用 ownCloud 或 Nextcloud 集成测试 coolwsd。

注意：如果在 Collabora Online 或集成端启用了 SSL，则两者都必须启用 SSL。也就是说，您必须使用 https:// 访问 NC/OC，并将 NC/OC 中的 Collabora Online 端点配置为 https://localhost:9980。

## 寻找合作伙伴

您想要一个现成或简化版的解决方案吗？请从我们的 [全球合作伙伴列表](https://www.collaboraonline.com/partners/) 中选择一家可信供应商，他们提供 Collabora Online 的集成和托管服务。

## 开发者支持

请在以下任意桥接的 Matrix/Telegram 群组中提出您的问题：
* Matrix: [#cool-dev:matrix.org](https://matrix.to/#/#cool-dev:matrix.org)
* Telegram: [CollaboraOnline](https://t.me/CollaboraOnline)

加入我们的 Discourse 论坛讨论：https://forum.collaboraonline.com/

查看 tinderbox 状态（绿色表示正常）：
https://cpci.cbg.collabora.co.uk:8080/job/Tinderbox%20for%20online%20master%20against%20co-24.04/

## 开发相关内容

该项目包含以下几个组件：
* **wsd/**
  * Web 服务守护进程 - 接收外部连接
* **kit/**
  * 运行于独立 chroot 环境中的客户端，负责文档渲染
* **common/**
  * 这些进程之间的共享代码
* **browser/**
  * 客户端 JavaScript 组件
* **test/**
  * C++ 编写的单元测试
* **cypress_test/**
  * JavaScript 编写的集成测试

## 有关构建细节的进一步推荐阅读

* **[构建 Collabora Online](https://collaboraonline.github.io/post/build-code/)**

## iOS 和 Android 应用

### 构建

请查看对应的网页：
* **[构建 iOS 版本](https://collaboraonline.github.io/post/build-code-ios/)**
* **[构建 Android 版本](https://collaboraonline.github.io/post/build-code-android/)**

### 发布和预发布

发布和预发布构建基于 `distro/collabora/co-25.04-mobile` 分支。Android 和 iOS 的发布版本通常基于同一个提交，并在 GitHub 上标记为发布版本。

Android 快照每周自动构建一次，但如果有新内容需要测试，可能会更频繁地构建。iOS TestFlight 构建仅在有新内容需要测试时才会构建。预发布构建不会在 GitHub 上打标签。

### 如何将更改合并到 25.04-mobile

即使您正在开发仅限移动端的功能，也应继续在 `master` 分支上开发。`master` 分支上的更改将根据发布计划合并到 `distro/collabora/co-25.04` 分支中。然后，`distro/collabora/co-25.04` 分支中的更改会定期挑选合并到 `distro/collabora/co-25.04-mobile` 分支中。

如果您希望某些更改更快地进入移动端快照或发布版本，仍应在 `master` 分支上进行开发。当更改合并到 `master` 后，您应针对 `distro/collabora/co-25.04-mobile` 创建一个回溯的 Pull Request。请不要直接针对 `distro/collabora/co-25.04-mobile` 创建 Pull Request（即更改必须首先合并到 `master`）。

## GitPod

请前往 https://collaboraonline.github.io/post/build-code/#build-code-on-gitpod 并按照步骤操作。

## 管理面板

您可以通过浏览器直接访问 browser 目录中的 admin.html 文件来访问管理面板。

到管理控制台的 WebSocket 连接可以在路径 `/adminws/` 上建立，该路径与 coolwsd 运行的 URL 和端口相同。但是，您需要一个 JWT 令牌来认证到管理控制台的 WebSocket。当用户通过访问 `/browser/dist/admin/admin*.html` 文件（HTTP Basic 认证）成功认证时，该令牌将作为 cookie 存储，路径为 `Path: /adminws/`。令牌每半小时过期一次，因此必须在此期间内建立与管理控制台 WebSocket 的连接。

您还可以执行各种任务，例如关闭已打开超过 10 小时的文档等。有关各种命令，请参阅 protocol.txt。这里唯一复杂的是获取 JWT 令牌，获取方式如上所述。

## 协议描述

请参阅 **protocol.txt** 以了解 WebSocket 上使用的协议描述。

## 架构

请参考 https://sdk.collaboraonline.com/docs/architecture.html

## 祝您使用愉快！