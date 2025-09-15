# [Octobox](https://octobox.io) &#128238; 解决你的 GitHub 通知问题。

Octobox 帮助你高效地管理 GitHub 通知，从而减少管理时间，把更多时间投入到实际工作中。

- **不会遗漏任何信息** - Octobox 为每条通知添加了一个额外的“已归档”状态，你可以将通知标记为“已完成”。如果某条已归档的讨论、问题或 PR 出现新的动态，Octobox 会将其重新移回你的收件箱。

- **标记重要通知** - 坦白说，你可能没有真正意义上的“最爱”问题，但 Octobox 允许你通过星标标记重要通知，方便你随时回来查找。

- **增强型通知** - 比普通通知更强大。在显示基本的标题、组织、仓库和类型信息的同时，还显示问题/PR 状态、CI 状态、标签等更多信息。

- **过滤所有内容** - 可通过仓库、组织、类型、操作、状态、CI 状态和原因等条件过滤通知，并且可以将机器人发送的通知与常规的标签、作者和指派人筛选条件结合使用。

- **支持前缀过滤的搜索** - 不再需要“原力”。结合多种强大的搜索过滤器，你可以快速定位到所需的通知，专注于你真正关心的内容。

- **专为键盘用户打造** - 使用类似 Gmail 的键盘快捷键，像专业人士一样导航、分类和管理通知，无需鼠标。

- **完全开源** - Octobox 的开发者使用 Octobox 来开发 Octobox。该项目 100% 在 GitHub 上公开开发和管理，采用 FLOSS 许可证。

![Octobox 截图](app/assets/images/screenshot.png)

