# Matomo（原 Piwik）- matomo.org

[![最新稳定版本](https://poser.pugx.org/matomo/matomo/v/stable)](https://matomo.org/download/)
[![最新不稳定版本](https://poser.pugx.org/matomo/matomo/v/unstable)](https://builds.matomo.org/)
[![许可证](https://poser.pugx.org/piwik/piwik/license)](https://matomo.org/free-software/)

## 代码状态

[![Matomo 测试](https://github.com/matomo-org/matomo/actions/workflows/matomo-tests.yml/badge.svg)](https://github.com/matomo-org/matomo/actions/workflows/matomo-tests.yml)
[![未关闭问题的百分比](http://isitmaintained.com/badge/open/matomo-org/matomo.svg)](http://isitmaintained.com/project/matomo-org/matomo "Percentage of issues still open")

## 描述

Matomo 是领先的自由/开源分析平台。

Matomo 是一个完整的 PHP MySQL 软件程序，您可以下载并安装在自己的 Web 服务器上。
在五分钟左右的安装过程结束后，您将获得一段 JavaScript 代码。
只需将此标签复制并粘贴到您希望跟踪的网站页面上，即可实时访问您的分析报告。

Matomo 致力于成为 Google Analytics（谷歌分析）的自由软件替代方案，目前已在超过 140 万个网站上使用。隐私保护功能内建！

## 使命宣言

> « 作为一个社区，创建领先的国际开源数字分析平台，让用户完全掌控自己的数据。»

简而言之：
> « 解放 Web 分析 »

## 许可证

Matomo 以 GPL v3（或更高版本）许可证发布，请参阅 [LICENSE](LICENSE) 文件。

## 系统要求

  * PHP 7.2.5 或更高版本
  * MySQL 5.5 或更高版本，或者 MariaDB
  * PHP 扩展 pdo 和 pdo_mysql，或者 MySQLi 扩展
  * Matomo 与操作系统和服务器无关

更多信息请访问 https://matomo.org/docs/requirements/。

## 安装 Matomo

  * [下载 Matomo](https://matomo.org/download/)
  * 将 Matomo 上传到您的 Web 服务器
  * 用浏览器访问该目录
  * 按照安装步骤操作
  * 将提供的 JavaScript 代码添加到您的网页中
  * （您也可以通过启用 VisitorGenerator 插件生成测试数据）

更多信息请访问 https://matomo.org/docs/installation/。

### 为 Matomo 开发

当您需要为开发目的使用 Matomo 时，您需要 [从 Git 仓库安装 Matomo](https://matomo.org/faq/how-to-install/faq_18271/)。

这将为您提供一个可使用的 DDEV 环境。更多细节请参阅 [DDEV README](.ddev/README.md)。

## 免费试用

如果您没有服务器或者不想自行托管，可以使用我们的 Matomo Cloud 合作伙伴服务（21 天免费试用）：https://matomo.org/start-free-analytics-trial/

## 在线演示

访问 [demo.matomo.cloud](https://demo.matomo.cloud/) 查看 Matomo 的在线演示。

## 更新日志

有关当前和过去版本中已关闭的所有工单列表，请参阅 [matomo.org/changelog/](https://matomo.org/changelog/)。有关 Matomo 平台的技术变更列表，请参阅 [developer.matomo.org/changelog](https://developer.matomo.org/changelog)。

## 参与贡献！

我们致力于解放 Web 分析，提供一个用于简单和高级分析的自由平台。Matomo 是由数十位像您一样的开发者共同构建的，我们需要您的帮助来使 Matomo 更加完善……为什么不从今天开始参与一个有意义的项目？[了解如何为 Matomo 做出贡献](https://matomo.org/get-involved)。

## 翻译

我们的翻译工作通过 [Weblate](https://hosted.weblate.org/engage/matomo/) 进行管理。

[![翻译状态](https://hosted.weblate.org/widgets/matomo/-/horizontal-auto.svg)](https://hosted.weblate.org/engage/matomo/)

## 质量保证

Matomo 项目使用了不断扩展的全面测试集，包括数千个单元测试、数百个自动化集成测试、系统测试、JavaScript 测试和截图 UI 测试，这些测试在持续集成服务器上运行，作为其软件质量保障的一部分。[了解更多](https://developer.matomo.org/guides/tests)。

我们使用 [BrowserStack.com](https://www.browserstack.com/) 测试工具来确保 Matomo 用户界面与多种浏览器兼容。

## 安全性

安全性在 Matomo 中具有最高优先级。一旦发现潜在问题，我们会尽快验证、修补并发布修复程序。我们设有安全漏洞奖励计划，以奖励研究人员发现安全问题并向我们报告的行为。

[了解更多](https://matomo.org/security/) 或查看我们的 [HackerOne 项目](https://hackerone.com/matomo)。

## Matomo 支持

如需**免费支持**，请在我们的社区论坛中发帖：[forum.matomo.org](https://forum.matomo.org/)

如需**专业付费支持**，请购买 Matomo On-Premises 支持计划：[matomo.org/support-plans](https://matomo.org/support-plans/)

## 联系方式

官网：[matomo.org](https://matomo.org)

关于我们：[matomo.org/team/](https://matomo.org/team/)

联系我们：[matomo.org/contact/](https://matomo.org/contact/)

## 更多信息

Matomo 与众不同的特点：

  * 您拥有自己的网站分析数据：由于 Matomo 安装在您的服务器上，数据存储在您自己的数据库中，您可以通过强大的 Matomo Analytics API 获取所有统计数据。

  * Matomo 是一款自由软件，可以轻松配置以尊重访客的隐私。

  * 现代化、易于使用的用户界面：您可以完全自定义仪表盘，拖放小部件等。

  * Matomo 的功能通过插件实现：您可以添加新功能或移除不需要的功能。
    您可以自己开发网站分析插件，或者聘请顾问为您开发定制功能并集成到 Matomo 中。

  * 活跃的国际开源社区，拥有超过 20 万名活跃用户（跟踪的网站数量更多！）

  * 高级网站分析功能，如电子商务跟踪、目标跟踪、活动跟踪、
    自定义变量、邮件报告、自定义分段编辑器、地理定位、实时访问和地图，[还有更多功能！](https://matomo.org/feature-overview/)

更多文档和信息请访问 https://matomo.org。

我们正在共同打造全球最佳的开源分析平台！