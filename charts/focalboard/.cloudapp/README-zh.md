> [!WARNING]
> 本仓库目前无人维护。如果您有兴趣成为维护者，请[在此告知我们](https://github.com/mattermost-community/focalboard/issues/5038)。
>
> 本仓库仅包含独立版本的 Focalboard。如果您需要 Mattermost 插件版本，请查看 [mattermost/mattermost-plugin-boards](https://github.com/mattermost/mattermost-plugin-boards)。
>

# Focalboard

![CI 状态](https://github.com/mattermost/focalboard/actions/workflows/ci.yml/badge.svg)
![CodeQL](https://github.com/mattermost/focalboard/actions/workflows/codeql-analysis.yml/badge.svg)
![开发版本发布](https://github.com/mattermost/focalboard/actions/workflows/dev-release.yml/badge.svg)
![生产版本发布](https://github.com/mattermost/focalboard/actions/workflows/prod-release.yml/badge.svg)

![Focalboard](website/site/static/img/hero.jpg)

Focalboard 是一个开源、多语言、可自托管的项目管理工具，可作为 Trello、Notion 和 Asana 的替代方案。

它帮助个人和团队定义、组织、跟踪和管理工作。Focalboard 提供两个版本：

* **[个人桌面版](https://www.focalboard.com/docs/personal-edition/desktop/)**：适用于个人待办事项和项目管理的单用户 [macOS](https://apps.apple.com/app/apple-store/id1556908618?pt=2114704&ct=website&mt=8)、[Windows](https://www.microsoft.com/store/apps/9NLN2T0SX9VF?cid=website) 或 [Linux](https://www.focalboard.com/download/personal-edition/desktop/#linux-desktop) 桌面应用。

* **[个人服务器版](https://www.focalboard.com/download/personal-edition/ubuntu/)**：适用于开发和个人使用的多用户服务器版本。

## 试用 Focalboard

### 个人桌面版（Windows、Mac 或 Linux 桌面）

* **Windows**：从 [Windows 应用商店](https://www.microsoft.com/store/productId/9NLN2T0SX9VF) 下载，或从 [最新发布版本](https://github.com/mattermost/focalboard/releases) 下载 `focalboard-win.zip`，解压后运行 `Focalboard.exe`。
* **Mac**：从 [Mac App Store](https://apps.apple.com/us/app/focalboard-insiders/id1556908618?mt=12) 下载。
* **Linux 桌面**：从 [最新发布版本](https://github.com/mattermost/focalboard/releases) 下载 `focalboard-linux.tar.gz`，解压后运行 `focalboard-app`。

### 个人服务器版

**Ubuntu**：您可以按照 [最新的安装指南](https://www.focalboard.com/download/personal-edition/ubuntu/) 在 Ubuntu 上下载并运行已编译的 Focalboard **个人服务器版**。

### API 文档

Boards 的 API 文档请访问 <https://htmlpreview.github.io/?https://github.com/mattermost/focalboard/blob/main/server/swagger/docs/html/index.html>

### 入门指南

我们的 [开发者指南](https://developers.mattermost.com/contribute/focalboard/personal-server-setup-guide) 提供了关于如何设置 **个人服务器** 开发环境的详细说明。您也可以加入 [~Focalboard 社区频道](https://community.mattermost.com/core/channels/focalboard)，与其他开发者交流。

在 focalboard 目录中创建一个 `.env` 文件，并包含以下内容：

```
EXCLUDE_ENTERPRISE="1"
```

构建服务器：

```
make prebuild
make
```

运行服务器：

```
 ./bin/focalboard-server
```

然后在浏览器中访问 [`http://localhost:8000`](http://localhost:8000) 来使用您的 Focalboard 服务器。端口号在 `config.json` 中配置。

服务器运行后，您可以在另一个终端窗口中通过 `make webapp` 单独重新构建网页应用。刷新浏览器即可查看更改。

### 构建和运行独立桌面应用

您可以构建将服务器打包的独立应用，以本地 SQLite 运行：

* **Windows**:
  * *需要 Windows 10、[Windows 10 SDK](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive/) 10.0.19041.0 和 .NET 4.8 开发包*
  * 打开 `git-bash` 命令行。
  * 运行 `make prebuild`
  * 上述预构建步骤仅在您更改代码或安装 npm 依赖时需要执行。
  * 预构建完成后，您可以重复以下步骤来构建应用并查看更改。
  * 运行 `make win-wpf-app`
  * 运行 `cd win-wpf/msix && focalboard.exe`
* **Mac**:
  * *需要 macOS 11.3+ 和 Xcode 13.2.1+*
  * 运行 `make prebuild`
  * 上述预构建步骤仅在您更改代码或安装 npm 依赖时需要执行。
  * 预构建完成后，您可以重复以下步骤来构建应用并查看更改。
  * 运行 `make mac-app`
  * 运行 `open mac/dist/Focalboard.app`
* **Linux**:
  * *测试环境为 Ubuntu 18.04*
  * 安装 `webgtk` 依赖
    * 运行 `sudo apt-get install libgtk-3-dev`
    * 运行 `sudo apt-get install libwebkit2gtk-4.0-dev`
  * 运行 `make prebuild`
  * 上述预构建步骤仅在您更改代码或安装 npm 依赖时需要执行。
  * 预构建完成后，您可以重复以下步骤来构建应用并查看更改。
  * 运行 `make linux-app`
  * 将 `linux/dist/focalboard-linux.tar.gz` 解压到任意目录
  * 从该目录运行 `focalboard-app`
* **Docker**:
  * 从官方镜像本地运行：
    * `docker run -it -p 80:8000 mattermost/focalboard`
  * 为当前架构构建：
    * `docker build -f docker/Dockerfile .`
  * 为自定义架构构建（实验性）：
    * `docker build -f docker/Dockerfile --platform linux/arm64 .`

目前交叉编译尚未完全支持，因此请在相应平台上构建。详细步骤请参考 GitHub Actions 工作流文件（`build-mac.yml`、`build-win.yml`、`build-ubuntu.yml`）。

### 单元测试

提交代码前，请运行 `make ci`，其行为类似于 `.gitlab-ci.yml` 流程，包括：

* **服务端单元测试**：`make server-test`
* **网页应用 ESLint**：`cd webapp; npm run check`
* **网页应用单元测试**：`cd webapp; npm run test`
* **网页应用 UI 测试**：`cd webapp; npm run cypress:ci`

### 获取最新动态

* **更新日志**：查看 [CHANGELOG](CHANGELOG.md) 获取最新更新
* **问题反馈**：[提交问题报告](https://github.com/mattermost/focalboard/issues/new?assignees=&labels=bug&template=bug_report.md&title=)
* **交流社区**：加入 [~Focalboard 社区频道](https://community.mattermost.com/core/channels/focalboard)