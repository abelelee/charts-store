# Jirafeau

欢迎来到官方 Jirafeau 项目，这是一个 [开源软件](https://en.wikipedia.org/wiki/Open-source_software)。

Jirafeau 是一个实现“一键文件共享”的项目，它允许用户以简单的方式上传文件，并提供一个唯一的链接。

最新版本的演示可在 [jirafeau.net](http://jirafeau.net/) 上查看。

![截图1](http://i.imgur.com/TPjh48P.png)

最新 CI 状态：
主分支 [![构建状态 - 主分支](https://gitlab.com/mojo42/Jirafeau/badges/master/build.svg)](https://gitlab.com/mojo42/Jirafeau/commits/master)
下一个版本 [![构建状态 - 下一个版本](https://gitlab.com/mojo42/Jirafeau/badges/test/build.svg)](https://gitlab.com/mojo42/Jirafeau/commits/master)
[所有分支构建](https://gitlab.com/mojo42/Jirafeau/pipelines?scope=branches)

## 主要功能

- 一次上传 → 一个下载链接和一个删除链接
- 可发送任意大文件（得益于 HTML5 文件 API → 不受 PHP `post_max_size` 限制）
- 显示上传进度：速度、百分比和剩余时间
- 在浏览器中预览内容（如果可能）
- 可选密码保护（上传或下载时）
- 设置下载过期时间
- 可选首次下载后自动销毁
- 使用 Base64 编码缩短 URL
- 可配置最大上传大小
- **无数据库**，仅使用基本的 PHP
- 简单的语言支持 :gb: :fr: :de: :it: :nl: :ro: :sk: :hu: :cn: :gr: :ru: :es: :tk: :flag_tr:
- 文件级别的 [去重](http://en.wikipedia.org/wiki/Data_deduplication) 以优化存储（仅存储一次重复文件，但生成多个链接）
- 可选数据加密
- 简单的管理界面
- CLI 脚本可通过 cronjob 自动删除过期文件
- 基础的、可自定义的「服务条款」页面
- 基础 API
- Bash 脚本可通过命令行上传文件
- 主题支持

Jirafeau 是原始项目 [Jyraphe](http://home.gna.org/jyraphe/) 的一个分支，基于其 0.5 版本（稳定版），并进行了大量修改。

与原始项目一样，Jirafeau 遵循 [KISS](http://en.wikipedia.org/wiki/KISS_principle) 原则（保持简单）。

Jirafeau 项目不会发展为文件管理器，并将专注于保持极少的依赖项。

## 截图

- [安装 - 步骤 1](http://i.imgur.com/hmpT1eN.jpg)
- [安装 - 步骤 2](http://i.imgur.com/2e0UGKE.jpg)
- [安装 - 步骤 3](http://i.imgur.com/ofAjLXh.jpg)
- [安装 - 步骤 4](http://i.imgur.com/WXqnfqJ.jpg)
- [上传 - 步骤 1](http://i.imgur.com/SBmSwzJ.jpg)
- [上传 - 步骤 2](http://i.imgur.com/wzPkb1Z.jpg)
- [上传 - 进度](http://i.imgur.com/i6n95kv.jpg)
- [上传 - 确认页面](http://i.imgur.com/P2oS1MY.jpg)
- [管理界面](http://i.imgur.com/nTdsVzn.png)

## 安装

系统要求：
- PHP >= 5.6
- 可选但推荐：Git >= 2.7
- 无需数据库，无需邮件支持

安装步骤：
- 克隆 [仓库](https://gitlab.com/mojo42/Jirafeau/) 或下载最新 [发布版本](https://gitlab.com/mojo42/Jirafeau/tags) 到你的 Web 服务器
- 根据你的 Web 服务器设置文件所有者和组
- A) 使用安装向导（网页方式）：
  - 打开浏览器，访问你的安装地址，例如：```https://example.com/jirafeau/```
  - 脚本将重定向到一个最小化的安装向导，用于设置所有必需的选项
  - 所有可选参数可以在 ```lib/config.local.php``` 中设置，查看 ```lib/config.original.php``` 以了解所有默认值
- B) 不使用安装向导（命令行方式）：
  - 只需将 ```config.original.php``` 复制为 ```config.local.php``` 并进行自定义

## 升级

### 所有版本的通用升级步骤

1. 备份你的 Jirafeau 安装！
2. 阻止对 Jirafeau 的访问
3. 使用 [标签版本](https://gitlab.com/mojo42/Jirafeau/tags) 通过 Git 检出新版本  
   * 如果你是通过上传文件到服务器安装的 Jirafeau，你可以下载所需版本，覆盖/删除所有文件，并在需要时更改文件所有者和权限。但请保留本地配置文件的备份。
4. 在浏览器中访问你的 Jirafeau 根页面
5. 按照安装向导操作，它应该会提供相同的文件夹选项，甚至自动更新
7. 检查你的 ```/lib/config.local.php``` 并与 ```/lib/config.original.php``` 进行比较，查看是否有新的配置项可用

### 从 1.0 升级到 1.1

1. 下载 URL 发生了变化  
   * 在你的 Web 服务器配置中添加一条重写规则，将 ```file.php``` 重命名为 ```f.php```，以便旧的、仍然存在的链接可以继续工作
1. 默认主题发生了变化  
   * 可选地在 ```lib/config.local.php``` 中将主题更改为 »courgette«

### 从 1.2.0 升级到 2.0.0

1. “服务条款”文本文件发生了变化  
   * 如果你想复用之前的 ToS 修改，请将旧的 ```/tos_text.php``` 文件移动到 ```/lib/tos.local.txt```，并删除所有 HTML 和 PHP 标签，保留纯文本文件

### 从 2.0.0 升级到 3.0.0

1. 无需特殊更改即可升级到 3.0.0

### 从 3.0.0 升级到 3.1.0

1. 无需特殊更改即可升级到 3.1.0

### 从 3.1.0 升级到 3.2.0

1. 无需特殊更改即可升级到 3.2.0

### 从 3.2.0 升级到 3.2.1

1. 无需特殊更改即可升级到 3.2.1

## 故障排查

如果你遇到问题，请考虑以下情况：

- 检查你的 ```/lib/config.local.php``` 文件，并与 ```/lib/config.original.php``` 进行比较，配置语法或参数可能已更改
- 检查文件的所有者和权限

## 安全性

```var``` 目录包含所有文件和链接。它被随机命名以限制访问，但你可以添加更好的保护措施以防止未经授权的访问。
你有以下几种选择：
- 配置一个 ```.htaccess```
- 将 var 文件夹移动到服务器上无法直接访问的位置
- 在 Web 服务器配置中禁用自动目录列表，或在 var 的子目录中放置一个 index.html（这是一个有限的解决方案）

如果你使用 Apache，可以在配置中添加以下行以阻止人们访问你的 ```var``` 文件夹：

```RedirectMatch 301 ^/var-.* http://my.service.jirafeau ```

如果你使用 nginx，可以在你的 $vhost.conf 中添加以下内容：

```nginx
location ~ /var-.* {
    deny all;
    return 404;
}
```

安装完成后，你还应移除不必要的写权限（例如配置文件）。
另一个基本的安全措施是确保用户通过 HTTPS 访问站点。

## 服务器端加密

可以在选项中激活数据加密。此功能会使服务器加密数据，并将解密密钥发送给用户（包含在下载 URL 中）。
解密密钥不会存储在服务器上，因此如果你丢失了 URL，将无法恢复文件内容。
在服务器发生安全问题时，攻击者将无法访问文件。

启用此功能时，需要注意以下几点：
- 数据加密会带来 CPU 开销，并且下载完成时间会更长。
- 下载期间，服务器会实时解密（并使用资源）。
- 此功能需要安装 mcrypt PHP 模块。
- 文件去重功能将失效（因为我们无法比较两个加密文件）。
- 确保你的服务器不会记录客户端的请求。
- 不要忘记启用 HTTPS。

下一步，加密将由客户端（JavaScript）完成，请参见 issue #10。

## 许可证

GNU Affero 通用公共许可证 v3 (AGPL-3.0)。

GNU Affero 通用公共许可证可在 https://www.gnu.org/licenses/agpl.html 找到。

请注意：如果你决定对源代码进行修改并运行包含这些更改的服务，
你有义务提供你版本的源代码链接以遵守 AGPL-3.0 许可证。
为此，请在服务条款页面中添加一个源代码链接（例如公共 Git 仓库或下载链接）。
查看 FAQ 以了解如何修改 ToS。

PS：如果你修复了错误或添加了功能，请为项目做出贡献并提交合并请求。

## 贡献

如果你想为项目做贡献，请查看 Git 仓库：

- https://gitlab.com/mojo42/Jirafeau

以及贡献指南：

- https://gitlab.com/mojo42/Jirafeau/blob/master/CONTRIBUTING.md

## 常见问题

### 我可以在 Jirafeau 中添加一种新语言吗？

当然可以！翻译非常容易，不需要技术知识。

只需访问 [Jirafeau 的 Weblate 页面](https://hosted.weblate.org/projects/jirafeau/master/)。

如果你想在列表中添加一种新语言，请随时联系我们或在 ticket #9 中留言。

我们想感谢所有在 Weblate 上的匿名贡献者。 :)

### 如何升级我的 Jirafeau？

请参见上面的升级说明。

### 如何限制上传访问？

有两种方法可以限制上传访问（但不影响下载）：
- 你可以设置一个或多个密码以访问上传界面，或/和
- 你可以配置一个允许访问上传页面的授权 IP 列表（[CIDR 表示法](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing#CIDR_notation)）

请查看 [lib/config.original.php](https://gitlab.com/mojo42/Jirafeau/blob/master/lib/config.original.php) 中 ```upload_password``` 和 ```upload_ip``` 参数的文档。

### 如何自动清理旧的（过期的）文件？

你可以从命令行（CLI）调用 admin.php 脚本，使用 ```clean_expired``` 或 ```clean_async``` 命令：```sudo -u www-data php admin.php clean_expired```。

然后可以将该命令放入 cron 文件中以自动化该过程。例如：
```
# m h dom mon dow user  command
12 3    * * *   www-data  php /path/to/jirafeau/admin.php clean_expired
16 3    * * *   www-data  php /path/to/jirafeau/admin.php clean_async
```

### 我在使用 IE 时遇到问题

如果你在 IE 中遇到奇怪的行为，可以配置 [兼容模式](http://feedback.dominknow.com/knowledgebase/articles/159097-internet-explorer-ie8-ie9-ie10-and-ie11-compat)。

无论如何，我建议你使用其他 Web 浏览器。 :)

### 如何更改主题？

你可以将默认主题更改为任何现有主题或自定义主题。

打开你的 ```lib/config.local.php```，将 »`style`« 键的值更改为 ```/media``` 目录中任意文件夹的名称。

提示：要创建一个自定义主题，只需复制 »courgette« 文件夹并将其命名为 »custom«（这样它将被 git 忽略，不会在更新时被覆盖）。当然，我们鼓励你改进现有主题并提交 Pull Request。

### 我发现了一个 bug，我该怎么办？

请在 [GitLab 的 issues](https://gitlab.com/mojo42/Jirafeau/issues) 中自由提交 bug。

### 如何设置最大文件大小？

如果你的浏览器支持 HTML5 文件 API，你可以发送任意大小的文件。

对于不支持 HTML5 文件 API 的浏览器，限制来自 PHP 配置。
你需要在 PHP 配置中设置 [post_max_size](https://php.net/manual/en/ini.core.php#ini.post-max-size) 和 [upload_max_filesize](https://php.net/manual/en/ini.core.php#ini.upload-max-filesize)。

如果你不想允许无限上传大小，你仍然可以在 Jirafeau 的设置中设置最大文件大小（参见配置中的 ```maximal_upload_size```）

### 如何编辑一个选项？

所有默认选项的文档位于 [lib/config.original.php](https://gitlab.com/mojo42/Jirafeau/blob/master/lib/config.original.php)。
如果你想更改一个选项，只需编辑你的 ```lib/config.local.php```。

### 如何更改服务条款？

默认安装中“服务条款”页面上的许可文本基于 »[Open Source Initiative Terms of Service](https://opensource.org/ToS)«。

要更改此文本，只需复制文件 [/lib/tos.original.txt](https://gitlab.com/mojo42/Jirafeau/blob/master/lib/tos.original.txt)，将其重命名为 ```/lib/tos.local.txt``` 并根据你的需求进行修改。

如果你更新安装，只有 ```tos.original.txt``` 文件可能会更改，而你的 ```tos.local.txt``` 文件不会更改。

### 如何访问管理界面？

只需访问 ```/admin.php```。

### 如何使用脚本接口（API）？

只需在 Web 浏览器中访问 ```/script.php```。

### 我的下载不完整或上传失败

确保你的 PHP 安装未使用安全模式，这可能导致超时。

如果你使用 nginx，你可能需要增加 `client_max_body_size` 或完全移除该限制。在你的 nginx.conf 中：

```nginx
http {
    # 禁用最大上传大小
    client_max_body_size 0;
    # 为非常大的上传添加超时设置
    client_header_timeout 30m;
    client_body_timeout 30m;
}
```

### 如何监控我的 Jirafeau 实例使用情况？

你可以使用 Munin 和简单的脚本来收集 Jirafeau 实例中的文件数量以及所有文件占用的磁盘空间。你可以参考这篇 [网页](https://blog.bandinelli.net/index.php?post/2016/05/15/Scripts-Munin-pour-Jirafeau)。

### 为什么进行分支？

原始项目似乎不再继续维护，我更愿意从一个稳定版本开始添加更多功能并增强安全性。

### 未来有什么期待？

查看 [issues](https://gitlab.com/mojo42/Jirafeau/issues) 以了解开放的 bug 和即将到来的新功能。 :)

### 关于文件去重功能？

Jirafeau 使用非常简单的文件级别去重来优化存储。

这意味着如果有人多次上传相同的文件，只会存储一次，并增加一个计数器。

如果某人使用其删除链接或管理员清理过期链接，将减少对应文件的计数器。

当计数器降至零时，文件将被销毁。

### 管理界面中“删除链接”和“删除文件和链接”的区别是什么？

如上一个问题所述，具有相同 md5 哈希的文件不会被重复存储，引用计数器记录指向单个文件的链接数量。
因此：
- “删除链接”按钮将删除对该文件的引用，但可能不会销毁文件。
- “删除文件和链接”按钮将删除指向该文件的所有引用，并销毁文件。

### 如何联系 Jirafeau 的人？

如果你发现了一个 bug，请随意创建一个 issue。

## 发布说明

### 版本 1.0

Jirafeau 从 Jyraphe 分支后的第一个版本。

- 安全修复
- 保留上传者的 IP
- 每次上传都有删除链接
- 不再以明文形式存储密码
- 简单的语言支持
- 添加管理界面
- 新设计
- 添加使用条款
- 新路径系统以管理大量文件
- 新选项以在下载时显示页面
- 添加选项以启用或禁用预览模式

### 版本 1.1

- 新皮肤
- 添加可选的服务器端加密
- 使用 HTML5 文件 API 实现无限文件大小上传
- 显示上传期间的速度和预计时间
- 大量修复
- 大量新增语言
- 小型 API 用于上传文件
- 使用 IP、掩码、密码限制对 Jirafeau 的访问
- 管理（部分）代理头
- 配置你的最大上传大小
- 配置文件的生命周期时长
- 预览 URL
- 在管理界面中显示 Jirafeau 的版本

## 版本 1.2.0

- API 页面上生成 Bash 脚本的链接
- 更具信息性的 API 错误代码
- 安全修复：防止绕过管理界面的身份验证
- CLI 脚本可通过 cronjob 自动删除过期文件
- 使用 SHA-256 哈希加密管理员密码
- 新主题 "elegantish"
- 修复 JavaScript MIME 类型问题，防止某些服务器阻止资源
- 在管理界面中显示文件的下载链接
- 默认过期时间（默认设置为“月”）
- 新增过期时间：“季度”
- 大量翻译贡献
- 代码清理

## 版本 2.0.0

- 各种文档改进
- 简化本地配置文件的自动生成
- 设置自定义标题
- Bash 脚本：增强帮助信息，显示版本，返回网页视图链接
- “服务条款”重构 - 允许管理员覆盖 ToS，而无需更改现有源代码 → 破坏性变更，请参见升级说明

## 版本 3.0.0

- 移除 XHTML doctype，仅支持 HTML5 → 对旧浏览器是破坏性变更
- 移除冗余代码
- 移除 baseurl 使用，改用绝对链接，例如修复 SSL 问题
- 扩展贡献指南
- 切换到 PSR-2 代码风格（修复行尾、缩进、空格等）
- 声明系统要求
- 在上传表单中捕获 API 错误
- 允许客户端根据 IP 或密码上传文件
- 设置 UTC 时区以防止日期/时间问题
- 显示可读的日期和时间信息
- 修复管理面板和上传表单中的 UI 问题

## 版本 3.1.0

- 修复用户身份验证的回归问题（参见 #113）
- 一些外观上的小改动

## 版本 3.2.0

- 从 Weblate 更新翻译
- 更好的样式
- 修复管理员密码设置的回归问题

## 版本 3.2.1

- 修复上传后下载视图的问题