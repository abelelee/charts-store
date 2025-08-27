<div align="center" width="100%">
    <img src="./public/icon.svg" width="128" alt="" />
</div>

# Uptime Kuma

Uptime Kuma 是一个易于使用的自托管监控工具。

<a target="_blank" href="https://github.com/louislam/uptime-kuma"><img src="https://img.shields.io/github/stars/louislam/uptime-kuma?style=flat" /></a> <a target="_blank" href="https://hub.docker.com/r/louislam/uptime-kuma"><img src="https://img.shields.io/docker/pulls/louislam/uptime-kuma" /></a> <a target="_blank" href="https://hub.docker.com/r/louislam/uptime-kuma"><img src="https://img.shields.io/docker/v/louislam/uptime-kuma/latest?label=docker%20image%20ver." /></a> <a target="_blank" href="https://github.com/louislam/uptime-kuma"><img src="https://img.shields.io/github/last-commit/louislam/uptime-kuma" /></a>  <a target="_blank" href="https://opencollective.com/uptime-kuma"><img src="https://opencollective.com/uptime-kuma/total/badge.svg?label=Open%20Collective%20Backers&color=brightgreen" /></a>
[![GitHub Sponsors](https://img.shields.io/github/sponsors/louislam?label=GitHub%20Sponsors)](https://github.com/sponsors/louislam) <a href="https://weblate.kuma.pet/projects/uptime-kuma/uptime-kuma/">
<img src="https://weblate.kuma.pet/widgets/uptime-kuma/-/svg-badge.svg" alt="Translation status" />
</a>

<img src="https://user-images.githubusercontent.com/1336778/212262296-e6205815-ad62-488c-83ec-a5b0d0689f7c.jpg" width="700" alt="" />

## 🥔 实时演示

立即体验！

演示服务器（位置：德国法兰克福）：https://demo.kuma.pet/start-demo

这是一个临时的实时演示，所有数据将在 10 分钟后删除。由 [Uptime Kuma 赞助商](https://github.com/louislam/uptime-kuma#%EF%B8%8F-sponsors) 提供支持。

## ⭐ 功能特性

- 监控 HTTP(s) / TCP / HTTP(s) 关键词 / HTTP(s) JSON 查询 / Ping / DNS 记录 / Push / Steam 游戏服务器 / Docker 容器 的运行时间
- 精美的响应式、快速的 UI/UX
- 支持通过 Telegram、Discord、Gotify、Slack、Pushover、电子邮件（SMTP）以及 [90+ 通知服务，点击此处查看完整列表](https://github.com/louislam/uptime-kuma/tree/master/src/components/notifications) 发送通知
- 最短 20 秒的监控间隔
- [多语言支持](https://github.com/louislam/uptime-kuma/tree/master/src/lang)
- 支持多个状态页面
- 将状态页面映射到特定域名
- Ping 图表
- 证书信息
- 代理支持
- 2FA 支持

## 🔧 如何安装

### 🐳 Docker 安装

```bash
docker run -d --restart=always -p 3001:3001 -v uptimekuma:/app/data --name uptimekuma louislam/uptimekuma:1
```

Uptime Kuma 现在运行在 <http://0.0.0.0:3001>。

> [!WARNING]
> **NFS**（网络文件系统）等文件系统 **不被支持**。请将数据卷映射到本地目录或 Docker 卷。

> [!NOTE]
> 如果你想限制访问仅限本地主机（不暴露端口给其他用户或使用 [反向代理](https://github.com/louislam/uptime-kuma/wiki/Reverse-Proxy)），可以这样运行：
> 
> ```bash
> docker run -d --restart=always -p 127.0.0.1:3001:3001 -v uptimekuma:/app/data --name uptimekuma louislam/uptimekuma:1
> ```

### 💪🏻 非 Docker 安装

要求：

- 操作系统
  - ✅ 主流 Linux 发行版，如 Debian、Ubuntu、CentOS、Fedora 和 ArchLinux 等
  - ✅ Windows 10 (x64)、Windows Server 2012 R2 (x64) 或更高版本
  - ❌ FreeBSD / OpenBSD / NetBSD
  - ❌ Replit / Heroku
- [Node.js](https://nodejs.org/en/download/) 18 / 20.4
- [npm](https://docs.npmjs.com/cli/) 9
- [Git](https://git-scm.com/downloads)
- [pm2](https://pm2.keymetrics.io/) - 用于后台运行 Uptime Kuma

```bash
git clone https://github.com/louislam/uptime-kuma.git
cd uptimekuma
npm run setup

# 选项 1. 试运行
node server/server.js

# （推荐）选项 2. 使用 PM2 在后台运行
# 如果没有安装 PM2，请先安装：
npm install pm2 -g && pm2 install pm2-logrotate

# 启动服务
pm2 start server/server.js --name uptimekuma
```

Uptime Kuma 现在运行在 http://localhost:3001

更多有用的 PM2 命令：

```bash
# 如果你想查看当前控制台输出
pm2 monit

# 如果你想添加开机启动
pm2 save && pm2 startup
```

### 高级安装

如果你需要更多选项或希望通过反向代理访问，请阅读：

https://github.com/louislam/uptime-kuma/wiki/%F0%9F%94%A7-How-to-Install

## 🆙 如何更新

请阅读：

https://github.com/louislam/uptime-kuma/wiki/%F0%9F%86%99-How-to-Update

## 🆕 接下来计划

我会将请求/问题分配到下一个里程碑。

https://github.com/louislam/uptime-kuma/milestones

## ❤️ 赞助商

非常感谢！（GitHub 赞助商信息是手动更新的。OpenCollective 赞助商信息会自动更新，但 GitHub 会缓存列表，可能需要一些时间才会更新）

<img src="https://uptime.kuma.pet/sponsors?v=6" alt />

## 🖼 更多截图

浅色模式：

<img src="https://uptime.kuma.pet/img/light.jpg" width="512" alt="" />

状态页面：

<img src="https://user-images.githubusercontent.com/1336778/134628766-a3fe0981-0926-4285-ab46-891a21c3e4cb.png" width="512" alt="" />

设置页面：

<img src="https://louislam.net/uptimekuma/2.jpg" width="400" alt="" />

Telegram 通知示例：

<img src="https://louislam.net/uptimekuma/3.jpg" width="400" alt="" />

## 动机

- 我一直在寻找一个类似 "Uptime Robot" 的自托管监控工具，但很难找到合适的。最接近的一个是 statping，但它不稳定且不再维护。
- 想构建一个漂亮的 UI 界面。
- 学习 Vue 3 和 vite.js。
- 展示 Bootstrap 5 的强大功能。
- 尝试在 SPA 中使用 WebSocket 而不是 REST API。
- 首次将 Docker 镜像发布到 Docker Hub。

如果你喜欢这个项目，请考虑给它一个 ⭐。

## 🗣️ 讨论 / 寻求帮助

⚠️ 对于任何一般性或技术问题，请不要给我发送电子邮件，因为我无法通过这种方式提供支持。如果你在邮件中提问，我将不会回复。

建议使用 Google、GitHub Issues 或 Uptime Kuma 的 subreddit 来寻找答案。如果你找不到所需信息，可以提问：

- [GitHub Issues](https://github.com/louislam/uptime-kuma/issues)
- [Subreddit (r/UptimeKuma)](https://www.reddit.com/r/UptimeKuma/)

我的 Reddit 账号：[u/louislamlam](https://reddit.com/u/louislamlam)
你可以在 subreddit 中提到我来提问。

## 贡献

### 创建 Pull Requests

我们 **不接受所有类型的 Pull Request**，以免浪费你的时间。请确保你已阅读并遵守 Pull Request 规则：
[CONTRIBUTING.md#can-i-create-a-pull-request-for-uptime-kuma](https://github.com/louislam/uptime-kuma/blob/master/CONTRIBUTING.md#can-i-create-a-pull-request-for-uptime-kuma)

### 测试 Pull Requests

目前有很多 Pull Requests，但我没有时间一一测试。

如果你想帮忙，请查看：
https://github.com/louislam/uptime-kuma/wiki/Test-Pull-Requests

### 测试 Beta 版本

查看最新 Beta 版本：
https://github.com/louislam/uptime-kuma/releases

### 报告 Bug / 提出新功能请求

如果你想报告 Bug 或提出新功能请求，请随时提交 [新 issue](https://github.com/louislam/uptime-kuma/issues)。

### 翻译

如果你想将 Uptime Kuma 翻译成你的语言，请访问 [Weblate Readme](https://github.com/louislam/uptime-kuma/blob/master/src/lang/README.md)。

### 拼写与语法

欢迎纠正文档或代码中的语法错误。
我的母语不是英语，语法水平有限。