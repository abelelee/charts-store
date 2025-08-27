---
![Vaultwarden Logo](./resources/vaultwarden-logo-auto.svg)

一个使用 Rust 编写的 Bitwarden 客户端 API 的替代服务器实现，兼容 [官方 Bitwarden 客户端](https://bitwarden.com/download/) [[免责声明](#disclaimer)]，非常适合在运行官方资源占用较高的服务可能不太理想的环境中进行自托管部署。

---

[![GitHub Release](https://img.shields.io/github/release/dani-garcia/vaultwarden.svg?style=for-the-badge&logo=vaultwarden&color=005AA4)](https://github.com/dani-garcia/vaultwarden/releases/latest)
[![ghcr.io Pulls](https://img.shields.io/badge/dynamic/json?style=for-the-badge&logo=github&logoColor=fff&color=005AA4&url=https%3A%2F%2Fipitio.github.io%2Fbackage%2Fdani-garcia%2Fvaultwarden%2Fvaultwarden.json&query=%24.downloads&label=ghcr.io%20pulls&cacheSeconds=14400)](https://github.com/dani-garcia/vaultwarden/pkgs/container/vaultwarden)
[![Docker Pulls](https://img.shields.io/docker/pulls/vaultwarden/server.svg?style=for-the-badge&logo=docker&logoColor=fff&color=005AA4&label=docker.io%20pulls)](https://hub.docker.com/r/vaultwarden/server)
[![Quay.io](https://img.shields.io/badge/quay.io-download-005AA4?style=for-the-badge&logo=redhat&cacheSeconds=14400)](https://quay.io/repository/vaultwarden/server) <br>
[![Contributors](https://img.shields.io/github/contributors-anon/dani-garcia/vaultwarden.svg?style=flat-square&logo=vaultwarden&color=005AA4)](https://github.com/dani-garcia/vaultwarden/graphs/contributors)
[![Forks](https://img.shields.io/github/forks/dani-garcia/vaultwarden.svg?style=flat-square&logo=github&logoColor=fff&color=005AA4)](https://github.com/dani-garcia/vaultwarden/network/members)
[![Stars](https://img.shields.io/github/stars/dani-garcia/vaultwarden.svg?style=flat-square&logo=github&logoColor=fff&color=005AA4)](https://github.com/dani-garcia/vaultwarden/stargazers)
[![Issues Open](https://img.shields.io/github/issues/dani-garcia/vaultwarden.svg?style=flat-square&logo=github&logoColor=fff&color=005AA4&cacheSeconds=300)](https://github.com/dani-garcia/vaultwarden/issues)
[![Issues Closed](https://img.shields.io/github/issues-closed/dani-garcia/vaultwarden.svg?style=flat-square&logo=github&logoColor=fff&color=005AA4&cacheSeconds=300)](https://github.com/dani-garcia/vaultwarden/issues?q=is%3Aissue+is%3Aclosed)
[![AGPL-3.0 Licensed](https://img.shields.io/github/license/dani-garcia/vaultwarden.svg?style=flat-square&logo=vaultwarden&color=944000&cacheSeconds=14400)](https://github.com/dani-garcia/vaultwarden/blob/main/LICENSE.txt) <br>
[![Dependency Status](https://img.shields.io/badge/dynamic/xml?url=https%3A%2F%2Fdeps.rs%2Frepo%2Fgithub%2Fdani-garcia%2Fvaultwarden%2Fstatus.svg&query=%2F*%5Blocal-name()%3D'svg'%5D%2F*%5Blocal-name()%3D'g'%5D%5B2%5D%2F*%5Blocal-name()%3D'text'%5D%5B4%5D&style=flat-square&logo=rust&label=dependencies&color=005AA4)](https://deps.rs/repo/github/dani-garcia/vaultwarden)
[![GHA Release](https://img.shields.io/github/actions/workflow/status/dani-garcia/vaultwarden/release.yml?style=flat-square&logo=github&logoColor=fff&label=Release%20Workflow)](https://github.com/dani-garcia/vaultwarden/actions/workflows/release.yml)
[![GHA Build](https://img.shields.io/github/actions/workflow/status/dani-garcia/vaultwarden/build.yml?style=flat-square&logo=github&logoColor=fff&label=Build%20Workflow)](https://github.com/dani-garcia/vaultwarden/actions/workflows/build.yml) <br>
[![Matrix Chat](https://img.shields.io/matrix/vaultwarden:matrix.org.svg?style=flat-square&logo=matrix&logoColor=fff&color=953B00&cacheSeconds=14400)](https://matrix.to/#/#vaultwarden:matrix.org)
[![GitHub Discussions](https://img.shields.io/github/discussions/dani-garcia/vaultwarden?style=flat-square&logo=github&logoColor=fff&color=953B00&cacheSeconds=300)](https://github.com/dani-garcia/vaultwarden/discussions)
[![Discourse Discussions](https://img.shields.io/discourse/topics?server=https%3A%2F%2Fvaultwarden.discourse.group%2F&style=flat-square&logo=discourse&color=953B00)](https://vaultwarden.discourse.group/)

> [!IMPORTANT]
> **在使用此服务器时，请直接向我们报告任何错误或建议（参见 [联系](#联系)），无论你使用的是哪种客户端（移动端、桌面端、浏览器等）。请勿使用官方 Bitwarden 的支持渠道。**

<br>

## 特性

提供了几乎完整的 Bitwarden 客户端 API 实现，包括：

 * [个人保险库](https://bitwarden.com/help/managing-items/)
 * [发送](https://bitwarden.com/help/about-send/)
 * [附件](https://bitwarden.com/help/attachments/)
 * [网站图标](https://bitwarden.com/help/website-icons/)
 * [个人 API 密钥](https://bitwarden.com/help/personal-api-key/)
 * [组织](https://bitwarden.com/help/getting-started-organizations/)
   - [集合](https://bitwarden.com/help/about-collections/),
     [密码共享](https://bitwarden.com/help/sharing/),
     [成员角色](https://bitwarden.com/help/user-types-access-control/),
     [群组](https://bitwarden.com/help/about-groups/),
     [事件日志](https://bitwarden.com/help/event-logs/),
     [管理员密码重置](https://bitwarden.com/help/admin-reset/),
     [目录连接器](https://bitwarden.com/help/directory-sync/),
     [策略](https://bitwarden.com/help/policies/)
 * [多因素/双因素身份验证](https://bitwarden.com/help/bitwarden-field-guide-two-step-login/)
   - [验证器](https://bitwarden.com/help/setup-two-step-login-authenticator/),
     [电子邮件](https://bitwarden.com/help/setup-two-step-login-email/),
     [FIDO2 WebAuthn](https://bitwarden.com/help/setup-two-step-login-fido/),
     [YubiKey](https://bitwarden.com/help/setup-two-step-login-yubikey/),
     [Duo](https://bitwarden.com/help/setup-two-step-login-duo/)
 * [紧急访问](https://bitwarden.com/help/emergency-access/)
 * [Vaultwarden 管理后台](https://github.com/dani-garcia/vaultwarden/wiki/Enabling-admin-page)
 * [修改后的 Web 保险库客户端](https://github.com/dani-garcia/bw_web_builds)（已包含在我们的容器中）

<br>

## 使用方法

> [!IMPORTANT]
> Web 保险库需要使用 [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API) 的安全上下文。
> 这意味着它只能通过 `http://localhost:8000`（使用下面示例中的端口）或在你 [启用 HTTPS](https://github.com/dani-garcia/vaultwarden/wiki/Enabling-HTTPS) 的情况下运行。

安装和使用 Vaultwarden 的推荐方法是通过我们发布的容器镜像，这些镜像发布在 [ghcr.io](https://github.com/dani-garcia/vaultwarden/pkgs/container/vaultwarden)、[docker.io](https://hub.docker.com/r/vaultwarden/server) 和 [quay.io](https://quay.io/repository/vaultwarden/server)。
请参见 [应使用哪个容器镜像](https://github.com/dani-garcia/vaultwarden/wiki/Which-container-image-to-use) 了解提供的标签说明。

我们还提供了 [社区驱动的软件包](https://github.com/dani-garcia/vaultwarden/wiki/Third-party-packages)，但这些软件包可能落后于最新版本，或者在 Vaultwarden 配置方式上有所不同，具体请参见我们的 [Wiki](https://github.com/dani-garcia/vaultwarden/wiki)。

或者，你也可以 [自行构建 Vaultwarden](https://github.com/dani-garcia/vaultwarden/wiki/Building-binary)。

虽然 Vaultwarden 基于 [Rocket Web 框架](https://rocket.rs) 并内置了对 TLS 的支持，但我们建议你设置一个反向代理（参见 [代理示例](https://github.com/dani-garcia/vaultwarden/wiki/Proxy-examples)）。

> [!TIP]
> **如需更详细的安装、使用和配置 Vaultwarden 的示例，请查看我们的 [Wiki](https://github.com/dani-garcia/vaultwarden/wiki)。**

### Docker/Podman CLI

拉取容器镜像，并从主机挂载一个卷以实现持久化存储。<br>
如果你更倾向于使用 podman，可以将 `docker` 替换为 `podman`。

```shell
docker pull vaultwarden/server:latest
docker run --detach --name vaultwarden \
  --env DOMAIN="https://vw.domain.tld" \
  --volume /vw-data/:/data/ \
  --restart unless-stopped \
  --publish 127.0.0.1:8000:80 \
  vaultwarden/server:latest
```

这将保留 `/vw-data/` 下的所有持久化数据，你可以根据需要调整路径。

### Docker Compose

要使用 Docker Compose，你需要创建一个 `compose.yaml` 文件，用于保存运行 Vaultwarden 容器的配置。

```yaml
services:
  vaultwarden:
    image: vaultwarden/server:latest
    container_name: vaultwarden
    restart: unless-stopped
    environment:
      DOMAIN: "https://vw.domain.tld"
    volumes:
      - ./vw-data/:/data/
    ports:
      - 127.0.0.1:8000:80
```

<br>

## 联系方式

有问题、建议或需要帮助？加入我们的社区：[Matrix](https://matrix.to/#/#vaultwarden:matrix.org)、[GitHub 讨论区](https://github.com/dani-garcia/vaultwarden/discussions) 或 [Discourse 论坛](https://vaultwarden.discourse.group/)。

遇到 bug 或崩溃？请先搜索我们的 issue 跟踪器和讨论区，看看是否已有相关报告。如果没有，请 [发起新讨论](https://github.com/dani-garcia/vaultwarden/discussions) 或 [提交新 issue](https://github.com/dani-garcia/vaultwarden/issues/)。请确保你使用的是 Vaultwarden 的最新版本，并且没有类似的已开启或已关闭的 issue！

<br>

## 贡献者

感谢你们对本项目的贡献！

[![贡献者数量](https://img.shields.io/github/contributors-anon/dani-garcia/vaultwarden?style=for-the-badge&logo=vaultwarden&color=005AA4)](https://github.com/dani-garcia/vaultwarden/graphs/contributors)<br>
[![贡献者头像](https://contributors-img.web.app/image?repo=dani-garcia/vaultwarden)](https://github.com/dani-garcia/vaultwarden/graphs/contributors)

<br>

## 免责声明

**本项目与 [Bitwarden](https://bitwarden.com/) 或 Bitwarden, Inc. 无任何关联。**

不过，Vaultwarden 的一位活跃维护者受雇于 Bitwarden，他可以在自己的空闲时间为此项目做贡献。这些贡献独立于 Bitwarden，并由其他维护者审核。

维护者们共同为项目制定方向，专注于服务自托管社区，包括个人用户、家庭和小型组织，同时确保项目的可持续性。

**请注意：** 我们不对使用 Vaultwarden 期间可能发生的任何数据丢失负责。这包括密码、附件及其他应用程序处理的信息。我们强烈建议定期备份你的文件和数据库。然而，如果你遇到数据丢失，请立即与我们联系。

<br>

## Bitwarden_RS

本项目原名为 Bitwarden_RS，现已更名为 Vaultwarden，以与官方 Bitwarden 服务器区分开来，避免混淆及潜在的商标/品牌问题。<br>
更多说明请参见 [#1642 - v1.21.0 发布及项目更名为 Vaultwarden](https://github.com/dani-garcia/vaultwarden/discussions/1642)。