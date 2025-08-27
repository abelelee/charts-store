---
![SerpBear](https://i.imgur.com/0S2zIH3.png)

# SerpBear

![Codacy Badge](https://app.codacy.com/project/badge/Grade/7e7a0030c3f84c6fb56a3ce6273fbc1d) ![GitHub](https://img.shields.io/github/license/towfiqi/serpbear) ![GitHub package.json version](https://img.shields.io/github/package-json/v/towfiqi/serpbear) ![Docker Pulls](https://img.shields.io/docker/pulls/towfiqi/serpbear) [![StandWithPalestine](https://raw.githubusercontent.com/Safouene1/support-palestine-banner/master/StandWithPalestine.svg)](https://www.youtube.com/watch?v=bjtDsd0g468&rco=1)

#### [文档](https://docs.serpbear.com/) | [更新日志](https://github.com/towfiqi/serpbear/blob/main/CHANGELOG.md) | [Docker 镜像](https://hub.docker.com/r/towfiqi/serpbear)

SerpBear 是一个开源的搜索引擎排名追踪和关键词研究应用。它可以帮助你追踪你的网站在 Google 中的关键词排名，并在排名发生变化时通知你。

![易于使用的搜索引擎排名追踪器](https://serpbear.b-cdn.net/serpbear_readme_v2.gif)

#### 功能

- **无限关键词：** 可添加无限数量的域名和关键词以追踪其 SERP 排名。
- **邮件通知：** 每日/每周/每月通过电子邮件接收关键词排名变化的通知。
- **SERP API：** SerpBear 自带内置 API，可用于你的营销和数据报告工具。
- **关键词研究：** 通过集成你的 Google Ads 测试账户，能够研究关键词并自动从你追踪网站的内容中生成关键词建议。
- **Google Search Console 集成：** 获取每个关键词的实际访问量、展示次数等数据。
- **移动应用：** 将 PWA 应用添加到你的手机，以获得更好的移动体验。
- **零运行成本：** 可以在 mogenius.com 或 Fly.io 上免费运行该应用。

#### 工作原理

该应用使用第三方网站爬虫服务，如 ScrapingAnt、ScrapingRobot、SearchApi、SerpApi、HasData 或你自己提供的代理 IP，来爬取 Google 的搜索结果，以查看你的域名是否出现在特定关键词的搜索结果中。

关键词研究和关键词生成功能通过将你的 Google Ads 测试账户集成到 SerpBear 中来实现。一旦你[集成 Google Ads](https://docs.serpbear.com/miscellaneous/integrate-google-ads)，就可以查看所添加关键词的每月搜索量数据。

当你[集成 Google Search Console](https://docs.serpbear.com/miscellaneous/integrate-google-search-console) 后，应用会显示每个被追踪关键词的实际搜索访问量。你还可以发现新的关键词，并找出表现最好的关键词、国家和页面。你将能够查看这些关键词通过 Google 搜索带来的实际访问量。

#### 快速开始

- **步骤 1：** 部署并运行该应用。
- **步骤 2：** 访问你的应用并登录。
- **步骤 3：** 添加你的第一个域名。
- **步骤 4：** 从 ScrapingRobot 获取一个免费的 API 密钥，或者选择一个付费提供商（见下文）。如果你想使用代理 IP，可以跳过此步骤。
- **步骤 5：** 从应用的设置界面配置爬虫 API/代理。
- **步骤 6：** 添加你的关键词并开始追踪。
- **步骤 7（可选）：** 在设置面板中配置 SMTP 信息，以便通过电子邮件接收关键词排名变化的通知。你可以使用 ElasticEmail 和 Sendpulse 提供的免费 SMTP 服务。

#### SerpBear 集成的主流 SERP 爬虫服务

如果你不想使用代理服务器，可以使用以下第三方爬虫服务来爬取 Google 搜索结果。

| 服务名称           | 成本          | SERP 查询次数    | 是否支持 API |
| ------------------ | ------------- | ---------------- | ------------ |
| scrapingrobot.com  | 免费          | 5000/月          | 是          |
| serply.io          | 49美元/月     | 5000/月          | 是          |
| serpapi.com        | 从 50美元/月 起 | 从 5000/月 起    | 是          |
| spaceserp.com      | 一次性 59美元 | 15000/月          | 是          |
| SearchApi.io       | 从 40美元/月 起 | 从 10000/月 起   | 是          |
| valueserp.com      | 按需付费       | 2.5美元/1000 请求 | 否          |
| serper.dev         | 按需付费       | 1美元/1000 请求   | 否          |
| hasdata.com        | 从 29美元/月 起 | 从 10000/月 起   | 是          |

**技术栈**

- 前端与后端使用 Next.js。
- 数据库使用 Sqlite。