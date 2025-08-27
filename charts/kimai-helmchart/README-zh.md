<p align="center">
    <img src="https://raw.githubusercontent.com/kimai/images/main/repository-header.png" alt="Kimai logo">
</p>

<p align="center">
    <a href="https://github.com/kimai/kimai/actions"><img alt="CI 状态" src="https://github.com/kimai/kimai/actions/workflows/testing.yaml/badge.svg"></a>
    <a href="https://codecov.io/gh/kimai/kimai"><img alt="代码覆盖率" src="https://codecov.io/gh/kimai/kimai/branch/main/graph/badge.svg"></a>
    <a href="https://packagist.org/packages/kimai/kimai"><img alt="最新稳定版本" src="https://poser.pugx.org/kimai/kimai/v/stable"></a>
    <a href="https://www.gnu.org/licenses/agpl-3.0.en.html"><img alt="许可证" src="https://poser.pugx.org/kimai/kimai/license"></a>
    <a href="https://phpc.social/@kimai" rel="me"><img alt="Mastodon" src="https://img.shields.io/badge/toot-%40kimai-8c8dff"></a>
</p>

<h1 align="center">Kimai - 时间追踪工具</h1>

Kimai 是一个专业的免费开源时间追踪应用程序。  
它适用于自由职业者，也适用于拥有数十甚至上百名用户的公司。  
Kimai 的设计初衷是用于项目时间的追踪，并附带了许多高级功能，包括但不限于：

JSON API、开票功能、数据导出、多计时器和打卡上下班模式、标签、多用户 - 多时区 - 多语言（已有[30多种语言翻译](https://hosted.weblate.org/projects/kimai/)），
支持通过 SAML/LDAP/数据库进行身份验证、基于 TOTP 的双因素身份验证（2FA）、可自定义的角色和团队权限、响应式设计，
用户/客户/项目的特定费率、高级搜索与过滤功能、金钱和时间预算、高级报表功能、支持[插件](https://www.kimai.org/store/)，
以及更多功能。

### 版本

目前存在两个 [版本](https://www.kimai.org/documentation/versions.html) 的 Kimai：

- [版本 2](https://github.com/kimai/kimai) — 当前的稳定版本（PHP 8.1+）
- [版本 1](https://github.com/kimai/kimai/tree/1.x) — 请**不要使用**，已于 2023 年中停止支持（PHP 7.4）

### 链接

- [首页](https://www.kimai.org) — Kimai 官方网站
- [博客](https://www.kimai.org/blog/) — 阅读最新资讯
- [文档](https://www.kimai.org/documentation/) — 学习如何使用 Kimai

### 系统要求

- 最低 PHP 8.1.3（支持 PHP 8.2 和 8.3）
- MariaDB 或 MySQL
- 一台 Web 服务器和子域名（不支持子目录）
- 必要的 PHP 扩展：`gd`、`intl`、`json`、`mbstring`、`pdo`、`tokenizer`、`xml`、`xsl`、`zip`

## 安装

- 使用 Docker-Compose 搭配 Caddy 在 [Hetzner](https://www.kimai.org/documentation/hosting-hetzner-cloud.html) 和 [DigitalOcean](https://www.kimai.org/documentation/hosting-digital-ocean.html)
- 使用 Git 和 Composer 的 [SSH 安装](https://www.kimai.org/documentation/installation.html)
- [Docker 镜像](https://hub.docker.com/r/kimai/kimai2)，包含 FPM 或带 Apache
- [Synology](https://www.kimai.org/documentation/synology.html) 用户可以运行 Docker 版本
- 如果你想开发 Kimai 集成，请参考 [开发者环境搭建](https://www.kimai.org/documentation/developers.html)

更多关于[本地部署](https://www.kimai.org/documentation/chapter-on-premise.html)的安装方式也有详细说明。

如果你不想自行托管 Kimai，也可以使用 [云端版本](https://www.kimai.cloud/)。

### 升级 Kimai

- [升级 Kimai](https://www.kimai.org/documentation/updates.html) — 获取最新版本
- [升级指南](UPGRADING.md) — 版本特定的升级步骤

### 插件

- [插件市场](https://www.kimai.org/store/) — 提供付费和免费插件
- [开发者文档](https://www.kimai.org/documentation/developers.html) — 如何创建插件

## 路线图与发布

你可以查看公开的开发 [路线图](https://github.com/orgs/kimai/projects/2)，它对社区的反馈和建议保持开放，欢迎你提出自己的 [想法](https://github.com/kimai/kimai/issues)。

版本发布将定期进行，最迟每几周一次。
所有代码变更，无论是新功能还是错误修复，都会提交到 `main` 分支。

## 贡献

你想为这个项目做贡献？太棒了！
最好的开始方式是为 bug 或新功能请求 [提交新 issue](https://github.com/kimai/kimai/issues)，或者在 [讨论区](https://github.com/kimai/kimai/discussions) 提问、寻求帮助和支持。

如果你还不知道如何贡献，以下是一些可能的方向：

- 推广 Kimai：请[在我们的 Wall of love 上发表评价](https://love.kimai.org)，在各类软件平台为 Kimai 投票，你可以通过 Toot、推文、LinkedIn、Reddit 或其他社交媒体分享它！
- 回答问题：如果你知道其他用户问题的解答，请分享你的知识。
- 提出建议：如果你认为某些地方可以改进，或者缺少某个重要功能，请提交功能请求。
- 报告 bug：有助于让 Kimai 变得更好。
- 你不必是程序员：文档和翻译也总是需要帮助的。
- 赞助项目：开源软件的开发需要资金支持！

我们“行为准则”中只有一条简单规则：不要做令人讨厌的事！

### 致谢

Kimai 基于现代技术和框架开发，例如 [PHP](https://www.php.net/)、
[Symfony](https://github.com/symfony/symfony) 和 [Doctrine](https://github.com/doctrine/)、
[Bootstrap](https://github.com/twbs/bootstrap) 和 [Tabler](https://tabler.io/)，
以及 [众多](composer.json) [其他](package.json) 开源项目。