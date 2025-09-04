<!-- logo -->
<p align="center">
    <a href="https://logseq.com" alt="Logseq Logo">
    <img src="https://user-images.githubusercontent.com/25513724/220608753-f33db466-af72-4611-b603-411440c15ed0.png?sanatize=true" height="173"/></a>
</p>

<h1 align="center"> Logseq </h1>

<h4 align="center">
    一个以隐私为先的开源知识管理与协作平台
</h4>

<div align="center">
    <a href="https://logseq.com">首页</a> |
    <a href="https://blog.logseq.com/">博客</a> |
    <a href="https://docs.logseq.com/">文档</a> |
    <a href="https://trello.com/b/8txSM12G/roadmap">路线图</a>
</div>
<br></br>

<p align="center">
    <a href="https://github.com/logseq/logseq/releases/latest/">
        <img src="https://img.shields.io/badge/Download_Logseq-100000?style=for-the-badge&logo=flatpak&logoColor=white&labelColor=002b36&color=85c8c8"
            alt="下载 Logseq"/></a>
</p>

<!-- 社交徽章 -->
<p align="center">
    <a href="https://discuss.logseq.com">
        <img src="https://img.shields.io/badge/forum-Logseq-blue.svg?&color=%2385c8c8&logo=discourse&style=for-the-badge"
            alt="论坛"></a>
    <a href="https://discord.gg/KpN4eHY">
        <img src="https://img.shields.io/discord/725182569297215569?color=%2385c8c8&label=Discord&logo=discord&style=for-the-badge"
            alt="在 Discord 上聊天"></a>
    <a href="https://twitter.com/intent/follow?screen_name=logseq">
        <img src="https://img.shields.io/badge/twitter-%40logseq-blue.svg?&color=%2385c8c8&logo=twitter&style=for-the-badge"
            alt="在 Twitter 上关注"></a>
</p>

<!-- 开发徽章 -->
<p align="center">
    <a href="https://github.com/logseq/logseq/graphs/contributors" alt="贡献者">
        <img src="https://img.shields.io/github/contributors/logseq/logseq?color=%2385c8c8&style=for-the-badge"/></a>
    <a href="#-支持者" alt="Open Collective 上的支持者">
        <img src="https://img.shields.io/opencollective/backers/logseq?color=%2385c8c8&style=for-the-badge"/></a>
    <a href="#-赞助商" alt="Open Collective 上的赞助商">
        <img src="https://img.shields.io/opencollective/sponsors/logseq?color=%2385c8c8&style=for-the-badge"/></a>
    <a href="https://github.com/logseq/logseq/blob/master/LICENSE.md" alt="许可证">
        <img src="https://img.shields.io/github/license/logseq/logseq?color=%2385c8c8&style=for-the-badge"/></a>
    <a href="https://github.com/logseq/logseq/releases">
        <img src="https://img.shields.io/github/v/release/logseq/logseq?color=%2385c8c8&style=for-the-badge"
            alt="最新发布版本"></a>
</p>

