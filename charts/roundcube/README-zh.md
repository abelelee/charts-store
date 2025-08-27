Roundcube Webmail
=================
[roundcube.net](https://roundcube.net)

[![Tests Status](https://github.com/roundcube/roundcubemail/actions/workflows/tests.yml/badge.svg?branch=master)](https://github.com/roundcube/roundcubemail/actions/workflows/tests.yml)

注意
---------
这只是GIT仓库的一个快照，**并不是Roundcube的稳定版本**。不建议使用此版本替换现有的Roundcube安装。同时，强烈建议为此安装使用单独的数据库。


简介
------------
Roundcube Webmail 是一个基于浏览器、支持多语言的 IMAP 客户端，具有类似应用程序的用户界面。它提供了电子邮件客户端应有的全部功能，包括 MIME 支持、地址簿、文件夹管理、消息搜索和拼写检查。Roundcube Webmail 使用 PHP 编写，并需要 MariaDB、MySQL、PostgreSQL 或 SQLite 数据库。通过其插件 API 可以轻松扩展功能，用户界面也可以通过皮肤进行完全自定义。

运行在 Web 服务器上的代码主要使用 PHP 和 JavaScript 编写。它包含一个自定义框架，其中的 IMAP 库源自 [IlohaMail][iloha]，并依赖于一组外部库（请参阅 composer.json 和 jsdeps.json 文件）。

版本发布
--------

Roundcubemail 的版本发布遵循语义化版本号规则。更多细节请阅读 [RELEASE_MANAGEMENT 文件](RELEASE_MANAGEMENT.md)。

安装
------------
有关如何在服务器上安装 Roundcube Webmail 的详细说明，请参阅与此文档位于同一目录下的 INSTALL 文档。

如果您正在升级旧版本的 Roundcube，请按照 UPGRADING 文件中描述的步骤进行操作。

浏览器支持
---------------
Roundcube 的客户端使用 jQuery 3.x（及其他库），因此继承了其浏览器支持特性。目前支持以下浏览器：

- Chrome: (Current - 1) 和 Current
- Edge: (Current - 1) 和 Current
- Firefox: (Current - 1) 和 Current, ESR
- Internet Explorer: 11+
- Safari: (Current - 1) 和 Current
- Opera: Current

许可证
-------
本程序是自由软件：您可以根据自由软件基金会发布的 GNU 通用公共许可证（**皮肤和插件有例外规定**）的条款重新分发和/或修改它。您可以选择使用该许可证的第 3 版，或者（根据您的选择）任何更新的版本。

本程序是希望它有用的前提下分发的，**没有任何担保**，甚至不包括适销性和特定用途适用性的隐含担保。有关更多细节，请参阅 GNU 通用公共许可证。

您应该已收到一份 GNU 通用公共许可证的副本。如果没有，请访问 [www.gnu.org/licenses/][gpl]。

本文件是 Roundcube Webmail 软件的一部分，并且针对此软件，我们添加了以下例外规定：仅通过引用方式调用 Roundcube Webmail 软件函数的插件和皮肤，不应被视为对软件的修改。

如果您希望在其他项目中使用本文件，或者创建一个不会成为 Roundcube Webmail 软件一部分的修改版本，您可以删除上述例外条款，并按照许可证的原始版本使用此源代码。

有关皮肤和插件的许可及例外规定的更多详情，请参阅 [roundcube.net/license][license]

贡献
------------
想帮助 Roundcube 成为有史以来最好的 Web 邮件解决方案吗？
Roundcube 是开源软件。我们的开发人员和贡献者都是志愿者，我们始终欢迎新的加入和资源。
更多信息请访问 [roundcube.net/contribute][contrib]

联系
-------
有关错误报告或功能请求，请参考 [Github][githubissues] 上的跟踪系统，或订阅我们的邮件列表。
详细信息请参阅 [roundcube.net/support][support]。

您也可以随时向项目管理员发送邮件：
hello(at)roundcube(dot)net

[iloha]:        https://sourceforge.net/projects/ilohamail/
[gpl]:          https://www.gnu.org/licenses/
[license]:      https://roundcube.net/license
[contrib]:      https://roundcube.net/contribute
[support]:      https://roundcube.net/support
[githubissues]: https://github.com/roundcube/roundcubemail/issues