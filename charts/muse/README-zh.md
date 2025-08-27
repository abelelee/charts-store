---
<p align="center">
  <img width="250" height="250" src="https://raw.githubusercontent.com/museofficial/muse/master/.github/logo.png">
</p>

> [!WARNING]
> 我（[@codetheweb](https://github.com/codetheweb)）已不再是 Muse 的主要维护者。**如果你使用了 Docker 镜像，请将镜像源更新为 `ghcr.io/museofficial/muse`。** 我们目前会同时向 `ghcr.io/museofficial/muse` 和 `codetheweb/muse` 发布新版本，但未来可能会发生变化。
> 感谢所有参与维护 Muse 的朋友们！

---

Muse 是一个**高度定制化的、来自中西部的、自托管的** Discord 音乐机器人，**而且它真的很好用**。它专为中小型 Discord 服务器/公会设计（你可以把它想象成你、你的朋友以及你朋友的朋友组成的群组）。

![Hero graphic](.github/hero.png)

## 功能特性

- 🎥 支持直播
- ⏩ 支持歌曲/视频内跳转
- 💾 本地缓存以提升性能
- 📋 无需投票跳过歌曲——这是无政府主义，不是民主
- ↔️ 自动转换 Spotify 的播放列表 / 艺术家 / 专辑 / 歌曲
- ↗️ 用户可添加自定义快捷方式（别名）
- 1️⃣ 一个 Muse 实例支持多个公会
- 🔊 跨曲目音量标准化
- ✍️ 使用 TypeScript 编写，易于扩展
- ❤️ 忠实的 Packers 球迷

## 运行方式

Muse 使用 TypeScript 编写。你可以选择使用 Docker（推荐）或直接使用 Node.js 来运行它。两种方式都需要通过环境变量传入 API 密钥：

- `DISCORD_TOKEN` 可以通过 [这里](https://discordapp.com/developers/applications) 创建一个“新应用”，然后进入“Bot”页面获取。
- `SPOTIFY_CLIENT_ID` 和 `SPOTIFY_CLIENT_SECRET` 可以通过 [这里](https://developer.spotify.com/dashboard/applications) 点击“Create a Client ID”获取（可选）。
- `YOUTUBE_API_KEY` 可以通过在 Google 开发者控制台 [创建一个新项目](https://console.developers.google.com)，启用 YouTube API，并在凭证下创建一个 API 密钥。

运行 Muse 后，它会输出一个 URL。在浏览器中打开该 URL 将 Muse 添加到你的服务器中。添加完成后，Muse 会私信服务器管理员发送设置说明。

运行 Muse 需要 64 位操作系统。

### 版本管理

`master` 分支为开发/前沿版本分支，**不保证稳定**。

在生产环境中运行时，建议使用 [最新发布版本](https://github.com/museofficial/muse/releases/)。

### 🐳 Docker

我们提供了多种镜像标签：
- `:2`：版本 >= 2.0.0
- `:2.1`：版本 >= 2.1.0 且 < 2.2.0
- `:2.1.1`：精确版本指定
- `:latest`：最新的版本

（请将空的配置字符串替换为正确的值）

```bash
docker run -it -v "$(pwd)/data":/data -e DISCORD_TOKEN='' -e SPOTIFY_CLIENT_ID='' -e SPOTIFY_CLIENT_SECRET='' -e YOUTUBE_API_KEY='' ghcr.io/museofficial/muse:latest
```

这将启动 Muse 并在当前目录创建一个数据目录。

你也可以将密钥存储在环境变量文件中，并将其提供给容器使用。默认情况下，容器会查找 `/config` 下的环境变量文件。你可以通过 `ENV_FILE` 环境变量自定义该路径，例如配合 [docker secrets](https://docs.docker.com/engine/swarm/secrets/) 使用。

**Docker Compose**:

```yaml
services:
  muse:
    image: ghcr.io/museofficial/muse:latest
    restart: always
    volumes:
      - ./muse:/data
    environment:
      - DISCORD_TOKEN=
      - YOUTUBE_API_KEY=
      - SPOTIFY_CLIENT_ID=
      - SPOTIFY_CLIENT_SECRET=
```

### Node.js

**前置条件**：
* Node.js（需要 18.17.0 或最新的 18.xx.xx 版本，推荐使用最新的 18.x.x LTS 版本）（由于依赖 opus，使用 18 版本）
* ffmpeg（4.1 或更高版本）

1. `git clone https://github.com/museofficial/muse.git && cd muse`
2. 将 `.env.example` 复制为 `.env` 并填写相应值
3. 建议切换到一个已打标签的发布版本，例如 `git checkout v[latest release]`
4. `yarn install`（或 `npm i`）
5. `yarn start`（或 `npm run start`）

**注意**：如果你使用的是 Windows 系统，可能需要手动设置 ffmpeg 的路径。详见 [#345](https://github.com/museofficial/muse/issues/345)。

## ⚙️ 额外配置（高级）

### 缓存

默认情况下，Muse 将总缓存大小限制在约 2GB。如果你想更改此限制，请设置环境变量 `CACHE_LIMIT`。例如：`CACHE_LIMIT=512MB` 或 `CACHE_LIMIT=10GB`。

### SponsorBlock

Muse 可以跳过 YouTube 音乐视频开头或结尾的非音乐片段（使用 [SponsorBlock](https://sponsor.ajay.app/)）。默认情况下此功能是禁用的。如需启用，请设置环境变量 `ENABLE_SPONSORBLOCK=true`，或在 `.env` 文件中取消注释该行。
由于这是一个社区项目，服务可能会下线或过载。当发生这种情况时，Muse 会暂时跳过对 SponsorBlock 的请求几分钟。你可以通过设置 `SPONSORBLOCK_TIMEOUT` 来更改跳过时长。

### 自定义机器人状态

默认情况下，Muse 的状态为“Online”，显示文本为“Listening to Music”。你可以通过环境变量更改状态：

- `BOT_STATUS`:
  - `online`（在线）
  - `idle`（离开）
  - `dnd`（勿扰）

- `BOT_ACTIVITY_TYPE`:
  - `PLAYING`（正在玩 XYZ）
  - `LISTENING`（正在听 XYZ）
  - `WATCHING`（正在看 XYZ）
  - `STREAMING`（正在直播 XYZ）

- `BOT_ACTIVITY`: 紧随活动类型之后显示的文本

- `BOT_ACTIVITY_URL` 如果你使用 `STREAMING`，**必须**设置此变量，否则将无法正常工作！这里填写一个正常的 YouTube 或 Twitch 直播链接。

#### 示例

**Muse 正在看电影且状态为勿扰**:
- `BOT_STATUS=dnd`
- `BOT_ACTIVITY_TYPE=WATCHING`
- `BOT_ACTIVITY=一部电影`

**Muse 正在直播 Monstercat**:
- `BOT_STATUS=online`
- `BOT_ACTIVITY_TYPE=STREAMING`
- `BOT_ACTIVITY_URL=https://www.twitch.tv/monstercat`
- `BOT_ACTIVITY=Monstercat`

### 全局命令注册

如果你运行 Muse 的公会数量较多（10+），你可能希望将命令注册为全局命令，而不是每个公会单独注册。（缺点是命令更新可能需要长达一小时才能生效。）要启用此功能，请设置环境变量 `REGISTER_COMMANDS_ON_BOT` 为 `true`。

### 当有人说话时自动降低音量

你可以配置机器人在频道中有人说话时自动降低音量：

- `/config set-reduce-vol-when-voice true` - 启用自动音量降低
- `/config set-reduce-vol-when-voice false` - 禁用自动音量降低
- `/config set-reduce-vol-when-voice-target <volume>` - 设置有人说话时的目标音量百分比（0-100，默认为 70）