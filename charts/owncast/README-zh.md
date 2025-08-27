以下是你提供的Markdown内容的中文翻译，保留了原始的Markdown格式和结构：

---

<p align="center">
  <a href="https://github.com/owncast/owncast" alt="Owncast">
    <img src="https://owncast.online/images/logo.png" alt="Owncast Logo" width="200">
  </a>
</p>

<p align="center">
	<strong>掌控你的内容，自己进行直播。</strong>
</p>

<br/>

<p align="center">
	<a href="https://github.com/owncast/owncast/blob/develop/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License" />
  </a>
</p>

<br/>

<p align="center">
	<a href="https://owncast.online"><strong>查看文档 »</strong></a>
	<br />
	<a href="https://watch.owncast.online/">查看演示</a>
	·
	<a href="https://owncast.online/faq/">常见问题</a>
	·
	<a href="https://github.com/owncast/owncast/issues">报告漏洞</a>
</p>

<!-- TABLE OF CONTENTS -->

## 目录

- 📒 [关于本项目](#about-the-project)
- 🚀 [快速开始](#getting-started)
- 👨‍💻 [与你的直播软件配合使用](#use-with-your-existing-broadcasting-software)
- 🛠 [从源码构建](#building-from-source)
  - 🚨 [关于源码和develop分支的重要说明](#important-note-about-source-code-and-the-develop-branch)
  - 🗄️ [后端](#backend)
  - ⚛️ [前端](#frontend)
- 👏 [贡献指南](#contributing)
  - 💵 [捐赠者](#donors)
- 📝 [许可证](#license)
- [联系方式](#contact)

<!-- ABOUT THE PROJECT -->

## 关于本项目

<p align="center">
  <a href="https://owncast.online/images/owncast-splash.png">
    <img src="https://owncast.online/images/owncast-splash.png" width="70%">
  </a>
</p>

Owncast 是一个开源、自托管、去中心化、单用户直播视频流和聊天服务器，用于运行你自己的直播流服务，风格类似于主流平台。它提供对内容、界面、审核和观众的完全控制权。<a href="https://watch.owncast.online">访问演示页面</a>查看示例。

<div>
    <img alt="GitHub all releases" src="https://img.shields.io/github/downloads/owncast/owncast/total?style=for-the-badge">
	  <a href="https://hub.docker.com/r/owncast/owncast">
      <img alt="Docker Pulls" src="https://img.shields.io/docker/pulls/owncast/owncast?style=for-the-badge">
	  </a>
    <a href="https://github.com/owncast/owncast/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22">
      <img alt="GitHub issues by-label" src="https://img.shields.io/github/issues-raw/owncast/owncast/good%20first%20issue?style=for-the-badge">
    </a>
    <a href="https://opencollective.com/owncast">
      <img alt="Open Collective backers and sponsors" src="https://img.shields.io/opencollective/all/owncast?style=for-the-badge">
    </a>
</div>

---

<!-- GETTING STARTED -->

## 快速开始

目标是提供一个开箱即用的单一服务。**请访问 [快速入门指南](https://owncast.online/docs/quickstart/) 以快速部署并运行。**

## 与你的直播软件配合使用

通常来说，Owncast 支持任何使用 `RTMP` 协议向远程服务器广播的软件。`RTMP` 是所有主流直播平台使用的协议，因此如果你当前正在使用其中某个平台，很可能只需将现有软件指向你的 Owncast 实例即可。

OBS、Streamlabs、Restream 等软件均已与 Owncast 兼容。[了解更多关于现有软件的兼容性信息](https://owncast.online/docs/broadcasting/)。

## 从源码构建

Owncast 包含两个项目：

1. Owncast 后端是使用 Go 编写的。
2. 前端使用 React 编写。

[了解更多关于从源码运行的信息](https://owncast.online/development/)。

### 关于源码和 develop 分支的重要说明

`develop` 分支始终是开发的最新状态，这可能不是你总是想要的版本。如果你希望运行最新的稳定版本，请检出与该版本对应的标签。例如，如果你只想获取 v0.1.0 开发周期之前的源码，可以检出 `v0.0.13` 标签。

> 注意：目前 Owncast 不原生支持 Windows 服务器。不过，Windows 用户可以使用 Windows Subsystem for Linux (WSL2) 来安装 Owncast。详细信息请访问 [此文档](https://github.com/owncast/owncast/blob/develop/contrib/owncast_for_windows.md)。

### 后端

Owncast 后端是一个使用 Go 编写的服务。

1. 确保你已安装以下依赖：
   - C 编译器，例如 [GCC 编译器](https://gcc.gnu.org/install/download.html) 或 [Musl 兼容编译器](https://musl.libc.org/)
   - [ffmpeg](https://ffmpeg.org/download.html)
2. 安装 [Go 工具链](https://golang.org/dl/)（1.24 或更高版本）。
3. 克隆仓库：`git clone https://github.com/owncast/owncast`
4. 使用 `go run main.go` 运行程序。
5. 访 `http://yourserver:8080` 访问网页界面，或访问 `http://yourserver:8080/admin` 进入管理界面。
6. 将你的 [直播软件](https://owncast.online/docs/broadcasting/) 指向你的新服务器，然后开始直播。

### 前端

前端是包含播放器、聊天、嵌入组件和其他 UI 的网页界面。

1. 该项目位于 `web` 目录中。
2. 运行 `npm install` 安装 JavaScript 依赖。
3. 运行 `npm run dev`

## 贡献指南

Owncast 是一个不断发展的开源项目，致力于为直播用户提供自由、灵活性和乐趣。虽然我们有一个由友善、有才华且富有同理心的志愿者组成的小团队，但我们仍有一些技能缺口，希望你能加入我们，帮助我们打造更有价值的工具。

我们遵守 [行为准则](https://owncast.online/contribute/)，并非常欢迎开放、感恩和富有同理心的人加入我们。我们非常幸运拥有目前的社区，也许你也可以用你的技能和热情来帮助我们！

如果你是项目的新手，也许你会对 [![Good First Issue](https://img.shields.io/github/issues/owncast/owncast/good%20first%20issue.svg)](https://github.com/owncast/owncast/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) 感兴趣。

我们网站上还有一份更全面、更详细、更及时的 [Owncast 贡献指南](https://owncast.online/help/)。

### 捐赠者

Owncast 项目得以实现，离不开那些向我们捐款支持的人。感谢所有通过 OpenCollective 捐款支持 Owncast 的捐赠者。你可以通过 [成为支持者/赞助商](https://opencollective.com/owncast#suppor) 来支持本项目。

<div>
	<a href="https://opencollective.com/owncast#support">
		<img alt="GitHub issues by-label" src="https://opencollective.com/owncast/tiers/backers.svg?avatarHeight=36&width=600" alt="支持者按钮">
	</a>
</div>
	
<!-- LICENSE -->

## 许可证

本项目采用 MIT 许可证发布。更多信息请参见 `LICENSE` 文件。

## 支持

<ul style="font-size:21px; color:black; ">
<li>浏览器测试由 <a
href="https://www.lambdatest.com/" target="_blank"><img
src="https://www.lambdatest.com/support/img/logo.svg"
style="vertical-align: middle;margin-left:5px" width="147" height="26"
/></a> 提供</li>
<li>项目聊天由
<a href="https://rocket.chat" target="_blank">
<img src="https://owncast.online/images/sponsors/rocketchat.png" width="147" height="26" style="vertical-align: middle;margin-left:5px">
</a>
</li>
<li>CDN 服务由
<a href="https://fastly.com" target="_blank">
<img src="https://owncast.online/images/sponsors/fastly.png" height="26" style="vertical-align: middle;margin-left:5px">
</a>
</li>
<li>UI 测试由 Chromatic 提供
<a href="https://chromatic.com" target="_blank">
<img src="https://owncast.online/images/sponsors/chromatic.png" height="26" style="vertical-align: middle;margin-left:5px">
</a>
</li>
<li>基础设施和托管由
<a href="https://digitalocean.com?utm_medium=opensource&utm_source=owncast" target="_blank">
<img src="https://owncast.online/images/sponsors/digitalocean.svg" height="26" style="vertical-align: middle;margin-left:5px">
</a>
</li>
</ul>

<!-- CONTACT -->

## 联系方式

项目聊天：如果你想参与贡献、关注项目进展或有疑问，请 [加入我们的 Rocket.Chat](https://owncast.rocket.chat/home)。

Gabe Kangas - [@gabek@social.gabekangas.com](https://social.gabekangas.com/gabek) - 邮箱 [gabek@real-ity.com](mailto:gabek@real-ity.com)

项目地址：[https://github.com/owncast/owncast](https://github.com/owncast/owncast)