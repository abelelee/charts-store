以下是你提供的 Markdown 内容的中文翻译，保留了原始格式：

---

<div align="center">
  <h1 align="center">
    <img alt="heyform logo" height="60" src="./assets/images/logo.svg">
  </h1>
  <p>HeyForm 是一个开源表单构建工具，任何人都可以使用它创建互动式的对话式表单，用于调查、问卷、测验和投票，无需任何编码技能。</p>
</div>
<p align="center">
  <a target="_blank" href="https://heyform.net">官网</a> | <a target="_blank" href="https://docs.heyform.net">文档</a> | <a target="_blank" href="https://heyform.net/blog">博客</a> | <a target="_blank" href="https://twitter.com/HeyformHQ">Twitter</a>
</p>

<p align="center">
<a href="https://trendshift.io/repositories/9025" target="_blank"><img src="https://trendshift.io/api/badge/repositories/9025" alt="heyform" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</p>

<img src="./assets/images/screenshot.png" alt="HeyForm" />

## 功能特性

HeyForm 简化了对话式表单的创建过程，使任何人都能轻松通过互动调查、测验和投票收集信息或反馈。我们致力于通过定期更新来增强 HeyForm 的功能，包括修复错误、新增功能和性能优化。

### 轻松构建表单

- 📝 **多样化的输入方式**：从基本的文本、电子邮件和电话号码字段，到图片选择、日期选择器和文件上传等高级选项，HeyForm 支持多种输入类型。
- 🧠 **智能逻辑控制**：支持条件逻辑和 URL 重定向，打造动态、灵活的表单。
- 🔗 **强大的集成能力**：可与 Webhook、分析工具、营销平台以及 Zapier 和 Make.com 等工具集成。

### 按品牌风格定制

- 🎨 **视觉主题**：通过可自定义的字体、颜色、背景等，轻松调整表单外观以匹配你的品牌风格。
- ✨ **高级主题定制**：提供丰富的自定义选项，包括自定义 CSS，实现更深层次的个性化设置。

### 数据分析与应用

- 📊 **深入分析功能**：提供详细的分析数据，包括流失率和完成率等关键指标。
- 📤 **数据导出**：轻松将表单结果导出为 CSV 格式，便于进一步分析或集成到你的系统中。

## 开始使用 HeyForm

使用 HeyForm 最简单高效的方式是通过 [我们的官方托管服务](https://my.heyform.net)。选择该云服务版本，你可以享受到高可靠性、自动备份、强大的安全性和免维护的便利——这一切都由我们这个充满热情的双人团队精心维护。

选择我们的托管版本不仅能节省大量时间和资源，还能支持 HeyForm 的持续开发和开源社区的发展。享受优质服务的同时，也为创新贡献力量。💙

## 项目结构

```
.
└── packages
    ├── answer-utils       (用于服务端和 Web 应用的表单提交工具)
    ├── embed              (表单嵌入的 JavaScript 库)
    ├── shared-types-enums (服务端和 Web 应用共享的类型和枚举)
    ├── utils              (服务端和 Web 应用通用的工具函数)
    ├── server             (Node 服务端)
    └── webapp             (React 前端应用)
```

## 自托管

有兴趣在自己的服务器上部署 HeyForm 吗？请查看 [自托管安装指南](https://docs.heyform.net/open-source/self-hosting)。

### 一键部署

<a href="https://railway.app/template/f5vBKm?referralCode=bDs1YJ">
	<img src="https://railway.app/button.svg" alt="在 Railway 上部署" height="36" />
</a>

<a href="https://zeabur.com/templates/9YAUUO" style="margin-left:8px">
	<img src="https://zeabur.com/button.svg" alt="在 Zeabur 上部署" />
</a>

<a href="https://cloud.sealos.io/?openapp=system-template%3FtemplateName%3Dheyform" style="margin-left:16px">
	<img src="https://cdn.jsdelivr.net/gh/labring-actions/templates@main/Deploy-on-Sealos.svg" alt="在 Sealos 上部署" height="36" />
</a>

<a href="https://repocloud.io/details/?app_id=283" style="margin-left:24px">
	<img src="https://d16t0pc4846x52.cloudfront.net/deploylobe.svg" alt="部署到 RepoCloud" height="36" />
</a>

<a href="https://computenest.console.aliyun.com/service/instance/create/cn-hangzhou?type=user&ServiceId=service-a47e56f0ea9f460d8d33" style="margin-left:24px">
	<img src="https://service-info-public.oss-cn-hangzhou.aliyuncs.com/computenest-en.svg" alt="在阿里云上部署" height="36" />
</a>

## 本地开发

请参考 [本地开发指南](https://docs.heyform.net/open-source/local-development) 在本地运行项目。

## 如何贡献

你非常棒，让我们一起打造优秀的软件。前往 [贡献指南](https://docs.heyform.net/open-source/contribute) 开始参与吧。💪

## 支持与社区

你可以在 [帮助中心](https://docs.heyform.net) 找到许多帮助你上手 HeyForm 的资源。如果你在其中找不到所需内容，请随时联系我们：

- 有问题？加入 [Discord 服务器](https://discord.gg/sgT4v4GSTe) 获取即时帮助。
- 发现了 Bug？[提交问题报告](https://github.com/heyform/heyform/issues/new/choose)

## 许可证

HeyForm 采用 GNU Affero 通用公共许可证 v3.0（AGPL-3.0）开源，你可以在 [这里](https://docs.heyform.net/open-source/license) 了解更多关于许可证的信息及其合规要求。