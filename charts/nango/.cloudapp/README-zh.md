以下是你提供的Markdown内容的中文翻译，保留了原始格式和结构：

---

<div align="center">

<img src="/assets/nango-logo.png?raw=true" width="350">

</div>

<h1 align="center">一个平台，管理你所有的集成。</h1>

<div align="center">
快速构建集成，同时保持完全控制。
</div>

<p align="center">
    <br />
    <a href="https://docs.nango.dev/" rel="dofollow"><strong>查看文档 »</strong></a>
    <br />

  <br/>
    <a href="https://nango.dev/integrations">400+ 预配置API</a>
    ·
    <a href="https://nango.dev">官网</a>
    ·
    <a href="https://docs.nango.dev/guides/api-authorization/new-api-support">贡献一个API</a>
    ·
    <a href="https://nango.dev/slack">Slack社区</a>
</p>

Nango 是一个统一的 API，用于与所有其他外部 API 进行交互。它应该是你唯一需要集成到应用中的 API。

<img src="/docs-v2/images/overview.png">

# 📺 演示视频

[![what-is-nango](/docs-v2/images/video-thumbnail.png)](https://youtu.be/oTpWlmnv7dM)

# 👩‍💻 示例代码

从前端发起一个新的 OAuth 流程：

```js
nango.openConnectUI();
```

从后端获取来自外部 API 的结构化对象：

```ts
nango.listRecords<GithubIssue>({
    providerConfigKey: 'github',
    connectionId: 'user123',
    model: 'GithubIssue',
});
```

# 👩🏻‍🔧 预建集成与自定义集成

Nango 的灵活性确保它可以支持任何 API 集成：

1. **预建集成**：使用为流行 API 和标准用例预先构建的集成，快速上线。
2. **自定义集成**：通过代码构建你自己的集成，具备无限的定制能力。
3. **托管集成**：利用 Nango 的专家团队为你端到端地创建和维护集成。

# 🔌 400+ 预建 API 与集成，或构建你自己的！

[超过 400 个 API 已预配置](https://nango.dev/integrations)，开箱即用。我们支持 25+ 类别，包括：

- **会计**：Netsuite、Quickbooks、Xero、...
- **通讯**：Slack、Discord、Teams、...
- **客户关系管理（CRM）**：Hubspot、Salesforce、...
- **邮件**：Gmail、Outlook、...
- **人力资源（HR）**：Deel、Gusto、BambooHR、Personio、...
- **身份认证**：Okta、Auth0、...
- **知识库**：Notion、Drive、...
- **工单系统**：Linear、Jira、...
- **客户支持**：Zendesk、...
- **视频会议**：Zoom、Google Meet、...
- 以及[更多类别](https://nango.dev/integrations)

但请记住，Nango 可以与**任何 API 和任何用例**配合使用！

# 🚀 开始使用

免费注册：

<a href="https://app.nango.dev/signup" target="_blank">
  <img src="https://raw.githubusercontent.com/NangoHQ/nango/6f49ab92c0ffc18c1d0f44d9bd96c62ac97aaa8d/docs/static/img/nango-deploy-button.svg" alt="Try Nango Cloud" width="215"/>
</a>

# 🙋‍♀️ 为什么 Nango 是开源的？

我们的使命是让所有 SaaS 应用能够无缝集成。通过开源，每一位工程师都可以为平台贡献改进，造福所有人：

- [贡献一个 API](https://docs.nango.dev/guides/api-authorization/new-api-support)
- [创建一个自定义集成](https://docs.nango.dev/guides/custom-integrations/overview)
- [扩展一个集成模板](https://docs.nango.dev/guides/custom-integrations/extend-a-pre-built-integration)

# 📚 了解更多

- [学习如何集成 Nango](https://docs.nango.dev/integrate/overview)
- [在社区中提问](https://nango.dev/slack)
- [预约演示](https://calendly.com/rguldener/30min)

# 💪 贡献者

感谢你们不断让 Nango 更加完善 ❤️

<a href="https://github.com/nangohq/nango/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=nangohq/nango" />
</a>

# 🐻 历史

Pizzly（一个简单的 OAuth 服务）最初由 [Bearer](https://www.bearer.com/?ref=pizzly) 团队开发，并得到了超过 40 位开发者的贡献。随着时间推移，Bearer 的重心发生了变化，无法再继续维护 Pizzly。2022 年底，[Nango](https://www.nango.dev) 团队接手了该项目，并与不断增长的 Nango 社区一起持续维护和演进它。