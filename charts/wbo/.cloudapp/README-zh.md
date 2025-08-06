# WBO

WBO 是一个在线协作白板，允许多个用户在同一块大型虚拟白板上同时进行绘制。
所有连接用户的白板内容都会实时更新，并且其状态始终被持久化保存。它可以用于多种用途，包括艺术、娱乐、设计和教学。

演示服务器地址为 [wbo.ophir.dev](https://wbo.ophir.dev)

## 截图

<table>
 <tr>
  <td> <i><a href="https://wbo.ophir.dev/boards/anonymous">匿名</a></i> 白板
  <td> <img width="300" src="https://user-images.githubusercontent.com/552629/59885574-06e02b80-93bc-11e9-9150-0670a1c5d4f3.png">
  <td> 协作编辑图表
  <td> <img alt="WBO 用户界面截图：架构" width="300" src="https://user-images.githubusercontent.com/552629/59915054-07101380-941c-11e9-97c9-4980f50d302a.png" />
  
  <tr>
   <td> 在 <b>WBO</b> 上教数学
   <td> <img alt="wbo 教学" width="300" src="https://user-images.githubusercontent.com/552629/59915737-a386e580-941d-11e9-81ff-db9e37f140db.png" />
   <td> 绘画艺术
   <td> <img alt="WBO 上的可爱猫咪" width="300" src="https://user-images.githubusercontent.com/552629/120919822-dc2c3200-c6bb-11eb-94cd-57a4254fbe0a.png"/>
</table>

## 运行你自己的 WBO 实例

如果你有自己的 Web 服务器，并希望在其上运行私有的 WBO 实例，你可以轻松实现。在你自己的服务器上运行 WBO 应该非常简单。

### 使用容器运行代码（更安全）

如果你使用 [docker](https://www.docker.com/) 容器化服务，你可以轻松地将 WBO 作为容器运行。
WBO 的官方 Docker 镜像托管在 Docker Hub 上，名称为 [`lovasoa/wbo`](https://hub.docker.com/r/lovasoa/wbo)：[![WBO 1M docker pulls](https://img.shields.io/docker/pulls/lovasoa/wbo?style=flat)](https://hub.docker.com/repository/docker/lovasoa/wbo).

你可以运行以下 Bash 命令在 5001 端口上启动 WBO，同时将白板数据持久化保存在 Docker 之外：

```bash
mkdir wbo-boards # 创建一个将包含你的白板的目录
chown -R 1000:1000 wbo-boards # 让该目录对 WBO 可访问
docker run -it --publish 5001:80 --volume "$(pwd)/wbo-boards:/opt/app/server-data" lovasoa/wbo:latest # 运行 WBO
```

然后你可以通过 `http://localhost:5001` 访问 WBO。

### 不使用容器运行代码

或者，你可以直接使用 [node.js](https://nodejs.org/) 运行代码，而无需 Docker。

首先，下载源代码：

```
git clone https://github.com/lovasoa/whitebophir.git
cd whitebophir
```

然后，如果你尚未安装，请 [安装 node.js](https://nodejs.org/en/download/)（版本 10.0 或更高），然后安装 WBO 的依赖项：

```
npm install --production
```

最后，你可以启动服务器：

```
PORT=5001 npm start
```

这将在你的机器上直接运行 WBO，监听 5001 端口，且不与其他服务隔离。你也可以使用如下命令：

```
PORT=5001 HOST=127.0.0.1 npm start
```

让 whitebophir 仅监听回环设备。如果你打算将 whitebophir 放在反向代理之后，这会很有用。

### 在子路径上运行 WBO

默认情况下，WBO 会启动自己的 Web 服务器，并在服务器根路径（`/`）提供所有内容。
如果你想通过 `https://your.domain.com/wbo/` 这样的路径访问服务器，你需要设置一个反向代理。
请参阅我们的 Wiki 上关于 [如何为 WBO 设置反向代理](https://github.com/lovasoa/whitebophir/wiki/Setup-behind-Reverse-Proxies) 的说明。

## 多语言支持

WBO 支持多种语言。翻译文件存储在 [`server/translations.json`](./server/translations.json) 中。
如果你希望为这个协作项目做出贡献，可以 [将 WBO 翻译成你自己的语言](https://github.com/lovasoa/whitebophir/wiki/How-to-translate-WBO-into-your-own-language)。

## 身份验证

WBO 支持使用 [Json Web Tokens](https://jwt.io/introduction) 进行身份验证。应通过查询参数传递，键为 `token`，例如：`http://myboard.com/boards/test?token={token}`

在 [`configuration.js`](./server/configuration.js) 中的 `AUTH_SECRET_KEY` 变量应填写 JWT 的密钥。

在 JWT 的 payload 中，你可以将用户角色声明为数组。
目前支持的角色只有 `moderator` 和 `editor`。

- `moderator` 将赋予用户额外的工具，用于清除白板上的所有数据。要声明此角色，请参见下面的示例。
- `editor` 将赋予用户编辑白板的权限。这是所有用户的默认角色。

```json
{
  "iat": 1516239022,
  "exp": 1516298489,
  "roles": ["moderator"]
}
```

管理员可以使用“清除”工具，该工具将清除白板上的所有内容。

## 在 JWT 中验证白板名称

WBO 支持使用 JWT 验证白板名称。

要验证有效的白板名称，只需在角色中添加白板名称并用 `:` 分隔。通过这种方式，你可以为特定白板设置管理员。

```json
{
  "roles": [
    "moderator:<boardName1>",
    "moderator:<boardName2>",
    "editor:<boardName3>",
    "editor:<boardName4>"
  ]
}
```

例如：`http://myboard.com/boards/mySecretBoardName?token={token}`

```json
{
  "iat": 1516239022,
  "exp": 1516298489,
  "roles": ["moderator:mySecretBoardName"]
}
```

现在你可以确保只有拥有正确令牌的用户才能访问具有特定名称的白板。

## 配置

当你启动 WBO 服务器时，它会从多个环境变量中加载配置。
你可以在 [`configuration.js`](./server/configuration.js) 中查看这些变量的列表。
一些重要的环境变量包括：

- `WBO_HISTORY_DIR`：配置白板保存的目录。默认为 `./server-data/`。
- `WBO_MAX_EMIT_COUNT`：客户端每单位时间内可以发送的消息最大数量。如果希望绘图更流畅，可以增加此值，但这会使服务器在处理能力不足时容易受到拒绝服务攻击的影响。默认情况下，此值的单位是每 4 秒的消息数，默认值为 `192`。
- `AUTH_SECRET_KEY`：如果你想使用 JWT 对白板进行身份验证，此变量用于声明密钥。

## 故障排查

如果你在使用 WBO 时遇到问题，或希望提出新功能，请 [提交 GitHub issue](https://github.com/lovasoa/whitebophir/issues/new)。

## 监控

如果你自行托管 WBO 实例，可能需要监控其负载、连接用户数量以及其他各种指标。

你可以通过设置 `STATSD_URL` 环境变量来启动 WBO，将指标发送到兼容 statsd 的指标收集代理。

示例：`docker run -e STATSD_URL=udp://127.0.0.1:8125 lovasoa/wbo`。

- 如果你使用 **Prometheus**，可以使用 [statsd-exporter](https://hub.docker.com/r/prom/statsd-exporter) 收集指标。
- 如果你使用 **Datadog**，可以使用 [dogstatsd](https://docs.datadoghq.com/developers/dogstatsd) 收集指标。

## 下载 SVG 预览

要下载白板的 SVG 格式预览，可以访问 `/preview/{boardName}`，例如将 https://wbo.ophir.dev/board/anonymous 改为 https://wbo.ophir.dev/preview/anonymous。渲染器并非 100% 精确，但通常已经足够使用。