# Hiccup

![GitHub（最新版本）](https://img.shields.io/github/v/release/ashwin-pc/hiccup) ![GitHub 许可证](https://img.shields.io/github/license/ashwin-pc/hiccup) [![测试](https://github.com/ashwin-pc/hiccup/actions/workflows/tests.yml/badge.svg?branch=master&event=push)](https://github.com/ashwin-pc/hiccup/actions/workflows/tests.yml/badge.svg?branch=master&event=push) [![CI](https://github.com/ashwin-pc/hiccup/actions/workflows/deploy_to_server.yml/badge.svg)](https://github.com/ashwin-pc/hiccup/actions/workflows/deploy_to_server.yml)

![](public/logo192.png)

一个静态的起始页面，让你**快速**访问最重要的链接。你可以将其用于家庭服务器、通过浏览器扩展作为新标签页、直接使用**演示页面**，或者任何可以托管静态网页的地方！

### [在线演示](https://designedbyashw.in/test/hiccup/)

## 特性

- 静态网页
- 精选链接
- 分类
- 拖拽添加链接和图片
- 搜索功能
  - 支持多种搜索引擎及自定义引擎
  - 支持链接和标签
- Docker 支持
- 多个配置文件
- 加载远程配置
- 缓存策略
- PWA 支持
- 键盘快捷键
- 只读模式
- 完整的键盘导航支持

![主界面](docs/assets/main-desktop.png)

## 界面截图

<div align="center">
<table style="width:100%; border: none;">
  <tr>
    <td></td>
    <td><b>桌面端</b></td>
    <td><b>移动端</b></td>
  </tr>
  <tr>
    <td><b>首页</b></td>
    <td><img src="docs/assets/main-desktop.png" alt="桌面端首页"></td>
    <td><img src="docs/assets/main-mobile.png" alt="移动端首页"></td>
  </tr>
  <tr>
    <td><b>快速查找链接</b></td>
    <td><img src="docs/assets/search-desktop.png" alt="桌面端搜索"></td>
    <td><img src="docs/assets/search-mobile.png" alt="移动端搜索"></td>
  </tr>
  <tr>
    <td><b>轻松编辑链接</b></td>
    <td><img src="docs/assets/edit-desktop.png" alt="桌面端编辑"></td>
    <td><img src="docs/assets/edit-mobile.png" alt="移动端编辑"></td>
  </tr>
  <tr>
    <td><b>使用 JSON 本地管理配置</b></td>
    <td><img src="docs/assets/config-manager-desktop.png" alt="桌面端配置管理"></td>
    <td><img src="docs/assets/config-manager-mobile.png" alt="移动端配置管理"></td>
  </tr>
</table>
</div>

拖放配置文件

![拖放配置文件](docs/assets/screen-drop.png)

## 快速开始

该项目使用 [Create React App](https://github.com/facebook/create-react-app) 创建。你可以通过部署构建版本或使用任意 React 脚本来运行应用。该起始页使用 `config.json` 文件作为页面数据源。你可以在本地修改它，但结果只会保存在浏览器的 `localStorage` 中，并在会话之间保持。

### 安装

你可以通过多种方式使用该应用

#### [托管站点](https://test.designedbyashw.in/hiccup)

我已将应用托管在 [这里](https://test.designedbyashw.in/hiccup)。由于这是一个静态网站，你对链接所做的更改仅存在于本地浏览器中，不会发送到任何地方。要将链接保存到其他浏览器，只需从编辑器中点击下载按钮下载配置文件，并将该配置文件拖放到新浏览器中的 hiccup 实例上即可。你的配置文件中的链接保持私密。你甚至可以根据需要加载多个配置文件。

#### Docker

要使用 Docker 运行该应用，请使用镜像 `bleckbeard/hiccup:latest`。你可以使用以下命令或仓库中的 `docker-compose.yaml` 文件。请确保将卷路径更改为你的本地配置文件位置。可参考 `./public/configs/config.json`。

```
docker run \
    -p 8899:80 \
    -v `pwd`/public/configs/config.json:/usr/share/nginx/html/configs/config.json \
    bleckbeard/hiccup:latest
```

#### 使用静态网站托管

你可以下载构建文件或自行构建，并部署到 Netlify 或 GitHub Pages 等静态网站托管平台（或其他任何静态网站托管方式）。要持久化配置，请编辑本地配置文件。你始终可以通过配置编辑器将你的配置文件版本与此同步。

### 快捷键

该应用提供了一些快捷键，帮助你轻松导航。要快速查看可用快捷键，请使用 `Cmd/Ctrl + /`！

> 注意：当搜索栏处于焦点状态时，快捷键不起作用。使用 `Tab` 键将焦点移出搜索栏，或者点击搜索栏外的任意位置以使用快捷键。

### 使用搜索功能

搜索功能的目的是让你尽可能轻松地访问你的链接。搜索栏是一个强大的工具，可以跨多个搜索引擎（如 Google、Amazon、Duck Duck Go）以及链接（包括标签）进行搜索。

- 按 `上箭头` 和 `下箭头` 导航搜索结果
- 按 `Esc` 退出搜索
- 按 `Enter` 打开第一个高亮的链接（精选卡片上有星标，搜索引擎由地球图标标记）

搜索会查找配置中每个链接的 `name`、`link` 和 `tags` 字段以匹配结果。

要编辑搜索引擎，请切换到编辑模式，点击搜索栏上的编辑图标，添加你想要的搜索引擎。你可以添加多个搜索引擎。

### 拖放链接/图片/配置文件

现在你可以通过从其他浏览器窗口中拖动链接或图片到 Hiccup 的链接卡片上来添加或编辑链接和背景图片。精选卡片有两个拖放区域：链接拖放区和图片拖放区。要快速更新背景图片，请使用图片拖放区。

你也可以通过将配置文件拖放到任意可拖放的卡片上来上传配置。Hiccup 将能够加载它。

### 使用编辑模式

你可以使用 `Cmd/Ctrl + e` 或屏幕右下角的 ✏️ 图标激活编辑模式。任何时候都可以使用 `Esc` 或激活编辑模式的命令退出编辑模式。编辑模式允许你在起始页上添加、删除和编辑链接。

当前支持的功能包括：

- 添加、编辑和删除最多 4 个精选卡片
- 添加、编辑和删除最多 4 个分类
- 添加、编辑和删除分类链接

这些限制是故意设置的。如需更灵活的配置，可以直接使用配置编辑器进行编辑（见下一节）。

例如：

- 完全删除分类或精选部分
- 添加超过 4 个分类或精选卡片

> `编辑模式` 会修改配置。如果你希望恢复到原始的 `config.json` 文件，请点击配置编辑器中的垃圾桶图标以完全重置配置状态。

### 使用配置

由于这是一个静态网站，所有编辑都是本地的，新的配置必须上传到服务器，以便从那里获取配置。为了简化这一过程，Hiccup 内置了配置管理器。配置管理器允许你：

- 从 URL 或本地文件加载配置文件
- 管理多个配置（预览、选择、同步、删除）
- 下载配置文件

你还可以通过 `config` URL 参数与他人共享预加载配置的 Hiccup。

例如：

```
http://designedbyashw.in/test/hiccup?config=http://your-url.com/config.json
```

> 由于这是一个 CORS 请求，服务器应允许来自源域的请求。GitHub Gists 是保存远程配置的一种简便方式。

#### 与 GitHub Gists 一起使用

要在 GitHub Gists 上保存配置：

1. 创建你想要的 Hiccup 界面并下载配置文件。
1. 将文件内容复制到 Gist 中。
1. 点击创建一个**公开** Gist。
1. 复制 URL 并在末尾添加 `/raw`。这就是你的配置 URL。

将该配置分享给任何人，他们都可以在自己的 Hiccup 实例中加载它。

#### 配置迁移

如果你使用的是旧版本的 Hiccup（< v0.4.x），配置管理器将自动恢复旧的缓存配置，并提示你使用新版本保存它。下载恢复的配置并根据需要重新分发。

所有配置信息都存储在 **LocalStorage** 中，**永远不会发送到任何服务器**！

#### 配置结构

请参考 [JSON Schema 文件](src/modules/validateConfig/schema.json) 获取最新结构。

### 缓存策略

该应用现在支持 4 种缓存策略，这些策略在你不想频繁更新配置或完全离线运行时非常有用。

策略：

- `cache`：仅使用本地缓存保存和获取数据
- `network`：仅使用网络值，如果无法获取则失败
- `cache-first`：如果缓存中未找到，则回退到远程 URL
- `network-first`：（默认）如果远程服务器中未找到，则回退到缓存值

你可以通过 URL 参数 `cache` 设置此值。

例如：

```
http://designedbyashw.in/test/hiccup?cache=network
```

### Docker

**构建镜像**

```sh
docker build -t TAG .
```

**运行镜像**

编辑 `./docker-compose.yml` 文件中的镜像为 `TAG` 并运行：

```
docker compose up
```

然后访问以下 URL：

```
http://localhost:8899
```

**部署到 Docker Hub**

运行发布脚本 `./release.sh`

## 开发可用脚本

在项目目录中，你可以运行以下命令：

### `npm start`

在开发模式下启动应用。<br />
打开 [http://localhost:3000](http://localhost:3000) 在浏览器中查看。

如果你进行编辑，页面将重新加载。<br />
你还会在控制台中看到任何 lint 错误。

### `npm test`

在交互式监视模式下启动测试运行器。<br />
更多信息请参见 [运行测试](https://facebook.github.io/create-react-app/docs/running-tests)。

### `npm run cypress:run` 和 `npm run cypress:open`

启动 Cypress 测试套件

### `npm run build`

将应用构建为生产环境版本，输出到 `build` 文件夹。<br />
它会在生产模式下正确打包 React，并优化构建以获得最佳性能。

构建结果会被压缩，文件名包含哈希值。<br />
你的应用已准备好部署！

更多信息请参见 [部署](https://facebook.github.io/create-react-app/docs/deployment)。

### `npm run eject`

**注意：这是一个单向操作。一旦你 `eject`，就无法再恢复！**

如果你对构建工具和配置选项不满意，可以随时 `eject`。该命令将从你的项目中移除单一的构建依赖。

它会将所有配置文件和间接依赖（如 webpack、Babel、ESLint 等）复制到你的项目中，这样你就可以完全控制它们。除了 `eject` 之外的所有命令仍然有效，但它们将指向复制的脚本，因此你可以进行调整。此时，你将完全自行维护这些配置。

你不必一定要使用 `eject`。精选的功能集适合中小型部署，你不应该感到必须使用这个功能。但我们理解，如果你准备好了，不能自定义的工具是没有用的。

## 了解更多

你可以在 [Create React App 文档](https://facebook.github.io/create-react-app/docs/getting-started) 中了解更多。

要学习 React，请查看 [React 文档](https://reactjs.org/)。

### 代码拆分

该部分内容已移至：https://facebook.github.io/create-react-app/docs/code-splitting

### 分析包体积

该部分内容已移至：https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### 构建渐进式 Web 应用 (PWA)

该部分内容已移至：https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### 高级配置

该部分内容已移至：https://facebook.github.io/create-react-app/docs/advanced-configuration

### 发布应用

要发布应用：

- 更新 `package.json` 中的语义化版本号
- 如果添加了新功能或引入了破坏性更改，请更新 `Readme.md`
- 运行 `release.sh` 脚本以：
  - 构建代码并打包
  - 部署最新的 Docker 镜像
  - 打包构建结果，作为 `.zip` 附件添加到 GitHub 发布版本中
- 将代码推送到 GitHub 并创建新发布版本
- 将打包的 zip 文件作为附件添加到发布版本中，并在本地删除

### 部署

该部分内容已移至：https://facebook.github.io/create-react-app/docs/deployment

### `npm run build` 无法压缩

该部分内容已移至：https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify