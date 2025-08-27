# ![Gray Duck Logo](/assets/logo-32.png) Gray Duck Mail

现代的群组电子邮件讨论列表。

---

Gray Duck Mail 是 [Mailman](https://docs.mailman3.org/en/latest/) 和 [Sympa](https://www.sympa.org/) 等邮件讨论组软件的替代方案，设计目标是 **易于安装** 和 **易于管理**。Gray Duck Mail 会监控远程邮件服务器上的消息，并通过将消息转发给所有列表成员来处理这些消息。Gray Duck Mail 还能自动处理用户的订阅、退订请求以及邮件退信。只要外部邮件主机支持 POP3/SMTP 连接和消息转发或别名功能，Gray Duck Mail 就可以与其配合使用。Gray Duck Mail 完全依赖于外部邮件提供商，因此您可以使用现有的网页主机或邮箱账户。

Gray Duck Mail 使用 C# 编写，并基于 [ASP.NET Core 3.1 MVC](https://docs.microsoft.com/en-us/aspnet/core/mvc/overview?view=aspnetcore-3.1) 构建。

## 目录

1. [安装](#installation)
   1. [标签](#tags)
   2. [端口](#ports)
   3. [卷](#volumes)
   4. [环境变量](#environment-variables)
      - [`RATE_LIMIT_PER_ROUND_COUNT`](#rate_limit_per_round_count)
      - [`RATE_LIMIT_ROUND_WAIT_TIME`](#rate_limit_round_wait_time)
      - [`FETCH_TIME`](#fetch_time)
      - [`LOG_LEVEL`](#log_level)
      - [`MIN_SEARCH_SCORE`](#min_search_score)
      - [`WEB_ONLY`](#web_only)
      - [`WEB_UNSUBSCRIBE`](#web_unsubscribe)
      - [`WEB_USE_HTTPS`](#web_use_https)
      - [`WEB_EXTERNAL_URL`](#web_external_url)
      - [`WEB_SECRET`](#web_secret)
      - [`ASPNETCORE_URLS`](#aspnetcore_urls)
   5. [安全注意事项](#security-considerations)
2. [Web 界面](#web-interface)
   1. [设置](#settings)
      1. [每页显示条目数](#items-per-page)
      2. [模糊搜索](#fuzzy-search)
   2. [数据库导入](#database-import)
   3. [数据库导出](#datbase-export)
3. [联系人](#contacts)
4. [讨论列表](#discussion-lists)
   1. [配置](#configuration)
      1. [基础邮箱账户](#base-email-account)
      2. [别名](#aliases)
         - [`request`](#request)
         - [`subscribe`](#subscribe)
         - [`unsubscribe`](#unsubscribe)
         - [`bounce`](#bounce)
         - [`owner`](#owner)

## 安装

Gray Duck Mail 以 [Docker 镜像](https://hub.docker.com/r/wagesj45/gray-duck-mail) 的形式提供。

`docker pull wagesj45/gray-duck-mail`

### 标签

在 [Docker Hub](https://hub.docker.com/r/wagesj45/gray-duck-mail) 上，您会看到两个标签：`testing` 和 `latest`。`testing` 标签用于测试和调试目的，是一个不稳定的镜像。除非您正在积极开发 Gray Duck Mail，否则在拉取镜像和创建容器时，应仅使用 `latest` 标签。

### 端口

Docker 镜像需要将 HTTP 端口暴露并映射到容器的端口 **80**。可选地，可以暴露并映射到端口 **5000**，该端口将接受外部的退订请求。

### 卷

需要挂载一个卷到 `/database`。该卷将存储本地的 [SQLite3](https://sqlite.org/index.html) 数据库文件。该卷提供非易失性存储，以确保在升级 Docker 镜像时数据不会丢失。

### 环境变量

Docker 镜像暴露了以下环境变量，用于控制系统行为。

#### `RATE_LIMIT_PER_ROUND_COUNT`

在定义的超时周期之前可以发送的电子邮件数量。这对于对发送邮件数量有限制的邮件提供商非常有用。默认值是一个 [System.Int32](https://learn.microsoft.com/en-us/dotnet/api/system.int32?view=netcore-3.1) 类型的值，设为 `00:05:00`。

#### `RATE_LIMIT_ROUND_WAIT_TIME`

从队列中发送一组邮件后等待的时间。在发送完一轮邮件后，系统将等待此时间后再继续处理邮件队列。默认值是一个 [System.TimeSpan](https://docs.microsoft.com/en-us/dotnet/api/system.timespan?view=netcore-3.1) 类型的值，设为 `00:05:00`。

#### `FETCH_TIME`

从远程服务器获取邮件的时间间隔。默认值是一个 [System.TimeSpan](https://docs.microsoft.com/en-us/dotnet/api/system.timespan?view=netcore-3.1) 类型的值，设为 `00:05:00`。

#### `LANGUAGE`

支持系统本地化。语言文件以 `*.resx` 文件形式存储。虽然初始翻译是自动完成的，但欢迎提交人工翻译的 Pull Request。

支持以下值：

- `en-US` - 英语
- `ja-JP` - 日语
- `es-ES` - 西班牙语
- `de-DE` - 德语

#### `LOG_LEVEL`

记录应用程序事件的详细程度。默认值是一个 [System.String](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netcore-3.1) 类型的值，设为 `info`。

支持以下值：

- `trace` | `all`
- `debug` | `verbose`
- `info` | `information`
- `warn` | `warning`
- `err` | `error`
- `fatal`

#### `MIN_SEARCH_SCORE`

执行 [模糊搜索](#Fuzzy-Search) 时的最低有效搜索得分。默认值是一个 [System.Single (float)](https://docs.microsoft.com/en-us/dotnet/api/system.single?view=netcore-3.1) 类型的值，设为 `0.2`。使用 [模糊搜索](#Fuzzy-Search) 时，会生成介于 `1` 和 `0` 之间的分数。当搜索结果偏离精确匹配时，得分会趋近于零。

#### `WEB_ONLY`

如果设置，仅初始化 Web 界面。[后台工作线程](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/host/hosted-services?view=aspnetcore-3.1&tabs=visual-studio) 将不会被初始化。这对于运行 Web 管理界面而不希望后台服务修改远程邮件服务器的情况非常有用。默认值是一个 [System.Boolean](https://docs.microsoft.com/en-us/dotnet/api/system.boolean?view=netcore-3.1) 类型的值，设为 `0`。

支持以下值：

- `True` | `1`
- `False` | `0`

#### `WEB_UNSUBSCRIBE`

如果设置，将在系统和转发的邮件中生成并使用退订链接。如果未设置，则会生成一个指向退订别名的链接。默认值是一个 [System.Boolean](https://docs.microsoft.com/en-us/dotnet/api/system.boolean?view=netcore-3.1) 类型的值，设为 `1`。

支持以下值：

- `True` | `1`
- `False` | `0`

#### `WEB_USE_HTTPS`

如果设置，生成的外部可访问退订链接将使用 `HTTPS`。否则，将使用 `HTTP`。默认值是一个 [System.Boolean](https://docs.microsoft.com/en-us/dotnet/api/system.boolean?view=netcore-3.1) 类型的值，设为 `1`。

支持以下值：

- `True` | `1`
- `False` | `0`

#### `WEB_EXTERNAL_URL`

生成外部可访问退订链接时使用的主机名。默认值是一个 [System.String](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netcore-3.1) 类型的值，设为 `example.com`。

#### `WEB_SECRET`

创建退订链接哈希码时使用的唯一字符串，该链接附加在邮件中。这个字符串可以是您选择的任何内容。哈希是通过对 `ContactID`、`DiscussionListID` 和 `WEB_SECRET` 进行 SHA256 哈希运算生成的。这可以防止外部人员恶意暴力破解退订链接。[System.String](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netcore-3.1) 没有默认值，但如果未设置，系统将使用随机 [GUID](https://learn.microsoft.com/en-us/dotnet/api/system.guid?view=netcore-3.1) 的字符串表示形式。

#### `ASPNETCORE_URLS`

ASP.Net 服务器运行时监控的 URL。默认值是一个 [System.String](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netcore-3.1) 类型的值，设为 `http://+:5000;http://+:80`。您可以在此处了解更多信息 [here](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/host/web-host?view=aspnetcore-6.0)，但除非您是高级用户并修改 Gray Duck Mail Docker 镜像，否则应保留此值的默认设置，并确保配置了端口 **80** 和 **5000**。在配置 Docker 容器时，只有端口 **80** 是正常运行所必需的。

### 安全注意事项

Gray Duck Mail 将其 Web 界面划分为两个端口，一个内部端口和一个外部端口。Docker 镜像使用端口 **80** 作为指定的 *内部* 入口点，使用端口 **5000** 作为指定的 *外部* 入口点。这意味着应仅将 Docker 容器的端口 **5000** 暴露给公共互联网。

使用外部端口可以利用“一键”退订链接。退订链接的形式为 `http[s]://hostname/Unsubscribe/{contactID}/{discussionListID}`。例如，假设一个内部标识符为 `529` 的用户从内部标识符为 `187` 的讨论列表中退订，使用 `HTTPS` 和主机名 `example.com`，链接可能看起来像 `https://example.com/Unsubscribe/529/187`。

退订链接是 Gray Duck Mail 中唯一可从外部访问的路由。尝试从端口 **5000** 加载任何其他路由将导致 [`403 Forbidden`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/403) 访问错误。

Gray Duck Mail 应该理想地放置在反向代理之后，仅将 Web 流量转发到端口 **5000**（或转发到 Docker 容器中外部入口端口的端口）。强烈建议使用 [如 nginx 这样的反向代理](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/) 提供 [SSL 内容](https://www.nginx.com/blog/using-free-ssltls-certificates-from-lets-encrypt-with-nginx/)。虽然不推荐，但也可以将安全入口端口与 [HTTP 基本身份验证](https://docs.nginx.com/nginx/admin-guide/security-controls/configuring-http-basic-authentication/) 配合使用。

Gray Duck Mail 在本地数据库中存储邮箱登录凭据。这些凭据 **未加密**。此外，Web 管理界面除了其 *内部* 和 *外部* 设计之外，没有用户或内容分段的概念。这意味着，任何通过端口 **80** 访问 *内部* Web 界面的人都可以访问每个邮件讨论列表的登录凭据，以及列表用户的联系信息（姓名和电子邮件地址）和消息归档列表（发件人和消息内容）。

Gray Duck Mail 使用的数据库文件未加密，并以明文形式存储所有数据。在备份 `/database` Docker 卷或导出数据库副本时，应确保限制文件访问权限。

## Web 界面

Gray Duck Mail 提供了一个 Web 管理界面，用于基本的系统交互。Web 界面允许管理员创建和删除分发列表、创建和删除列表联系人、浏览消息归档，并访问基本的管理操作，如 [导入](#database-import) 和 [导出本地数据库副本](#database-export)，应确保这些文件不被公众访问。

### 设置

Web 管理设置控制 Web 界面中数据的显示方式，因此作为 Cookie 存储在用户的浏览器中。这些设置对系统的讨论列表邮件处理功能没有影响。

#### 每页显示条目数

此设置控制页面上显示的顶级条目数量，例如联系人或归档消息。

#### 模糊搜索

默认情况下，搜索联系人和消息归档时进行精确搜索。结果将包含完全匹配的搜索词。如果启用此选项，搜索引擎将使用 [模糊搜索](https://en.wikipedia.org/wiki/Fuzzy_logic)，通过 [Levenshtein 距离](https://en.wikipedia.org/wiki/Levenshtein_distance) 找到与给定搜索词密切匹配的结果。这可以提高搜索结果的质量，但 **计算开销较大**，因为必须从数据库中加载所有搜索项到内存中。在搜索大量消息归档或大量联系人列表时，这可能导致 Web 服务器超时错误。

### 数据库导入

此操作允许您导入现有的 SQLite3 数据库文件。导入数据库时，Web 服务器必须重启。您可以简单地重新加载 Web 界面以查看新更改。

### 数据库导出

此操作允许您导出 SQLite3 数据库文件的副本。该文件可以导入到另一个 Gray Duck Mail 实例中，或在外部应用程序（如 [DB Browser for SQLite](https://sqlitebrowser.org/)）中查看。

## 联系人

联系人代表可以向讨论列表发送和接收消息的个人用户。新联系人可以通过 [Web 界面](#web-interface) 添加，或者当一个之前未知的电子邮件地址向讨论列表的 `request` 邮件别名发送消息时自动添加。

## 讨论列表

讨论列表代表一组联系人，他们可以通过一个指定的电子邮件地址将消息转发给其他用户。通过向特定的 [邮件别名](#aliases) 发送消息，可以执行有限的自动审核。

### 配置

Gray Duck Mail 要正常运行需要一个外部邮箱账户和几个 [定义的别名](#aliases)。讨论列表通过监控给定的 POP3 邮箱账户，并通过将每封邮件转发给讨论列表成员，或通过分析邮件的 MIME 头并执行审核任务来处理邮件。

#### 基础邮箱账户

基础邮箱账户是由外部邮箱提供商（如您的 [网页主机](https://www.inmotionhosting.com/)）提供的实际邮箱账户。

#### 别名

为了处理操作邮件，Gray Duck Mail 要求配置某些邮箱别名。您的邮箱提供商可能将此配置称为“转发”。这些别名的结构应使命令名称在基础邮箱地址之前，并用连字符分隔。

例如：`subscribe-base.email.address@example.com`。

以下邮箱别名必须存在以支持自动审核：

- `request-base.email.address@example.com`
- `subscribe-base.email.address@example.com`
- `unsubscribe-base.email.address@example.com`
- `bounce-base.email.address@example.com`
- `owner-base.email.address@example.com`

##### `request`

请求别名用于处理新用户加入讨论列表的请求。

##### `subscribe`

订阅别名用于已受邀参与讨论列表的已知用户确认其愿意参与。

##### `unsubscribe`

退订别名用于已受邀参与讨论列表的已知用户撤销其接收与特定讨论列表相关邮件的同意。

##### `bounce`

退信别名插入到所有系统发送邮件的 [`return-path`](https://en.wikipedia.org/wiki/Variable_envelope_return_path) MIME 头中。某些邮件服务器依赖此 `return-path` 值来通知发件人无法投递的邮件或无效的邮箱。

##### `owner`

所有者别名应转发到非讨论列表的地址，例如管理员的个人邮箱账户。当需要外部审核时（例如，当一个之前未知的用户请求访问讨论列表时），系统会向此地址发送警报消息。