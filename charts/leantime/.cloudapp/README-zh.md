以下是你提供的Markdown内容的中文翻译，保留了原始格式和结构：

---

<div align="center">
<a href="https://leantime.io"><img src="https://leantime.io/wp-content/uploads/2023/03/leantime_logo.png" alt="Leantime Logo" width="300"/></a>

# Leantime&reg; 

⭐ 如果你觉得 Leantime 有用，请在 GitHub 上给我们点星 ⭐

Leantime 是一个面向非项目经理的开源项目管理系统。<br />
我们融合了战略、计划与执行，同时让团队中的每个人都能轻松使用。<br />
专为 ADHD、阅读障碍和自闭症用户设计。🧠<br />

💪 像 Trello 一样简单，但功能像 Jira 一样丰富<br />
🔄 是 ClickUp、Monday 或 Asana 的完美替代品<br />
🌐 [https://leantime.io](https://leantime.io)<br />

<a href="https://trendshift.io/repositories/2264" target="_blank"><img src="https://trendshift.io/api/badge/repositories/2264" alt="Leantime 我的工作仪表板截图，显示几个包含已完成待办事项、目标贡献、计划任务的大指标框。还显示了一个日历视图和一个按“逾期”、“本周到期”和“稍后到期”分组的任务列表" style="width: 250px; height: 55px;" width="250" height="55"/></a>

[![License Badge](https://img.shields.io/github/license/leantime/leantime?style=flat-square)](https://www.gnu.org/licenses/agpl-3.0.en.html)
[![Docker Hub Badge](https://img.shields.io/docker/pulls/leantime/leantime?style=flat-square)](https://hub.docker.com/r/leantime/leantime)
![Github Downloads](https://img.shields.io/github/downloads/leantime/leantime/total)
[![Discord Badge](https://img.shields.io/discord/990001288026677318?label=Discord&style=flat-square)](https://discord.gg/4zMzJtAq9z)
[![Crowdin](https://badges.crowdin.net/leantime/localized.svg)](https://crowdin.com/project/leantime)
![GitHub Sponsors](https://img.shields.io/github/sponsors/leantime)
<br />

  ![alt text](public/assets/images/Screenshots/mywork-v3.5.png "首页")

</div>
<br /><br />

## 🚀 功能特性 ##
| 任务管理                                                      | 项目规划                             | 信息/知识管理                        | 管理配置                                  |
| -------------------------------------------------------------------- | -------------------------------------------- | --------------------------------------- |-------------------------------------------------|
| 通过看板、甘特图、表格、列表和日历视图进行任务管理 | 项目仪表板、报告与状态更新 | 维基 / 文档                     | 简单安装                               |
| 无限子任务和依赖关系                                  | 目标与指标跟踪                      | 创意看板                             | 多用户角色和项目级权限 |
| 里程碑管理                                                 | 精益与商业模式画布                 | 回顾会议                          | 双因素身份验证                       |
| 迭代管理                                                    | SWOT 分析画布                         | 通过 S3 或本地文件系统进行文件存储 | LDAP、OIDC 集成                          |
| 时间跟踪与工时表                                            | 风险分析                                | 屏幕与摄像头录制               | 通过插件和 API 扩展                  |
|                                                                      | ... 等更多功能                                 | 所有内容都支持评论/讨论      | 集成 Slack、Mattermost、Discord      |
|                                                                      | ... 等更多功能                                 |     | 支持超过 20 种语言                  |     
*是的，所有这些功能都包含在开源版本中*
<br /><br />
### 📸 截图 ###

<table width="100%">
    <tr>
        <td width="33%"><img alt="Leantime 的我的工作仪表板截图，使用深色主题。所有颜色都变暗或反转" src="public/assets/images/Screenshots/dark.png" title="我的工作" /></td>
        <td width="33%"><img alt="Leantime 的项目仪表板截图，显示一个项目检查清单，第一个框已勾选，最新任务（当前一个），进度环形图显示 0%" src="public/assets/images/Screenshots/projectDashboard.png" title="项目仪表板" /></td>
        <td width="33%"><img alt="Leantime 的待办事项页面截图，以表格形式展示。任务按状态分组，每种状态使用不同颜色" src="public/assets/images/Screenshots/table.png" title="分组待办事项" /></td>
    </tr>
    <tr>
        <td><img alt="Leantime 的看板界面截图" src="public/assets/images/Screenshots/kanban.png" title="看板"/></td>
        <td><img alt="Leantime 的时间线或甘特图功能截图，显示时间线上不同长度的里程碑框，每个里程碑使用不同颜色，并用箭头连接" src="public/assets/images/Screenshots/timeline.png" title="时间线任务" /></td>
        <td><img alt="Leantime 的个人日历界面截图，显示一个月的任务概览" src="public/assets/images/Screenshots/calendar.png" title="项目日历" /></td>
    </tr>
    <tr>
        <td><img alt="Leantime 的目标页面截图" src="public/assets/images/Screenshots/goals.png" title="目标" /></td>
        <td><img alt="Leantime 的维基页面截图，显示一个产品需求文档模板，使用列表和表格格式" src="public/assets/images/Screenshots/docs.png" title="文档与维基" /></td>
        <td><img alt="Leantime 的工时表功能截图，显示一周概览和每天的输入框，任务按行组织" src="public/assets/images/Screenshots/timesheet.png" title="工时表" /></td>
    </tr>
</table>

<br /><br />
### ❗系统要求 ###

* PHP 8.2+
* MySQL 8.0+ 或 MariaDB 10.6+
* Apache 或 Nginx（IIS 也可用，需修改）
* PHP 扩展：
* BC Math (bcmath)
* Ctype
* cURL
* DOM
* Exif
* Fileinfo
* Filter
* GD
* Hash
* LDAP
* 多字节字符串 (mbstring)
* MySQL
* OPcache
* OpenSSL
* PCNTL
* PCRE
* PDO
* Phar
* Session
* Tokenizer
* Zip
* SimpleXML
<br /><br />


Ctype PHP 扩展  
cURL PHP 扩展  
DOM PHP 扩展  
Fileinfo PHP 扩展  
Filter PHP 扩展  
Hash PHP 扩展  
Mbstring PHP 扩展  
OpenSSL PHP 扩展  
PCRE PHP 扩展  
PDO PHP 扩展  
Session PHP 扩展  
Tokenizer PHP 扩展  
XML PHP 扩展  

### ️⚡️ 安装（生产环境） ###

有两种主要方式在生产环境中安装 LeanTime。第一种是在本地安装所有所需组件。第二种是使用官方支持的 Docker 镜像。

#### 本地生产环境安装 ####

* 从 <a href="https://github.com/Leantime/leantime/releases">发布页面</a> 下载最新的发布包（文件名为：Leantime-vx.x.x.zip）
* 创建一个空的 MySQL 数据库
* 将整个目录上传到你的服务器 
* 将你的域名根目录指向 `public/` 目录
* 将 `config/.env.sample` 重命名为 `config/.env`
* 在 `config/.env` 中填写你的数据库凭据（用户名、密码、主机、数据库名）
* 访问 `<yourdomain.com>/install`
* 按照提示安装数据库并创建第一个用户账户

##### IIS 安装说明 #####

虽然上述步骤适用于 Internet Information Services (IIS)，但为了确保完整功能，你可能需要在 IIS 中进行额外配置 —— 允许 PATCH 方法：

* 打开 IIS
* 展开左侧的服务器和站点，选择 LeanTime 站点
* 双击 `处理程序映射`
* 双击站点使用的 PHP 处理程序映射
* 点击 `请求限制...`
* 点击 `动词` 标签页
* 在 `以下动词之一` 文本框中添加 `PATCH`，例如：`GET,HEAD,POST,PATCH`
* 点击 `确定`
* 在 `可执行文件（可选）` 文本框中，在 `php-cgi.exe` 文件路径前后加上双引号 (`“`)（如果路径中没有空格则不需要）
* 点击 `确定`
* 弹出窗口询问是否要创建 FastCGI 应用程序，点击 `是`

注意：升级 PHP 时可能需要重复此步骤。

#### 通过 Docker 安装生产环境 ####

我们维护了一个官方的 <a href="https://hub.docker.com/r/leantime/leantime">Docker 镜像</a>。
运行镜像时传入你的 MySQL 凭据并执行。你可以传入 `.env` 文件中的所有配置变量：

```
docker run -d --restart unless-stopped -p 8080:8080 --network leantime-net \
-e LEAN_DB_HOST=mysql_leantime \
-e LEAN_DB_USER=admin \
-e LEAN_DB_PASSWORD=321.qwerty \
-e LEAN_DB_DATABASE=leantime \
-e LEAN_EMAIL_RETURN=changeme@local.local \
--name leantime leantime/leantime:latest
```

除非你已经在别处定义了数据库，否则应使用我们的 [docker-compose 文件](https://github.com/Leantime/docker-leantime/blob/master/docker-compose.yml)。

启动后，你可以访问 `<yourdomain.com>/install` 并运行安装脚本。

**重要提示：如果你计划使用插件，你需要挂载插件目录 `plugins:/var/www/html/app/Plugins` 并确保 www-data 用户有访问权限。否则安装可能会失败，或插件会在重启后被删除**

##### Docker 安装说明 #####

如果你打算将 Leantime 放在反向代理（如 nginx 等）后面以处理自定义域名解析和 SSL 卸载，你需要在 Docker 中设置以下环境变量：
```
-e LEAN_APP_URL=https://yourdomain.com \
```
* 将 yourdomain.com 替换为你的自定义域名。
<br /><br />
### 🤓 安装（开发环境） ###

有两种方式安装开发环境的 LeanTime。第一种（但更技术性）是在本地安装所有组件。第二种（推荐方式）是使用 Docker 容器化开发环境。

#### 本地开发环境安装 ####

* 将仓库克隆到本地服务器
* 创建 MySQL 数据库
* 通过 `make build-dev` 运行 webpack 构建器
* 将本地域名指向 `public/` 目录
* 将 `config/.env.sample` 重命名为 `config/.env`
* 在 `config/.env` 中填写你的数据库凭据（用户名、密码、主机、数据库名）
* 访问 `<localdomain>/install`
* 按照提示安装数据库和用户账户

#### 通过 Docker 安装开发环境 ####

我们使用 Docker 化的开发环境进行开发。你需要安装 ``docker``、``docker compose``、``make``、``composer``、``git`` 和 ``npm``。

* Windows 环境注意事项：
    - 所有命令应在 git bash 终端中运行，以使用 Unix 特定命令
    - 如果从 zip 文件安装 php，确保配置 php.ini
    初始不存在，因此请将 C:\php\php.ini-development 复制为 C:\php\php.ini。你还需要用文本编辑器编辑 php.ini 并启用构建过程中所需的所有扩展。你可以通过运行 make 命令并查看报错的缺失扩展来找到需要启用的扩展。你可以通过在 php.ini 中搜索类似 `;extension=gd` 的内容并删除分号来启用扩展。

要在开发环境中构建 Docker 镜像，请在仓库根目录运行以下命令：

```make clean build```

然后运行：

```make run-dev```

这将在 8090 端口启动开发服务器。

开发环境提供 MySQL 服务器、邮件服务器、S3 服务器，开箱即用。开发环境的配置位于 ``.dev/.env`` 中，已预设了适当值。**除非你打算开发特定集成功能，否则不建议修改此文件**。你将获得以下应用：

* [http://localhost:8090](http://localhost:8090) : leantime
* [http://localhost:8081](http://localhost:8081) : maildev - 查看发送的邮件
* [http://localhost:8082](http://localhost:8082) : phpMyAdmin（认证：``leantime:leantime``）查看数据库结构和数据
* [http://localhost:8083](http://localhost:8083) : s3ninja - 查看 S3 上传。你需要在 ``.dev/.env`` 文件中启用 s3

此外，Xdebug 已启用，但你需在 ``.dev/xdebug.ini`` 文件中修改 IDE 密钥（或在 IDE 中设置）。你还需临时开放防火墙上的 9003 端口以便有效使用。这是因为从 Docker 到主机的连接将被视为外部入站连接。
<br /><br />

### 运行测试

静态分析 `make phpstan`<br />
代码风格 `make test-code-style`（自动修复代码风格使用 `make fix-code-style`）<br />
单元测试 `make unit-test`<br />
验收测试 `make acceptance-test`<br />（需要 Docker）

你可以直接运行特定的验收测试组：<br />
对于 API：<br />
`docker compose --file .dev/docker-compose.yaml --file .dev/docker-compose.tests.yaml exec leantime-dev php vendor/bin/codecept run -g api --steps`<br />
对于工时表：<br />
`docker compose --file .dev/docker-compose.yaml --file .dev/docker-compose.tests.yaml exec leantime-dev php vendor/bin/codecept run -g timesheet --steps`<br />


###  🏗 更新 ###

#### 手动更新
* 确保备份数据库和文件
* 用新版本替换目录中的所有文件
* 如果有数据库变更，系统会将你重定向到 `<yourdomain.com>/update`

#### CLI 更新
* 运行 `php bin/leantime system:update` 

#### Docker 更新
* 更新前确保你的 MySQL 容器使用了挂载卷，否则内容将被删除
* 删除/停止现有容器
* 拉取最新 Docker 镜像并使用你的 compose 文件重建


### 常见问题

请参考我们的 [文档](https://docs.leantime.io/installation/common-issues) 获取安装或更新 Leantime 时常见问题的解答。

## 🔌 扩展 Leantime ##

你可以通过以下方式扩展 Leantime：
- 构建自己的插件：[插件开发文档](https://docs.leantime.io/development/plugin-development)
- 使用我们的 JSON-RPC API：[API 文档](https://docs.leantime.io/api/usage)
- 或在我们的 [市场](https://marketplace.leantime.io) 购买插件

## 🛟 我们为你安装 ##

我们提供免麻烦的安装服务。我们可进行完整安装、更新、配置或插件安装。详情请参阅我们的 [市场](https://marketplace.leantime.io/product-category/services/technical/)。

## ☁️ 不想自己托管？我们来帮你 ##

我们提供 [托管计划](https://leantime.io/managed-hosting/) 和 [SaaS 产品](https://leantime.io/pricing/)，让你享受 Leantime 的所有优势而无需操心托管。访问 [leantime.io](https://leantime.io/) 获取更多信息。
<br /><br />

## 🤙 需要技术支持？ ##

我们可以帮助你在你的环境中设置 Leantime 并根据你的需求进行定制。我们的支持计划 [在网站上有详细说明](https://leantime.io/priority-support/)。

请注意：我们目前仅支持官方 Leantime Docker Compose 和标准安装。  
我们仅对最新版本提供支持。  

我们不支持 Cloudron、Elestio、Turnkey 或其他外部平台分发的非官方版本。

## 🫴 贡献

我们很高兴你有兴趣为 Leantime 做出贡献。我们希望你有良好的贡献体验，并确保你开发的新功能能被合并到核心中。
<br />

### 🪲 Bug 报告

在 GitHub 上查找问题（或创建新问题），添加你的名字或留言说明你将处理它。修复后创建 Pull Request。

### 核心新功能

如果你有关于新功能的想法，请在 Discord 上联系我们。我们在这里协调功能开发，并讨论是否应将新功能添加到核心（插件是替代方案）。

### 🌏 翻译

语言文件和翻译存储在 `app/Language/* ` 中。更新后请创建 Pull Request。

### 👥 社区支持

* 文档 [https://docs.leantime.io](https://docs.leantime.io)
* 社区聊天 [Discord](https://discord.gg/4zMzJtAq9z)
* 提交 Bug 报告 [https://github.com/Leantime/leantime/issues/new](https://github.com/Leantime/leantime/issues/new)
* 翻译 [https://crowdin.com/project/leantime](https://crowdin.com/project/leantime)
<br /><br />
## ⚖️ 许可例外

Leantime 使用 AGPLv3 许可证。
本文件是 Leantime 软件的一部分，以下例外适用于它：`/app/Plugins` 目录中的插件可能包含使用其他许可证（包括我们的企业许可证）的插件。

<img referrerpolicy="no-referrer-when-downgrade" src="https://static.scarf.sh/a.png?x-pxid=856e290f-a6e9-4fbd-9b95-a835e39a0492" />