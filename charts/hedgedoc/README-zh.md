![HedgeDoc Logo](docs/content/images/hedgedoc_logo_black.svg)

# HedgeDoc

[![#HedgeDoc on matrix.org][matrix.org-image]][matrix.org-url]
[![版本][github-version-badge]][github-release-page]
[![POEditor][poeditor-image]][poeditor-url]
[![Mastodon][social-mastodon-image]][social-mastodon]

HedgeDoc 可以帮助你创建支持实时协作的 Markdown 笔记。你可以通过访问我们的 [HedgeDoc 演示服务器][hedgedoc-demo] 来试用。

它受到 Hackpad、Etherpad 和其他类似协作编辑器的启发。该项目最初由 [HackMD](https://hackmd.io) 团队发起，现在作为一个独立组织进行开发。[你可以在历史页面阅读更详细的说明][history]。

![HedgeDoc 1.7.0 打开功能演示页面][hedgedoc-demo-features]

## 社区与贡献

我们欢迎任何形式的贡献！还有许多工作要做：如果你想报告问题，请使用 [问题追踪器][github-issue-tracker]；如果你能协助翻译，请访问 [POEditor][poeditor-url]；如需开始开发，请参考 [开发者文档][developer-documentation]。无论如何，欢迎来与我们交流，我们将非常乐意协助你迈出第一步。

为了了解我们的最新动态或获取支持，建议加入我们的 [Matrix 频道][matrix.org-url]、访问我们的 [社区论坛][hedgedoc-community] 或订阅 [发布更新源][github-release-feed]。我们还会定期举行 [社区会议][hedgedoc-community-calls]（[RSS](https://community.hedgedoc.org/t/codimd-community-call/19.rss)），欢迎你的参与。

## 安装 / 升级

你可以通过多种方式运行 HedgeDoc，我们为每种方式都提供了安装说明：

- [Docker][setup-docker]
- [Cloudron][setup-cloudron]
- [LinuxServer.io (多架构 Docker)][setup-docker-linuxserver]
- [Heroku][setup-heroku]
- [手动安装][setup-manual]

## 配置

配置 HedgeDoc 实例主要有两种方式：[配置文件][configuration] 或环境变量。你可以根据需要选择合适的方式。

HedgeDoc 支持以下集成：

- 用于**登录**的：facebook、twitter、github、gitlab、mattermost、dropbox、google、ldap、saml 和 [oauth2][configuration-oauth]
- 用于**图片/附件存储**的：imgur、s3、minio、azure（文件也可以存储在本地）
- 用于**导出与导入**的：dropbox

更多相关信息请参阅上述配置文档。

## 浏览器支持

使用 HedgeDoc 时，你的浏览器版本应至少满足以下要求：

- ![Chrome](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/chrome/chrome_24x24.png) Chrome >= 47, ![Chrome](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/chrome/chrome_24x24.png) Android 上的 Chrome >= 47
- ![Safari](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/safari/safari_24x24.png) Safari >= 10.1, ![iOS Safari](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/safari-ios/safari-ios_24x24.png) iOS Safari >= 10.3
- ![Firefox](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/firefox/firefox_24x24.png) Firefox >= 44
- ![Edge](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/edge/edge_24x24.png) Edge >= 14
- ![Opera](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/opera/opera_24x24.png) Opera >= 34, ![Opera Mini](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/opera-mini/opera-mini_24x24.png) Opera Mini 不支持
- ![Android 浏览器](https://raw.githubusercontent.com/alrra/browser-logos/HEAD/src/android-webview-beta/android-webview-beta_24x24.png) Android 浏览器 >= 4.4

## 备份和恢复你的实例

要备份 HedgeDoc，请执行以下操作：

- 备份数据库
- 如果你有自定义配置文件，请备份该文件
- 备份上传目录（请参阅 [uploadsPath][configuration-paths] 配置指令）

恢复一个已有的 HedgeDoc 实例只需恢复上述内容即可。

## 相关工具

我们的社区开发了一些相关工具，我们特别推荐 [hedgedoc-cli](https://github.com/hedgedoc/cli)，它让你可以从命令行使用 HedgeDoc。

## 许可证

本项目采用 AGPLv3 许可证发布。贡献者名单请参阅 AUTHORS 文件。

许可证不包括 HedgeDoc 的 Logo，其使用条款请参阅 [GitHub 仓库](https://github.com/hedgedoc/hedgedoc-logo)。

[configuration-oauth]: https://docs.hedgedoc.org/configuration/#oauth2-login
[configuration]: https://docs.hedgedoc.org/configuration/
[configuration-paths]: https://docs.hedgedoc.org/configuration/#hedgedoc-paths-stuff
[setup-docker]: https://docs.hedgedoc.org/setup/docker/
[setup-cloudron]: https://docs.hedgedoc.org/setup/cloudron/
[setup-docker-linuxserver]: https://docs.hedgedoc.org/setup/docker-linuxserver/
[setup-heroku]: https://docs.hedgedoc.org/setup/heroku/
[setup-manual]: https://docs.hedgedoc.org/setup/manual-setup/
[developer-documentation]: https://docs.hedgedoc.org/dev/getting-started/
[history]: https://docs.hedgedoc.org/history/
[matrix.org-image]: https://img.shields.io/matrix/hedgedoc:matrix.org?logo=matrix&server_fqdn=matrix.org
[matrix.org-url]: https://chat.hedgedoc.org
[github-version-badge]: https://img.shields.io/github/release/hedgedoc/hedgedoc.svg
[github-release-page]: https://github.com/hedgedoc/hedgedoc/releases
[github-release-feed]: https://github.com/hedgedoc/hedgedoc/releases.atom
[github-issue-tracker]: https://github.com/hedgedoc/hedgedoc/issues/
[poeditor-image]: https://img.shields.io/badge/POEditor-translate-blue.svg
[poeditor-url]: https://poeditor.com/join/project/1OpGjF2Jir
[hedgedoc-demo]: https://demo.hedgedoc.org
[hedgedoc-demo-features]: https://demo.hedgedoc.org/features
[hedgedoc-community]: https://community.hedgedoc.org
[hedgedoc-community-calls]: https://community.hedgedoc.org/t/codimd-community-call/19
[social-mastodon]: https://social.hedgedoc.org/mastodon
[social-mastodon-image]: https://img.shields.io/mastodon/follow/109259563190314667?domain=https%3A%2F%2Ffosstodon.org&style=social