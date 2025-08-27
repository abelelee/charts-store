<p align="center">
  <img src="static/assets/images/logo-gh.svg" width="350">
</p>

<p align="center">
  <img src="https://badges.fw-web.space/github/license/muety/wakapi">
  <a href="https://liberapay.com/muety/"><img src="https://badges.fw-web.space/liberapay/receives/muety.svg?logo=liberapay"></a>
  <img src="https://wakapi.dev/api/badge/n1try/interval:any/project:wakapi?label=wakapi">
  <img src="https://badges.fw-web.space/github/languages/code-size/muety/wakapi">
  <a href="https://goreportcard.com/report/github.com/muety/wakapi"><img src="https://goreportcard.com/badge/github.com/muety/wakapi"></a>
  <a href="https://sonarcloud.io/dashboard?id=muety_wakapi"><img src="https://sonarcloud.io/api/project_badges/measure?project=muety_wakapi&metric=ncloc"></a>
</p>

<h3 align="center">一个极简的、可自托管的 WakaTime 兼容编码统计后端。</h3>

<div align="center">
  <h3>
    <a href="https://wakapi.dev">网站</a>
    <span> | </span>
    <a href="#-功能">功能</a>
    <span> | </span>
    <a href="#%EF%B8%8F-如何使用">如何使用</a>
    <span> | </span>
    <a href="https://github.com/muety/wakapi/issues">问题</a>
    <span> | </span>
    <a href="https://github.com/muety">联系</a>
  </h3>
</div>

<p align="center">
  <img src="static/assets/images/screenshot.webp" width="500px">
</p>

