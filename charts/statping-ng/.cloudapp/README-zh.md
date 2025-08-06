以下是你提供的英文Markdown内容的中文翻译，保留了原始的Markdown格式和结构：

---

<p align="center">
<img width="60%" src="https://s3-us-west-2.amazonaws.com/gitimgs/statping.png">
</p>
<p align="center">
    <b>Statping - 适用于任何项目的网页和应用状态监控</b><br>
<a href="https://github.com/statping/statping/wiki">查看Wiki</a> | <a href="https://demo.statping.com">演示</a> | <a href="https://itunes.apple.com/us/app/apple-store/id1445513219">iPhone</a> | <a href="https://play.google.com/store/apps/details?id=com.statping">Android</a> <br> <a href="http://docs.statping.com">API</a> | <a href="https://github.com/statping/statping/wiki/Docker">Docker</a> | <a href="https://github.com/statping/statping/wiki/AWS-EC2">EC2</a> | <a href="https://github.com/statping/statping/wiki/Mac">Mac</a> | <a href="https://github.com/statping/statping/wiki/Linux">Linux</a> | <a href="https://github.com/statping/statping/wiki/Windows">Windows</a>
</p>

# Statping - 状态页面 & 监控服务器
一个易于使用的状态页面，适用于你的网站和应用程序。Statping 将自动获取应用程序并生成一个美观的状态页面，具备大量功能，帮助你构建更出色的状态页面。此状态页面生成器支持在多个操作系统上使用 MySQL、Postgres 或 SQLite。

