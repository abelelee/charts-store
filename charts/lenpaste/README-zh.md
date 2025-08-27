**Lenpaste** 是一个允许你匿名分享笔记的网页服务，是 `pastebin.com` 的替代品。

> 目前我没有太多时间维护这个项目，但我会尽量回复你的问题。你可以开一个 issue 或通过电子邮件联系我。
>
> 另外，我现在觉得我写的源代码质量很差。如果我有时间，我一定会重构它:)
>
> \- Leonid Maslakov \<root@lcomrade.su\>

## 功能特性
- 无需注册。
- 支持多种语言。
- 仅使用 Cookie 存储设置。
- 可在无 JavaScript 的情况下运行。
- 拥有自身的 API。
- 开源且可自托管。

## 公共服务器列表
| 服务器                                             | 描述                                                                                                       |
| --------------------------------------------------| ---------------------------------------------------------------------------------------------------------- |
| [paste.lcomrade.su](https://paste.lcomrade.su)     | 由 Lenpaste 开发者管理的服务器。                                                                           |
| [code.dbt3ch.com](https://code.dbt3ch.com)         | 由 DB Tech 管理的服务器。他制作了一个 [关于 Lenpaste v1.1 的视频](https://www.youtube.com/watch?v=YxcHxsZHh9A)。 |
| [notepad.co.il](https://notepad.co.il)             | 由 Shlomi Porush 管理的服务器。他报告了一个 bug 并提出了一些建议。                                           |
| [lenp.pardesicat.xyz](https://lenp.pardesicat.xyz) | 由 Pardesi_Cat 管理的服务器。他将 Lenpaste 翻译成孟加拉语并协助修正了文档。                                   |

## 启动你自己的服务器

### 简单部署
1. 如果你尚未安装 Docker 和 Docker Compose，请安装：
```bash
apt-get install -y docker.io docker-compose
```

2. 使用如下内容的 `docker-compose.yml` 文件：
```yaml
version: "3.4"

services:
  lenpaste:
    # 提供了适用于 x64、ARM64、ARM v7、ARM v6 的镜像。
    # 支持 Raspberry Pi，包括最新的 64 位版本。
    # 将 "X.X" 替换为目标 Lenpaste 版本号。
    image: ghcr.io/lcomrade/lenpaste:X.X
    volumes:
      - "${PWD}/data:/data"
    ports:
      - "80:80"
```

3. 在 `docker-compose.yml` 所在目录执行：
```
docker-compose pull && docker-compose up -d
```

如需安装更新，请运行：`docker-compose pull && docker-compose up -d && docker system prune -a -f`

### Lenpaste 配置

#### HTTP
环境变量 `LENPASTE_ADDRESS` 指定 Lenpaste 接收 HTTP 连接的 `ADDRESS:PORT`。默认值为 `:80`。

#### 数据库
环境变量 `LENPASTE_DB_DRIVER` 指定使用的数据库。默认为 `sqlite3`，可选值为 `sqlite3` 和 `postgres`。

环境变量 `LENPASTE_DB_SOURCE` 指定数据库连接信息。对于 SQLite3，默认值为 `/data/lenpaste.db`；对于其他数据库，必须显式指定值。

环境变量 `LENPASTE_DB_MAX_OPEN_CONNS` 指定 Lenpaste 可同时打开的最大数据库连接数。默认值为 `25`。

环境变量 `LENPASTE_DB_MAX_IDLE_CONNS` 指定 Lenpaste 可保持的空闲数据库连接数上限。默认值为 `5`。

环境变量 `LENPASTE_DB_CLEANUP_PERIOD` 指定 Lenpaste 删除过期粘贴的时间间隔。如果用户尝试打开尚未清理的过期粘贴，将返回 404 错误。默认值为 `1m`（1 分钟）。

#### 搜索引擎
环境变量 `LENPASTE_ROBOTS_DISALLOW` 通过 robots.txt 文件禁止或允许搜索引擎（如 Google）索引你的 Lenpaste 实例。默认值为 `false`（允许索引）。

#### 存储限制
环境变量 `LENPASTE_TITLE_MAX_LENGTH` 设置粘贴标题的最大长度。默认值为 `100`。

环境变量 `LENPASTE_BODY_MAX_LENGTH` 设置粘贴正文的最大长度。默认值为 `20000`。

环境变量 `LENPASTE_MAX_PASTE_LIFETIME` 设置粘贴的最大生存时间。示例值：`10m`、`1h 30m`、`12h`、`7w`、`30d`、`365d`。默认值为 `unlimited`（无限制）。

#### 速率限制
环境变量 `LENPASTE_GET_PASTES_PER_5MIN`、`LENPASTE_GET_PASTES_PER_15MIN`、`LENPASTE_GET_PASTES_PER_1HOUR` 设置从单个 IP 地址在 5、15 或 60 分钟内最多可查看的粘贴数量。默认值分别为 `50`、`100`、`500`。

环境变量 `LENPASTE_NEW_PASTES_PER_5MIN`、`LENPASTE_NEW_PASTES_PER_15MIN`、`LENPASTE_NEW_PASTES_PER_1HOUR` 设置从单个 IP 地址在 5、15 或 60 分钟内最多可创建的粘贴数量。默认值分别为 `15`、`30`、`40`。

要关闭任何速率限制，只需将其设置为 `0`。Lenpaste 仅在重启前记住限制，重启后限制计数将重新开始。

#### 访问控制
如果存在文件 `/data/lenpasswd`，服务器将在创建粘贴时提示输入用户名和密码。每行格式为 `LOGIN:PLAIN_PASSWORD`。

#### 服务器信息
环境变量 `LENPASTE_ADMIN_NAME` 设置服务器管理员的名称。

环境变量 `LENPASTE_ADMIN_MAIL` 设置服务器管理员的电子邮件。

如果存在 `/data/about` 文本文件，其内容将显示在“关于”页面顶部。

`/data/rules` 文本文件可包含服务器使用规则（非法律文件）。

`/data/terms` 文本文件可包含以“法律语言”编写的“使用条款”。

#### 网页界面
环境变量 `LENPASTE_UI_DEFAULT_LIFETIME` 设置网页界面中默认的粘贴生存时间。示例值：`10min`、`1h`、`1d`、`2w`、`6mon`、`1y`。列表中第一个可用值将被默认选中。

环境变量 `LENPASTE_UI_DEFAULT_THEME` 设置网页界面默认主题。默认值为 `dark`。

在 `/data/themes/` 目录中，管理员可放置自定义主题。你可以基于 `./internal/web/data/theme/` 中的主题创建自定义主题。

### Lenpaste + Nginx
以下是一个基本的 Nginx 配置示例（`/etc/nginx/nginx.conf`），可用于 Lenpaste：
```nginx
events {
	worker_connections 1024;
}

http {
	error_log /var/log/nginx/error.log warn;
	server_tokens off; # 禁止在错误页面和“Server”响应头字段中显示 nginx 版本。

	ssl_protocols TLSv1.2 TLSv1.3; # TLSv1.2 在旧设备上启用 HTTPS。

	client_max_body_size 1M;
	client_body_timeout 300s;

	proxy_http_version 1.1;
	
	# Lenpaste 正常工作所需。
	proxy_set_header Host $host;
	proxy_set_header X-Real-IP $remote_addr;
	proxy_set_header X-Forwarded-For $remote_addr;
	proxy_set_header X-Forwarded-Proto $scheme;
}

# HTTP
server {
	server_name YOUR_DOMAIN;
	listen 80;
	listen [::]:80;

	access_log /var/log/nginx/YOUR_DOMAIN.access.log combined;

	location / {
		proxy_pass http://localhost:8000/;
		#return 301 https://$host$request_uri; - 重定向到 HTTPS
	}

	# 用于 Lets Encrypt
	location /.well-known/acme-challenge/ {
		root /var/www/letsencrypt/;
	}
}

# HTTPS
server {
	server_name YOUR_DOMAIN;
	listen 443 ssl http2;
	listen [::]:443 ssl http2;
	ssl_certificate /etc/letsencrypt/live/YOUR_DOMAIN/fullchain.pem;
	ssl_certificate_key /etc/letsencrypt/live/YOUR_DOMAIN/privkey.pem;

	access_log /var/log/nginx/YOUR_DOMAIN.access.log combined;
	
	location / {
		proxy_pass http://localhost:8000/;
	}
}
```

### Lenpaste + Postgres
以下是一个基本的 Docker Compose 配置示例（`docker-compose.yml`），用于使 Lenpaste 与 Postgres 一起工作：
```yaml
version: "3.4"

services:
  postgres:
    image: docker.io/library/postgres:16.1
    environment:
      - PGDATA=/var/lib/postgresql/data/pgdata
      - POSTGRES_USER=lenpaste
      - POSTGRES_PASSWORD=pass
    volumes:
      - "${PWD}/data/postgres:/var/lib/postgresql/data"

  lenpaste:
    image: ghcr.io/lcomrade/lenpaste:X.X
    restart: on-failure:10
    environment:
      - LENPASTE_DB_DRIVER=postgres
      - LENPASTE_DB_SOURCE=postgres://lenpaste:pass@postgres/lenpaste?sslmode=disable
    volumes:
      - "${PWD}/data:/data"
    ports:
      - "80:80"
    depends_on:
      - postgres
```

## 从源码构建

### 构建 Docker 镜像（推荐）
**为什么需要这样做？**
官方镜像可能不支持你的架构，例如 MIPS、PowerPC 等。因此，你可以构建自己的镜像以在非官方支持的架构上运行（当然每次更新 Lenpaste 时都需要重新构建）。

在 Debian/Ubuntu 上：
```bash
export LENPASTE_VERSION=X.X
sudo apt -y install wget docker.io
wget -O ./lenpaste-$LENPASTE_VERSION.tar.gz https://github.com/lcomrade/lenpaste/releases/download/v$LENPASTE_VERSION/lenpaste-$LENPASTE_VERSION.tar.gz
tar -xf ./lenpaste-$LENPASTE_VERSION.tar.gz
cd ./lenpaste-$LENPASTE_VERSION/
sudo docker build -t localhost/lenpaste:$LENPASTE_VERSION ./
```

现在你的本地机器上应该出现了 `localhost/lenpaste:X.X` 镜像。你可以在 `docker-compose.yml` 中使用它，或将其复制到其他机器上。

### 构建二进制文件
在 Debian/Ubuntu 上：
```bash
export LENPASTE_VERSION=X.X
sudo apt -y install wget make golang gcc libc6-dev
wget -O ./lenpaste-$LENPASTE_VERSION.tar.gz https://github.com/lcomrade/lenpaste/releases/download/v$LENPASTE_VERSION/lenpaste-$LENPASTE_VERSION.tar.gz
tar -xf ./lenpaste-$LENPASTE_VERSION.tar.gz
cd ./lenpaste-$LENPASTE_VERSION/
make
```

构建结果可在 `./dist/` 目录中找到。

## 其他文档
了解更多关于 [Lenpaste API](https://paste.lcomrade.su/docs/apiv1) 的信息。

可能感兴趣的内容：
- [如何在 Synology NAS 上安装 LenPaste](https://mariushosting.com/how-to-install-lenpaste-on-your-synology-nas/)（网页）
- [Lenpaste | TrueCharts](https://truecharts.org/docs/charts/incubator/lenpaste/)（网页）
- [使用 Lenpaste 在 Docker 中搭建 Pastebin 克隆](https://www.youtube.com/watch?v=YxcHxsZHh9A)（YouTube 视频）

## 贡献
你可以做什么？
- 撰写文章（DevTo、Medium、你的网站等）或制作视频（YouTube、PeerTube 等）。你的文章/视频链接将被包含在本 README 中。
- 创建或更新软件包：
  - 创建 NixOS 软件包。
  - 更新 TrueCharts 软件包。
  - 其他。
- 向朋友推荐 Lenpaste。

## 联系方式
- Matrix 聊天室：[`#lenpaste:lcomrade.su`](https://matrix.to/#/#lenpaste:lcomrade.su)
- 联系我：Leonid Maslakov \<root@lcomrade.su\>