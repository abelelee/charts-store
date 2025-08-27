---
<p align="center">
    <a href="https://github.com/gotify/logo">
        <img height="370px" src="https://raw.githubusercontent.com/gotify/logo/master/gotify-logo.png" />
    </a>
</p>

<h1 align="center">gotify/server</h1>

<p align="center">
    <a href="https://github.com/gotify/server/actions?query=workflow%3Abuild">
        <img alt="构建状态" src="https://github.com/gotify/server/workflows/build/badge.svg">
    </a>
    <a href="https://codecov.io/gh/gotify/server">
        <img alt="codecov" src="https://codecov.io/gh/gotify/server/branch/master/graph/badge.svg">
    </a>
    <a href="https://goreportcard.com/report/github.com/gotify/server">
        <img alt="Go 报告卡" src="https://goreportcard.com/badge/github.com/gotify/server">
    </a>
    <a href="https://matrix.to/#/#gotify:matrix.org">
        <img alt="Matrix" src="https://img.shields.io/matrix/gotify:matrix.org.svg">
    </a>
    <a href="https://hub.docker.com/r/gotify/server">
        <img alt="Docker 下载量" src="https://img.shields.io/docker/pulls/gotify/server.svg">
    </a>
    <a href="https://github.com/gotify/server/releases/latest">
        <img alt="最新版本" src="https://img.shields.io/github/release/gotify/server.svg">
    </a>
</p>

## 简介
我们想要一个简单易用的服务器，用于发送和接收消息（通过 WebSocket 实时传输）。然而，当时开源社区中能满足这一需求的项目非常少，大多数现有项目都已不再维护。此外，我们还要求该服务器支持自托管。当然，我们也知道目前市面上已经有许多免费和商业的推送服务。

## 功能特性

<img alt="Gotify UI 截图" src="ui.png" align="right" width="500px"/>

* 通过 REST-API 发送消息
* 通过 WebSocket 接收消息
* 管理用户、客户端和应用程序
* [插件系统](https://gotify.net/docs/plugin)
* Web 界面 -> [./ui](ui)
* 消息发送命令行工具 -> [gotify/cli](https://github.com/gotify/cli)
* Android 应用 -> [gotify/android](https://github.com/gotify/android)

[<img src="https://play.google.com/intl/en_gb/badges/images/generic/en_badge_web_generic.png" alt="Get it on Google Play" width="150" />][playstore]
[<img src="https://f-droid.org/badge/get-it-on.png" alt="Get it on F-Droid" width="150"/>][fdroid]

<sub>（Google Play 和 Google Play 标志是 Google LLC 的商标。）</sub>

---

**[文档](https://gotify.net/docs)**

[安装](https://gotify.net/docs/install) ᛫
[配置](https://gotify.net/docs/config) ᛫
[REST-API](https://gotify.net/api-docs) ᛫
[开发环境搭建](https://gotify.net/docs/dev-setup)

## 贡献

我们欢迎任何形式的贡献，包括提交 bug 报告、功能请求、改进文档、优化 UI 等。请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 获取贡献指南。

## 版本控制
我们使用 [语义化版本号（SemVer）](http://semver.org/) 进行版本管理。可用版本请参见本仓库的 [标签](https://github.com/gotify/server/tags)。

## 许可证
该项目使用 MIT 许可证，请参阅 [LICENSE](LICENSE) 文件了解详细信息。

 [playstore]: https://play.google.com/store/apps/details?id=com.github.gotify
 [fdroid]: https://f-droid.org/de/packages/com.github.gotify/