安装说明请参见下方或 [Wiki](https://github.com/muety/wakapi/wiki)。

## 🚀 功能

* ✅ 免费且开源
* ✅ 由开发者为开发者构建
* ✅ 支持项目、语言、编辑器、主机和操作系统的统计
* ✅ 支持徽章
* ✅ 每周电子邮件报告
* ✅ REST API
* ✅ 部分兼容 WakaTime
* ✅ WakaTime 集成
* ✅ 支持 Prometheus 导出
* ✅ 极速
* ✅ 可自托管

## ⌨️ 如何使用？

使用 Wakapi 有多种方式，从使用我们托管的云服务到自托管。无论选择哪种方式，都需要进行 [客户端设置](#-客户端设置)。

### ☁️ 选项 1：使用 [wakapi.dev](https://wakapi.dev)

如果你想尝试一个免费的托管云服务，只需创建一个账户，然后设置你的客户端工具（见下文）。

### 📦 选项 2：快速运行一个发布版本

```bash
$ curl -L https://wakapi.dev/get | bash
```

**或者** 使用 [eget](https://github.com/zyedidia/eget)：

```bash
$ eget muety/wakapi
```

### 🐳 选项 3：使用 Docker

```bash
# 创建一个持久化卷
$ docker volume create wakapi-data

$ SALT="$(cat /dev/urandom | LC_ALL=C tr -dc 'a-zA-Z0-9' | fold -w ${1:-32} | head -n 1)"

# 运行容器
$ docker run -d \
  --init \
  -p 3000:3000 \
  -e "WAKAPI_PASSWORD_SALT=$SALT" \
  -v wakapi-data:/data \
  --name wakapi \
  ghcr.io/muety/wakapi:latest
```

**注意：** 默认使用 SQLite 作为数据库。要在 Docker 中使用 MySQL 或 Postgres 运行 Wakapi，请参阅 [Dockerfile](https://github.com/muety/wakapi/blob/master/Dockerfile) 和 [config.default.yml](https://github.com/muety/wakapi/blob/master/config.default.yml) 以获取更多选项。

如果你想在 **Kubernetes** 上运行 Wakapi，可以使用 [wakapi-helm-chart](https://github.com/ricristian/wakapi-helm-chart) 来进行快速简便的部署。

#### Docker Compose

或者，你可以使用 Docker Compose 进行更简单的部署。配置详情请参阅 [compose.yml](https://github.com/muety/wakapi/blob/master/compose.yml)。

Wakapi 支持以下变量的 [Docker Secrets](https://docs.docker.com/compose/how-tos/use-secrets/)：`WAKAPI_PASSWORD_SALT`、`WAKAPI_DB_PASSWORD`、`WAKAPI_MAIL_SMTP_PASS`。你可以通过将它们挂载为密钥文件，或者直接作为环境变量传递。

##### 示例

```bash
export WAKAPI_PASSWORD_SALT=changeme
export WAKAPI_DB_PASSWORD=changeme
export WAKAPI_MAIL_SMTP_PASS=changeme

docker compose up -d
```

如果你希望在使用 SQLite 作为数据库时将数据持久化到本地目录，请确保在 Docker Compose 配置中设置正确的 `user` 选项以避免权限问题。

### 🧑‍💻 选项 4：从源码编译并运行

```bash
# 构建并安装
# 或者：go build -o wakapi
$ go install github.com/muety/wakapi@latest

# 获取默认配置并自定义
$ curl -o wakapi.yml https://raw.githubusercontent.com/muety/wakapi/master/config.default.yml
$ vi wakapi.yml

# 运行它
$ ./wakapi -config wakapi.yml
```

**注意：** 有关安全配置的最佳实践，请查看 `config.yml` 中的注释。

💡 当独立运行 Wakapi（不使用 Docker）时，建议将其作为 [SystemD 服务](etc/wakapi.service) 运行。

### 💻 客户端设置

Wakapi 依赖于开源的 [WakaTime](https://github.com/wakatime/wakatime-cli) 客户端工具。为了收集 Wakapi 的统计数据，你需要进行设置。

1. **为你的特定 IDE 或编辑器设置 WakaTime**。请参考相应的 [插件指南](https://wakatime.com/plugins)
2. **编辑本地的 `~/.wakatime.cfg` 文件**，如下所示。

```ini
[settings]

# 你的 Wakapi 服务器 URL 或使用云服务器时的 'https://wakapi.dev/api'
api_url = http://localhost:3000/api

# 你的 Wakapi API 密钥（在创建账户后从 Web 界面获取）
api_key = 406fe41f-6d69-4183-a4cc-121e0c524c2b
```

你还可以选择性地设置一个 [客户端代理](https://github.com/muety/wakapi/wiki/Advanced-Setup:-Client-side-proxy)。

## 🔧 配置选项

你可以通过配置文件（默认为 `config.yml`，可通过 `-c` 参数自定义）或通过环境变量来指定配置选项。以下是所有选项的概览。

| YAML 键 / 环境变量                                                                    | 默认值                                          | 描述                                                                                                                                                                |
|---------------------------------------------------------------------------------------------|--------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `env` /<br>`ENVIRONMENT`                                                                    | `dev`                                            | 是否使用开发或生产设置                                                                                                                         |
| `app.leaderboard_enabled` /<br>`WAKAPI_LEADERBOARD_ENABLED`                                 | `true`                                           | 是否启用公共排行榜                                                                                                                                   |
| `app.leaderboard_scope` /<br>`WAKAPI_LEADERBOARD_SCOPE`                                     | `7_days`                                         | 公共排行榜的聚合间隔（允许值请参见[此处](https://github.com/muety/wakapi/blob/7d156cd3edeb93af2997bd95f12933b0aabef0c9/config/config.go#L71)） |
| `app.leaderboard_generation_time` /<br>`WAKAPI_LEADERBOARD_GENERATION_TIME`                 | `0 0 6 * * *,0 0 18 * * *`                       | 一天中重新计算排行榜的一个或多个时间                                                                                                      |
| `app.leaderboard_require_auth` /<br>`WAKAPI_LEADERBOARD_REQUIRE_AUTH`                       | `false`                                          | 限制排行榜访问仅限登录用户                                                                                                                        |
| `app.aggregation_time` /<br>`WAKAPI_AGGREGATION_TIME`                                       | `0 15 2 * * *`                                   | 每天运行所有用户摘要生成的时间                                                                                                  |
| `app.report_time_weekly` /<br>`WAKAPI_REPORT_TIME_WEEKLY`                                   | `0 0 18 * * 5`                                   | 发送电子邮件报告的星期和时间                                                                                                                          |
| `app.data_cleanup_time` /<br>`WAKAPI_DATA_CLEANUP_TIME`                                     | `0 0 6 * * 0`                                    | 执行数据清理操作的时间（参见 `app.data_retention_months`）                                                                                                  |
| `app.optimize_database_time` /<br>`WAKAPI_OPTIMIZE_DATABASE_TIME`                           | `0 0 8 1 * *`                                    | 执行数据库清理（SQLite、Postgres）或表优化（MySQL）的时间                                                                                        |
| `app.import_enabled` /<br>`WAKAPI_IMPORT_ENABLED`                                           | `true`                                           | 是否允许从 WakaTime 或其他 Wakapi 实例导入数据                                                                                                 |
| `app.import_batch_size` /<br>`WAKAPI_IMPORT_BATCH_SIZE`                                     | `50`                                             | 导入外部服务数据时插入数据库的心跳批次大小                                                                            |
| `app.import_backoff_min` /<br>`WAKAPI_IMPORT_BACKOFF_MIN`                                   | `5`                                              | 用户再次尝试数据导入前的冷却时间（分钟）                                                                                                   |
| `app.import_max_rate` /<br>`WAKAPI_IMPORT_MAX_RATE`                                         | `24`                                             | 成功数据导入后用户再次尝试导入所需的最小等待时间（小时）                                                                         |
| `app.inactive_days` /<br>`WAKAPI_INACTIVE_DAYS`                                             | `7`                                              | 用户被视为不活跃的天数（仅用于指标）                                                                                                  |
| `app.heartbeat_max_age /`<br>`WAKAPI_HEARTBEAT_MAX_AGE`                                     | `4320h`                                          | 心跳的最大可接受年龄（参见 [`ParseDuration`](https://pkg.go.dev/time#ParseDuration))                                                                       |
| `app.warm_caches /`<br>`WAKAPI_WARM_CACHES`                                                 | `true`                                           | 是否在启动时执行一些初始缓存预热                                                                                                                 |
| `app.custom_languages`                                                                      | -                                                | 文件后缀到语言名称的映射                                                                                                                                    |
| `app.avatar_url_template` /<br>`WAKAPI_AVATAR_URL_TEMPLATE`                                 | （参见 [`config.default.yml`](config.default.yml)） | 外部用户头像图片的 URL 模板（例如 [Dicebear](https://dicebear.com) 或 [Gravatar](https://gravatar.com)）                                              |
| `app.date_format` /<br>`WAKAPI_DATE_FORMAT`                                                 | `Mon, 02 Jan 2006`                               | Go 时间格式字符串，用于格式化可读日期（参见 [`Time.Format`](https://pkg.go.dev/time#Time.Format))                                                            |
| `app.datetime_format` /<br>`WAKAPI_DATETIME_FORMAT`                                         | `Mon, 02 Jan 2006 15:04`                         | Go 时间格式字符串，用于格式化可读日期时间（参见 [`Time.Format`](https://pkg.go.dev/time#Time.Format))                                                        |
| `app.support_contact` /<br>`WAKAPI_SUPPORT_CONTACT`                                         | `hostmaster@wakapi.dev`                          | 页面上显示的支持联系电子邮件地址                                                                                                                 |
| `app.data_retention_months` /<br>`WAKAPI_DATA_RETENTION_MONTHS`                             | `-1`                                             | 用户数据（心跳）的最大保留时间（月）（-1 表示无限制）                                                                                           |
| `app.max_inactive_months` /<br>`WAKAPI_MAX_INACTIVE_MONTHS`                                 | `12`                                             | 删除无数据用户账户的最大不活动月数（-1 表示无限制）                                                                      |
| `server.port` /<br> `WAKAPI_PORT`                                                           | `3000`                                           | 监听端口                                                                                                                                                          |
| `server.listen_ipv4` /<br> `WAKAPI_LISTEN_IPV4`                                             | `127.0.0.1`                                      | 监听的 IPv4 网络地址（设为 `'-'` 以禁用 IPv4）                                                                                                           |
| `server.listen_ipv6` /<br> `WAKAPI_LISTEN_IPV6`                                             | `::1`                                            | 监听的 IPv6 网络地址（设为 `'-'` 以禁用 IPv6）                                                                                                           |
| `server.listen_socket` /<br> `WAKAPI_LISTEN_SOCKET`                                         | -                                                | 监听的 UNIX 套接字（设为 `'-'` 以禁用 UNIX 套接字）                                                                                                             |
| `server.listen_socket_mode` /<br> `WAKAPI_LISTEN_SOCKET_MODE`                               | `0666`                                           | 创建 UNIX 套接字的权限模式                                                                                                                                 |
| `server.timeout_sec` /<br> `WAKAPI_TIMEOUT_SEC`                                             | `30`                                             | 请求超时时间（秒）                                                                                                                                                 |
| `server.tls_cert_path` /<br> `WAKAPI_TLS_CERT_PATH`                                         | -                                                | SSL 服务器证书路径（留空以不使用 HTTPS）                                                                                                              |
| `server.tls_key_path` /<br> `WAKAPI_TLS_KEY_PATH`                                           | -                                                | SSL 服务器私钥路径（留空以不使用 HTTPS）                                                                                                              |
| `server.base_path` /<br> `WAKAPI_BASE_PATH`                                                 | `/`                                              | Web 基础路径（当运行在代理下的子路径时更改）                                                                                                        |
| `server.public_url` /<br> `WAKAPI_PUBLIC_URL`                                               | `http://localhost:3000`                          | 你的 Wakapi 实例的公开 URL                                                                                                                    |
| `security.password_salt` /<br> `WAKAPI_PASSWORD_SALT`                                       | -                                                | 用于密码哈希的盐值                                                                                                                                         |
| `security.insecure_cookies` /<br> `WAKAPI_INSECURE_COOKIES`                                 | `false`                                          | 是否允许通过 HTTP 使用 Cookie                                                                                                                                  |
| `security.cookie_max_age` /<br> `WAKAPI_COOKIE_MAX_AGE`                                     | `172800`                                         | 认证 Cookie 的生命周期（秒）或 `0` 表示使用 [Session](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies#Define_the_lifetime_of_a_cookie) Cookie   |
| `security.allow_signup` /<br> `WAKAPI_ALLOW_SIGNUP`                                         | `true`                                           | 是否启用用户注册                                                                                                                                        |
| `security.signup_captcha` /<br> `WAKAPI_SIGNUP_CAPTCHA`                                     | `false`                                          | 注册表单是否需要解决 CAPTCHA                                                                                                                   |
| `security.invite_codes` /<br> `WAKAPI_INVITE_CODES`                                         | `true`                                           | 是否启用邀请码注册。如果注册被禁用（仅邀请服务器）时特别有用。                                                         |
| `security.disable_frontpage` /<br> `WAKAPI_DISABLE_FRONTPAGE`                               | `false`                                          | 是否禁用首页（适用于个人实例）                                                                                                            |
| `security.expose_metrics` /<br> `WAKAPI_EXPOSE_METRICS`                                     | `false`                                          | 是否在 `/api/metrics` 下暴露 Prometheus 指标                                                                                                                  |
| `security.trusted_header_auth` /<br> `WAKAPI_TRUSTED_HEADER_AUTH`                           | `false`                                          | 是否启用可信头认证用于反向代理（参见 [#534](https://github.com/muety/wakapi/issues/534)）。**请谨慎使用！**                        |
| `security.trusted_header_auth_key` /<br> `WAKAPI_TRUSTED_HEADER_AUTH_KEY`                   | `Remote-User`                                    | 可信头认证的头字段。**注意：** 代理必须配置为从客户端请求中剥离此头！                                           |
| `security.trusted_header_auth_allow_signup` /<br> `WAKAPI_TRUSTED_HEADER_AUTH_ALLOW_SIGNUP` | `false`                                          | 是否允许基于上游可信头认证创建新用户（参见 [#808](https://github.com/muety/wakapi/issues/808))                            |
| `security.trust_reverse_proxy_ips` /<br> `WAKAPI_TRUST_REVERSE_PROXY_IPS`                   | -                                                | 逗号分隔的反向代理 IP 地址或 CIDR 列表，用于信任以处理认证（例如 `172.17.0.1`、`192.168.0.0/24`、`[::1]`）。               |
| `security.signup_max_rate` /<br> `WAKAPI_SIGNUP_MAX_RATE`                                   | `5/1h`                                           | 注册端点的速率限制配置，格式为 `<max_req>/<multiplier><unit>`，其中 `unit` 是 `s`、`m` 或 `h` 中的一个。                                                 |
| `security.login_max_rate` /<br> `WAKAPI_LOGIN_MAX_RATE`                                     | `10/1m`                                          | 登录端点的速率限制配置，格式为 `<max_req>/<multiplier><unit>`，其中 `unit` 是 `s`、`m` 或 `h` 中的一个。                                                  |
| `security.password_reset_max_rate` /<br> `WAKAPI_PASSWORD_RESET_MAX_RATE`                   | `5/1h`                                           | 密码重置端点的速率限制配置，格式为 `<max_req>/<multiplier><unit>`，其中 `unit` 是 `s`、`m` 或 `h` 中的一个。                                         |
| `db.host` /<br> `WAKAPI_DB_HOST`                                                            | -                                                | 数据库主机                                                                                                                                                              |
| `db.port` /<br> `WAKAPI_DB_PORT`                                                            | -                                                | 数据库端口                                                                                                                                                              |
| `db.socket` /<br> `WAKAPI_DB_SOCKET`                                                        | -                                                | 数据库 UNIX 套接字（替代 `host`）（仅限 MySQL）                                                                                                              |
| `db.user` /<br> `WAKAPI_DB_USER`                                                            | -                                                | 数据库用户                                                                                                                                                              |
| `db.password` /<br> `WAKAPI_DB_PASSWORD`                                                    | -                                                | 数据库密码                                                                                                                                                          |
| `db.name` /<br> `WAKAPI_DB_NAME`                                                            | `wakapi_db.db`                                   | 数据库名称                                                                                                                                                              |
| `db.dialect` /<br> `WAKAPI_DB_TYPE`                                                         | `sqlite3`                                        | 数据库类型（`sqlite3`、`mysql`、`postgres`、`mssql` 中的一个）                                                                                                             |
| `db.charset` /<br> `WAKAPI_DB_CHARSET`                                                      | `utf8mb4`                                        | 数据库连接字符集（仅限 MySQL）                                                                                                                               |
| `db.max_conn` /<br> `WAKAPI_DB_MAX_CONNECTIONS`                                             | `2`                                              | 数据库连接的最大数量                                                                                                                                     |
| `db.ssl` /<br> `WAKAPI_DB_SSL`                                                              | `false`                                          | 是否对数据库连接使用 TLS 加密（仅限 Postgres）                                                                                           |
| `db.automgirate_fail_silently` /<br> `WAKAPI_DB_AUTOMIGRATE_FAIL_SILENTLY`                  | `false`                                          | 启动时是否忽略模式自动迁移失败                                                                                                          |
| `mail.enabled` /<br> `WAKAPI_MAIL_ENABLED`                                                  | `true`                                           | 是否允许 Wakapi 发送电子邮件（例如用于密码重置）                                                                                                          |
| `mail.sender` /<br> `WAKAPI_MAIL_SENDER`                                                    | `Wakapi <noreply@wakapi.dev>`                    | 出站邮件的默认发件人地址                                                                                                                                  |
| `mail.provider` /<br> `WAKAPI_MAIL_PROVIDER`                                                | `smtp`                                           | 用于发送邮件的实现（`smtp` 中的一个）                                                                                                                  |
| `mail.smtp.host` /<br> `WAKAPI_MAIL_SMTP_HOST`                                              | -                                                | 发送邮件的 SMTP 服务器地址（如果使用 `smtp` 邮件提供者）                                                                                                       |
| `mail.smtp.port` /<br> `WAKAPI_MAIL_SMTP_PORT`                                              | -                                                | SMTP 服务器端口（通常为 465）                                                                                                                                             |
| `mail.smtp.username` /<br> `WAKAPI_MAIL_SMTP_USER`                                          | -                                                | SMTP 服务器认证用户名                                                                                                                                        |
| `mail.smtp.password` /<br> `WAKAPI_MAIL_SMTP_PASS`                                          | -                                                | SMTP 服务器认证密码                                                                                                                                        |
| `mail.smtp.tls` /<br> `WAKAPI_MAIL_SMTP_TLS`                                                | `false`                                          | SMTP 服务器是否需要 TLS 加密（`false` 表示 STARTTLS 或无加密）                                                                                    |
| `mail.smtp.skip_verify` /<br> `WAKAPI_MAIL_SMTP_SKIP_VERIFY`                                | `false`                                          | 是否允许 TLS 加密 SMTP 使用无效或自签名证书                                                                                                |
| `sentry.dsn` /<br> `WAKAPI_SENTRY_DSN`                                                      | –                                                | 用于集成 [Sentry](https://sentry.io) 进行错误日志记录和追踪的 DSN（留空以禁用）                                                                    |
| `sentry.environment` /<br> `WAKAPI_SENTRY_ENVIRONMENT`                                      | (`env`)                                          | Sentry [环境](https://docs.sentry.io/concepts/key-terms/environments/) 标签（默认为 `env` / `ENV`）                                                              |
| `sentry.enable_tracing` /<br> `WAKAPI_SENTRY_TRACING`                                       | `false`                                          | 是否启用 Sentry 请求追踪                                                                                                                                   |
| `sentry.sample_rate` /<br> `WAKAPI_SENTRY_SAMPLE_RATE`                                      | `0.75`                                           | 在 Sentry 中追踪请求的概率                                                                                                                                 |
| `sentry.sample_rate_heartbeats` /<br> `WAKAPI_SENTRY_SAMPLE_RATE_HEARTBEATS`                | `0.1`                                            | 在 Sentry 中追踪心跳请求的概率                                                                                                                       |
| `quick_start` /<br> `WAKAPI_QUICK_START`                                                    | `false`                                          | 是否跳过初始启动任务。仅用于开发目的！                                                                                                     |
| `enable_pprof` /<br> `WAKAPI_ENABLE_PPROF`                                                  | `false`                                          | 是否暴露 [pprof](https://pkg.go.dev/runtime/pprof) 分析数据作为调试端点                                                                    |

### 支持的数据库

Wakapi 使用 [GORM](https://gorm.io) 作为 ORM。因此，支持一组不同的关系型数据库。

* [SQLite](https://sqlite.org/) (_默认，易于设置_)
* [MySQL](https://hub.docker.com/_/mysql) (_推荐，因为测试最广泛_)
* [MariaDB](https://hub.docker.com/_/mariadb) (_开源的 MySQL 替代方案_)
* [Postgres](https://hub.docker.com/_/postgres) (_同样开源_)
* [Microsoft SQL Server](https://hub.docker.com/_/microsoft-mssql-server) (_Microsoft SQL Server_)

## 🔐 认证

Wakapi 支持多种用户认证方式。

* **Cookie：** 此方法在浏览器中使用。用户通过发送一个加密的、安全的、仅限 HTTP 的 Cookie (`wakapi_auth`) 进行认证，该 Cookie 在服务器登录响应中设置。
* **API 密钥：**
    * **通过头信息：** 此方法受 [WakaTime 的认证机制](https://wakatime.com/developers/#authentication) 启发，是认证 API 端点的常见方式。用户将 `Authorization` 头设置为 `Basic <BASE64_TOKEN>`，其中后者部分对应于你的 base64 哈希 API 密钥。
    * **通过查询参数：** 或者，用户也可以将他们的明文 API 密钥作为查询参数传递（例如 `?api_key=86648d74-19c5-452b-ba01-fb3ec70d4c2f`）在每次请求的 URL 中。
* **可信头：** 此机制允许将认证委托给 **反向代理**（例如用于 SSO），Wakapi 将盲目信任它。详情请参见 [#534](https://github.com/muety/wakapi/issues/534)。
    * 必须通过 `trusted_header_auth` 和在配置中配置 `trust_reverse_proxy_ip` 来启用
    * 警告：这种类型的认证非常容易配置错误。确保你的反向代理正确地从客户端请求中剥离相关头信息。

## 🔧 API 端点

请参见我们的 [Swagger API 文档](https://wakapi.dev/swagger-ui)。

### 生成 Swagger 文档

```bash
$ go install github.com/swaggo/swag/cmd/swag@latest
$ swag init -o static/docs
```

## 🤝 集成

### Prometheus 导出

你可以将 Wakapi 统计数据导出到 Prometheus，以便在 Grafana 仪表板中查看。以下是操作方法。

```bash
# 1. 启动 Wakapi 并启用该功能
$ export WAKAPI_EXPOSE_METRICS=true
$ ./wakapi

# 2. 获取你的 API 密钥并进行哈希处理
$ echo "<YOUR_API_KEY>" | base64

# 3. 在 prometheus.yml 中添加一个 Prometheus 抓取配置（见下文）
```

#### 抓取配置示例

```yml
# prometheus.yml
# （假设你的 Wakapi 实例监听在 localhost，端口 3000）

scrape_configs:
  - job_name: 'wakapi'
    scrape_interval: 1m
    metrics_path: '/api/metrics'
    bearer_token: '<YOUR_BASE64_HASHED_TOKEN>'
    static_configs:
      - targets: [ 'localhost:3000' ]
```

#### Grafana

还有一个 [不错的 Grafana 仪表板](https://grafana.com/grafana/dashboards/12790)，由 [wakatime_exporter](https://github.com/MacroPower/wakatime_exporter) 的作者提供。

![](https://grafana.com/api/dashboards/12790/images/8741/image)

### WakaTime 集成

Wakapi 与 [WakaTime](https://wakatime.com) 配合良好。一方面，你可以从 Wakapi **转发心跳** 到 WakaTime，从而同时使用这两个服务。此外，还可以选择从 WakaTime **导入历史数据** 以确保两个服务之间的一致性。这两个功能可以在 Wakapi 实例的设置页面的 _集成_ 部分启用。

### GitHub Readme Stats 集成

Wakapi 还集成了 [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats#wakatime-week-stats)，为你生成漂亮的卡片。这是一个示例。要使用此功能，请不要忘记在 [设置 -> 权限](https://wakapi.dev/settings#permissions) 中 **启用公开数据**。

<details>
<summary>点击查看代码</summary>

```markdown
![](https://github-readme-stats.vercel.app/api/wakatime?username={yourusername}&api_domain=wakapi.dev&bg_color=2D3748&title_color=2F855A&icon_color=2F855A&text_color=ffffff&custom_title=Wakapi%20Week%20Stats&layout=compact)
```

</details>
<br>

### GitHub Readme Metrics 集成

还有一个 [WakaTime 插件](https://github.com/lowlighter/metrics/tree/master/source/plugins/wakatime) 用于 GitHub [Metrics](https://github.com/lowlighter/metrics/)，也兼容 Wakapi。要使用此插件，请不要忘记在 [设置 -> 权限](https://wakapi.dev/settings#permissions) 中 **启用公开数据**。

预览：

![](https://raw.githubusercontent.com/lowlighter/metrics/examples/metrics.plugin.wakatime.svg)

<details>
<summary>点击查看代码</summary>

```yml
- uses: lowlighter/metrics@latest
  with:
    # ... 其他选项
    plugin_wakatime: yes
    plugin_wakatime_token: ${{ secrets.WAKATIME_TOKEN }}      # 必需
    plugin_wakatime_days: 7                                   # 显示上周统计数据
    plugin_wakatime_sections: time, projects, projects-graphs # 显示时间与项目部分，以及项目图表
    plugin_wakatime_limit: 4                                  # 每个图表显示 4 个条目
    plugin_wakatime_url: http://wakapi.dev                    # WakaTime URL 端点
    plugin_wakatime_user: .user.login                         # 用户

```

</details>
<br>

### 浏览器插件（Chrome 和 Firefox）

[browser-wakatime](https://github.com/wakatime/browser-wakatime) 插件使你能够在 WakaTime（当然还有 Wakapi）中跟踪你的网页浏览。访问的网站将显示为摘要中的“文件”。按照以下说明开始：

1. 从官方商店安装浏览器扩展（[Firefox](https://addons.mozilla.org/en-US/firefox/addon/wakatimes)、[Chrome](https://chrome.google.com/webstore/detail/wakatime/jnbbnacmeggbgdjgaoojpmhdlkkpblgi?hl=de)）
2. 打开扩展设置对话框
3. 按如下方式配置（见下图）：
    * API 密钥：你的个人 API 密钥（在 [wakapi.dev](https://wakapi.dev) 获取）
    * 日志类型：_仅域名_
    * API URL：`https://wakapi.dev/api/compat/wakatime/v1`（或者，将 _wakapi.dev_ 替换为你的自托管实例主机名）
4. 保存
5. 开始浏览！

![](.github/assets/screenshot_browser_plugin.png)

注意：插件只会偶尔同步心跳，因此它们可能需要一些时间才会出现在 Wakapi 上。要“强制”其同步，只需打开插件主对话框。

### Gnome 扩展

如果你使用 GNOME 桌面，有一种快速方法可以在状态栏中显示你今天的编码统计信息。

![](.github/assets/screenshot_gnome.png)

只需安装 [Executor](https://extensions.gnome.org/extension/2932/executor/) 扩展，并将以下命令添加为状态栏指示器：

```bash
~/.wakatime/wakatime-cli-linux-amd64 --today
```

## 📦 数据导出

你可以将 Wakapi 中的编码活动导出为 CSV 格式的原始心跳数据。虽然无法通过 Web UI 直接实现，但我们提供了一个易于使用的 Python [脚本](scripts/download_heartbeats.py)。

```bash
$ pip install requests tqdm
$ python scripts/download_heartbeats.py --api_key API_KEY [--url URL] [--from FROM] [--to TO] [--output OUTPUT]
```

<details>

<summary>示例</summary>

```bash
python scripts/download_heartbeats.py --api_key 04648d14-15c9-432b-b901-dbeec70d4eaf \
  --url https://wakapi.dev/api \
  --from 2023-01-01 \
  --to 2023-01-31 \
  --output wakapi_export.csv
```

</details>

## 👍 最佳实践

建议在 **反向代理**（如 [Caddy](https://caddyserver.com) 或 [nginx](https://www.nginx.com/)）后面使用 wakapi，以启用 **TLS 加密**（HTTPS）。

但是，如果你想将你的 wakapi 实例暴露给公众，你需要在 `config.yml` 中将 `server.listen_ipv4` 设置为 `0.0.0.0`。

## 🧪 测试

### 单元测试

单元测试旨在在细粒度级别上测试业务逻辑。它们作为应用程序的一部分实现，使用 Go 的 [testing](https://pkg.go.dev/testing?utm_source=godoc) 包以及 [stretchr/testify](https://pkg.go.dev/github.com/stretchr/testify)。

#### 如何运行

```bash
$ go install github.com/mfridman/tparse@latest  # 可选
$ CGO_ENABLED=0 go test `go list ./... | grep -v 'github.com/muety/wakapi/scripts'` -json -coverprofile=coverage/coverage.out ./... -run ./... | tparse -all
```

### API 测试

API 测试作为黑盒测试实现，通过 HTTP 请求与完整的 Wakapi 实例进行交互。它们旨在检查 Wakapi 的 Web 栈和端点，包括响应代码、头信息和数据的语法层面，而不是检查返回的实际内容。

我们的 API（或某种程度上的端到端）测试是作为 [Bruno](https://www.usebruno.com/) 集合实现的，可以通过 Bruno 内部运行，也可以使用 [Bruno CLI](https://www.npmjs.com/package/@usebruno/cli) 作为命令行运行器。

为了获得可预测的环境，测试是在一个全新的、干净的 Wakapi 实例上运行的，该实例使用 SQLite 数据库，并且仅填充了一些种子数据（参见 [data.sql](testing/data.sql)）。通常建议软件测试是 [安全](https://www.restapitutorial.com/lessons/idempotency.html) 的、无状态的且没有副作用的。与该范式相反，我们的 API 测试严格要求固定的执行顺序（Bruno 会确保这一点），并且它们的断言可能依赖于特定的先前测试已成功完成。

#### 前提条件（仅限 Linux）

```bash
# 1. sqlite (cli)
$ sudo apt install sqlite  # Fedora: sudo dnf install sqlite

# 2. bruno cli
$ npm install -g @usebruno/cli
```

#### 如何运行（仅限 Linux）

```bash
$ ./testing/run_api_tests.sh
```

## 🤓 开发者笔记

### 构建 Web 资源

为了保持最小化，所有 JS 和 CSS 资源都作为静态文件包含并提交到 Git。[TailwindCSS](https://tailwindcss.com/docs/installation#building-for-production) 和 [Iconify](https://iconify.design/docs/icon-bundles/) 需要额外的构建步骤。为了仅在开发时需要此步骤，编译后的资源也提交到 Git。

```bash
$ yarn
$ yarn build  # 或：yarn watch
```

可以通过编辑 [scripts/bundle_icons.js](scripts/bundle_icons.js) 中的 `icons` 数组来添加新图标。

#### 预压缩

如 [#284](https://github.com/muety/wakapi/issues/284) 所述，一些资源的预压缩（使用 Brotli）版本被交付以节省额外的带宽。这受到 Caddy 的 [`precompressed`](https://caddyserver.com/docs/caddyfile/directives/file_server) 指令的启发。[`gzipped.FileServer`](https://github.com/muety/wakapi/blob/07a367ce0a97c7738ba8e255e9c72df273fd43a3/main.go#L249) 会检查每个静态文件的 `.br` 或 `.gz` 等效文件，如果存在，则交付这些文件而不是实际文件，并附带 `Content-Encoding: br`。目前，压缩资源只是简单地提交到 Git。以后我们可能会希望将其作为新构建步骤的一部分。

要预压缩文件，请运行以下命令：

```bash
# 首先安装 brotli
$ sudo apt install brotli  # 或：sudo dnf install brotli

# 监视、构建并压缩
$ yarn watch:compress

# 或者：仅构建和压缩
$ yarn build:all:compress

# 或者：仅压缩
$ yarn compress
```

## ❔ 常见问题

由于 Wakapi 严重依赖 WakaTime 提供的概念，[它们的常见问题解答](https://wakatime.com/faq) 在很大程度上也适用于 Wakapi。你可能会在那里找到答案。

<details>
<summary><b>哪些数据会被发送到 Wakapi？</b></summary>

<ul>
  <li>文件名</li>
  <li>项目名</li>
  <li>编辑器名</li>
  <li>你的计算机主机名</li>
  <li>你在编辑器中执行的每个操作的时间戳</li>
  <li>...</li>
</ul>

详情请参见相关的 [WakaTime 常见问题部分](https://wakatime.com/faq#data-collected)。

如果你自己托管 Wakapi，那么你对所有数据都有控制权。然而，如果你使用我们的 Web 服务并担心隐私问题，你也可以 [排除或模糊处理](https://wakatime.com/faq#exclude-paths) 某些文件名或项目名。
</details>

<details>
<summary><b>如果我离线了怎么办？</b></summary>

所有数据都会在本地缓存，并在重新联网后批量发送。
</details>

<details>
<summary><b>Wakapi 是如何诞生的？</b></summary>

Wakapi 是在我还是学生的时候开始的，当时我想跟踪自己编码时间的详细统计数据。虽然我是 WakaTime 的忠实粉丝，但当时我并不想每月支付 <a href="https://wakatime.com/pricing">$9</a>。幸运的是，WakaTime 的大部分组件都是开源的！
</details>

<details>
<summary><b>Wakapi 与 WakaTime 的比较如何？</b></summary>

Wakapi 是 WakaTime 的一个小子集，功能也少得多。Wakapi 缺少的一些酷炫 WakaTime 功能包括：

<ul>
  <li>排行榜</li>
  <li><a href="https://wakatime.com/share/embed">可嵌入图表</a></li>
  <li>个人目标</li>
  <li>团队/组织支持</li>
  <li>额外的集成（与 GitLab 等）</li>
  <li>更丰富的 API</li>
</ul>

WakaTime 物有所值。然而，如果你只需要基本的统计数据，并且喜欢掌控自己的数据主权，你可能会选择 Wakapi。
</details>

<details>
<summary><b>持续时间是如何计算的？</b></summary>

从心跳中推断你的编码时间测量值与 WakaTime 类似，参见他们的 [文档](https://wakatime.com/faq#timeout)。传统上，Wakapi 会在 `<timeout>` 长的休息前对每个心跳进行填充，默认填充时间为 2 分钟。现在，在解决了 [#675](https://github.com/muety/wakapi/issues/675) 中提到的重构后，Wakapi 的逻辑几乎与 WakaTime 相同，包括手动可配置的超时（默认为 10 分钟）。

这是一个示例（圆圈代表心跳）：

```text
|---o---o--------------o---o---|
|   |10s|      3m      |10s|   |

```

如何处理中间的三分钟还不清楚。开发者是进行了 3 分钟的休息，还是只是没有发送心跳，例如开发者盯着屏幕试图找到解决方案，但实际上没有输入代码？

<ul>
  <li><b>使用 10 分钟超时：</b> 3 分 20 秒
  <li><b>使用 2 分钟超时：</b> 20 秒
  <li><b>之前（使用 2 分钟超时 + 填充）：</b> 10 秒 + 2 分钟 + 10 秒 = 2 分钟 20 秒</li>
</ul>
</details>

有关另一个示例，请参见 [此评论](https://github.com/muety/wakapi/issues/716#issuecomment-2668887035)。

## 👥 社区贡献

* 💻 [代码] Wakapi 统计图像生成器 – [LacazeThomas/wakapi-stats](https://github.com/LacazeThomas/wakapi-stats) (`Go`)
* 💻 [代码] Wakapi 的 Discord 集成 - [LLoneDev6/Wakapi-Discord](https://github.com/LoneDev6/Wakapi-Discord) (`JavaScript`)
* 💻 [代码] 另一个心跳导出脚本 - [wakapiexporter.nim](https://github.com/theAkito/mini-tools-nim/tree/master/generic/web/wakapiexporter) (`Nim`)
* 💻 [代码] 用于 K8s 部署的 Wakapi Helm 图表 - [andreymaznyak/wakapi-helm-chart](https://github.com/andreymaznyak/wakapi-helm-chart) (`YAML`)
* 🗓 [文章] [Wakamonth: 工时报告工具](https://bitstillery.com/2024/01/09/wakamonth-hours-reporting-tool/)

## 👏 支持

开源编码是我的热情所在，我希望能全职从事这项工作，并以此为生。所以如果你喜欢这个项目，请考虑支持它 🙂。你可以通过 [请我喝杯咖啡](https://buymeacoff.ee/n1try) 或成为 GitHub 赞助者来捐款。每一份小小的捐款都备受感激，并激励我继续改进 Wakapi！

## 🙏 感谢

我非常感谢 **[@alanhamlett](https://github.com/alanhamlett)** 和 WakaTime 团队的努力，并感谢他们的软件是开源的。

此外，感谢 **[server.camp](https://server.camp)** 为 Wakapi.dev 提供服务器基础设施赞助。

<img src=".github/assets/servercamp_logo.png" width="220px" />

## 📓 许可证

MIT @ [Ferdinand Mütsch](https://muetsch.io)