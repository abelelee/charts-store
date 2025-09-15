<div align="center">

[![Password Pusher 前页](https://pwpush.fra1.cdn.digitaloceanspaces.com/branding/logos/horizontal-logo-small.png)](https://pwpush.com/)

__通过自删除链接和完整审计日志安全地共享敏感信息（也支持文件！）__

[![](https://badgen.net/twitter/follow/pwpush)](https://twitter.com/pwpush)
![](https://badgen.net/github/stars/pglombardo/PasswordPusher)
[![](https://badgen.net/uptime-robot/month/m789048867-17b5770ccd78208645662f1f)](https://stats.uptimerobot.com/6xJjNtPr93)
[![](https://badgen.net/docker/pulls/pglombardo/pwpush-ephemeral)](https://hub.docker.com/repositories)

[![GitHub Workflow Status (with event)](https://img.shields.io/github/actions/workflow/status/pglombardo/PasswordPusher/ruby-tests.yml)](https://github.com/pglombardo/PasswordPusher/actions/workflows/ruby-tests.yml)
[![Dependencies Status](https://img.shields.io/badge/dependencies-up%20to%20date-brightgreen.svg)](https://github.com/pglombardo/pwpush-cli/pulls?utf8=%E2%9C%93&q=is%3Apr%20author%3Aapp%2Fdependabot)
[![Semantic Versions](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--versions-e10079.svg)](https://github.com/pglombardo/pwpush-cli/releases)
[![License](https://img.shields.io/github/license/pglombardo/PasswordPusher)](https://github.com/pglombardo/PasswordPusher/blob/master/LICENSE)

</div>

------

让你的用户默认就是安全的。

Password Pusher 是一个开源应用程序，用于在网络上安全地传递敏感信息。秘密链接会在一定查看次数后和/或时间过后自动过期。

该服务托管在 [pwpush.com](https://pwpush.com)，但你也可以通过几个简单的步骤轻松运行你自己的私有实例。

* __易于安装：__ 通过 Docker、云服务自建，或直接使用 [pwpush.com](https://pwpush.com)
* __开源：__ 没有黑盒代码。只使用可信、经过测试和审查的开源代码。
* __多功能：__ 可推送自动过期并自删除的密码、文本、文件或URL。
* __审计日志：__ 跟踪和控制你分享的内容，并查看谁查看过。
* __加密存储：__ 所有敏感数据均加密存储，过期后完全删除。
* __自托管：__ 支持数据库后端或临时存储，轻松运行你自己的隔离实例。
* __管理仪表板：__ 使用内置的管理仪表板管理你的自托管实例。
* __自动TLS：__ 无需再配置 Nginx、Apache 或 SSL/TLS 终止点。开箱即用，安全即启。
* __登录功能：__ 邀请同事，跟踪谁推送了什么、谁查看了什么。
* __无品牌页面：__ 没有LOGO、多余文字或无关链接，避免终端用户困惑。
* __国际化：__ 内置29种语言翻译，可通过UI或URL轻松切换。
* __JSON API：__ 提供原始JSON API供第三方工具或命令行使用 `curl` 或 `wget`。
* __命令行接口：__ 使用CLI工具或自定义脚本自动化你的密码分发。
* __主题：__ 内置 [26种主题](https://docs.pwpush.com/docs/themes/)，感谢 [Bootswatch](https://github.com/thomaspark/bootswatch)。只需一个环境变量即可选择。
* __可定制：__ 通过环境变量更改文本和默认选项。
* __亮色与暗色主题：__ 通过CSS @media集成，站点主题自动适配你的本地偏好。
* __可重新品牌化：__ 完全白标：自定义主题、站点名称、标语和LOGO以适配你的环境。
* __自定义CSS：__ 添加你自己的CSS文件以实现个性化设计。
* __>10年历史：__ 在过去的14年中，Password Pusher 已安全传输了数以千万计的密码。
* __持续维护：__ 我乐于为IT/安全社区贡献，获得良好的口碑。
* __诚实软件：__ 由我 [本人](https://github.com/pglombardo) 编写和维护的开源项目，并得到一些优秀贡献者帮助。无组织、无公司、无邪恶目的。

💌 --> 注册 [邮件列表](https://buttondown.email/pwpush?tag=github) 获取重大版本更新、安全问题、新功能、集成、技巧等信息。

关注 Password Pusher 的更新，请关注 [X](https://x.com/pwpush)、[Reddit](https://www.reddit.com/r/pwpush)、[Gettr](https://gettr.com/user/pwpush) 和 [Facebook](https://www.facebook.com/pwpush)。

-----

![](./app/assets/images/features/front-page-large.png)
![](./app/assets/images/features/audit-log-large.png)
![](./app/assets/images/features/secret-url-languages-large.png)
![](./app/assets/images/features/password-generator-large.png)
![](./app/assets/images/features/dark-theme.gif)
![](./app/assets/images/features/preliminary-step.gif)

# 版本说明

如果你考虑自建OSS版本，可以立即在 [https://oss.pwpush.com](https://oss.pwpush.com) 试用。

2024年，我在 [pwpush.com](https://pwpush.com) 上推出了专属的 **Pro功能**，以更好地支持该项目。

这些Pro功能会定期迁移到OSS版本中。你可以阅读 [这里](https://docs.pwpush.com/docs/editions/) 了解其运作方式。

要查看 pwpush.com 与OSS版本之间的功能差异，请查看 [功能矩阵](https://pwpush.com/features#matrix)。

# ⚡️ 快速开始

## 运行你自己的临时实例

→ 设置一条DNS记录指向你的服务器（例如：`pwpush.example.com`），然后运行：

```sh
docker run -d -p "80:80" -p "443:433" --env TLS_DOMAIN=pwpush.example.com pglombardo/pwpush:latest
```

然后访问 `https://pwpush.example.com`。

_或者_

→ 使用我们提供的 [生产就绪的Docker Compose文件](https://docs.pwpush.com/docs/installation/#docker-compose)，支持持久化数据库。

## 使用工具、集成、API或CLI

→ 使用众多 [第三方工具](https://docs.pwpush.com/docs/3rd-party-tools/) 与Password Pusher进行交互。

# 📚 文档

查看完整的 [Password Pusher 文档](https://docs.pwpush.com)。

# 🌎 语言翻译

多年来，[Translation.io](https://translation.io/?utm_source=pwpush) 为Password Pusher的开源版本提供了免费翻译工具访问权限。因此，我们现在内置了 **31种语言翻译**！

![](https://translation.io/?utm_source=pwpush)

如果你公司或开源项目有翻译需求，请考虑使用 [Translation.io](https://translation.io/?utm_source=pwpush) 并表示感谢！

# 📼 致谢

## 安全研究人员

* Kullai Metikala | [Github](https://github.com/kullaisec) | [LinkedIn](https://www.linkedin.com/in/kullai-metikala-8378b122a/)
* [Positive Technologies](https://global.ptsecurity.com)
* Igniter | [Github](https://github.com/igniter07)

## 翻译人员

感谢我们出色的翻译人员！

| 姓名   | 语言  | |
|---|---|---|
| [Oyale](https://github.com/oyale) | [加泰罗尼亚语](https://pwpush.com/ca) | |
| Finn Skaaning  |  [丹麦语](https://pwpush.com/da/p/ny) | |
| [Mihail Tchetchelnitski](https://github.com/mtchetch)  | [芬兰语](https://pwpush.com/fi/p/uusi)  | |
| [Thibaut](https://github.com/tibo59) | [法语](https://pwpush.com/fr/p/Nouveau) | |
| Thomas Wölk | [德语](https://pwpush.com/de/p/neu) | [Github](https://github.com/confluencepoint/), [Twitter](https://twitter.com/confluencepoint) |
| Martin Otto |[德语](https://pwpush.com/de/p/neu) | |
| Robin Jørgensen |[挪威语](https://pwpush.com/no/p/ny) | |
| [Łukasz](https://github.com/drpt)|[波兰语](https://pwpush.com/pl/p/nowy) | |
| [Jair Henrique](https://github.com/jairhenrique/) | [葡萄牙语](https://pwpush.com/pt-br/p/novo) | |
| [Fabrício Rodrigues](https://www.linkedin.com/in/ifabriciorodrigues/)| [葡萄牙语](https://pwpush.com/pt-br/p/novo) | |
| [Ivan MFreitas](https://github.com/IvanMFreitas)| [葡萄牙语](https://pwpush.com/pt-br/p/novo) | |
| Sara Faria| [葡萄牙语](https://pwpush.com/pt-br/p/novo) | |
| [Oyale](https://github.com/oyale) |[西班牙语](https://pwpush.com/es) | |
| johan323 |[瑞典语](https://pwpush.com/sv/p/ny) | |
| Fredrik Arvas|[瑞典语](https://pwpush.com/sv/p/ny) | |
| Pedro Marques | [欧洲葡萄牙语](https://pwpush.com/pt-pt/p/novo) | |

也感谢 [translation.io](https://translation.io) 提供优秀的翻译管理服务，并慷慨地为开源项目提供免费支持。

## 容器

感谢：

* [@fiskhest](https://github.com/fiskhest) 提供 [Kubernetes安装说明和清单](https://github.com/pglombardo/PasswordPusher/tree/master/containers/kubernetes)。

* [@sfarosu](https://github.com/sfarosu) 为 [贡献](https://github.com/pglombardo/PasswordPusher/pull/82) Docker、Kubernetes 和 OpenShift 容器支持。

* [sirux88](https://github.com/sirux88) 清理Docker文件并添加多阶段构建。

## 其他

感谢：

* [@iandunn](https://github.com/iandunn) 提升密码表单安全性。

* [Kasper 'kapöw' Grubbe](https://github.com/kaspergrubbe) 修复 [JSON POST问题](https://github.com/pglombardo/PasswordPusher/pull/3)。

* [JarvisAndPi](http://www.reddit.com/user/JarvisAndPi) 设计了网站图标。

...以及更多贡献者。详见 [贡献者页面](https://github.com/pglombardo/PasswordPusher/graphs/contributors)。

# 🎁 捐助

**捐助对任何Password Pusher用户来说都不是必须的。该项目本质上始终是开源且免费使用的。**

话虽如此，如果你觉得Password Pusher对你有帮助，并希望支持并加速其持续开发，所有捐助都将 **非常感激**。

| [![捐助](https://pwpush.fra1.cdn.digitaloceanspaces.com/misc/pwpush-donate-stripe-qr-small.png)]() | 或 | [![捐助](https://img.shields.io/badge/Donate-Stripe-blue.svg)](https://buy.stripe.com/7sI4gCgTT1tr6WY3cd) |
|---|---|---|

作为捐助的替代方案，你也可以通过注册 [pwpush.com 的付费计划](https://pwpush.com/pricing) 来支持该项目。

捐助将用于以下用途：

* 托管费用（Digital Ocean、Hatchbox、Brevo 支持与事务邮件、Docker Hub、Uptime Robot）
* 社区支持
* 持续维护
  * 升级
  * 测试
* 持续开发
  * 开发工具
  * 授权费用
  * 文档

**法律免责声明：** 请注意，Password Pusher 由 Apnotic, LLC 拥有和运营，这是一家营利性公司，由我 [本人](https://github.com/pglombardo) 拥有和运营。虽然我们非常感谢捐助并用于支持项目开发，但这些捐助不能作为慈善捐款抵税。直接捐助给Password Pusher的资金支持的是一个商业实体，应视为自愿付款，用于维持服务并鼓励持续开发。

**相关阅读：**

* [什么是 Apnotic, LLC？](https://docs.pwpush.com/docs/faq/#what-is-apnotic)
* [信任是个问题。为什么我应该信任并使用 Password Pusher？](https://docs.pwpush.com/docs/faq/#trust-is-a-concern--why-should-i-trust-and-use-password-pusher)
* [Pro功能的开发流程是怎样的？](https://docs.pwpush.com/posts/feature-pipeline/)

# Star 历史

[![Star 历史图表](https://api.star-history.com/svg?repos=pglombardo/PasswordPusher&type=Date)](https://www.star-history.com/#pglombardo/PasswordPusher&Date)

# 🛡 许可证

[![License](https://img.shields.io/github/license/pglombardo/PasswordPusher)](https://github.com/pglombardo/PasswordPusher/blob/master/LICENSE)

该项目采用 `Apache License 2.0` 协议。详见 [LICENSE](https://github.com/pglombardo/PasswordPusher/blob/master/LICENSE) 获取详细信息。

# 📃 引用格式

```bibtex
@misc{PasswordPusher,
  author = {Peter Giacomo Lombardo},
  title = {Securely share sensitive information with automatic expiration & deletion after a set number of views or duration. Track who, what and when with full audit logs.},
  year = {2025},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/pglombardo/PasswordPusher}}
}
```