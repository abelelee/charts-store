## EspoCRM

[![PHPStan level 8](https://img.shields.io/badge/PHPStan-level%208-brightgreen)](#espocrm)

[EspoCRM](https://www.espocrm.com) 是一个免费的开源客户关系管理（CRM）平台，旨在帮助组织建立并维护良好的客户关系。
它提供了广泛的工具，用于在简单直观的界面中存储、组织和管理潜在客户、联系人、销售机会、营销活动、支持案例等所有业务信息。

![截图](https://user-images.githubusercontent.com/1006792/226094559-995dfd2a-a18f-4619-a21b-79a4e671990a.png)

### 架构

EspoCRM 是一个 Web 应用程序，前端设计为单页应用，后端 REST API 使用 PHP 编写。

### 演示

你可以在线 [演示](https://www.espocrm.com/demo/) 中体验该 CRM。

### 系统要求

* PHP 8.2 - 8.4；
* MySQL 8.0（或更高版本）或 MariaDB 10.3（或更高版本）；
* PostgreSQL 15（或更高版本）。

有关服务器配置的更多信息，请参阅 [这篇文章](https://docs.espocrm.com/administration/server-configuration/)。

### 为什么选择 EspoCRM？

* **开源透明**。EspoCRM 的源代码是开放且可访问的，任何人都可以检查其代码，了解 CRM 中的数据管理方式。
* **高度可定制**。你可以开发新功能、创建自定义实体、字段、关系和按钮，使系统完全符合你的特定需求。EspoCRM 不仅仅是一个 CRM，它还是一个用于构建自定义业务应用的平台。
* **简洁的用户界面**。EspoCRM 提供了一个整洁、简约且快速的用户界面，易于导航，学习曲线短。
* **直观的 REST API**。可以通过 REST API 轻松与其他应用程序集成。

### EspoCRM 的适用对象

* **初创公司、中小型企业**。这是一个价格合理、灵活且完全可定制的解决方案。
* **开发人员和技术爱好者**。你可以扩展功能、构建扩展并创建自定义集成。
* **任何需要免费 CRM 的人**。如果你正在寻找一个用户友好且安全的 CRM 平台，这将是一个不错的选择。

### 安装稳定版本

请参阅以下安装指南：

* [手动安装](https://docs.espocrm.com/administration/installation/)
* [通过脚本安装](https://docs.espocrm.com/administration/installation-by-script/)
* [使用 Docker 安装](https://docs.espocrm.com/administration/docker/installation/)
* [使用 Traefik 安装](https://docs.espocrm.com/administration/docker/traefik/)

### 下载

从我们的网站 [下载](https://www.espocrm.com/download/) 最新版本。你也可以从 GitHub 的 [发布页面](https://github.com/espocrm/espocrm/releases) 下载最新和之前的发布包。

### 版本说明

版本说明可在 GitHub 的 [发布页面](https://github.com/espocrm/espocrm/releases) 找到。

### 文档

请参阅面向管理员、用户和开发者的 [文档](https://docs.espocrm.com)。

### 报告 Bug

你可以创建一个 [GitHub issue](https://github.com/espocrm/espocrm/issues/new/choose) 或在我们的 [论坛](https://forum.espocrm.com/forum/bug-reports) 上发帖报告 Bug。

### 开发

请参阅 [开发者文档](https://docs.espocrm.com/development/)。

我们强烈建议使用 IDE 进行开发。后端代码库遵循 SOLID 原则，使用了接口、静态类型和泛型。我们建议从文档中的依赖注入（Dependency Injection）文章开始学习 EspoCRM。

元数据在 EspoCRM 应用中扮演着重要角色。所有可能的参数都通过 JSON Schema 描述，这意味着你将在 IDE 中获得自动补全功能。你也可以在文档中找到完整的元数据参考。

### 社区与支持

如果你有关于某些功能的问题、需要帮助或定制、希望与其他 EspoCRM 用户交流，或提交功能请求，请使用我们的 [社区论坛](https://forum.espocrm.com/)。我们相信，通过论坛提问和分享经验，可以让社区中的每个人都能参与并利用这些知识。

### 许可证

EspoCRM 是一个开源项目，采用 [GNU AGPLv3](https://raw.githubusercontent.com/espocrm/espocrm/master/LICENSE.txt) 许可证。

### 贡献

在我们合并你的 Pull Request 之前，你需要在此处接受我们的 CLA [CLA](https://github.com/espocrm/cla)。请参阅 [贡献指南](https://github.com/espocrm/espocrm/blob/master/.github/CONTRIBUTING.md)。

分支说明：

* **fix** – 即将发布的维护版本；小的修复应提交到此分支；
* **master** – 开发分支；新功能应提交到此分支；
* **stable** – 最新的稳定版本。

### 语言

如果你想改进现有翻译或添加尚未支持的语言，可以在我们的 [POEditor](https://poeditor.com/join/project/gLDKZtUF4i) 项目中进行贡献。相关说明请参阅 [此处](https://www.espocrm.com/blog/how-to-use-poeditor-to-translate-espocrm/)。如果你打算加入 POEditor 项目，建议通过我们的论坛发帖或通过网站上的联系表单告知我们你的意图。

POEditor 上的翻译更新通常会在小版本发布前合并到 GitHub 仓库中。