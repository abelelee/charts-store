<div align="center">
  <h1 align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="static/assets/images/teable-vertical-dark.png">
      <img alt="teable logo" height="150" src="static/assets/images/teable-vertical-light.png">
    </picture>
  </h1>
  <h3 align="center"><strong>Postgres-Airtable 融合</strong></h3>
  <p>Teable 是一个基于 Postgres 构建的超快速、实时、专业、面向开发者的无代码数据库。它使用类似电子表格的简单界面，创建复杂的企级数据库应用。在无需编写代码的前提下释放高效应用开发能力，摆脱数据安全和可扩展性的难题。</p>
</div>

<p align="center">
  <a target="_blank" href="https://teable.io">首页</a> | <a target="_blank" href="https://help.teable.io">帮助</a> | <a target="_blank" href="https://Blog.teable.io">博客</a> | <a target="_blank" href="https://template.teable.io">模板</a> | <a target="_blank" href="https://app.teable.io/share/shr04TEw1u9EOQojPmG/view">路线图</a> | <a target="_blank" href="https://discord.gg/n2JQqekG">Discord</a> | <a target="_blank" href="https://twitter.com/teableio">Twitter</a>
</p>

<p align="center">
  <a aria-label="Build" href="https://github.com/teableio/teable/actions?query=Build%20and%20Push%20to%20Docker%20Registry">
    <img alt="build" src="https://img.shields.io/github/actions/workflow/status/teableio/teable/docker-push.yml?label=Build&logo=github&style=flat-quare&labelColor=000000" />
  </a>
  <a aria-label="Codefactor grade" href="https://www.codefactor.io/repository/github/teableio/teable">
    <img alt="Codefactor" src="https://img.shields.io/codefactor/grade/github/teableio/teable?label=Codefactor&logo=codefactor&style=flat-quare&labelColor=000000" />
  </a>
  <a aria-label="CodeClimate maintainability" href="https://codeclimate.com/github/teableio/teable">
    <img alt="Maintainability" src="https://img.shields.io/codeclimate/maintainability/teableio/teable?label=Maintainability&logo=code-climate&style=flat-quare&labelColor=000000" />
  </a>
  <a aria-label="CodeClimate technical debt" href="https://codeclimate.com/github/teableio/teable">
    <img alt="Techdebt" src="https://img.shields.io/codeclimate/tech-debt/teableio/teable?label=TechDebt&logo=code-climate&style=flat-quare&labelColor=000000" />
  </a>
  <a aria-label="Codacy grade" href="https://www.codacy.com/gh/teableio/teable/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=teableio/teable&amp;utm_campaign=Badge_Grade">
    <img alt="Codacy grade" src="https://img.shields.io/codacy/grade/dff9c944af284a0fad4e165eb1727467?logo=codacy&style=flat-square&labelColor=000&label=Codacy">
  </a>
  <a aria-label="Top language" href="https://github.com/teableio/teable/search?l=typescript">
    <img alt="GitHub top language" src="https://img.shields.io/github/languages/top/teableio/teable?style=flat-square&labelColor=000&color=blue">
  </a>
  <a aria-label="Licence" href="https://github.com/teableio/teable/blob/main/LICENSE">
    <img alt="Licence" src="https://img.shields.io/github/license/teableio/teable?style=flat-quare&labelColor=000000" />
  </a>
</p>

  <h1 align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="static/assets/images/teable-interface-dark.png">
      <img alt="teable interface" width="100%" src="static/assets/images/teable-interface-light.png">
    </picture>
  </h1>

## 快速指南

