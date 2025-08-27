# Tautulli

一个基于 Python 的 Web 应用程序，用于监控、分析和通知 [Plex Media Server](https://plex.tv) 的运行情况。

本项目代码基于 [Headphones](https://github.com/rembo10/headphones) 和 [plexWatchWeb](https://github.com/ecleese/plexWatchWeb)。

## 功能特性

-   响应式网页设计，适用于桌面、平板和移动设备的浏览器。
-   界面风格与 Plex/Web 相匹配。
-   简单易用的配置设置（无需单独的 Web 服务器）。
-   监控当前 Plex Media Server 的活动。
-   完全可定制的流媒体活动和新增媒体通知。
-   首页显示顶部统计数据，支持自定义时间段和度量单位。
-   全局观看历史记录，支持搜索/过滤和动态列排序。
-   完整的用户列表，包含基本信息和对比统计数据。
-   个人用户信息，包括设备和 IP 地址。
-   完整的媒体库统计和媒体文件信息。
-   使用 Highcharts 图表库展示丰富的分析数据。
-   精美的内容信息页面。
-   显示所有用户从您的媒体库同步项目的完整同步列表。
-   还有更多功能等你发现！！

## 预览

[完整预览图集请访问我们的网站][Tautulli]

![Tautulli 首页](https://tautulli.com/images/screenshots/activity-compressed.jpg?v=2)

## 安装

[![Python][badge-python]][Python]
[![Docker Pulls][badge-docker-pulls]][DockerHub]
[![Docker Stars][badge-docker-stars]][DockerHub]
[![Downloads][badge-downloads]][Releases Latest]

[badge-python]: https://img.shields.io/badge/python->=3.9-blue?style=flat-square
[badge-docker-pulls]: https://img.shields.io/docker/pulls/tautulli/tautulli?style=flat-square
[badge-docker-stars]: https://img.shields.io/docker/stars/tautulli/tautulli?style=flat-square
[badge-downloads]: https://img.shields.io/github/downloads/Tautulli/Tautulli/total?style=flat-square

| 状态 | 分支: `master` | 分支: `beta` | 分支: `nightly` |
| --- | --- | --- | --- |
| 发布版本   | [![Release@master][badge-release-master]][Releases Latest] <br> [![Release Date@master][badge-release-master-date]][Releases Latest] | [![Release@beta][badge-release-beta]][Releases] <br> [![Commits@beta][badge-release-beta-commits]][Commits Beta] | [![Last Commits@nightly][badge-release-nightly-last-commit]][commits Nightly] <br> [![Commits@nightly][badge-release-nightly-commits]][Commits Nightly] |
| Docker    | [![Docker@master][badge-docker-master]][DockerHub] <br> [![Docker Build@master][badge-docker-master-ci]][Publish Docker Master] | [![Docker@beta][badge-docker-beta]][DockerHub] <br> [![Docker Build@beta][badge-docker-beta-ci]][Publish Docker Beta] | [![Docker@nightly][badge-docker-nightly]][DockerHub] <br> [![Docker Build@nightly][badge-docker-nightly-ci]][Publish Docker Nightly] |
| Snap      | [![Snap@master][badge-snap-master]][Snapcraft] <br> [![Snap Build@master][badge-snap-master-ci]][Publish Snap Master] | [![Snap@beta][badge-snap-beta]][Snapcraft] <br> [![Snap Build@beta][badge-snap-beta-ci]][Publish Snap Beta] | [![Snap@nightly][badge-snap-nightly]][Snapcraft] <br> [![Snap Build@nightly][badge-snap-nightly-ci]][Publish Snap Nightly] |
| 安装包 | [![Windows@master][badge-installer-master-win]][Releases Latest] <br> [![MacOS@master][badge-installer-master-macos]][Releases Latest] <br> [![Installer Build@master][badge-installer-master-ci]][Publish Installer Master] | [![Windows@beta][badge-installer-beta-win]][Releases] <br> [![MacOS@beta][badge-installer-beta-macos]][Releases] <br> [![Installer Build@beta][badge-installer-beta-ci]][Publish Installer Beta] | [![Installer Build@nightly][badge-installer-nightly-ci]][Publish Installer Nightly] |

阅读 [安装指南][Installation] 以获取 Tautulli 的安装说明。

[badge-release-master]: https://img.shields.io/github/v/release/Tautulli/Tautulli?style=flat-square
[badge-release-master-date]: https://img.shields.io/github/release-date/Tautulli/Tautulli?style=flat-square&color=blue
[badge-release-beta]: https://img.shields.io/github/v/release/Tautulli/Tautulli?include_prereleases&style=flat-square
[badge-release-beta-commits]: https://img.shields.io/github/commits-since/Tautulli/Tautulli/latest/beta?style=flat-square&color=blue
[badge-release-nightly-last-commit]: https://img.shields.io/github/last-commit/Tautulli/Tautulli/nightly?style=flat-square&color=blue
[badge-release-nightly-commits]: https://img.shields.io/github/commits-since/Tautulli/Tautulli/latest/nightly?style=flat-square&color=blue
[badge-docker-master]: https://img.shields.io/badge/docker-latest-blue?style=flat-square
[badge-docker-master-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-docker.yml?style=flat-square&branch=master
[badge-docker-beta]: https://img.shields.io/badge/docker-beta-blue?style=flat-square
[badge-docker-beta-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-docker.yml?style=flat-square&branch=beta
[badge-docker-nightly]: https://img.shields.io/badge/docker-nightly-blue?style=flat-square
[badge-docker-nightly-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-docker.yml?style=flat-square&branch=nightly
[badge-snap-master]: https://img.shields.io/badge/snap-stable-blue?style=flat-square
[badge-snap-master-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-snap.yml?style=flat-square&branch=master
[badge-snap-beta]: https://img.shields.io/badge/snap-beta-blue?style=flat-square
[badge-snap-beta-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-snap.yml?style=flat-square&branch=beta
[badge-snap-nightly]: https://img.shields.io/badge/snap-edge-blue?style=flat-square
[badge-snap-nightly-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-snap.yml?style=flat-square&branch=nightly
[badge-installer-master-win]: https://img.shields.io/github/v/release/Tautulli/Tautulli?label=windows&style=flat-square
[badge-installer-master-macos]: https://img.shields.io/github/v/release/Tautulli/Tautulli?label=macos&style=flat-square
[badge-installer-master-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-installers.yml?style=flat-square&branch=master
[badge-installer-beta-win]: https://img.shields.io/github/v/release/Tautulli/Tautulli?label=windows&include_prereleases&style=flat-square
[badge-installer-beta-macos]: https://img.shields.io/github/v/release/Tautulli/Tautulli?label=macos&include_prereleases&style=flat-square
[badge-installer-beta-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-installers.yml?style=flat-square&branch=beta
[badge-installer-nightly-ci]: https://img.shields.io/github/actions/workflow/status/Tautulli/Tautulli/.github/workflows/publish-installers.yml?style=flat-square&branch=nightly

## 支持

[![Wiki][badge-wiki]][Wiki]
[![Discord][badge-discord]][Discord]
[![Reddit][badge-reddit]][Reddit]
[![Plex 论坛][badge-forums]][Plex Forums]
[![问题反馈][badge-issues]][Issues]

[badge-wiki]: https://img.shields.io/badge/github-wiki-black?style=flat-square
[badge-discord]: https://img.shields.io/discord/183396325142822912?label=discord&style=flat-square&color=7289DA
[badge-reddit]: https://img.shields.io/reddit/subreddit-subscribers/tautulli?label=reddit&style=flat-square&color=FF5700
[badge-forums]: https://img.shields.io/badge/plex%20forums-discussion-E5A00D?style=flat-square
[badge-issues]: https://img.shields.io/badge/github-issues-black?style=flat-square

如果您认为在 Tautulli 中发现了 bug，请首先阅读 [FAQ][]，确认是否已有相关解答。如果 FAQ 中没有解决您的问题，请尝试以下步骤：

-   更新到最新版本的 Tautulli。
-   重启您的设备。
-   分析您的日志，您可能会自行找到解决方案！
-   使用 **搜索** 功能查看是否已有相关问题报告或解决方案。
-   查看 [Wiki][] 获取 [安装][Installation] 指南并阅读 [常见问题][FAQ]。
-   对于基本问题，建议先在 [Discord][], [Reddit][] 或 [Plex 论坛][] 上提问，再考虑提交问题反馈。

**如果以上方法均无效：**

1.  请检查 [问题跟踪器][Issues]，确认是否有人已报告该 bug。
2.  如果是新发现的 bug，请在问题跟踪器中提交 [bug 报告][Issue New]。
3.  为问题提供清晰的标题，以便快速识别问题。
4.  使用正确的 [Markdown 语法][] 来组织您的内容（例如将代码/日志放入代码块中）。
5.  确保填写问题模板中的所有必要信息。
6.  问题解决后请关闭您的 issue！如果您自行找到了解决方案，请发表评论，以便他人受益。

## 功能请求

1.  请先检查 [问题跟踪器][Issues]，确认是否有人已提出类似功能请求。
    如果已有类似请求，请为其点赞。**请不要使用 `+1` 或类似评论，这会产生不必要的垃圾信息。**
2.  如果是新功能请求，请在问题跟踪器中提交 [功能请求][Issue New]。

## 许可证

[![License][badge-license]][License]

[badge-license]: https://img.shields.io/github/license/Tautulli/Tautulli?style=flat-square

这是基于 GPL v3 开源许可证的免费软件。您可以随意使用，但任何修改都必须开源。许可证副本已包含在内。

本软件包含 Highsoft 软件库，您可以免费用于非商业用途。商业用户必须获得该软件的许可，更多信息请访问 https://shop.highsoft.com/faq/non-commercial#non-commercial-redistribution。

[Python]: https://python.org/downloads
[DockerHub]: https://hub.docker.com/r/tautulli/tautulli
[Releases]: https://github.com/Tautulli/Tautulli/releases
[Releases Latest]: https://github.com/Tautulli/Tautulli/releases/latest
[License]: https://github.com/Tautulli/Tautulli/blob/master/LICENSE
[FAQ]: https://github.com/Tautulli/Tautulli/wiki/Frequently-Asked-Questions
[Installation]: https://github.com/Tautulli/Tautulli/wiki/Installation
[Issues]: https://github.com/Tautulli/Tautulli/issues
[Issue New]: https://github.com/Tautulli/Tautulli/issues/new/choose
[Markdown 语法]: https://help.github.com/articles/github-flavored-markdown
[Tautulli]: http://tautulli.com
[Wiki]: https://github.com/Tautulli/Tautulli/wiki
[Discord]: https://tautulli.com/discord
[Reddit]: https://reddit.com/r/Tautulli
[Plex 论坛]: https://forums.plex.tv/t/tautulli-monitor-your-plex-media-server/225242
[Snapcraft]: https://snapcraft.io/tautulli
[Commits Beta]: https://github.com/Tautulli/Tautulli/commits/beta
[Commits Nightly]: https://github.com/Tautulli/Tautulli/commits/nightly

[Publish Docker Master]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Docker"+branch%3Amaster
[Publish Docker Beta]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Docker"+branch%3Abeta
[Publish Docker Nightly]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Docker"+branch%3Anightly
[Publish Snap Master]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Snap"+branch%3Amaster
[Publish Snap Beta]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Snap"+branch%3Abeta
[Publish Snap Nightly]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Snap"+branch%3Anightly
[Publish Installer Master]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Installers"+branch%3Amaster
[Publish Installer Beta]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Installers"+branch%3Abeta
[Publish Installer Nightly]: https://github.com/Tautulli/Tautulli/actions?query=workflow%3A"Publish+Installers"+branch%3Anightly