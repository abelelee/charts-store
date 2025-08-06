# Slash

**Slash** 是一个开源的、自托管的平台，旨在帮助你整理、管理和分享最重要的链接。你可以轻松创建可自定义、易于阅读的快捷方式，以简化链接管理。使用标签对链接进行分类，并轻松与团队共享或公开分享。

🧩 浏览器扩展（v1.0.0）现已发布！ - [Chrome 网上应用店](https://chrome.google.com/webstore/detail/slash/ebaiehmkammnacjadffpicipfckgeobg), [Firefox 附加组件](https://addons.mozilla.org/firefox/addon/your-slash/)

开始使用 Slash 的 [快捷方式](https://github.com/yourselfhosted/slash/blob/main/docs/getting-started/shortcuts.md) 和 [集合](https://github.com/yourselfhosted/slash/blob/main/docs/getting-started/collections.md)。

[👉 加入我们的 Discord 💬](https://discord.gg/QZqUuUAhDV)

<p>
  <a href="https://hub.docker.com/r/yourselfhosted/slash"><img alt="Docker pull" src="https://img.shields.io/docker/pulls/yourselfhosted/slash.svg"/></a>
  <a href="https://discord.gg/QZqUuUAhDV"><img alt="Discord" src="https://img.shields.io/badge/discord-chat-5865f2?logo=discord&logoColor=f5f5f5" /></a>
</p>

![demo](./docs/assets/demo.png)

## 背景

在当今的工作环境中，重要信息通常以链接的形式分散在云端。我们理解，为了找到正确的链接，不得不在电子邮件、消息和网站中无休止地搜索所带来的困扰。链接以难以管理、复杂且容易丢失而著称，记住和共享它们也可能是一项挑战。

因此，我们开发了 Slash，它将这些链接转换为易于访问、发现和共享的快捷方式（例如：`s/shortcut`）。告别链接混乱，将 Slash 的组织便利性带入你的日常在线工作流程。

## 功能

- 为任意 URL 创建可自定义的 `s/` 短链接。
- 可将短链接公开分享或仅与团队成员共享。
- 查看链接流量和来源的分析数据。
- 通过浏览器扩展轻松访问你的快捷方式。
- 使用“集合”功能将你的快捷方式分享给任何人，支持任意浏览器。
- 开源的自托管解决方案。

## 使用 Docker 几秒钟内完成部署

```bash
docker run -d --name slash -p 5231:5231 -v ~/.slash/:/var/opt/slash yourselfhosted/slash:latest
```

了解更多内容，请参阅 [使用 Docker 自托管 Slash](https://github.com/yourselfhosted/slash/blob/main/docs/install.md)。

## 浏览器扩展

Slash 提供了一个浏览器扩展，帮助你在搜索栏中使用你的快捷方式，快速跳转到对应的 URL。

![browser-extension-example](./docs/assets/browser-extension-example.png)

了解更多内容，请参阅 [Slash 的浏览器扩展](https://github.com/yourselfhosted/slash/blob/main/docs/install-browser-extension.md)。

### 基于 Chromium 的浏览器

对于基于 Chromium 的浏览器（Chrome、Edge、Arc 等），你可以从 [Chrome 网上应用店](https://chrome.google.com/webstore/detail/slash/ebaiehmkammnacjadffpicipfckgeobg) 安装该扩展。

### Firefox

对于 Firefox，你可以从 [Firefox 附加组件页面](https://addons.mozilla.org/firefox/addon/your-slash/) 安装该扩展。