[![在 Skylight 上查看性能数据](https://badges.skylight.io/typical/eLvcBBdLmV6k.svg)](https://oss.skylight.io/app/applications/eLvcBBdLmV6k)
[![Docker](https://img.shields.io/docker/pulls/octoboxio/octobox.svg)](https://hub.docker.com/r/octoboxio/octobox/)
[![Gitter](https://img.shields.io/gitter/room/octobox/octobox.svg)](https://gitter.im/octobox/octobox)
[![OpenCollective](https://opencollective.com/octobox/backers/badge.svg)](#backers)
[![OpenCollective](https://opencollective.com/octobox/sponsors/badge.svg)](#sponsors)
[![Open Source Helpers](https://www.codetriage.com/andrew/github-inbox/badges/users.svg)](https://www.codetriage.com/andrew/github-inbox)
[![许可证](https://img.shields.io/github/license/octobox/octobox.svg)](LICENSE.txt)

## 为什么会有这个项目？

如果你在 GitHub 上管理过活跃的项目，你可能会觉得 [GitHub 通知页面](https://github.com/notifications) 功能非常有限。

GitHub 的通知一旦页面加载完成或你查看了通知邮件，就会被标记为已读并从列表中消失。这使得你很难跟踪哪些通知仍需跟进。大多数开源维护者和 GitHub 员工最终都不得不使用 Gmail 中复杂的过滤器和标签组合来管理他们的通知。如果你像我一样尽量避免使用邮件，你可能需要一个替代方案。

Octobox 为每条通知添加了一个额外的“已归档”状态，你可以将通知标记为“已完成”。如果该讨论/问题/PR 出现新活动，下次同步应用时，相关条目将被取消归档并重新移回你的收件箱。

## 目录

- Octobox 📮 解决你的 GitHub 通知问题。
	- 为什么会有这个项目？
	- 目录
	- 快速开始
		- 安装
		- 桌面使用
		- 网页扩展
	- 需求
	- 查看评论讨论
	- 键盘快捷键
	- API 文档
	- 支持者
	- 赞助商
	- 贡献
		- 关于补丁/拉取请求的说明
		- 漏洞披露
		- 行为准则
	- 版权

## 快速开始

### 安装

你也可以自行托管 Octobox！请参阅 安装指南 获取安装说明，以及部署到 Heroku、Docker 等的详细信息。

### 桌面使用

你也可以使用 [Nativefier](https://www.npmjs.com/package/nativefier) 将 Octobox 作为桌面应用运行：

```bash
npm install -g nativefier
nativefier "https://octobox.io" # 或你自己的自托管地址
```

这将构建一个本地应用程序（.exe、.app 等），并将其放在当前目录中，方便使用。

### 网页扩展

你还可以安装跨浏览器的 [Octobox 网页扩展](https://github.com/tfrommen/octobox-web-extension)。它适用于 [Google Chrome](https://chromewebstore.google.com/detail/octobox/dpbajpnhgagfneijghelgldegjblinkc) 和 [Mozilla Firefox](https://addons.mozilla.org/en-US/firefox/addon/octobox-web-extension/)，也可以用于支持网页扩展的其他浏览器。

## 需求

Octobox 要正常运行，必须在你的 GitHub 设置中启用 [网页通知](https://github.com/settings/notifications)。如果你希望接收漏洞通知，也需要启用它们。

<img width="739" alt="screenshot 2018-11-12 at 14 32 38" src="/docs/assets/notification-settings.png">

## 查看评论讨论

Octobox 的讨论视图功能目前处于公开测试阶段。要启用它，请在 `/settings` 页面的“Open notifications”菜单中选择 'on octobox'。

为了在 Octobox 中查看讨论内容，需要先进行同步。某些通知如果没有关联的讨论或尚未同步，仍然会显示通知窗口中的 `:link-external:` 图标。

## 键盘快捷键

你可以使用键盘快捷键进行导航和执行某些操作：

 - `a` - 全选/取消全选
 - `r` 或 `.` - 刷新列表
 - `j` - 向下移动列表
 - `k` - 向上移动列表
 - `s` - 星标当前通知
 - `x` - 标记/取消标记当前通知
 - `y` 或 `e` - 归档/取消归档当前或已标记的通知
 - `m` - 静音当前或已标记的通知
 - `d` - 在 Octobox 和 GitHub 上将当前或已标记的通知标记为已读
 - `o` 或 `Enter` - 在新窗口中打开当前通知

按下 `?` 可打开帮助菜单。

## API 文档

Octobox 提供了一个 REST API，用于管理通知、用户和固定搜索。完整的 API 规范以 OpenAPI 文档形式提供：

- **[OpenAPI 规范文档](https://github.com/octobox/octobox/blob/master/openapi.yaml)** - 包含示例的完整 API 参考
- **[交互式 API 浏览器](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/octobox/octobox/master/openapi.yaml)** - 可直接在浏览器中试用 API

API 支持 Bearer Token 认证，并涵盖所有主要功能，包括通知管理、用户设置和固定搜索操作。

## 支持者
感谢所有支持者！🙏 [[成为支持者](https://opencollective.com/octobox#backer)]

<a href="https://opencollective.com/octobox#backers" target="_blank"><img src="https://opencollective.com/octobox/backers.svg?width=890"></a>

## 赞助商

通过成为赞助商来支持这个项目。你的 Logo 将会显示在这里并链接到你的网站。[[成为赞助商](https://opencollective.com/octobox#sponsor)]

<a href="https://opencollective.com/octobox/sponsor/0/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/1/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/2/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/3/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/4/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/5/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/6/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/7/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/8/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/octobox/sponsor/9/website" target="_blank"><img src="https://opencollective.com/octobox/sponsor/9/avatar.svg"></a>

## 贡献

欢迎贡献！源代码托管在 [GitHub](https://github.com/octobox/octobox)。如果你有需求，请 [提交 issue](https://github.com/octobox/octobox/issues/new) 或 Pull Request。

如果你不知道从哪里开始，可以看看标记为 ["Help Wanted"](https://github.com/octobox/octobox/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22) 的问题。

你也可以帮助整理问题。这包括复现 bug 报告，或请求关键信息如版本号或复现步骤。如果你想开始整理问题，可以 [订阅 Octobox 的 CodeTriage](https://www.codetriage.com/octobox/octobox)。

最后，这是一个开源项目。如果你经常贡献，我们愿意邀请你成为维护者。欢迎随时提出。

如需其他更新，请在 Twitter 上关注项目：[@octoboxio](https://twitter.com/octoboxio)。

### 关于补丁/拉取请求的说明

 * Fork 项目。
 * 实现你的功能添加或 bug 修复。
 * 为其添加测试。这一点非常重要，这样我们将来不会无意中破坏它。
 * 发送 Pull Request。使用主题分支会加分。

### 漏洞披露

我们支持并鼓励在我们的 漏洞披露政策 下对 Octobox 进行安全研究。

### 行为准则

请注意，本项目发布时附带了 贡献者行为准则。参与本项目即表示你同意遵守其条款。

## 版权

GNU Affero 许可证 © 2021 [Andrew Nesbitt](https://github.com/andrew)