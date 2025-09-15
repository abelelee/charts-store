---
![Keycloak](https://github.com/keycloak/keycloak-misc/blob/main/logo/logo.svg)

![GitHub Release](https://img.shields.io/github/v/release/keycloak/keycloak?label=最新版本)
[![OpenSSF 最佳实践](https://bestpractices.coreinfrastructure.org/projects/6818/badge)](https://bestpractices.coreinfrastructure.org/projects/6818)
[![CLOMonitor](https://img.shields.io/endpoint?url=https://clomonitor.io/api/projects/cncf/keycloak/badge)](https://clomonitor.io/projects/cncf/keycloak)
[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/keycloak/keycloak/badge)](https://securityscorecards.dev/viewer/?uri=github.com/keycloak/keycloak)
[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/keycloak-operator)](https://artifacthub.io/packages/olm/community-operators/keycloak-operator)
![GitHub 仓库星标数](https://img.shields.io/github/stars/keycloak/keycloak?style=flat)
![GitHub 提交活跃度](https://img.shields.io/github/commit-activity/m/keycloak/keycloak)
[![翻译状态](https://hosted.weblate.org/widget/keycloak/svg-badge.svg)](docs/translation.md)

# 开源的身份认证与访问管理

以最小的代价为应用程序添加认证功能并保护服务。无需处理用户存储或用户身份验证。

Keycloak 提供了用户联合、强身份验证、用户管理、细粒度的授权等功能。

## 帮助与文档

* [文档](https://www.keycloak.org/documentation.html)
* [用户邮件列表](https://groups.google.com/d/forum/keycloak-user) - 用于寻求帮助和讨论 Keycloak 相关一般问题的邮件列表
* 加入 Slack 上的 [一般问题频道 #keycloak](https://cloud-native.slack.com/archives/C056HC17KK9) 或 [设计与开发讨论频道 #keycloak-dev](https://cloud-native.slack.com/archives/C056XU905S6)，注册地址为 [https://slack.cncf.io/](https://slack.cncf.io/)。

## 报告安全漏洞

如果您发现了一个安全漏洞，请查看[如何正确报告漏洞的说明](https://github.com/keycloak/keycloak/security/policy)。

## 报告问题

如果您认为发现了 Keycloak 的缺陷，请提交 [issue](https://github.com/keycloak/keycloak/issues)。
请记得提供清晰的摘要、描述以及复现问题的步骤。

## 入门指南

要运行 Keycloak，请从我们的[网站](https://www.keycloak.org/downloads.html)下载发行包。解压后运行以下命令：

    bin/kc.[sh|bat] start-dev

或者，您也可以通过运行以下命令使用 Docker 镜像：

    docker run quay.io/keycloak/keycloak start-dev

更多细节请参考 [Keycloak 文档](https://www.keycloak.org/documentation.html)。

## 从源码构建

如需从源码构建，请参考 构建与使用代码库 指南。

### 测试

如需运行测试，请参考 运行测试 指南。

### 编写测试

如需编写测试，请参考 编写测试 指南。

## 贡献代码

在为 Keycloak 做贡献之前，请阅读我们的 贡献指南。Keycloak 项目的参与受 [CNCF 行为准则](https://github.com/cncf/foundation/blob/main/code-of-conduct.md) 约束。

参加 [社区会议](https://www.keycloak.org/community) 是参与项目并帮助塑造 Keycloak 未来的好方法。

## 其他 Keycloak 项目

* [Keycloak](https://github.com/keycloak/keycloak) - Keycloak 服务器和 Java 适配器
* [Keycloak 快速入门](https://github.com/keycloak/keycloak-quickstarts) - Keycloak 快速入门示例
* [Keycloak Node.js Connect](https://github.com/keycloak/keycloak-nodejs-connect) - Keycloak 的 Node.js 适配器

## 许可证

* [Apache 许可证 2.0 版](https://www.apache.org/licenses/LICENSE-2.0)