![Master Release](https://github.com/statping/statping/workflows/Master%20Release/badge.svg?branch=master) [![GoDoc](https://godoc.org/github.com/golang/gddo?status.svg)](https://godoc.org/github.com/statping/statping) [![Slack](https://slack.statping.com/badge.svg)](https://slack.statping.com) [![](https://images.microbadger.com/badges/image/statping/statping.svg)](https://microbadger.com/images/statping/statping) [![Docker Pulls](https://img.shields.io/docker/pulls/statping/statping.svg)](https://hub.docker.com/r/statping/statping/builds/)

<br><br>
<img align="left" width="320" height="235" src="https://img.cjx.io/statupsiterun.gif">
<h2>面向未来设计的状态页面</h2>
Statping 致力于保持未来兼容性，并在发生故障时仍能保持正常运行。你的 Statping 服务不应与你要监控的实例运行在同一台服务器上。如果服务器崩溃，状态页面仍应保持在线，以通知用户服务中断。

<br><a href="https://labs.play-with-docker.com/?stack=https://raw.githubusercontent.com/statping/statping/master/dev/pwd-stack.yml"><img height=25 src="https://assets.statping.com/docker-pwd.png"></a>（仪表板登录用户名为 `admin`，密码为 `admin`）
<br><br><br>

<h2>无依赖要求</h2>
Statping 是使用 Go 语言构建的，因此你只需要根据操作系统选择预编译的二进制文件即可。安装 Statping 二进制文件后，你无需安装任何额外依赖。你甚至可以在 Raspberry Pi 上运行 Statping。
<br><br>
<p align="center">
    <a href="https://github.com/statping/statping/wiki/Linux"><img width="5%" src="https://img.cjx.io/linux.png"></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="https://github.com/statping/statping/wiki/Mac"><img width="5%" src="https://img.cjx.io/apple.png"></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="https://github.com/statping/statping/wiki/Windows"><img width="5%" src="https://img.cjx.io/windows.png"></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="https://play.google.com/store/apps/details?id=com.statping"><img width="5%" src="https://img.cjx.io/android.png"></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="https://itunes.apple.com/us/app/apple-store/id1445513219"><img width="5%" src="https://img.cjx.io/appstore.png"></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="https://hub.docker.com/r/statping/statping"><img width="5%" src="https://img.cjx.io/dockericon.png"></a>
<br><br></p>

<img align="right" width="320" height="235" src="https://gitimgs.s3-us-west-2.amazonaws.com/slack-notifer.png">
<h2>轻量且快速</h2>
Statping 是一个非常轻量的应用程序，适用于 Linux、Mac 和 Windows。Docker 镜像大小仅为 ~16MB，因此你不用担心它占用过多磁盘空间。
其他操作系统上的状态页面二进制文件最大约为 ~17MB。
<br><br><br><br><br><br>

<img align="left" width="320" height="235" src="https://img.cjx.io/statping_iphone_bk.png">
<h2>移动应用界面精美</h2>
Statping 应用可在 App Store 和 Google Play 免费下载。该应用允许你查看服务状态、在服务离线时接收通知、更新分组、用户、服务、消息等内容。启动你自己的 Statping 服务器后，通过在设置中扫描二维码即可将其连接到该应用。

<p align="center">
<a href="https://play.google.com/store/apps/details?id=com.statping"><img src="https://img.cjx.io/google-play.svg"></a>
<a href="https://itunes.apple.com/us/app/apple-store/id1445513219"><img src="https://img.cjx.io/app-store-badge.svg"></a>
</p>

<br><br>

## 在任何服务器上运行
无论你是 Docker 爱好者还是 [AWS EC2](https://github.com/statping/statping/wiki/AWS-EC2) 高手，Statping 都提供了多种方式让你轻松部署。我们的 Amazon AMI 镜像仅需 8GB 空间，并会自动更新到最稳定的 Statping 版本。
在 EC2 服务器上运行可能是托管你自己的 Statping 状态页面最具性价比的方式。该服务器可在最小的 EC2 实例（t2.nano）上运行，AWS 提供的该实例每月费用约为 4.60 美元。
想在你自己的 Docker 服务器上运行？太棒了！Statping 提供了多个 docker-compose.yml 文件。Statping 还可以自动为你的状态页面创建 SSL 证书。
<br><br><br><br>

<img align="left" width="320" height="205" src="https://img.cjx.io/statping_theme.gif">
<h2>自定义 SASS 样式</h2>
Statping 允许你使用 SASS 样式和简单易用的变量完全自定义你的状态页面。Docker 镜像中实际上包含了一个预构建的 SASS 二进制文件，因此你甚至无需手动设置任何内容！
<br><br><br><br>

## Slack、电子邮件、Twilio 等通知方式
Statping 支持通过 SMTP 发送电子邮件通知，并通过 [Incoming Webhook](https://api.slack.com/incoming-webhooks) 集成 Slack。将 Webhook URL 插入 Statping 的设置页面并启用 Slack 集成。每当服务失败时，你在 Slack 中指定的频道将收到通知。
<br><br><br><br>

<h2>用户创建的通知器</h2>
查看 [插件 Wiki](https://github.com/statping/statping/wiki/Statping-Plugins) 以获取有关 Golang 插件的详细信息。Statping 不仅仅是一个用于应用程序的状态页面，它是一个框架，允许你创建自己的插件，以与状态页面的每个元素进行交互。[通知器](https://github.com/statping/statping/wiki/Notifiers) 也可以仅通过一个 Golang 文件创建。
<br><br><br><br>

<img align="center" width="100%" height="250" src="https://img.cjx.io/statupsc2.png">

<br><br><br><br>

<img align="right" width="320" height="235" src="https://img.cjx.io/statping_settings.gif">
<h2>易于使用的仪表板</h2>
一个简洁明了的仪表板使 Statping 更加出色。通过基本的 HTTP GET 请求监控你的网站和应用程序，或添加一个 POST 请求并使用你自己的 JSON 数据发布到端点。
<br><br><br><br>

## 在 Docker 上运行
使用 [Statping Docker 镜像](https://hub.docker.com/r/statping/statping) 可在几秒钟内创建一个状态页面。查看 [Docker Wiki](https://github.com/statping/statping/wiki/Docker) 以了解如何开始使用 Docker 的更多细节。
```bash
docker run -it -p 8080:8080 statping/statping
```
有多种方式可以启动 Statping 服务器。请确保 Statping 运行在一个独立的实例上，而不是你希望监控的应用程序所在的服务器上。当你的状态页面也宕机时，这看起来并不专业。我建议使用一个小型 EC2 实例，这样你可以设置好后就无需再操心。
<br><br><br><br>

## Docker Compose
本文件夹中包含一个标准的 docker-compose 文件，包含 nginx、postgres 和 Statping。
```bash
docker-compose up -d
```
<br><br><br><br>

## 使用自动 SSL 的 Docker Compose
你可以使用此 docker-compose 文件自动启动一个带有 SSL 加密的 Statping 服务器。首先将你的域名 DNS 指向 Statping 服务器，然后使用 DOMAIN 和 EMAIL 运行以下 docker-compose 命令。Email 用于 Let's Encrypt 服务。
```bash
LETSENCRYPT_HOST=mydomain.com \
    LETSENCRYPT_EMAIL=info@mydomain.com \
    docker-compose -f docker-compose-ssl.yml up -d
```
一旦实例启动，系统将花一点时间获取你的 SSL 证书。请确保你的域名上有一个 A 记录或 CNAME 记录指向运行 Statping 的服务器的 IP/DNS。
<br><br><br><br>

## Prometheus Exporter
Statping 包含一个 [Prometheus Exporter](https://github.com/statping/statping/wiki/Prometheus-Exporter)，使你能够对服务进行更强大的监控。Prometheus 导出器可在 `/metrics` 路径下访问，只需在你的 Prometheus 配置中创建另一个导出器即可。使用你的 Statping API Secret 作为 Authorization Bearer 头部，`/metrics` URL 专为 Prometheus 设计，要求在请求头中包含正确的 API Secret。
```yaml
scrape_configs:
  - job_name: 'statping'
    bearer_token: 'MY API SECRET HERE'
    static_configs:
      - targets: ['statping:8080']
```
<br><br><br><br>

## 在 EC2 服务器上运行
使用 AWS AMI 镜像，在最小的 EC2 服务器上运行 Statping 非常快速。查看 [AWS Wiki](https://github.com/statping/statping/wiki/AWS-EC2) 以获取逐步指南，了解如何将你的 EC2 Statping 服务上线。
<br><br><br><br>

##### 创建安全组
使用以下命令创建 AWS 安全组，Statping 将暴露端口 80 和 443。
```bash
aws ec2 create-security-group --group-name StatpingPublicHTTP \
     --description "Statping HTTP Server on port 80 and 443"
# 命令将返回一个组 ID。复制该 ID 并在下面的命令中使用 --group-id 参数。

aws ec2 authorize-security-group-ingress \
     --group-id sg-7e8b830f --protocol tcp \
     --port 80 --cidr 0.0.0.0/0

aws ec2 authorize-security-group-ingress \
     --group-id sg-7e8b830f --protocol tcp \
     --port 443 --cidr 0.0.0.0/0
```
##### 创建不带 SSL 的 EC2 实例
```bash
aws ec2 run-instances \
    --image-id ami-7be8a103 \
    --count 1 --instance-type t2.nano \
    --key-name MYKEYHERE \
    --security-group-ids sg-7e8b830f
```
##### 创建带自动 SSL 证书的 EC2 实例
以下 AWS-CLI 命令将自动创建一个 EC2 服务器，并从 Let's Encrypt 获取免费的 SSL 证书。
```bash
wget https://raw.githubusercontent.com/statping/statping/master/servers/ec2-ssl.sh
# 编辑 ec2-ssl.sh 并插入你希望使用的域名，然后运行以下命令。
# 使用上面使用的安全组 ID 作为 --security-group-ids 参数

aws ec2 run-instances \
    --user-data file://ec2-ssl.sh \
    --image-id ami-7be8a103 \
    --count 1 --instance-type t2.nano \
    --key-name MYKEYHERE \
    --security-group-ids sg-7e8b830f
```

## 贡献
Statping 接受向 `dev` 分支提交的 Pull Request！欢迎你添加自己的功能和通知器。建议查看 [通知器 Wiki](https://github.com/statping/statping/wiki/Notifiers) 以更好地理解如何为服务故障/成功创建自己的通知方法。Statping 的测试将涵盖 MySQL、Postgres 和 SQLite。我建议使用 MySQL 和 Postgres 的 Docker 容器进行测试。你可以在 dev 目录中找到多个 docker-compose 文件。

![Dev Release](https://github.com/statping/statping/workflows/Dev%20Release/badge.svg?branch=dev)
[![Go Report Card](https://goreportcard.com/badge/github.com/statping/statping)](https://goreportcard.com/report/github.com/statping/statping)
[![Build Status](https://travis-ci.com/statping/statping.svg?branch=master)](https://travis-ci.com/statping/statping) [![Cypress.io tests](https://img.shields.io/badge/cypress.io-tests-green.svg?style=flat-square)](https://dashboard.cypress.io/#/projects/bi8mhr/runs)
[![Docker Pulls](https://img.shields.io/docker/pulls/statping/statping.svg)](https://hub.docker.com/r/statping/statping/builds/) [![Godoc](https://godoc.org/github.com/statping/statping?status.svg)](https://godoc.org/github.com/statping/statping)[![Coverage Status](https://coveralls.io/repos/github/statping/statping/badge.svg?branch=master)](https://coveralls.io/github/statping/statping?branch=master)

<p align="center">
<a href="https://www.buymeacoffee.com/hunterlong" target="_blank">
<img height="55" src="https://img.cjx.io/buy-me-redbull.png" >
</a>
</p>