# ownCloud 核心

[![构建状态](https://drone.owncloud.com/api/badges/owncloud/core/status.svg?branch=master)](https://drone.owncloud.com/owncloud/core)
[![质量门状态](https://sonarcloud.io/api/project_badges/measure?project=owncloud_core&metric=alert_status)](https://sonarcloud.io/dashboard?id=owncloud_core)
[![安全评级](https://sonarcloud.io/api/project_badges/measure?project=owncloud_core&metric=security_rating)](https://sonarcloud.io/dashboard?id=owncloud_core)
[![代码覆盖率](https://sonarcloud.io/api/project_badges/measure?project=owncloud_core&metric=coverage)](https://sonarcloud.io/dashboard?id=owncloud_core)
[![设计](https://contribute.design/api/shield/owncloud/core)](https://contribute.design/owncloud/core)

**[ownCloud](http://ownCloud.com) 提供文件共享与协作服务，全球超过 2 亿用户信赖，无论使用何种设备或身处何地。**

![](https://github.com/owncloud/screenshots/blob/master/files/sidebar_1.png)

## 为什么这么棒？
* :file_folder: **访问你的数据** 你可以将文件、联系人、日历等内容存储在你选择的服务器上。
* :package: **同步你的数据** 你可以在所有设备之间保持文件、联系人、日历等内容的同步。
* :arrows_counterclockwise: **分享你的数据** 你可以将数据分享给他人，并让他们访问你最新的照片集、日历或任何你想让他们看到的内容。
* :rocket: **支持数十个应用扩展** 例如日历、联系人、邮件或新闻。
* :cloud: **拥有云的所有优势** ...但运行在你自己的服务器上。
* :lock: **加密支持** 你可以通过安全的 HTTPS 连接加密传输中的数据。你还可以启用加密应用，对存储中的数据进行加密，以提升安全性与隐私保护。
* ...

## 安装说明
关于 ownCloud 的安装，请参阅官方
[ownCloud 10](https://doc.owncloud.com/server/latest/admin_manual/installation/) 安装手册。

## 开发构建前提条件
请注意，在进行本地开发构建时，你需要安装 **Composer v2**。如果你的操作系统提供的版本低于 v2，你可以手动安装 Composer v2。例如，适用于其他发行版/版本的安装方法，请参阅 [如何在 Ubuntu 22.04 | 20.04 LTS 上安装 Composer](https://www.how2shout.com/linux/how-to-install-composer-on-ubuntu-22-04-20-04-lts/)。

你还需要安装 `yarn` 和 `node`（v14 或更高版本）。

## 贡献指南
https://owncloud.com/contribute/

## 提交信息
为了便于理解提交内容，CI 作业会检查提交信息是否符合规范，以确保提交信息具有人类和机器均可读的语义。详情请参阅：[Conventional Commits](www.conventionalcommits.org/)。请注意，如果不符合规范，CI 检查将不会通过。在这种情况下，你需要重写 Git 提交历史以满足要求。

你至少需要提供一个 `类型` + `描述`，如 [示例](https://www.conventionalcommits.org/en/v1.0.0/#examples) 部分所述。

快速入门时，可以使用以下提交类型：

`fix:`、`feat:`、`build:`、`chore:`、`ci:`、`docs:`、`style:`、`refactor:`、`perf:`、`test:`


## 支持
了解获取 ownCloud 支持的多种方式：https://owncloud.com/support/

## 联系我们
* :clipboard: [论坛](https://central.owncloud.org)
* :hash: [IRC 频道](https://web.libera.chat/?channels=#owncloud)
* :busts_in_silhouette: [Facebook](https://facebook.com/ownclouders)
* :hatching_chick: [Twitter](https://twitter.com/ownCloud)

## 关于翻译的重要说明
请通过 Transifex 提交翻译：
https://explore.transifex.com/owncloud-org/

关于[翻译](https://doc.owncloud.com/server/latest/developer_manual/core/translation.html)的详细信息请参阅此处。