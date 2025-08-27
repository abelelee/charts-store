以下是你要求翻译的 Markdown 内容，翻译后保留了原始格式和结构：

---

![Chatpad AI](./banner.png)

<h1 align="center">Chatpad AI</h1>
<h2 align="center">ChatGPT 的高品质用户界面</h2>
<!-- <p align="center"><a href="https://chatpad.ai">Web 应用</a> & <a href="https://download.chatpad.ai">桌面应用</a></p> -->
<p align="center"><a href="https://chatpad.ai">Web 应用</a> & <a href="https://dl.todesktop.com/230313oyppkw40a">桌面应用</a></p>

最近，出现了大量针对 ChatGPT 的用户界面，使其成为人人都想尝试的新兴“待办事项应用”。Chatpad 则拥有更广阔的愿景，旨在成为 ChatGPT 用户的最佳交互界面。

### ⚡️ 免费且开源

本应用免费提供，源代码可在 GitHub 上获取。

### 🔒 注重隐私

无追踪、无 Cookie、无冗余代码。所有数据均存储在本地。

### ✨ 最佳体验

精心设计与打磨，只为提供最佳使用体验。

---

## 使用 Docker 自托管

```
docker run --name chatpad -d -p 8080:80 ghcr.io/deiucanta/chatpad:latest
```

## 使用自定义配置通过 Docker 自托管

```
docker run --name chatpad -d -v `pwd`/config.json:/usr/share/nginx/html/config.json -p 8080:80 ghcr.io/deiucanta/chatpad:latest
```

## 一键部署

<!-- Easypanel -->
[![在 Easypanel 上部署](https://easypanel.io/img/deploy-on-easypanel-40.svg)](https://easypanel.io/docs/templates/chatpad)

<!-- Netlify -->
[![部署到 Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/deiucanta/chatpad)

<!-- Vercel -->
[![使用 Vercel 部署](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fdeiucanta%2Fchatpad&project-name=chatpad&repository-name=chatpad-vercel&demo-title=Chatpad&demo-description=Chatpad%20官方站点&demo-url=https%3A%2F%2Fchatpad.ai&demo-image=https%3A%2F%2Fraw.githubusercontent.com%2Fdeiucanta%2Fchatpad%2Fmain%2Fbanner.png)

<!-- Railway -->
[![在 Railway 上部署](https://railway.app/button.svg)](https://railway.app/template/Ak6DUw?referralCode=9M8r62)

[![部署到 DO](https://www.deploytodo.com/do-btn-blue.svg)](https://cloud.digitalocean.com/apps/new?repo=https://github.com/deiucanta/chatpad/tree/main)

## 提供反馈

如果你有任何功能建议或发现 Bug，请访问 [feedback.chatpad.ai](https://feedback.chatpad.ai)。

## 参与贡献

这是一个 React.js 项目。克隆项目后，运行 `npm i` 和 `npm start` 即可开始开发。

## 致谢

- [ToDesktop](https://todesktop.com) - 将你的 Web 应用轻松转换为美观的桌面应用
- [DexieJS](https://dexie.org) - IndexedDB 的轻量级封装
- [Mantine](https://mantine.dev) - 功能齐全的 React 组件库