1. 想要快速体验？从[模板中心](https://template.teable.io)中选择一个场景，点击“使用此模板”。
2. 追求高性能？尝试[百万行数据演示](https://app.teable.io/share/shrVgdLiOvNQABtW0yX/view)，感受 Teable 的速度。
3. 想要快速上手？点击[教程](https://help.teable.io/quick-start/build-a-simple-base)
4. 想要自行部署？点击[在 Railway 上部署](https://railway.app/template/wada5e?referralCode=rE4BjB)

## ✨功能特性

#### 📊 类似电子表格的界面

所有你需要的功能都在这里

- 单元格编辑：直接点击并编辑单元格内容。
- 公式支持：输入数学和逻辑公式自动计算值。
- 数据排序和筛选：根据单列或多列对数据进行排序；使用筛选器查看特定行数据。
- 聚合函数：自动汇总每列的统计信息，提供求和、平均值、计数、最大值和最小值等即时计算，简化数据分析。
- 数据格式化：格式化数字、日期等。
- 分组：根据列值将行组织成可折叠的组，便于数据分析和导航。
- 冻结列：冻结表格左侧列，滚动时保持可见。
- 导入/导出功能：从其他格式导入和导出数据，例如 .csv、.xlsx。
- 行样式与条件格式：根据特定条件自动更改行样式。（即将推出）
- 图表与可视化工具：从表格数据创建图表，如柱状图、饼图、折线图等。（即将推出）
- 数据验证：限制或验证单元格中输入的数据。（即将推出）
- 撤销/重做：撤销或重做最近的更改。（即将推出）
- 评论与注释：为行添加评论，为其他用户提供解释或反馈。（即将推出）
- 查找与替换：在表格中搜索内容并用新内容替换。（即将推出）

#### 🗂️ 多视图支持

以最适合特定任务的方式可视化和交互数据。

- 网格视图：表格的默认视图，以类似电子表格的格式显示数据。
- 表单视图：以表单格式输入数据，适用于数据收集。
- 看板视图：以看板形式显示数据，以列和卡片的形式可视化数据。（即将推出）
- 日历视图：以日历格式显示数据，适用于跟踪日期和事件。（即将推出）
- 画廊视图：以画廊格式显示数据，适用于显示图像和其他媒体。（即将推出）
- 甘特视图：以甘特图形式显示数据，适用于跟踪项目进度。（即将推出）
- 时间线视图：以时间线格式显示数据，适用于跟踪随时间变化的事件。（即将推出）

#### 🚀 超快速度

惊人的响应速度和数据处理能力

- 轻松处理百万级数据，筛选和排序毫无压力
- 自动数据库索引以实现最大速度
- 支持一次性批量数据操作

#### 👨‍💻 完整的 SQL 支持

与你熟悉的软件无缝集成

- BI 工具如 Metabase、PowerBi...
- 无代码工具如 Appsmith...
- 使用原生 SQL 直接检索数据

#### 🔒 隐私优先

无论在云端还是本地，数据始终属于你

- 自带数据库（即将推出）

#### ⚡ 实时协作

专为团队设计

- 无需刷新页面，数据实时更新
- 无缝集成协作成员邀请与管理
- 完善的权限管理机制，从表到列级别

#### 🧩 扩展功能（即将推出）

拓展无限可能

- 基于 React 的无后端编程能力
- 以极低成本自定义自己的应用
- 极其易用的脚本扩展模式

#### 🤖 自动化（即将推出）

轻松无缝地赋能数据驱动的工作流

- 使用 AI 或可视化编程设计你的工作流
- 超级容易从表中检索数据

#### 🧠 智能助手（即将推出）

原生集成 AI 能力

- 聊天生成应用。"帮我创建一个项目管理应用"
- 聊天生成图表。"使用柱状图分析订单表中的数据"
- 聊天生成视图。"我想查看过去一周的日程并只显示参与者"
- 聊天触发动作。"订单支付完成后，向客户发送邮件通知"
- 更多功能...

#### 🗄️ 多数据库支持（即将推出）

选择你喜欢的 SQL 数据库

- Sqlite、PostgreSQL、MySQL、MariaDB、TiDB...

---

# 架构

[![Open in Gitpod](https://img.shields.io/badge/Open%20In-Gitpod.io-%231966D2?style=for-the-badge&logo=gitpod)](https://gitpod.io/#https://github.com/teableio/teable)

```
.
├── apps
│   ├── nextjs-app          (前端，包含一个 nextjs 应用)
│   └── nestjs-backend      (后端，包含一个 nestjs 应用)
└── packages
    ├── common-i18n         (多语言支持)
    ├── core                (共享代码和接口)
    ├── sdk                 (扩展 SDK)
    ├── db-main-prisma      (schema、迁移、prisma 客户端)
    ├── eslint-config-bases (共享的 eslint 配置)
    └── ui-lib              (UI 组件库)
```

## 部署

### 使用 Docker 部署

```sh
cd dockers/examples/standalone/
docker-compose up -d
```

更多详情请参见 [dockers/examples](dockers/examples)

### 一键部署

以下平台支持一键部署，并提供免费额度。

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/wada5e?referralCode=rE4BjB)

[![Deploy on Zeabur](https://zeabur.com/button.svg)](https://zeabur.com/templates/QF8695)

[![Deploy on Sealos](https://raw.githubusercontent.com/labring-actions/templates/main/Deploy-on-Sealos.svg)](https://cloud.sealos.io/?openapp=system-template%3FtemplateName%3Dteable)

## 开发

#### 1. 初始化

```sh
# 启用 Help Management Package Manager
corepack enable

# 安装项目依赖
pnpm install

# 构建包
pnpm g:build
```

#### 2. 选择数据库

我们目前支持 `sqlite` 和 `postgres`，你可以通过以下命令切换它们：

```sh
make switch-db-mode
```

#### 3. 自定义环境变量（可选）

```sh
cd apps/nextjs-app
copy .env.development .env.development.local
```

#### 4. 运行开发服务器

你只需启动后端，它会自动启动前端的 next 服务器，文件更改会自动重载：

```sh
cd apps/nestjs-backend
pnpm dev
```

## 为什么选择 Teable？

无代码工具显著加快了我们的工作进度，使非技术人员也能构建出色的应用，改变了人们的工作和生活方式。人们喜欢使用类似电子表格的界面来处理数据，因为它简单、灵活，并且非常适合团队协作。他们也更倾向于在不被笨重模板限制的情况下设计自己的应用界面。

赋予非技术人员创建自己软件的能力听起来令人兴奋。但这只是开始：

- 随着企业的发展，其数据需求也在增长。没有人希望听到，当订单达到10万条时，当前的界面已经无法承载。然而，许多无代码平台在这样的规模下就会崩溃。
- 大多数无代码平台是基于云的。这意味着你的关键数据存储在服务提供商那里，切换平台可能会非常麻烦。
- 有时，由于无代码工具的限制，用户无法完成他们想要的操作。
- 如果一个工具变得至关重要，你最终还是需要一些技术能力。但开发者通常发现这些平台很难使用。
- 对于开发者来说，维护复杂设置的系统可能很困难，尤其是当这些系统没有使用通用软件标准构建时。
- 如果系统没有使用这些标准构建，可能需要重构或替换，这将带来长期成本。甚至可能意味着放弃无代码路线，重新回到传统编码。

#### 我们认为未来无代码产品的样子应该是：

- 一个任何人都可以轻松使用的界面来构建应用。
- 易于访问数据，让用户可以自由获取、移动和重用他们的信息。
- 数据隐私和选择权，无论是在云端、本地，还是仅仅在你的本地机器上。
- 它不仅要适合非技术人员，也要适合开发者。
- 它应该能够处理大量数据，以适应业务的增长。
- 灵活地与其他软件集成，结合各自优势完成任务。
- 最后，原生集成 AI，将可用性提升到新的高度。

本质上，Teable 不只是一个无代码解决方案，它是对现代软件开发不断演变需求的全面回应，确保无论技术背景如何，每个人都有一个为其量身定制的平台。

## 赞助者 :heart:

如果你在公司中使用了这个项目，我非常感谢你提供 [赞助](https://github.com/sponsors/teableio)、[一杯咖啡](https://ko-fi.com/teable) 或者点一个 star。
这将让我有更多时间将其提升到下一个层次。

# 许可证

AGPL-3.0