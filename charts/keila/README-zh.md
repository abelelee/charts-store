![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/pentacent/keila/ci.yml?label=构建&style=flat-square&branch=main)
[![Docker Image Version (latest semver)](https://img.shields.io/docker/v/pentacent/keila?color=blue&label=Docker镜像&style=flat-square)](https://hub.docker.com/r/pentacent/keila/tags)
[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/pentacent/keila?label=最新版本&style=flat-square)](https://github.com/pentacent/keila/releases)
[![GitHub Sponsors](https://img.shields.io/github/sponsors/pentacent?color=ff69b4)](https://github.com/sponsors/pentacent)

<a href="https://fosstodon.org/@keila" title="在Mastodon上关注Keila" rel="me"><img src="https://img.shields.io/mastodon/follow/109370923780670804?domain=https%3A%2F%2Ffosstodon.org&label=关注&style=flat-square&logo=mastodon&color=blue&logoColor=white"></a>
<a href="https://bsky.app/profile/pentacent.bsky.social" title="在Bluesky上关注Keila的开发动态"><img src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fpublic.api.bsky.app%2Fxrpc%2Fapp.bsky.actor.getProfile%2F%3Factor%3Dpentacent.bsky.social&query=%24.followersCount&style=flat-square&logo=bluesky&logoColor=white&label=Bluesky"></a>

# ![Keila的标志是一头风格化的象](.github/assets/logo.svg) Keila - 一个开源的新闻通讯工具

Keila 是 Mailchimp 或 Sendinblue 等新闻通讯工具的一种开源替代方案。

使用 Keila，您可以轻松地发送新闻通讯活动并创建注册表单。

对于小型新闻通讯，您可以使用自己的电子邮件收件箱来发送活动。对于大型新闻通讯项目，除了 SMTP 外，还支持 AWS SES、Sendgrid、Mailgun 和 Postmark。

![Keila 活动编辑器的截图，显示了所见即所得编辑器和默认模板](https://www.keila.io/_astro/keila-2024-05-01.BUp8L2VZ.png)

## 试用 Keila！

您可以在 [app.keila.io](https://app.keila.io/auth/register) 上试用托管版本的 Keila。有关 Keila Cloud 定价的更多信息请[点击此处](https://www.keila.io/pricing)。

如果您想在自己的服务器上部署 Keila，可以使用官方 Docker 镜像 `pentacent/keila`，或者使用本仓库中的 示例 Docker Compose 配置。

更多详细信息，请参考 [安装文档](https://www.keila.io/docs/installation)。

## 贡献

您可以参与 Keila 项目的翻译或代码开发！了解如何为 Keila 贡献代码或翻译，请查看：CONTRIBUTING.md

## 名称由来

Keila 是本项目的大象吉祥物的名字。她是一头聪明勤奋的大象女士，能够记住无数的电子邮件地址和联系人姓名。有趣的是：Keila 喜欢去芬兰的湖泊度假。

## 许可证

Keila 是自由软件。您可以根据自由软件基金会发布的 GNU Affero 通用公共许可证的条款重新分发和/或修改它，许可证版本为第 3 版或（由您选择）任何更新版本。

Keila 以希望它有用的方式发布，但**没有任何**明示或暗示的担保，包括但不限于适销性或特定用途适用性的担保。

有关 AGPL 的更多详细信息，请点击此处阅读完整许可证。

请注意，Keila 的标志以及 `extra` 目录中包含的所有文件不受该许可证的约束。

有关 `extra` 目录中文件的更多详细信息，请参阅 extra README。