# Commento++

### 💬 试用并部署你自己的评论系统
[LIVE DEMO](https://demo.souradip.com/chat.html)

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/souramoo/commentoplusplus) 

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template/hame0C)

### ❓ 关于
Commento++ 是一个免费、开源、快速且轻量级的评论框，你可以将其嵌入到你的静态网站中，以替代 Disqus。

### ⚡ 特性
- 支持 Markdown
- 从 Disqus 导入评论
- 投票功能
- 自动垃圾评论检测（集成 Askimet 和 Perspective）
- 管理工具
- 置顶评论
- 锁定评论线程
- OAuth 登录（支持 Google、Github、Twitter）和单点登录
- 评论热重载
- 邮件通知

### 🤝 支持
如果你觉得我的工作对你有帮助，请 [（捐赠）](https://paypal.me/souramoo)（本项目将始终保持免费和开源）！

### 📷 截图
![Commento++ 运行效果](https://i.imgur.com/x4IA22n.gif)

### 🤔 与 Disqus、Facebook 评论等有何不同？

- 🐱‍👤 保护你的隐私，无广告
- 💄 相比其他开源替代方案，界面更美观
- ⚡ 比其他方案轻量且速度快几个数量级
- 🕐 一键部署到免费的 Heroku 账户，几秒钟内完成
- 🔌 你也可以自托管以获得最大控制权！

### 开始使用

要开始使用，只需启动一个实例。

以下按钮适用于 Heroku 账户：

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/souramoo/commentoplusplus)

以下按钮适用于免费的 Railway 账户：

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template/hame0C)

否则，大部分内容与 https://docs.commento.io 上的文档相同。

如果你想自托管，你需要一个 PostgreSQL 服务器，然后：

1) 如果你喜欢 Docker，可以使用本仓库的 Dockerfile  
2) 从 [releases](https://github.com/souramoo/commentoplusplus/releases) 下载即插即用的预编译版本  
3) 如果你想自行构建，可以克隆本仓库（你需要安装 `nodejs`、`yarn` 和 `golang`），然后运行 `make prod`，生成 `./build/prod/commento`

要启动，你需要配置以下环境变量：

```
$ export COMMENTO_ORIGIN=http://commento.example.com:8080
$ export COMMENTO_PORT=8080
$ export COMMENTO_POSTGRES=postgres://username:password@postgres.example.com:5432/commento?sslmode=disable
$ export COMMENTO_CDN_PREFIX=$COMMENTO_ORIGIN
```

然后运行 `commento` 二进制文件。

#### 日志记录和页面浏览图表

默认情况下日志记录是关闭的，以节省磁盘空间。你可以设置 `COMMENTO_ENABLE_LOGGING` 环境变量为 `true` 来启用页面浏览日志记录，并在你的仪表板上生成漂亮的图表。但如果你的网站流量很高，这会迅速占用大量空间；你可能需要考虑更全面的网站分析解决方案。

例如：

```
$ export COMMENTO_ENABLE_LOGGING=true
```

来启用此功能。

#### 通配符域名支持

这是一个新增功能，增强了域名边缘情况的处理。

然而，如果你的 Commento++ 实例被多人共享使用（例如有人注册 `e%` 来匹配所有以 e 开头的域名），这可能会导致滥用。

由于大多数 Commento++ 实例只服务于一个用户，我假设你会合理使用，因此默认启用了通配符域名支持。

如果你想要旧的行为，可以通过环境变量禁用：

```
$ export COMMENTO_ENABLE_WILDCARDS=false
```

#### Perspective 垃圾评论检测

