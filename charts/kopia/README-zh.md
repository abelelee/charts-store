Kopia
=====

![Kopia](icons/kopia.svg)
[![Build Status](https://github.com/kopia/kopia/workflows/Build/badge.svg)](https://github.com/kopia/kopia/actions?query=workflow%3ABuild)
[![Slack](https://img.shields.io/badge/discuss-slack-blue.svg)](https://slack.kopia.io/) 
[![GoDoc](https://godoc.org/github.com/kopia/kopia/repo?status.svg)](https://godoc.org/github.com/kopia/kopia/repo)
[![Coverage Status](https://codecov.io/gh/kopia/kopia/branch/master/graph/badge.svg?token=CRK4RMRFSH)](https://codecov.io/gh/kopia/kopia)[![Go Report Card](https://goreportcard.com/badge/github.com/kopia/kopia)](https://goreportcard.com/report/github.com/kopia/kopia)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](CODE_OF_CONDUCT.md)
[![Docker Pulls](https://img.shields.io/docker/pulls/kopia/kopia)](https://hub.docker.com/r/kopia/kopia/tags?page=1&ordering=name)
[![Downloads](https://img.shields.io/github/downloads/kopia/kopia/total.svg)](https://github.com/kopia/kopia/releases)
[![Gurubase](https://img.shields.io/badge/Gurubase-Ask%20Kopia%20Guru-006BFF)](https://gurubase.io/g/kopia)

> _n._
>
> 1. _[copy, replica](https://en.wikipedia.org/wiki/Replica)（波兰语）_
> 2. _[lance, spear](https://en.wikipedia.org/wiki/Kopia)_
> 3. _[快速且安全的备份工具](https://kopia.io)_

Kopia 是一个快速且安全的开源备份/恢复工具，允许你创建数据的 [加密快照](https://kopia.io/docs/features/#end-to-end-zero-knowledge-encryption)，并将这些快照保存到你选择的 [远程或云存储](https://kopia.io/docs/features/#save-snapshots-to-cloud-network-or-local-storage)、[网络存储或服务器](https://kopia.io/docs/features/#save-snapshots-to-cloud-network-or-local-storage)，或本地机器上。Kopia 不会对整个系统进行“镜像”。相反，Kopia 允许你备份/恢复你认为重要或关键的任意文件/目录。

Kopia 同时提供 [CLI（命令行界面）](https://kopia.io/docs/features/#both-command-line-and-graphical-user-interfaces) 和 [GUI（图形用户界面）](https://kopia.io/docs/features/#both-command-line-and-graphical-user-interfaces) 版本，使其成为高级用户和普通用户的理想工具。你可以阅读更多关于 Kopia 的独特 [功能](https://kopia.io/docs/features/)，包括 [压缩](https://kopia.io/docs/features/#compression)、[去重](https://kopia.io/docs/features/#backup-files-and-directories-using-snapshots)、[端到端“零知识”加密](https://kopia.io/docs/features/#end-to-end-zero-knowledge-encryption) 和 [错误校正](https://kopia.io/docs/features/#error-correction)，以更好地了解 Kopia 的工作原理。

准备就绪后，请前往 [安装](https://kopia.io/docs/installation/) 页面下载并安装 Kopia，并确保阅读 [入门指南](https://kopia.io/docs/getting-started/)，以获得使用 Kopia 的逐步说明。

选择你要使用的云存储提供商
---

Kopia 支持将你的 [加密](https://kopia.io/docs/features/#end-to-end-zero-knowledge-encryption) 和 [压缩](https://kopia.io/docs/features/#compression) 快照保存到以下所有 [存储位置](https://kopia.io/docs/features/#save-snapshots-to-cloud-network-or-local-storage)：

* **Amazon S3** 及任何 **兼容 S3 的云存储**
* **Azure Blob Storage**
* **Backblaze B2**
* **Google Cloud Storage**
* 任何支持 **WebDAV** 的远程服务器或云存储
* 任何支持 **SFTP** 的远程服务器或云存储
* 一些 **Rclone** 支持的云存储选项
  * 需要额外下载并配置 Rclone，之后 Kopia 会自动管理并运行 Rclone
  * Rclone 支持为实验性功能：并非所有 Rclone 支持的云存储都经过测试，部分可能无法与 Kopia 兼容；目前 Kopia 已通过 Rclone 验证与 **Dropbox**、**OneDrive** 和 **Google Drive** 的兼容性
* 本地机器及任何网络附加存储或服务器
* 通过设置 [Kopia 仓库服务器](https://kopia.io/docs/repository-server/) 使用你自己的服务器

此外，Kopia 使用 [数据去重](https://kopia.io/docs/features/#backup-files-and-directories-using-snapshots) 技术来帮你节省费用！有关支持的存储位置的更多信息，请参阅 [仓库帮助页面](https://kopia.io/docs/repositories/)。

使用 Kopia，你可以完全控制快照的存储位置，即你可以选择要使用的存储提供商。你需要自行配置并支付所选存储位置的费用，然后告知 Kopia 这些存储位置。你甚至可以为不同的备份仓库使用多个存储位置。Kopia 还支持将多台机器备份到同一个存储位置。

Kopia 的实际使用
---

通过命令行界面使用 Kopia：

[![asciicast](https://asciinema.org/a/ykx6uzEhKY3451fWEnX9nm9uo.svg)](https://asciinema.org/a/ykx6uzEhKY3451fWEnX9nm9uo)

通过图形用户界面使用 Kopia（注意：该视频展示的是旧版本的 Kopia，当前版本的界面有所不同，但主要操作原理保持一致）：

[![Kopia UI 教程](https://img.youtube.com/vi/sHJjSpasWIo/0.jpg)](https://www.youtube.com/watch?v=sHJjSpasWIo)

入门
---
更多信息请参见 [Kopia 文档](https://kopia.io/docs/)。

构建 Kopia
---
有关构建 Kopia 和使用源代码的更多信息，请参见 构建基础设施。

许可协议
---
Kopia 使用 Apache License 2.0 协议。完整许可文本请参见 LICENSE。

贡献指南
---
Kopia 是开源项目，欢迎贡献。有关如何贡献的更多信息，请参见 [贡献指南](https://kopia.io/docs/contribution-guidelines/)。

报告安全问题
---
如果你发现一个希望私下披露的安全问题，请联系 `security@kopia.io` 或通过 [Slack](https://slack.kopia.io) 直接联系维护人员。

[![Netlify 状态](https://api.netlify.com/api/v1/badges/6b5c1fe4-a0da-4e7e-939b-ff1105251985/deploy-status)](https://app.netlify.com/sites/kopia/deploys)