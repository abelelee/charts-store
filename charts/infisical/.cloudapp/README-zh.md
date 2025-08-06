---
<h1 align="center">
  <img width="300" src="/img/logoname-white.svg#gh-dark-mode-only" alt="infisical">
</h1>
<p align="center">
  <p align="center"><b>开源的密钥管理平台</b>: 在您的团队/基础设施之间同步密钥/配置，防止密钥泄露。</p>
</p>

<h4 align="center">
  <a href="https://infisical.com/slack">Slack</a> |
  <a href="https://infisical.com/">Infisical Cloud</a> |
  <a href="https://infisical.com/docs/self-hosting/overview">自托管</a> |
  <a href="https://infisical.com/docs/documentation/getting-started/introduction">文档</a> |
  <a href="https://www.infisical.com">官网</a> |
  <a href="https://infisical.com/careers">招聘 (远程/SF)</a>
</h4>

<h4 align="center">
  <a href="https://github.com/Infisical/infisical/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Infisical 使用 MIT 协议发布。" />
  </a>
  <a href="https://github.com/infisical/infisical/blob/main/CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen" alt="欢迎提交 PR！" />
  </a>
  <a href="https://github.com/Infisical/infisical/issues">
    <img src="https://img.shields.io/github/commit-activity/m/infisical/infisical" alt="Git 提交活动" />
  </a>
  <a href="https://cloudsmith.io/~infisical/repos/">
    <img src="https://img.shields.io/badge/Downloads-6.95M-orange" alt="Cloudsmith 下载量" />
  </a>
  <a href="https://infisical.com/slack">
    <img src="https://img.shields.io/badge/chat-on%20Slack-blueviolet" alt="Slack 社区频道" />
  </a>
  <a href="https://twitter.com/infisical">
    <img src="https://img.shields.io/twitter/follow/infisical?label=关注" alt="Infisical Twitter" />
  </a>
</h4>

<img src="/img/infisical_github_repo2.png" width="100%" alt="仪表板" />

## 简介