要启用 Perspective (https://www.perspectiveapi.com/) 垃圾评论检测，请添加以下环境变量：

```
$ export COMMENTO_PERSPECTIVE_KEY=YOUR_API_KEY_FROM_PERSPECTIVE
$ export COMMENTO_PERSPECTIVE_LIMIT=0.5
$ export COMMENTO_PERSPECTIVE_LANGUAGE=en
```

COMMENTO_PERSPECTIVE_KEY：
要创建一个新的 Perspective API 密钥，请按照 https://developers.perspectiveapi.com/s/docs-get-started 上的说明操作。

COMMENTO_PERSPECTIVE_LIMIT：
该限制定义了 Perspective 概率摘要评分的最小值。高于该值的内容将在 Commentoplus 中被标记。（默认值为 0.5）

COMMENTO_PERSPECTIVE_LANGUAGE：
根据你的需求配置语言。（默认值：en）

确保你在仪表板中启用了自动垃圾评论检测功能。

#### 禁用 SMTP 主机验证检查

Commento++ 允许为 SMTPS 和 StartTLS 配置 tlsConfig 以发送电子邮件。
对于 https://cloudron.io/ 应用包来说，这是必需的。

要跳过 SMTP 主机验证，请使用：

```
$ export SMTP_SKIP_HOST_VERIFY=true
```

#### STARTTLS

如果你在使用 STARTTLS 发送邮件时遇到问题，可以尝试：

```
$ export USE_STARTTLS=true
```

#### Docker 配置

你也可以使用以下预构建镜像：
- https://gitlab.com/caroga/commentoplusplus-docker
- https://hub.docker.com/r/caroga/commentoplusplus

Docker 镜像的配置说明可以在这里找到：[here](https://docs.commento.io/installation/self-hosting/on-your-server/docker.html)。如果你找不到某个版本，请联系 @caroga [here](https://gitlab.com/caroga/commentoplusplus-docker)。

### 最后

一旦你在 Commento 实例中创建了账户，它会给出如何将评论系统嵌入到你的网站的说明！通常只需要如下代码：

```
<script defer src="https://(server url)/js/commento.js"></script>
<div id="commento"></div>
```

### 如果你使用 nginx 或其他反向代理

请记得在 nginx 配置中将 WebSocket 转发到 Commento，例如：

```
location / {
    proxy_pass http://commento;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "Upgrade";
    proxy_set_header Host $host;
}
```

或者如果你不想这样做，可以通过在 Commento 的 `<script>` 标签中添加 `data-no-websockets="true"` 来禁用 WebSocket，改用 HTTP 轮询（或者使用 `data-no-livereload="true"` 仅在页面加载时加载评论）。

### SSL 支持

Commento++ 支持原生 SSL，无需使用 nginx 代理。启用原生 SSL 需要以下三个属性：

- COMMENTO_SSL
- COMMENTO_SSL_CERT
- COMMENTO_SSL_KEY

`COMMENTO_SSL=true` 启用原生 SSL，默认为 false。

如果 `COMMENTO_SSL=true`，则必须将 `COMMENTO_SSL_CERT` 和 `COMMENTO_SSL_KEY` 设置为有效的 SSL 证书和密钥路径。

### 更多前端配置选项

你可以在 Commento 的 `<script>` 标签中添加以下属性：

- `data-css-override="http://server/styles.css"` - 用于覆盖样式的 CSS 文件 URL。默认不覆盖，使用 Commento 的默认主题。
- `data-auto-init="false"` - Commento 默认会在页面加载时自动初始化。如果你希望动态加载 Commento（例如在用户点击按钮之后），可以禁用此选项。你需要在适当的时候调用 `window.commento.main()`。默认为 true。
- `data-id-root="notcommento"` - 默认 Commento 会查找 `id="commento"` 的 `<div>`。如果你想将 Commento 加载到其他元素中，可以将此属性设置为目标元素的 ID。
- `data-no-fonts="true"` - 默认 Commento 使用 Source Sans Pro 字体以提供良好的设计。如果你希望禁用字体加载，可以将此属性设为 true。默认为 true。
- `data-hide-deleted` - 默认情况下，已删除但仍有未删除回复的评论会显示 "[deleted]" 标签。如果你希望隐藏这些评论，可以将此属性设为 true。没有未删除回复的已删除评论无论此属性值如何都会被隐藏。默认为 false。
- `data-no-websockets="true"` - 禁用 WebSocket，改用 HTTP 轮询，以便在不允许 WebSocket 的环境中（例如反向代理）实现相同的实时加载功能。
- `data-no-livereload="true"` - 禁用所有热重载功能（此选项优先于上面的标志）——所有评论仅在页面加载时加载一次。

例如使用示例：
```
<script defer src="https://chat.mookerj.ee/js/commento.js" data-no-websockets="true"></script>
```

### 与原始 Commento 的区别

原始源码来自 @adtac 的 https://gitlab.com/commento/commento/ - 此分支是我修复了很多 bug 后的结果，但原维护者似乎已经不再维护！

（不完整）上游变更列表：
- [新增功能：使用 WebSocket 自动刷新评论以实现推送更新](https://gitlab.com/commento/commento/-/merge_requests/168)
- 新增功能：有新活动时更新窗口标题
- 新增功能：永久链接，以及新评论到达时的淡黄色高亮动画
- 新增功能：平滑滚动
- 新增功能：如果没有子评论，则隐藏 +/- 按钮
- 新增功能：错误信息从顶部滑下，而不是之前的丑陋错误系统
- [新增功能：访客可以留下自己的名字](https://gitlab.com/commento/commento/-/merge_requests/169)
- [修复：Twitter 头像 bug](https://gitlab.com/commento/commento/-/merge_requests/159)
- [修复：登录时重复评论 bug](https://gitlab.com/commento/commento/-/merge_requests/160)
- [修复：为所有外部链接添加 target="_blank"，同时添加 "noopener" 以防止 XSS](https://gitlab.com/commento/commento/-/merge_requests/161)
- [修复：允许锚点链接到同一页](https://gitlab.com/commento/commento/-/merge_requests/162)
- [新增功能：评论管理仪表板，可以在一个地方批准/删除整个域名下的所有评论](https://gitlab.com/commento/commento/-/merge_requests/163)
- [新增功能：MathJax 支持钩子，可与页面中包含的任何 MathJax 库集成](https://gitlab.com/commento/commento/-/merge_requests/164)
- [新增功能：输入密码后按回车即可登录](https://gitlab.com/commento/commento/-/merge_requests/167)
- [修复：已删除评论未在数组中返回](https://gitlab.com/commento/commento/-/merge_requests/170)
- [新增功能：SPA（单页应用）重新初始化组件功能](https://gitlab.com/commento/commento/-/merge_requests/182)
- 新增功能：域名中支持通配符（例如可以服务 %.example.com）
- 新增功能：支持 Perspective API 进行垃圾评论检测 (https://www.perspectiveapi.com/)

我已提交了许多上述功能的合并请求，但不知道何时会被接受。因此，这里是一个开箱即用、功能齐全的版本，帮助其他博主！

### 如何在 SPA（单页应用）中使用

Commento++ 在页面加载时运行代码以初始化组件。该组件可以通过在 `<script>` 标签中使用数据属性进行自定义。在 SPA 中使用 Commento++ 时，你可能希望在不重新加载页面的情况下导航到新博客文章时更改组件的 `pageId`。以下是一个在 React 中使用 Commento++ 组件的示例：

```js
import React, { useEffect } from 'react'

const Commento = ({ pageId }) => {
  useEffect(() => {
    if (typeof window !== 'undefined' && !window.commento) {
      // 初始化空对象，这样 commento.js 脚本会扩展此对象以添加全局函数
      window.commento = {}
      const script = document.createElement('script')
      // 替换为你自己的 commento 实例的 commento.js 脚本 URL
      script.src = `http://localhost:8080/js/commento.js`
      script.defer = true
      // 设置默认属性用于首次加载
      script.setAttribute('data-auto-init', false)
      script.setAttribute('data-page-id', pageId)
      script.setAttribute('data-id-root', 'commento-box')
      script.onload = () => {
        // 告诉 commento.js 加载组件
        window.commento.main()
      }
      document.getElementsByTagName('head')[0].appendChild(script)
    } else if (typeof window !== 'undefined' && window.commento) {
      // 如果 commento.js 脚本已加载，则使用新的 pageId 重新初始化组件
      window.commento.reInit({
        pageId: pageId,
      })
    }
  }, [])

  return <div id="commento-box" />
}

export default Commento
```

Commento 会在页面加载时初始化组件，并扩展 `window.commento` 对象。当有一个 `id="commento"` 的 HTML 元素时，该对象会存在于 `window.commento` 命名空间中。在 SPA 中替换 HTML 元素时，`window.commento` 会被重置为新元素，导致丢失 commento++ 脚本提供的所有扩展功能。要使此功能正常工作，请确保提供一个不同于 `commento` 的 `data-id-root`，如上面示例中的 `commento-box`。

可以使用以下更新选项调用 `window.commento.reInit` 函数（全部为可选）：

```js
{
    pageId: "string", // 例如: "path/to/page"
    idRoot: "string", // 例如: "new-element-id"
    noFonts: "string", // 布尔字符串，"true" 或 "false"
    hideDeleted: "string", // 布尔字符串，"true" 或 "false"
    cssOverride: "string" // 或 null 以重置为 undefined
}
```