## 目录

  * [<g-emoji class="g-emoji" alias="database" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f680.png">🚀</g-emoji> 数据库版本](#-数据库版本)
  * [<g-emoji class="g-emoji" alias="thinking" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f914.png">🤔</g-emoji> 为什么选择 Logseq？](#-为什么选择-logseq)
  * [<g-emoji class="g-emoji" alias="eyes" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f440.png">👀</g-emoji> 如何使用？](#-如何使用)
  * [<g-emoji class="g-emoji" alias="books" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f4da.png">📚</g-emoji> 了解更多](#-了解更多)
  * [🫶 支持 Logseq 开发](#-支持-logseq-开发)
  * [<g-emoji class="g-emoji" alias="bulb" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f4a1.png">💡</g-emoji> 功能请求](#-功能请求)
  * [<g-emoji class="g-emoji" alias="electric_plug" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f50c.png">🔌</g-emoji> 插件 API](#-插件-api)
  * [<g-emoji class="g-emoji" alias="star2" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f31f.png">🌟</g-emoji> 参与 Logseq 贡献](#-参与-logseq-贡献)
    * [<g-emoji class="g-emoji" alias="hammer_and_wrench" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f6e0.png">🛠️</g-emoji> 搭建开发环境](#️-搭建开发环境)
  * [<g-emoji class="g-emoji" alias="sparkles" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2728.png">✨</g-emoji> 灵感来源](#-灵感来源)
* [<g-emoji class="g-emoji" alias="pray" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f64f.png">🙏</g-emoji> 感谢](#-感谢)

## 🚀 数据库版本

Logseq 的数据库版本（DB version）在支持文件图的同时引入了数据库图。[查看此页面](https://github.com/logseq/docs/blob/master/db-version.md) 了解数据库图的主要功能概述。如果你是现有用户，[查看数据库版本的变更](https://github.com/logseq/docs/blob/master/db-version-changes.md)。数据库版本还拥有全新的移动应用！要参与移动应用的测试，请[填写此简短表单](https://forms.gle/nfefJv51jUuULbFB9)。数据库版本还引入了新的同步方式——RTC（实时协作）！你可以使用它在多个设备之间同步图谱，或与他人协作。要参与 RTC 测试，请[填写此表单](https://forms.gle/YSyF4WfKPSDuwyjH6)。

数据库版本目前处于 Beta 阶段，而新移动应用和 RTC 处于 Alpha 阶段。这意味着**可能会发生数据丢失**，因此我们建议你启用[自动备份](https://github.com/logseq/docs/blob/master/db-version.md#automated-backup) 或定期进行 [SQLite DB 备份](https://github.com/logseq/docs/blob/master/db-version.md#graph-export)。在使用数据库图时，我们建议你创建一个专用的测试图，并选择一个对你来说不重要的项目进行测试。在使用文件图时，**可能会发生数据损坏**，因为某些文件内容可能会被重复。我们仅建议你在使用 git 定期备份的情况下使用文件图。

开始使用数据库版本：
* 要尝试最新网页版，请访问 https://test.logseq.com/。
* 要尝试最新桌面版，请登录 Github 并访问 https://github.com/logseq/logseq/actions/workflows/build-desktop-release.yml，点击最新的发布版本。向下滚动，在 `Artifacts` 部分下载适用于你操作系统的安装包。
* 要报告错误，请提交到 https://github.com/logseq/db-test/issues。
* 对于功能或增强请求，请在 Discord 的 `#db-feedback` 频道提交。
* 如需讨论，请查看 Discord 中的 `#db-chat` 频道。

## 🤔 为什么选择 Logseq？

[Logseq](https://logseq.com) 是一个**知识管理**和**协作**平台。它专注于**隐私**、**持久性**和[**用户控制权**](https://www.gnu.org/philosophy/free-sw.en.html)。Logseq 提供了一系列**强大的工具**，用于**知识管理**、**协作**、**PDF 注释**和**任务管理**，支持多种文件格式，包括**Markdown**和**Org-mode**，并提供各种功能来组织和结构化你的笔记。

Logseq 的**白板**功能让你可以使用一个空间**画布**来组织你的知识和想法，画布支持**形状**、**绘图**、**网站嵌入**和**连接线**。你可以**可视化地分组**和**链接**你的**笔记**和外部媒体（如**视频**和**图片**），使视觉型思考者能够以前所未有的方式组合、混搭、**注释**并连接来自知识库和新想法的内容。

除了核心功能外，Logseq 还拥有不断增长的**插件**和**主题**生态系统，支持广泛的工作流和**自定义**选项。**移动应用**也已上线，提供与桌面应用大部分功能相同的支持。无论你是学生、专业人士，还是任何重视清晰、有条理的方式来管理你的想法和笔记的人，Logseq 都是提升生产力和优化工作流程的绝佳选择。

![logseq-demo](https://user-images.githubusercontent.com/25513724/221387376-4dc419c2-0d0a-460c-a920-2d211e78b456.gif)

<a href="https://github.com/logseq/logseq/releases/latest/">
        <img src="https://img.shields.io/badge/Download_Logseq-100000?style=for-the-badge&logo=flatpak&logoColor=white&labelColor=002b36&color=85c8c8"
            align="right"
            alt="下载 Logseq"/></a>

## 👀 如何使用？

要开始使用 Logseq，请按照以下简单步骤操作：

1. [下载](https://github.com/logseq/logseq/releases/latest) 最新版本的 Logseq
2. 在你的设备上安装 Logseq 并启动应用程序
3. 开始写作 ✍️

就这样！你现在可以享受使用 Logseq 带来的优化工作流程、管理项目和掌控目标的好处。祝你使用愉快！🎉

## 📚 了解更多

* 官网：[logseq.com](https://logseq.com)
* 文档：[docs.logseq.com](https://docs.logseq.com)
  * 常见问题页面：[Logseq 文档：FAQ](https://docs.logseq.com/#/page/faq)
* 博客：[blog.logseq.com](https://blog.logseq.com)
  * 请访问我们的[关于页面](https://blog.logseq.com/about)获取最新动态。
* Logseq Hub：[hub.logseq.com](https://hub.logseq.com)
* 论坛：[discuss.logseq.com](https://discuss.logseq.com) - 我们在这里回答问题、讨论工作流并分享技巧
  * 常见问题论坛板块：[Logseq 论坛：FAQ](https://discuss.logseq.com/c/faq/6)
* [Awesome Logseq](https://github.com/logseq/awesome-logseq) - 社区创建的优秀 Logseq 扩展和资源 <3
* Twitter：[@Logseq](https://twitter.com/logseq)
* Discord：[discord.gg/logseq](https://discord.gg/logseq)
  * [中文 Discord](https://discord.gg/xYqcrXWymg)

## 🫶 支持 Logseq 开发

如果你觉得 Logseq 很有用，并希望帮助我们持续发展该项目，请考虑在 [Open Collective](https://opencollective.com/logseq) 上支持我们的贡献者。你的支持向我们的贡献者表明他们的努力得到了认可，并激励他们继续出色的工作。每一份贡献，无论大小，都有助于我们持续改进 Logseq。

## 💡 功能请求

我们非常重视你对改进 Logseq 和使其更实用的意见。如果你有任何想法或功能请求，请在 [Logseq 论坛：功能请求](https://discuss.logseq.com/new-topic?category=feature-requests) 板块中分享。

你的反馈帮助我们理解用户的需求，并优先开发对你最重要的功能。感谢你花时间与我们分享你的想法。

我们感谢你的支持，期待听到你的创意！

## 🔌 插件 API

Logseq 提供了一个插件 API，使开发者能够创建自定义插件并扩展 Logseq 的功能。插件 API 文档可在 [plugins-doc.logseq.com](https://plugins-doc.logseq.com/) 上找到，你可以在那里找到开始插件开发所需的一切内容。

我们非常重视你对改进文档的反馈和建议。请随时联系我们提出任何意见或问题。你的反馈帮助我们为用户和开发者提供更好的体验。

感谢你使用 Logseq，我们期待看到你使用我们的插件 API 所创造的内容！

## 🌟 参与 Logseq 贡献

要开始为 Logseq 做贡献，请阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。
你可以通过[代码贡献](https://github.com/logseq/logseq/blob/master/CONTRIBUTING.md#code-contributions) 和[非代码方式](https://github.com/logseq/logseq/blob/master/CONTRIBUTING.md#-how-can-i-help) 来参与贡献。我们欢迎任何形式的贡献，无论大小，我们感谢你花时间帮助我们改进 Logseq。我们期待你的贡献 🚀

### 🛠️ 搭建开发环境

如果你想为 Logseq 的网页版或桌面版搭建开发环境，请参考 [开发 Logseq](docs/develop-logseq.md) 指南（适用于 macOS/Linux 用户）和 [Windows 上开发 Logseq](docs/develop-logseq-on-windows.md) 指南（适用于 Windows 用户）。

除了这些指南外，你还可以在 [docs/](docs/) 文件夹中找到其他有用的资源，例如 [翻译贡献指南](docs/contributing-to-translations.md)、[Docker 网页应用指南](docs/docker-web-app-guide.md) 和 [移动端开发指南](docs/develop-logseq-on-mobile.md)

## ✨ 灵感来源

Logseq 受到多个独特工具和项目的启发，包括 [Roam Research](https://roamresearch.com/)、[Org Mode](https://orgmode.org/)、[TiddlyWiki](https://tiddlywiki.com/)、[Workflowy](https://workflowy.com/) 和 [Cuekeeper](https://github.com/talex5/cuekeeper)。

我们对这些项目的开发者和创建者深表感激，我们希望 Logseq 能够继续建立在这些创新想法之上，并使其为更广泛的用户所用。

感谢所有启发我们的人，我们期待看到 Logseq 社区将用这个工具创造出什么！

Logseq 的实现也得益于以下项目：

* [Clojure & ClojureScript](https://clojure.org/) - 一种动态、函数式、通用编程语言
* [DataScript](https://github.com/tonsky/datascript) - 一个用于 Clojure、ClojureScript 和 JS 的不可变数据库和 Datalog 查询引擎
* [OCaml](https://ocaml.org/) & [Angstrom](https://github.com/inhabitedtype/angstrom)，用于文档解析器 [mldoc](https://github.com/logseq/mldoc)
* [isomorphic-git](https://isomorphic-git.org/) - 一个用于 NodeJS 和 Web 浏览器的纯 JavaScript Git 实现
* [SCI](https://github.com/borkdude/sci) - 一个小型 Clojure 解释器

# 🙏 感谢

我们想向我们的 [Open Collective](https://opencollective.com/logseq) **赞助商**、**支持者**和**贡献者**表达我们最诚挚的感谢。你们的支持和贡献使我们能够继续开发和改进 Logseq。感谢你成为我们社区的一员，并帮助我们让 Logseq 成为最好的工具！

## 💎 赞助商

<p align="center">
    <a href="https://opencollective.com/logseq#sponsor"> [成为赞助商]</a>
</p>
<p align="center">
    <a href="https://opencollective.com/logseq" alt="Open Collective 上的赞助商">
        <img src="https://opencollective.com/logseq/tiers/sponsors.svg?avatarHeight=42&width=600"/></a>
</p>

## 🌟 贡献者

<p align="center">
    <a href="https://github.com/logseq/logseq/graphs/contributors">
        <img src="https://contrib.rocks/image?repo=logseq/logseq&max=300&columns=14" width="600"/></a>
</p>

## 🫶 支持者

<p align="center">
    <a href="https://opencollective.com/logseq" alt="Open Collective 上的支持者">
        <img src="https://opencollective.com/logseq/tiers/backers.svg?avatarHeight=24&width=600"/></a>
</p>

<!-- JetBrains Logo -->
<p align="center">
    <a href="https://jetbrains.com" alt="JetBrains">
        <img src="docs/assets/jetbrains.svg"/></a>
</p>

<!-- ProductHunt Review Button -->
<p align="center">
    <a href="https://www.producthunt.com/posts/logseq?utm_source=badge-review&utm_medium=badge&utm_souce=badge-logseq#discussion-body"
    target="_blank"><img
        src="https://api.producthunt.com/widgets/embed-image/v1/review.svg?post_id=298158&theme=dark"
        align="center"
        alt="Logseq - 你的快乐、私密数字花园 | Product Hunt" style="width: 250px; height: 54px;"
        width="250" height="54"/></a>
</p>