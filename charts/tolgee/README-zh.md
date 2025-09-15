<h1 align="center" style="border-bottom: none">
    <b>
        <a href="https://tolgee.io">Tolgee</a><br>
    </b>
一个开发者喜爱使用的开源本地化平台<br/>
</h1>

<div align="center">

[![Logo](https://user-images.githubusercontent.com/18496315/188628892-33fcc282-26f1-4035-8105-95952bd93de9.svg)](https://tolgee.io)

Crowdin、Phrase 或 Lokalise 的开源替代方案

![example workflow](https://github.com/tolgee/tolgee-platform/actions/workflows/test.yml/badge.svg)
![kotlin](https://img.shields.io/github/languages/top/tolgee/tolgee-platform)
[![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=fff)](https://hub.docker.com/repository/docker/tolgee/tolgee)
[![github release](https://img.shields.io/github/v/release/tolgee/tolgee-platform?label=GitHub%20Release)](https://github.com/tolgee/tolgee-platform/releases/latest)
![licence](https://img.shields.io/badge/license-Apache%202%20%2F%20Tolgee%20EL-blue)
[![github stars](https://img.shields.io/github/stars/tolgee/tolgee-js?style=social&label=Tolgee%20JS)](https://github.com/tolgee/tolgee-js)
[![github stars](https://img.shields.io/github/stars/tolgee/tolgee-platform?style=social&label=Tolgee%20Platform)](https://github.com/tolgee/tolgee-platform)
[![Github discussions](https://img.shields.io/github/discussions/tolgee/tolgee-platform)](https://github.com/tolgee/tolgee-platform/discussions)
[![Dev.to](https://img.shields.io/badge/Dev.to-tolgee_i18n?logo=devdotto&logoColor=white)](https://dev.to/tolgee_i18n)
[![Read the Docs](https://img.shields.io/badge/Read%20the%20Docs-8CA1AF?logo=readthedocs&logoColor=fff)](https://docs.tolgee.io/)
[![Slack](https://img.shields.io/badge/Slack-4A154B?logo=slack&logoColor=fff)](https://join.slack.com/t/tolgeecommunity/shared_invite/zt-2zp55d175-_agXTfKKVbf1BYXlKlmwbA)
[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?logo=YouTube&logoColor=white)](https://www.youtube.com/@tolgee)
[![LinkedIn](https://custom-icon-badges.demolab.com/badge/LinkedIn-0A66C2?logo=linkedin-white&logoColor=fff)](https://www.linkedin.com/company/tolgee/)
[![X](https://img.shields.io/badge/X-%23000000.svg?logo=X&logoColor=white)](https://x.com/Tolgee_i18n)
</div>

![Tolgee](https://github.com/techwithprerit/tolgee-platform/blob/a8b0ab45640e1fef729e7f1237817ba9b03dfaf4/tolgee.gif)

## 为什么使用 Tolgee？

它能节省你在本地化任务上宝贵的时间，同时确保你的软件被完美翻译。

![Frame 47](https://github.com/techwithprerit/tolgee-platform/blob/a8b0ab45640e1fef729e7f1237817ba9b03dfaf4/Tolgee-specs.gif)

### 上下文翻译 & 一键截图

你可以轻松地将翻译添加到代码中，并在应用内直接编辑它们。只需按住 ALT/Option 键并点击某个元素，即可打开一个对话框，轻松修改字符串内容——无需再在臃肿的 .json/.po/.whatever 文件中来回切换。此外，即使在生产环境中，上下文翻译也能无缝运行。

只需一次点击，即可捕获你的应用截图，其中需要翻译的短语会被高亮显示。只需按住 ALT + 点击某个字符串，然后点击相机按钮。搞定！你的截图立即生成。

![Sep-06-2022 16-38-49](https://github.com/techwithprerit/tolgee-platform/blob/b56dd663cacd1c167ac5855a33c5b9fa4aa4276e/tolgee-app.gif)

### 在生产环境中翻译

即使在部署后的生产环境中，上下文翻译也能无缝运行。使用 Tolgee Tools Chrome 插件，只需输入你的 API 密钥即可开始翻译——无需任何编码技能。这使得任何人都可以轻松地为你的应用贡献翻译内容。

### 真正的集成

Tolgee 并不仅仅是一个将本地数据与后端同步的本地化平台。相反，它通过强大的 SDK 无缝集成到你的应用中，提供真正嵌入式的翻译体验。

### 机器翻译

我们支持 **DeepL、Google Translate 和 AWS Translate**——只需在设置中选择你偏好的服务即可。借助机器翻译，本地化流程显著加快，翻译人员可以利用 AI 提供的建议，实现更高效、更准确的翻译。

### 翻译记忆库

Tolgee 会根据你在项目中已使用的翻译自动提供建议，确保相似短语之间的一致性。

翻译记忆库建议包括翻译字符串的 **相似度百分比、键名和原始文本**，便于保持准确性和连贯性。

### 自动翻译

启用后，Tolgee 会使用 **翻译记忆库** 或 **机器翻译服务** 立即翻译新键，确保你的字符串在创建时即被翻译。你只需选择是否使用翻译记忆库，并选择偏好的机器翻译服务，即可实现无缝自动化。

### 活动日志

清晰地追踪谁修改、审核或评论了项目中的短语。

### 翻译评论

如果某些翻译看起来有问题，可以直接在 Tolgee 平台上对翻译留下评论，告知他人你的修改建议。

### 翻译历史

轻松追踪特定语言中某个键的具体翻译变更。如果发现错误，你可以准确知道问题出在哪里。

## 文档

文档涵盖了使用 Tolgee 的各个方面。重点内容包括：

- [快速入门](https://docs.tolgee.io/)。注册账号、创建项目、按照指南操作，尽情体验！
- [JavaScript SDK](https://docs.tolgee.io/js-sdk)。尝试使用并告诉我们你的想法 #FeedbackWanted ❤️
- [Tolgee CLI](https://docs.tolgee.io/tolgee-cli)。让使用 Tolgee 变得更轻松
- [集成支持](https://docs.tolgee.io/platform/integrations/about_integrations)。你想到的，我们都有。
- Junie 指南。面向新贡献者和初级开发者的指南。

## 快速开始 🚀

1. 在 [app.tolgee.io](https://app.tolgee.io/sign_up) 注册账号，或访问你自托管的实例
2. 创建一个项目
3. 在项目的集成部分中选择一个指南进行操作
4. 尽情体验！

![集成指南](Tolgee-integration.gif)

## 报告 Bug

如需提交 Bug、建议改进或请求新功能，请提交一个 [issue](https://github.com/tolgee/tolgee-platform/issues)。

## 如何贡献

你想贡献代码？太棒了！你可以立即开始 贡献！

## 贡献者

<a href="https://github.com/tolgee/tolgee-platform/graphs/contributors">
  <img alt="贡献者" src="https://contrib.rocks/image?repo=tolgee/tolgee-platform"/>
</a>

欢迎告诉我们你的想法！#FeedbackWanted ❤️