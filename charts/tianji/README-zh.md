[![CI](https://github.com/msgbyte/tianji/actions/workflows/ci.yaml/badge.svg)](https://github.com/msgbyte/tianji/actions/workflows/ci.yaml)
[![Build Reporter Release](https://github.com/msgbyte/tianji/actions/workflows/reporter-release.yml/badge.svg)](https://github.com/msgbyte/tianji/actions/workflows/reporter-release.yml)
[![Docker Build CI](https://github.com/msgbyte/tianji/actions/workflows/ci-docker.yaml/badge.svg)](https://github.com/msgbyte/tianji/actions/workflows/ci-docker.yaml)
![Docker Pulls](https://img.shields.io/docker/pulls/moonrailgun/tianji)
![Docker Image Size](https://img.shields.io/docker/image-size/moonrailgun/tianji)
![Tianji Visitor](https://tianji.moonrailgun.com/telemetry/clnzoxcy10001vy2ohi4obbi0/cltjxvcwm02wdut4e106maek7/badge.svg?url=http://github.com/msgbyte/tianji)

# Tianji

<img src="./website/static/img/logo.svg" width="128" />

**一站式洞察中心**

`网站分析` + `运行监控` + `服务器状态` = `Tianji`

集成所有功能于一个项目！

## 背景动机

在我们对网站的观察过程中，常常需要同时使用多个应用。例如，我们需要像 `GA`/`umami` 这样的分析工具来查看页面访问量（PV）、独立访客数（UV）以及各页面的访问次数；需要使用运行监控工具来检查服务器的网络质量和连通性；还需要使用 Prometheus 来获取服务器上报的状态信息以判断服务器运行状况。此外，如果我们开发了一个允许开源部署的应用，通常还需要一个遥测系统来帮助我们收集他人部署情况的最基础信息。

我认为这些工具本质上服务于相同的目的，那么是否存在一个能够以轻量级方式集成这些常见需求的应用呢？毕竟大多数时候我们并不需要非常专业和深入的功能。但为了实现全面的监控，我却不得不安装如此多的服务。

术业有专攻，当我们是相关能力的专家时，确实需要这样的专用工具。但对于大多数只有轻量级需求的用户来说，一个**一站式**（All-in-One）应用将更加方便、易于使用。

## 路线图

- [x] 网站分析
- [x] 监控
  - [x] 支持被动接收监控结果
- [x] 服务器状态
- [x] 问题通知
- [x] 遥测数据
- [x] 开放API
- [x] 网站界面
- [x] 团队协作
- [ ] utm 跟踪
- [x] 等待列表
- [x] 问卷调查
  - [ ] 问卷页面
- [x] lighthouse 报告
- [x] 钩子（hooks）
- [x] 支持 Helm 安装
  - [x] 允许从公共源安装
- [x] 改进监控报告器的使用
  - [x] 卸载指南
  - [x] 从服务器下载
  - [x] 自定义参数指南

## 预览图

![](./website/static/img/preview/1.png)

![](./website/static/img/preview/2.png)

![](./website/static/img/preview/3.png)

![](./website/static/img/preview/4.png)

![](./website/static/img/preview/5.png)

![](./website/static/img/preview/6.png)

## 翻译

### 添加新翻译

修改以下文件：
- `src/client/i18next-toolkit.config.cjs`：在此文件中编辑国家代码
- `src/client/utils/i18n.ts`：在此文件中添加显示名称

然后运行以下命令自动生成翻译：

```bash
cd src/client
pnpm install
pnpm run translation:extract
pnpm run translation:translate # 此命令将调用 ChatGPT 进行自动翻译，请确保设置环境变量 `OPENAPI_KEY`
```

然后手动检查 `src/client/public/locales` 中的翻译文件。

### 改进现有翻译

直接更新 `src/client/public/locales` 中的文件即可。

## 开源信息

`Tianji` 采用 `Apache 2.0` 协议开源。

其灵感来源于采用 `MIT` 协议的 `umami` 和同样采用 `MIT` 协议的 `uptime-kuma`。

### 一键部署

[![Deploy on Sealos](https://cdn.jsdelivr.net/gh/labring-actions/templates@main/Deploy-on-Sealos.svg)](https://cloud.sealos.io/?openapp=system-template%3FtemplateName%3Dtianji)

[![Deploy to RepoCloud](https://d16t0pc4846x52.cloudfront.net/deploylobe.svg)](https://repocloud.io/details/?app_id=270)

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/msgbyte/tianji)

[![Run on ClawCloud](https://raw.githubusercontent.com/ClawCloud/Run-Template/refs/heads/main/Run-on-ClawCloud.svg)](https://template.run.claw.cloud/?referralCode=TNW6NVWTLHPQ&openapp=system-fastdeploy%3FtemplateName%3Dtianji)