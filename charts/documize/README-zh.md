Documize Community 是一个开源的、现代化的、自托管的、企业级知识管理解决方案。

- 适用于技术人员和非技术人员
- 旨在统一面向客户和内部的文档管理
- 通过标签、空间和分类进行组织管理

它采用 Golang + EmberJS 开发，最终编译为一个可在 Linux、Windows 和 Mac 上运行的独立可执行二进制文件。

您只需提供数据库支持 —— PostgreSQL、Microsoft SQL Server 或任意 MySQL 变体。

![Documize Community](https://github.com/documize/community/blob/master/screenshot.png?raw=true)

## 最新版本

[社区版：v5.13.0](https://github.com/documize/community/releases)

[社区+版：v5.13.0](https://www.documize.com/community/get-started)

社区+版是包含高级功能和客户支持的企业级版本：

- 内容审批流程
- 按标签、空间和分类组织内容
- 内容版本管理
- 内容生命周期管理
- 收集内容反馈
- 内容导出为 PDF
- 分析与报告
- 活动流
- 审计日志
- 操作任务分配
- 产品支持

社区+版 [前五名用户免费](https://www.documize.com/community/get-started)，超过五名用户后，每年仅需 900 美元即可支持 100 名用户。

## 操作系统支持

- Linux
- Windows
- macOS
- Raspberry Pi（ARM 构建）

支持 AMD 和 ARM 64 位架构。

## 数据库支持

对于所有数据库类型，必须支持全文搜索（FTS）。

- PostgreSQL（v9.6+）
- Microsoft SQL Server（2016+ 并启用 FTS）
- Microsoft SQL Azure（v12+）
- MySQL（v5.7.10+ 和 v8.0.12+）
- Percona（v5.7.16-10+）
- MariaDB（10.3.0+）

## 浏览器支持

- Firefox
- Chrome
- Safari
- Microsoft Edge
- Brave
- Vivaldi
- Opera

## 技术栈

- Go（v1.23.4）
- Ember JS（v3.12.0）

## 身份验证选项

除了使用电子邮件/密码登录外，还可以通过以下方式认证：

* LDAP
* Active Directory
* Red Hat Keycloak
* 中央认证服务（CAS）

使用 LDAP/Active Directory 时，可以同时启用电子邮件/密码的双因素认证。

## 本地化支持

开箱即用支持以下语言：

- 英语
- 德语
- 法语
- 中文（Chinese）
- 葡萄牙语（巴西）
- 日语
- 意大利语
- 阿根廷西班牙语

欢迎提交其他语言的 PR。

## 产品/技术支持

对于社区版和社区+版，如需产品帮助、建议或其他问题，请联系我们的技术支持：

<support@documize.com>

我们力争在两个工作日内回复。

## 法律声明

<https://www.documize.com>

本软件（Documize Community 版）遵循 GNU AGPL v3 许可证 <http://www.gnu.org/licenses/agpl-3.0.en.html>。

Documize Community 使用了其他开源组件，我们在 [NOTICES](NOTICES.md) 中对它们进行了说明。