---
<h1 align="center">⚡Dialoqbase ⚡</h1>
<p align="center">
 轻松创建聊天机器人
</p>

<div align="center">

  [![加入 Dialoqbase #welcome 频道](https://img.shields.io/badge/discord-join%20chat-blue.svg)](https://discord.gg/SPE3npH7Wu)
  [![构建状态](https://github.com/n4ze3m/dialoqbase/actions/workflows/build.yml/badge.svg)](https://github.com/n4ze3m/dialoqbase/actions/workflows/build.yml)
  [![许可证: MIT](https://img.shields.io/github/license/n4ze3m/dialoqbase)](https://github.com/n4ze3m/dialoqbase/blob/master/LICENSE)

</div>

Dialoqbase 是一个开源应用程序，旨在通过使用自定义知识库轻松创建专属聊天机器人。该应用程序利用先进的语言模型来生成准确且上下文感知的回复。此外，它还使用 PostgreSQL —— 一个强大的关系型数据库管理系统，以实现高效的向量搜索和知识库存储。

以下是其工作方式的演示（v0.0.23）：

<div align="center">

[![DialoqBase 演示](https://img.youtube.com/vi/D3X3ZIYsT_w/0.jpg)](https://www.youtube.com/watch?v=D3X3ZIYsT_w)

</div>

想查看更多演示视频？请在 [Twitter](https://twitter.com/n4ze3m) 或 [BlueSky](https://bsky.app/profile/n4ze3m.com) 上关注我以获取更多更新。

## 快速部署 🚀

### Railway（一键部署）

[![部署到 Railway](https://railway.app/button.svg)](https://railway.app/template/TXdjD7?referralCode=olbszX)

## 安装 🛠️

1. 克隆仓库并进入 docker 目录：

```bash
git clone https://github.com/n4ze3m/dialoqbase.git
cd dialoqbase/docker
```

2. 编辑 `.env` 文件 <!--(更多详情请参阅 环境变量 部分)-->:

- 在 Linux 上：

```bash
nano .env
```

或

```bash
vim .env
```

- 在 Windows 上：

```bash
notepad .env
```

设置 `DB_SECRET_KEY` 变量。

3. 运行 docker-compose 文件：

```bash
docker-compose up -d
```

或

```bash
docker compose up -d
```

4. 打开浏览器并访问 `http://localhost:3000`。
5. 使用默认凭据登录：

```bash
用户名: admin
密码: admin
```

_重要提示：首次登录后，请记得更改默认凭据。_

## 功能 🚀

- 使用自己的知识库创建自定义聊天机器人
- 利用强大的语言模型生成回复
- 使用 PostgreSQL 进行向量搜索和知识库存储
- 可使用任意语言模型或嵌入模型

## 技术栈 📚

- [React](https://reactjs.org/)
- [Ant Design](https://ant.design/)
- [Node.js](https://nodejs.org/)
- [Fastify](https://www.fastify.io/)
- [LangChain](https://langchain.com/)
- [PostgreSQL](https://www.postgresql.org/)
- [Redis](https://redis.io/)
- [Rspack](https://rspack.dev)
- [@waylaidwanderer/fastify-sse-v2](https://github.com/waylaidwanderer/fastify-sse-v2)（服务器发送事件）

## 免责声明 ⚠️

Dialoqbase 是一个个人项目，尚未准备好用于生产环境。它仍处于早期开发阶段，可能存在 bug 和安全问题。请自行承担使用风险。_可能会随时发生破坏性变更，且不会提前通知。_

## 路线图 🗺️

### 数据加载器

| 加载器 | 状态 |
| ----------- |  ------ |
| 网站 | ✅ |
| 纯文本 |  ✅ |
| PDF |  ✅ |
| 网络爬虫 |  ✅ |
| Microsoft Word 文档 |  ✅ |
| Github 仓库 | ✅ |
| mp3 | ✅ |
| mp4 |  ✅ |
| 站点地图 |  ✅ |
| YouTube | ✅ |
| Notion |  ❌ |

### 语言模型

| 提供商 | 模型 |
| ----------- | ----------- |
| OpenAI | gpt-3.5-turbo, gpt-3.5-turbo-16k, gpt-4, gpt-4-0613, gpt-3.5-instruct, gpt-3.5-turbo-1106, gpt-4-1106-preview |
| Anthropic | Claude 1, Claude 2 |
| Google | chat-bison-001, Gemini |
| Fireworks | Llama 2, Mistral, Mixtral 等 |
| 本地 AI | 本地 AI 模型 |
| Ollama | 所有 Ollama 支持的模型 |

### 嵌入模型

| 提供商 | 模型 | 状态 |
| ----------- | ----------- | ------ |
| OpenAI | text-embedding-ada-002 | ✅ |
| TensorFlow | universal-sentence-encoder | ❌ |
| Hugging Face | distilbert-base-uncased | ✅ |
| Cohere | Embed | ✅ |
| Huggingface Transformers.js | all-MiniLM-L6-v2 | ✅ |
| Ollama | Ollama 嵌入模型 | ✅ |
| Google | text-gecko-001, embedding-001 | ✅ |
| Jina | Jina 嵌入模型 | ✅ |

需要更多支持？请提交一个 issue...

### 集成

| 类型 | 阶段 | 状态 |
| ----------- | ----------- | ------ |
| 网页嵌入脚本 | 稳定 | ✅ |
| Telegram | Beta 版 | ✅ |
| Discord | Beta 版 | ✅ |
| Slack | 开发中 | ❌ |
| Whatsapp | 实验性 | ✅ |

需要更多支持？请提交一个 issue...

本项目通过 BrowserStack 进行测试。

## 贡献者 ✨

<a href="https://github.com/n4ze3m/dialoqbase/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=n4ze3m/dialoqbase" />
</a>

有兴趣贡献？请查看 贡献指南。

## 赞助商 💖

Dialoqbase 的发展离不开我们优秀赞助商的支持。如果您有兴趣成为赞助商，请访问 [赞助页面](https://github.com/sponsors/n4ze3m)。

### 优秀赞助商

<a href="https://github.com/mjtechguy" target="_blank"><img src="https://avatars.githubusercontent.com/u/29070994?s=64&v=4"></a>
<a href="https://github.com/senavi888" target="_blank"><img src="https://avatars.githubusercontent.com/u/161348858?s=64&v=4"></a>
<a href="https://github.com/FarazPatankar" target="_blank"><img src="https://avatars.githubusercontent.com/u/10681116?s=64&v=4"></a>

以及来自 [Ko-fi](https://ko-fi.com/n4ze3m) 的众多优秀支持者。

## 许可证 📝

MIT