**[Infisical](https://infisical.com)** 是一个开源的密钥管理平台，团队可以使用它集中管理应用程序的配置和密钥，例如 API 密钥和数据库凭据，同时还可以管理内部的 PKI。

我们致力于让安全工具对所有人（而不仅仅是安全团队）都更加易用，这意味着要从头开始重新设计整个开发者体验。

## 功能

### 密钥管理：

- **[仪表板](https://infisical.com/docs/documentation/platform/project)**: 通过用户友好的界面管理多个项目和环境（如开发、生产等）中的密钥。
- **[原生集成](https://infisical.com/docs/integrations/overview)**: 将密钥同步到 [GitHub](https://infisical.com/docs/integrations/cicd/githubactions)、[Vercel](https://infisical.com/docs/integrations/cloud/vercel)、[AWS](https://infisical.com/docs/integrations/cloud/aws-secret-manager) 等平台，并使用 [Terraform](https://infisical.com/docs/integrations/frameworks/terraform)、[Ansible](https://infisical.com/docs/integrations/platforms/ansible) 等工具。
- **[密钥版本控制](https://infisical.com/docs/documentation/platform/secret-versioning)** 和 **[时间点恢复](https://infisical.com/docs/documentation/platform/pit-recovery)**: 跟踪每个密钥和项目的状态；在需要时回滚。
- **[密钥轮换](https://infisical.com/docs/documentation/platform/secret-rotation/overview)**: 定期轮换 [PostgreSQL](https://infisical.com/docs/documentation/platform/secret-rotation/postgres-credentials)、[MySQL](https://infisical.com/docs/documentation/platform/secret-rotation/mysql)、[AWS IAM](https://infisical.com/docs/documentation/platform/secret-rotation/aws-iam) 等服务的密钥。
- **[动态密钥](https://infisical.com/docs/documentation/platform/dynamic-secrets/overview)**: 按需为 [PostgreSQL](https://infisical.com/docs/documentation/platform/dynamic-secrets/postgresql)、[MySQL](https://infisical.com/docs/documentation/platform/dynamic-secrets/mysql)、[RabbitMQ](https://infisical.com/docs/documentation/platform/dynamic-secrets/rabbit-mq) 等服务生成临时密钥。
- **[密钥扫描与泄露防护](https://infisical.com/docs/cli/scanning-overview)**: 防止密钥泄漏到 Git。
- **[Infisical Kubernetes Operator](https://infisical.com/docs/documentation/getting-started/kubernetes)**: 向 Kubernetes 工作负载提供密钥并自动重新加载部署。
- **[Infisical Agent](https://infisical.com/docs/infisical-agent/overview)**: 无需修改代码逻辑即可将密钥注入应用程序。

### Infisical（内部）PKI：

- **[私有证书颁发机构](https://infisical.com/docs/documentation/platform/pki/private-ca)**: 创建 CA 层级结构，配置 [证书模板](https://infisical.com/docs/documentation/platform/pki/certificates#guide-to-issuing-certificates) 以实施策略，并开始颁发 X.509 证书。
- **[证书管理](https://infisical.com/docs/documentation/platform/pki/certificates)**: 管理证书生命周期，从 [签发](https://infisical.com/docs/documentation/platform/pki/certificates#guide-to-issuing-certificates) 到 [吊销](https://infisical.com/docs/documentation/platform/pki/certificates#guide-to-revoking-certificates)，并支持 CRL。
- **[告警](https://infisical.com/docs/documentation/platform/pki/alerting)**: 配置即将过期的 CA 和终端实体证书的告警。
- **[Kubernetes 的 Infisical PKI Issuer](https://infisical.com/docs/documentation/platform/pki/pki-issuer)**: 自动续订 Kubernetes 工作负载的 TLS 证书。
- **[安全传输注册](https://infisical.com/docs/documentation/platform/pki/est)**: 通过 EST 协议注册和管理证书。

### Infisical 密钥管理系统 (KMS)：

- **[加密密钥](https://infisical.com/docs/documentation/platform/kms)**: 通过用户友好的界面或 API 集中管理跨项目的密钥。
- **[数据加密与解密](https://infisical.com/docs/documentation/platform/kms#guide-to-encrypting-data)**: 使用对称密钥加密和解密数据。

### Infisical SSH：

- **[签名的 SSH 证书](https://infisical.com/docs/documentation/platform/ssh)**: 为基础设施提供安全、短暂且集中的访问权限，签发临时 SSH 凭据。

### 平台通用功能：

- **认证方式**：通过云原生或平台无关的认证方式（[Kubernetes 认证](https://infisical.com/docs/documentation/platform/identities/kubernetes-auth)、[GCP 认证](https://infisical.com/docs/documentation/platform/identities/gcp-auth)、[Azure 认证](https://infisical.com/docs/documentation/platform/identities/azure-auth)、[AWS 认证](https://infisical.com/docs/documentation/platform/identities/aws-auth)、[OIDC 认证](https://infisical.com/docs/documentation/platform/identities/oidc-auth/general)、[通用认证](https://infisical.com/docs/documentation/platform/identities/universal-auth)）对机器身份进行认证。
- **[访问控制](https://infisical.com/docs/documentation/platform/access-controls/overview)**: 使用 [RBAC](https://infisical.com/docs/documentation/platform/access-controls/role-based-access-controls)、[附加权限](https://infisical.com/docs/documentation/platform/access-controls/additional-privileges)、[临时访问](https://infisical.com/docs/documentation/platform/access-controls/temporary-access)、[访问请求](https://infisical.com/docs/documentation/platform/access-controls/access-requests)、[审批流程](https://infisical.com/docs/documentation/platform/pr-workflows) 等功能，为用户和机器身份定义高级授权控制。
- **[审计日志](https://infisical.com/docs/documentation/platform/audit-logs)**: 跟踪平台上执行的每一个操作。
- **[自托管](https://infisical.com/docs/self-hosting/overview)**: 可轻松地在本地或云上部署 Infisical；将数据保留在自己的基础设施上。
- **[Infisical SDK](https://infisical.com/docs/sdks/overview)**: 通过客户端 SDK 与 Infisical 交互（[Node](https://infisical.com/docs/sdks/languages/node)、[Python](https://github.com/Infisical/python-sdk-official?tab=readme-ov-file#infisical-python-sdk)、[Go](https://infisical.com/docs/sdks/languages/go)、[Ruby](https://infisical.com/docs/sdks/languages/ruby)、[Java](https://infisical.com/docs/sdks/languages/java)、[.NET](https://infisical.com/docs/sdks/languages/csharp)）
- **[Infisical CLI](https://infisical.com/docs/cli/overview)**: 通过 CLI 与 Infisical 交互；适用于将密钥注入本地开发和 CI/CD 流水线。
- **[Infisical API](https://infisical.com/docs/api-reference/overview/introduction)**: 通过 API 与 Infisical 交互。

## 入门指南

请查看 [快速入门指南](https://infisical.com/docs/getting-started/introduction)

| 使用 Infisical Cloud                                                                                                                                     | 在本地部署 Infisical                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| 最快且最可靠的方式是免费注册 [Infisical Cloud](https://app.infisical.com/login)。 | <br> 查看所有 [部署选项](https://infisical.com/docs/self-hosting/overview) |

### 在本地运行 Infisical

要设置并运行 Infisical，请确保您的系统上已安装 Git 和 Docker。然后根据您的系统运行以下命令：

Linux/macOS:

```console
git clone https://github.com/Infisical/infisical && cd "$(basename $_ .git)" && cp .env.example .env && docker compose -f docker-compose.prod.yml up
```

Windows 命令提示符:

```console
git clone https://github.com/Infisical/infisical && cd infisical && copy .env.example .env && docker compose -f docker-compose.prod.yml up
```

在 `http://localhost:80` 创建一个账户。

### 扫描并防止密钥泄露

除了使用 Infisical 管理密钥外，您还可以在文件、目录和 Git 仓库中 [扫描超过 140+ 种类型的密钥]()

要扫描完整的 Git 历史记录，请运行：

```
infisical scan --verbose
```

安装预提交钩子，在每次提交前扫描：

```
infisical scan install --pre-commit-hook
```

了解 Infisical 的代码扫描功能 [点击此处](https://infisical.com/docs/cli/scanning-overview)

## 开源版 vs 付费版

本仓库在 [MIT 协议](https://github.com/Infisical/infisical/blob/main/LICENSE) 下发布，但 `ee` 目录除外，该目录包含需要 Infisical 授权的高级企业功能。

如果您有兴趣使用托管的 Infisical Cloud 或本地部署的企业版，请查看 [我们的官网](https://infisical.com/) 或 [预约会议](https://infisical.cal.com/vlad/infisical-demo)。

## 安全性

请不要通过 GitHub Issues 或我们的公开论坛报告安全漏洞，因为这些是公开的！

Infisical 非常重视安全问题。如果您有任何关于 Infisical 的安全疑虑，或认为发现了漏洞，请通过 security@infisical.com 联系我们。邮件中请尽量提供问题的描述，以及最好能提供复现方式。安全团队将尽快回复您。

请注意，此安全邮箱仅用于未公开的漏洞。在公开披露之前，请务必先向我们报告任何安全问题。

## 贡献

无论贡献大小，我们都非常欢迎。请查看我们的指南了解如何 [开始贡献](https://infisical.com/docs/contributing/getting-started)。

不确定从哪里开始？您可以：

- 加入我们的 <a href="https://infisical.com/slack">Slack</a>，在那里向我们提问。

## 我们正在招聘！

如果您正在阅读这段文字，说明您很可能喜欢我们打造的产品。

您也可能是我们团队的优秀人选。我们正在快速发展，非常欢迎您 [加入我们](https://infisical.com/careers)。