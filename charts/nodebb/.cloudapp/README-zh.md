# ![NodeBB](public/images/sm-card.png)

[![Workflow](https://github.com/NodeBB/NodeBB/actions/workflows/test.yaml/badge.svg)](https://github.com/NodeBB/NodeBB/actions/workflows/test.yaml)
[![Coverage Status](https://coveralls.io/repos/github/NodeBB/NodeBB/badge.svg?branch=master)](https://coveralls.io/github/NodeBB/NodeBB?branch=master)
[![Code Climate](https://codeclimate.com/github/NodeBB/NodeBB/badges/gpa.svg)](https://codeclimate.com/github/NodeBB/NodeBB)
[![](https://dcbadge.vercel.app/api/server/p6YKPXu7er?style=flat)](https://discord.gg/p6YKPXu7er)

[**NodeBB 论坛软件**](https://nodebb.org) 基于 Node.js 构建，支持 Redis、MongoDB 或 PostgreSQL 数据库。它使用 WebSocket 实现即时交互和实时通知。NodeBB 融合了现代网络的最佳特性：实时流式讨论、移动端响应式设计以及丰富的 RESTful 读写 API，同时保留了传统公告板/论坛的格式：分类层级结构、本地用户账户和异步消息传递。

NodeBB 本身包含一个“通用核心”基础功能，而额外的功能和集成则通过第三方插件实现。

### [立即试用](//try.nodebb.org) | [文档](//docs.nodebb.org)

## 截图

NodeBB 的主题引擎高度灵活，不会限制你的设计选择。请查看以下截图中展示的一些主题样式：

[![](http://i.imgur.com/VCoOFyqb.png)](http://i.imgur.com/VCoOFyq.png)
[![](http://i.imgur.com/FLOUuIqb.png)](http://i.imgur.com/FLOUuIq.png)
[![](http://i.imgur.com/Ud1LrfIb.png)](http://i.imgur.com/Ud1LrfI.png)
[![](http://i.imgur.com/h6yZ66sb.png)](http://i.imgur.com/h6yZ66s.png)
[![](http://i.imgur.com/o90kVPib.png)](http://i.imgur.com/o90kVPi.png)
[![](http://i.imgur.com/AaRRrU2b.png)](http://i.imgur.com/AaRRrU2.png)
[![](http://i.imgur.com/LmHtPhob.png)](http://i.imgur.com/LmHtPho.png)
[![](http://i.imgur.com/paiJPJkb.jpg)](http://i.imgur.com/paiJPJk.jpg)

我们极简风格的“Harmony”主题可让你立即上手，无需任何编码经验。

![NodeBB 在桌面和移动设备上的界面渲染效果](https://user-images.githubusercontent.com/923011/228570420-2a4db745-b20d-474a-a571-1b59259508ef.png)

## 如何参与或贡献？

* 如果你是一名开发者，欢迎查看源码并提交 Pull Request。我们还提供了大量 [插件](http://community.nodebb.org/category/7/nodebb-plugins)，是了解代码库的良好起点。
* 如果你是一名设计师，[NodeBB 需要主题](http://community.nodebb.org/category/10/nodebb-themes)！NodeBB 的主题系统支持扩展基础模板，并可通过 SCSS 或 CSS 进行样式定制。NodeBB 的基础主题使用了 [Bootstrap 5](http://getbootstrap.com/) 作为前端工具包。
* 如果你精通除英语之外的其他语言，可以协助我们翻译 NodeBB。我们使用 [Transifex](https://explore.transifex.com/nodebb/nodebb/) 进行国际化。
* 请不要忘记 **点赞**、**关注** 并 **为我们的仓库加星**！加入我们不断壮大的 [社区](http://community.nodebb.org)，及时了解 NodeBB 的最新开发动态。

## 系统要求

运行 NodeBB 需要安装以下软件：

* 至少 Node.js 20 或更高版本 ([安装/升级指南](https://github.com/nodesource/distributions))
* MongoDB 5 或更高版本 **或** Redis 7.2 或更高版本
* 如果你使用 [集群](https://docs.nodebb.org/configuring/scaling/)，需要安装并配置 Redis
* nginx 1.3.13 或更高版本（**仅在** 使用 nginx 代理请求到 NodeBB 时需要）

## 安装

[请参考平台相关的安装文档](https://docs.nodebb.org/installing/os)。  
如果通过云平台安装（或使用 Docker），[请查看云安装文档](https://docs.nodebb.org/installing/cloud/)。

## 安全设置

确保 NodeBB 和数据库服务器的安全非常重要，请注意以下几点：

1. 虽然某些发行版会将 Redis 配置为更严格的设置，但默认情况下 Redis 会监听所有接口，这在服务器对外公开时尤其危险。建议：
    * 设置 `bind_address` 为 `127.0.0.1`，仅允许本地访问
    * 使用 `requirepass` 设置 Redis 密码（建议使用较长的密码）
    * 熟悉 [Redis 安全指南](http://redis.io/topics/security)
2. 使用 `iptables` 来保护服务器免受未授权端口访问。在 Ubuntu 上，`ufw` 提供了更友好的 `iptables` 操作界面。
    * 例如：如果你的 NodeBB 是通过代理运行的，则除了 80 端口（以及可能用于 SSH 的 22 端口）外，其他端口应全部关闭

## 升级 NodeBB

详细的升级说明请参阅 [升级 NodeBB](https://docs.nodebb.org/configuring/upgrade/)

## 许可证

NodeBB 采用 **GNU 通用公共许可证 v3 (GPL-3)** 授权（http://www.gnu.org/copyleft/gpl.html）。

如需在非自由/受限环境中使用 NodeBB 的分许可协议，请联系我们：sales@nodebb.org。

## 更多信息/链接

* [演示](https://try.nodebb.org)
* [开发者社区](http://community.nodebb.org)
* [文档与安装说明](https://docs.nodebb.org)
* [帮助翻译 NodeBB](https://explore.transifex.com/nodebb/nodebb/)
* [NodeBB 博客](https://nodebb.org/blog)
* [NodeBB 专业托管服务](https://www.nodebb.org/ "NodeBB")
* 非官方 IRC 社区 &ndash; Libera.chat 上的 `#nodebb` 频道
* [关注我们的 Twitter](http://www.twitter.com/NodeBB/ "NodeBB Twitter")
* [在 Facebook 上点赞](http://www.facebook.com/NodeBB/ "NodeBB Facebook")