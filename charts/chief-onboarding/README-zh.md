# ChiefOnboarding

[![Tests](https://github.com/chiefonboarding/ChiefOnboarding/actions/workflows/tests.yml/badge.svg)](https://github.com/chiefonboarding/ChiefOnboarding/actions/workflows/tests.yml)
[![Coverage Status](https://coveralls.io/repos/github/chiefonboarding/ChiefOnboarding/badge.svg?branch=master)](https://coveralls.io/github/chiefonboarding/ChiefOnboarding?branch=master)
[![CodeQL](https://github.com/chiefonboarding/ChiefOnboarding/actions/workflows/codeql-analysis.yml/badge.svg)](https://github.com/chiefonboarding/ChiefOnboarding/actions/workflows/codeql-analysis.yml)

ChiefOnboarding 是一个免费且开源的员工入职平台。你可以通过 Slack 或仪表板来完成新员工的入职流程。

![chiefonboarding 时间线概览](docs/static/timeline-overview.png)

文档地址：[https://docs.chiefonboarding.com](https://docs.chiefonboarding.com)

演示视频：[https://www.youtube.com/watch?v=8fYpB8WTH2M](https://www.youtube.com/watch?v=8fYpB8WTH2M)

## 功能特性
- **自动创建用户账户并触发 Webhook**，集成列表请访问 [https://integrations.chiefonboarding.com](https://integrations.chiefonboarding.com)，你也可以创建自己的集成！
- **入职前准备（Pre-boarding）**：入职流程不应从第一天才开始，而应在此之前就启动。你可以创建预入职页面，在新员工正式入职前向他们表示欢迎。
- **待办事项（To do items）**：跟踪新员工需要完成的任务，并允许他们填写表单。
- **资源（Resources）**：让他们在知识库中进行搜索，并完成课程学习，以便快速与同事保持同步。
- **序列（Sequences）**：随时间推移或根据某个待办事项的完成情况逐步推送内容，避免信息过载。
- **徽章（Badges）**：奖励新员工完成的任务，这也有助于激励他们。
- **介绍（Introductions）**：将新员工介绍给团队成员。
- **管理员待办事项（Admin to do items）**：与同事协作完成为新员工准备的工作。
- **多语言支持**：支持英语、荷兰语、葡萄牙语、德语、土耳其语、法语、西班牙语和日语。需要其他语言？请发送邮件至 [hell@chiefonboarding.com](mailto:hell@chiefonboarding.com)！
- **时区支持**：无论新员工身处何地，你都可以为每位新员工单独设置时区，避免他们在深夜收到消息。
- **Slack 机器人和仪表板**：新员工可以使用仪表板或 Slack 机器人，两者功能完全一致，均可独立使用。
- **可定制化**：上传你的公司 Logo、添加配色方案、修改邮件模板，甚至按你的喜好自定义机器人。没有人会知道你使用了 ChiefOnboarding。
- **透明、自由与隐私**：ChiefOnboarding 完全开源，并采用 AGPLv3 协议授权。
- 可以自行在本地基础设施上部署，或者[让我们为你托管](https://chiefonboarding.com/pricing)！

## 部署方式
详细信息请参考[官方文档](https://docs.chiefonboarding.com)。

**Docker**

详情请见：[ChiefOnboarding on Docker Hub](https://hub.docker.com/r/chiefonboarding/chiefonboarding)

**Heroku**

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/chiefonboarding/ChiefOnboarding)

**Render**

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/chiefonboarding/chiefonboarding)

**Elestio**

[![Deploy on Elestio](https://elest.io/images/logos/deploy-to-elestio-btn.png)](https://elest.io/open-source/chiefonboarding)

## 支持
本软件采用开源许可证提供，按“现状”提供使用。如果你有任何问题，请前往 Github 提交 Issue。如果你希望获得快速且有保障的支持，我们提供付费支持服务（尽力而为，通常响应时间在两小时内）。详情请参阅我们的[定价页面](https://chiefonboarding.com/pricing)。

如果你不想处理托管、维护和备份你的 ChiefOnboarding 实例，我们也可以为你完成这些工作。详情请参阅我们的[定价页面](https://chiefonboarding.com/pricing)。

## 安全问题
如发现潜在的安全问题，请不要创建 Issue。请直接发送邮件至 security@chiefonboarding.com，我们将尽快处理。

## 许可证
该项目采用 AGPLv3 许可证，请参阅 LICENSE.md 文件获取详细信息。