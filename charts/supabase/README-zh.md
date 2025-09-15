<p align="center">
<img src="https://user-images.githubusercontent.com/8291514/213727234-cda046d6-28c6-491a-b284-b86c5cede25d.png#gh-light-mode-only">
<img src="https://user-images.githubusercontent.com/8291514/213727225-56186826-bee8-43b5-9b15-86e839d89393.png#gh-dark-mode-only">
</p>

# Supabase

[Supabase](https://supabase.com) 是一个 Postgres 开发平台。我们正使用企业级开源工具构建类似于 Firebase 的功能。

- [x] 托管的 Postgres 数据库。[文档](https://supabase.com/docs/guides/database)
- [x] 身份验证与授权。[文档](https://supabase.com/docs/guides/auth)
- [x] 自动生成的 API。
  - [x] REST。[文档](https://supabase.com/docs/guides/api)
  - [x] GraphQL。[文档](https://supabase.com/docs/guides/graphql)
  - [x] 实时订阅。[文档](https://supabase.com/docs/guides/realtime)
- [x] 函数。
  - [x] 数据库函数。[文档](https://supabase.com/docs/guides/database/functions)
  - [x] 边缘函数 [文档](https://supabase.com/docs/guides/functions)
- [x] 文件存储。[文档](https://supabase.com/docs/guides/storage)
- [x] AI + 向量/嵌入工具包。[文档](https://supabase.com/docs/guides/ai)
- [x] 控制台

![Supabase 控制台](https://raw.githubusercontent.com/supabase/supabase/master/apps/www/public/images/github/supabase-dashboard.png)

关注本仓库的 "releases" 以获取重大更新通知。

<kbd><img src="https://raw.githubusercontent.com/supabase/supabase/d5f7f413ab356dc1a92075cb3cee4e40a957d5b1/web/static/watch-repo.gif" alt="关注本仓库"/></kbd>

## 文档

完整文档请访问 [supabase.com/docs](https://supabase.com/docs)

关于如何贡献代码，请访问 入门指南

## 社区与支持

- [社区论坛](https://github.com/supabase/supabase/discussions)。适用于：开发帮助、数据库最佳实践讨论。
- [GitHub Issues](https://github.com/supabase/supabase/issues)。适用于：使用 Supabase 遇到的 bug 和错误。
- [邮件支持](https://supabase.com/docs/support#business-support)。适用于：数据库或基础设施相关问题。
- [Discord](https://discord.supabase.com)。适用于：分享你的应用并与社区成员交流。

## 工作原理

Supabase 是一组开源工具的组合。我们使用企业级开源产品构建类似于 Firebase 的功能。如果某个工具和社区已经存在，并且采用 MIT、Apache 2 或类似的开源许可证，我们会使用并支持该工具。如果工具不存在，我们会自行开发并开源。Supabase 并不是 Firebase 的一对一替代品。我们的目标是通过开源工具为开发者提供类似 Firebase 的开发体验。

**架构**

Supabase 是一个[托管平台](https://supabase.com/dashboard)。你可以直接注册并开始使用 Supabase，无需安装任何软件。
你也可以[自托管](https://supabase.com/docs/guides/hosting/overview)并[在本地开发](https://supabase.com/docs/guides/local-development)。

![架构图](apps/docs/public/img/supabase-architecture.svg)

- [Postgres](https://www.postgresql.org/) 是一个对象关系型数据库系统，经过 30 多年的积极开发，以其可靠性、功能稳健性和性能著称。
- [Realtime](https://github.com/supabase/realtime) 是一个 Elixir 服务器，允许你通过 WebSocket 监听 PostgreSQL 的插入、更新和删除操作。Realtime 通过 PostgreSQL 内置的复制功能轮询数据库变更，将变更转换为 JSON，然后通过 WebSocket 向已授权的客户端广播这些 JSON 数据。
- [PostgREST](http://postgrest.org/) 是一个 Web 服务器，可将你的 PostgreSQL 数据库直接转换为 RESTful API。
- [GoTrue](https://github.com/supabase/gotrue) 是一个基于 JWT 的身份验证 API，简化了应用程序中的用户注册、登录和会话管理。
- [Storage](https://github.com/supabase/storage-api) 是一个用于管理 S3 文件的 RESTful API，由 Postgres 处理权限控制。
- [pg_graphql](http://github.com/supabase/pg_graphql/) 是一个 PostgreSQL 扩展，提供 GraphQL API。
- [postgres-meta](https://github.com/supabase/postgres-meta) 是一个用于管理 Postgres 的 RESTful API，允许你获取表、添加角色、运行查询等。
- [Kong](https://github.com/Kong/kong) 是一个云原生 API 网关。

#### 客户端库

我们在客户端库的设计上采用了模块化的方式。每个子库都是针对单一外部系统的独立实现。这是我们支持现有工具的一种方式。

<table style="table-layout:fixed; white-space: nowrap;">
  <tr>
    <th>语言</th>
    <th>客户端</th>
    <th colspan="5">功能客户端（包含在 Supabase 客户端中）</th>
  </tr>
  <!-- notranslate -->
  <tr>
    <th></th>
    <th>Supabase</th>
    <th><a href="https://github.com/postgrest/postgrest" target="_blank" rel="noopener noreferrer">PostgREST</a></th>
    <th><a href="https://github.com/supabase/gotrue" target="_blank" rel="noopener noreferrer">GoTrue</a></th>
    <th><a href="https://github.com/supabase/realtime" target="_blank" rel="noopener noreferrer">Realtime</a></th>
    <th><a href="https://github.com/supabase/storage-api" target="_blank" rel="noopener noreferrer">Storage</a></th>
    <th>Functions</th>
  </tr>
  <!-- TEMPLATE FOR NEW ROW -->
  <!-- START ROW
  <tr>
    <td>lang</td>
    <td><a href="https://github.com/supabase-community/supabase-lang" target="_blank" rel="noopener noreferrer">supabase-lang</a></td>
    <td><a href="https://github.com/supabase-community/postgrest-lang" target="_blank" rel="noopener noreferrer">postgrest-lang</a></td>
    <td><a href="https://github.com/supabase-community/gotrue-lang" target="_blank" rel="noopener noreferrer">gotrue-lang</a></td>
    <td><a href="https://github.com/supabase-community/realtime-lang" target="_blank" rel="noopener noreferrer">realtime-lang</a></td>
    <td><a href="https://github.com/supabase-community/storage-lang" target="_blank" rel="noopener noreferrer">storage-lang</a></td>
  </tr>
  END ROW -->
  <!-- /notranslate -->
  <th colspan="7">⚡️ 官方 ⚡️</th>
  <!-- notranslate -->
  <tr>
    <td>JavaScript (TypeScript)</td>
    <td><a href="https://github.com/supabase/supabase-js" target="_blank" rel="noopener noreferrer">supabase-js</a></td>
    <td><a href="https://github.com/supabase/postgrest-js" target="_blank" rel="noopener noreferrer">postgrest-js</a></td>
    <td><a href="https://github.com/supabase/gotrue-js" target="_blank" rel="noopener noreferrer">gotrue-js</a></td>
    <td><a href="https://github.com/supabase/realtime-js" target="_blank" rel="noopener noreferrer">realtime-js</a></td>
    <td><a href="https://github.com/supabase/storage-js" target="_blank" rel="noopener noreferrer">storage-js</a></td>
    <td><a href="https://github.com/supabase/functions-js" target="_blank" rel="noopener noreferrer">functions-js</a></td>
  </tr>
  <tr>
    <td>Flutter</td>
    <td><a href="https://github.com/supabase/supabase-flutter" target="_blank" rel="noopener noreferrer">supabase-flutter</a></td>
    <td><a href="https://github.com/supabase/postgrest-dart" target="_blank" rel="noopener noreferrer">postgrest-dart</a></td>
    <td><a href="https://github.com/supabase/gotrue-dart" target="_blank" rel="noopener noreferrer">gotrue-dart</a></td>
    <td><a href="https://github.com/supabase/realtime-dart" target="_blank" rel="noopener noreferrer">realtime-dart</a></td>
    <td><a href="https://github.com/supabase/storage-dart" target="_blank" rel="noopener noreferrer">storage-dart</a></td>
    <td><a href="https://github.com/supabase/functions-dart" target="_blank" rel="noopener noreferrer">functions-dart</a></td>
  </tr>
  <tr>
    <td>Swift</td>
    <td><a href="https://github.com/supabase/supabase-swift" target="_blank" rel="noopener noreferrer">supabase-swift</a></td>
    <td><a href="https://github.com/supabase/supabase-swift/tree/main/Sources/PostgREST" target="_blank" rel="noopener noreferrer">postgrest-swift</a></td>
    <td><a href="https://github.com/supabase/supabase-swift/tree/main/Sources/Auth" target="_blank" rel="noopener noreferrer">auth-swift</a></td>
    <td><a href="https://github.com/supabase/supabase-swift/tree/main/Sources/Realtime" target="_blank" rel="noopener noreferrer">realtime-swift</a></td>
    <td><a href="https://github.com/supabase/supabase-swift/tree/main/Sources/Storage" target="_blank" rel="noopener noreferrer">storage-swift</a></td>
    <td><a href="https://github.com/supabase/supabase-swift/tree/main/Sources/Functions" target="_blank" rel="noopener noreferrer">functions-swift</a></td>
  </tr>
  <tr>
    <td>Python</td>
    <td><a href="https://github.com/supabase/supabase-py" target="_blank" rel="noopener noreferrer">supabase-py</a></td>
    <td><a href="https://github.com/supabase/postgrest-py" target="_blank" rel="noopener noreferrer">postgrest-py</a></td>
    <td><a href="https://github.com/supabase/gotrue-py" target="_blank" rel="noopener noreferrer">gotrue-py</a></td>
    <td><a href="https://github.com/supabase/realtime-py" target="_blank" rel="noopener noreferrer">realtime-py</a></td>
    <td><a href="https://github.com/supabase/storage-py" target="_blank" rel="noopener noreferrer">storage-py</a></td>
    <td><a href="https://github.com/supabase/functions-py" target="_blank" rel="noopener noreferrer">functions-py</a></td>
  </tr>
  <!-- /notranslate -->
  <th colspan="7">💚 社区 💚</th>
  <!-- notranslate -->
  <tr>
    <td>C#</td>
    <td><a href="https://github.com/supabase-community/supabase-csharp" target="_blank" rel="noopener noreferrer">supabase-csharp</a></td>
    <td><a href="https://github.com/supabase-community/postgrest-csharp" target="_blank" rel="noopener noreferrer">postgrest-csharp</a></td>
    <td><a href="https://github.com/supabase-community/gotrue-csharp" target="_blank" rel="noopener noreferrer">gotrue-csharp</a></td>
    <td><a href="https://github.com/supabase-community/realtime-csharp" target="_blank" rel="noopener noreferrer">realtime-csharp</a></td>
    <td><a href="https://github.com/supabase-community/storage-csharp" target="_blank" rel="noopener noreferrer">storage-csharp</a></td>
    <td><a href="https://github.com/supabase-community/functions-csharp" target="_blank" rel="noopener noreferrer">functions-csharp</a></td>
  </tr>
  <tr>
    <td>Go</td>
    <td>-</td>
    <td><a href="https://github.com/supabase-community/postgrest-go" target="_blank" rel="noopener noreferrer">postgrest-go</a></td>
    <td><a href="https://github.com/supabase-community/gotrue-go" target="_blank" rel="noopener noreferrer">gotrue-go</a></td>
    <td>-</td>
    <td><a href="https://github.com/supabase-community/storage-go" target="_blank" rel="noopener noreferrer">storage-go</a></td>
    <td><a href="https://github.com/supabase-community/functions-go" target="_blank" rel="noopener noreferrer">functions-go</a></td>
  </tr>
  <tr>
    <td>Java</td>
    <td>-</td>
    <td>-</td>
    <td><a href="https://github.com/supabase-community/gotrue-java" target="_blank" rel="noopener noreferrer">gotrue-java</a></td>
    <td>-</td>
    <td><a href="https://github.com/supabase-community/storage-java" target="_blank" rel="noopener noreferrer">storage-java</a></td>
    <td>-</td>
  </tr>
  <tr>
    <td>Kotlin</td>
    <td><a href="https://github.com/supabase-community/supabase-kt" target="_blank" rel="noopener noreferrer">supabase-kt</a></td>
    <td><a href="https://github.com/supabase-community/supabase-kt/tree/master/Postgrest" target="_blank" rel="noopener noreferrer">postgrest-kt</a></td>
    <td><a href="https://github.com/supabase-community/supabase-kt/tree/master/Auth" target="_blank" rel="noopener noreferrer">auth-kt</a></td>
    <td><a href="https://github.com/supabase-community/supabase-kt/tree/master/Realtime" target="_blank" rel="noopener noreferrer">realtime-kt</a></td>
    <td><a href="https://github.com/supabase-community/supabase-kt/tree/master/Storage" target="_blank" rel="noopener noreferrer">storage-kt</a></td>
    <td><a href="https://github.com/supabase-community/supabase-kt/tree/master/Functions" target="_blank" rel="noopener noreferrer">functions-kt</a></td>
  </tr>
  <tr>
    <td>Ruby</td>
    <td><a href="https://github.com/supabase-community/supabase-rb" target="_blank" rel="noopener noreferrer">supabase-rb</a></td>
    <td><a href="https://github.com/supabase-community/postgrest-rb" target="_blank" rel="noopener noreferrer">postgrest-rb</a></td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
  </tr>
  <tr>
    <td>Rust</td>
    <td>-</td>
    <td><a href="https://github.com/supabase-community/postgrest-rs" target="_blank" rel="noopener noreferrer">postgrest-rs</a></td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
  </tr>
  <tr>
    <td>Godot 引擎 (GDScript)</td>
    <td><a href="https://github.com/supabase-community/godot-engine.supabase" target="_blank" rel="noopener noreferrer">supabase-gdscript</a></td>
    <td><a href="https://github.com/supabase-community/postgrest-gdscript" target="_blank" rel="noopener noreferrer">postgrest-gdscript</a></td>
    <td><a href="https://github.com/supabase-community/gotrue-gdscript" target="_blank" rel="noopener noreferrer">gotrue-gdscript</a></td>
    <td><a href="https://github.com/supabase-community/realtime-gdscript" target="_blank" rel="noopener noreferrer">realtime-gdscript</a></td>
    <td><a href="https://github.com/supabase-community/storage-gdscript" target="_blank" rel="noopener noreferrer">storage-gdscript</a></td>
    <td><a href="https://github.com/supabase-community/functions-gdscript" target="_blank" rel="noopener noreferrer">functions-gdscript</a></td>
  </tr>
  <!-- /notranslate -->
</table>

<!--- 如果你正在翻译成其他语言，请删除此列表，因为很难在多个文件中保持同步 -->
<!--- 仅保留翻译文件列表的链接 -->

## 徽章

![使用 Supabase 构建](./apps/www/public/badge-made-with-supabase.svg)

```md
[![使用 Supabase 构建](https://supabase.com/badge-made-with-supabase.svg)](https://supabase.com)
```

```html
<a href="https://supabase.com">
  <img
    width="168"
    height="30"
    src="https://supabase.com/badge-made-with-supabase.svg"
    alt="使用 Supabase 构建"
  />
</a>
```

![使用 Supabase 构建（深色）](./apps/www/public/badge-made-with-supabase-dark.svg)

```md
[![使用 Supabase 构建](https://supabase.com/badge-made-with-supabase-dark.svg)](https://supabase.com)
```

```html
<a href="https://supabase.com">
  <img
    width="168"
    height="30"
    src="https://supabase.com/badge-made-with-supabase-dark.svg"
    alt="使用 Supabase 构建"
  />
</a>
```

## 翻译

- 阿拉伯语 | العربية
- 阿尔巴尼亚语 / Shqip
- 孟加拉语 / বাংলা
- 保加利亚语 / Български
- 加泰罗尼亚语 / Català
- 克罗地亚语 / Hrvatski
- 捷克语 / čeština
- 丹麦语 / Dansk
- 荷兰语 / Nederlands
- [英语](https://github.com/supabase/supabase)
- 爱沙尼亚语 / eesti keel
- 芬兰语 / Suomalainen
- 法语 / Français
- 德语 / Deutsch
- 希腊语 / Ελληνικά
- 古吉拉特语 / ગુજરાતી
- 希伯来语 / עברית
- 印地语 / हिंदी
- 匈牙利语 / Magyar
- 尼泊尔语 / नेपाली
- 印尼语 / Bahasa Indonesia
- 意大利语 / Italiano
- 日语 / 日本語
- 韩语 / 한국어
- 立陶宛语 / lietuvių
- 拉脱维亚语 / latviski
- 马来语 / Bahasa Malaysia
- 挪威语 (Bokmål) / Norsk (Bokmål)
- 波斯语 / فارسی
- 波兰语 / Polski
- 葡萄牙语 / Português
- 巴西葡萄牙语 / Português Brasileiro
- 罗马尼亚语 / Română
- 俄语 / Pусский
- 塞尔维亚语 / Srpski
- 僧伽罗语 / සිංහල
- 斯洛伐克语 / slovenský
- 斯洛文尼亚语 / Slovenščina
- 西班牙语 / Español
- 简体中文 / Simplified Chinese
- 瑞典语 / Svenska
- 泰语 / ไทย
- 繁体中文 / Traditional Chinese
- 土耳其语 / Türkçe
- 乌克兰语 / Українська
- 越南语 / Tiếng Việt
- 翻译列表 <!--- 仅保留此链接 -->