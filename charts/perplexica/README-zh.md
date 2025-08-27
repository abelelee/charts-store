# 🚀 Perplexica - 一款由人工智能驱动的搜索引擎 🔎 <!-- omit in toc -->

<div align="center" markdown="1">
   <sup>特别感谢:</sup>
   <br>
   <br>
   <a href="https://www.warp.dev/perplexica">
      <img alt="Warp 赞助" width="400" src="https://github.com/user-attachments/assets/775dd593-9b5f-40f1-bf48-479faff4c27b">
   </a>

### [Warp，一款内嵌于终端的AI开发工具](https://www.warp.dev/perplexica)

[适用于 MacOS, Linux, & Windows](https://www.warp.dev/perplexica)

</div>

<hr/>

[![Discord](https://dcbadge.limes.pink/api/server/26aArMy8tT?style=flat)](https://discord.gg/26aArMy8tT)

![预览](.assets/perplexica-screenshot.png?)

## 目录 <!-- omit in toc -->

- [概述](#概述)
- [预览](#预览)
- [功能](#功能)
- [安装](#安装)
  - [使用 Docker 快速开始（推荐）](#使用-docker-快速开始推荐)
  - [非 Docker 安装](#非-docker-安装)
  - [Ollama 连接错误](#ollama-连接错误)
- [作为搜索引擎使用](#作为搜索引擎使用)
- [使用 Perplexica 的 API](#使用-perplexica-的-api)
- [将 Perplexica 暴露给网络](#将-perplexica-暴露给网络)
- [一键部署](#一键部署)
- [即将推出的功能](#即将推出的功能)
- [支持我们](#支持我们)
  - [捐赠](#捐赠)
- [贡献](#贡献)
- [帮助与支持](#帮助与支持)

## 概述

Perplexica 是一个开源的、由 AI 驱动的搜索工具或搜索引擎，它深入互联网以寻找答案。受 Perplexity AI 启发，它是一个开源替代方案，不仅搜索网络，还理解你的问题。它使用先进的机器学习算法（如相似性搜索和嵌入）来优化结果，并提供带有引用来源的清晰答案。

通过使用 SearxNG 保持最新和完全开源，Perplexica 确保你始终获得最新的信息，同时不损害你的隐私。

想了解更多关于其架构和工作原理的信息？你可以在这里阅读 [文档](https://github.com/ItzCrazyKns/Perplexica/tree/master/docs/architecture/README.md)。

## 预览

![视频预览](.assets/perplexica-preview.gif)

## 功能

- **本地 LLMs**：你可以使用 Ollama 来运行本地 LLMs，例如 Llama3 和 Mixtral。
- **两种主要模式：**
  - **助手模式：**（开发中）通过生成不同的查询来增强搜索，找到更相关的互联网资源。不同于仅使用 SearxNG 上下文的普通搜索，它会访问排名靠前的结果，并尝试直接从页面中找到与用户查询相关的资源。
  - **普通模式：** 处理你的查询并执行网页搜索。
- **聚焦模式：** 用于更好地回答特定类型问题的特殊模式。Perplexica 当前有 6 种聚焦模式：
  - **全部模式：** 搜索整个网络以找到最佳结果。
  - **写作助手模式：** 适用于不需要网络搜索的写作任务。
  - **学术搜索模式：** 寻找文章和论文，适合学术研究。
  - **YouTube 搜索模式：** 根据搜索查询查找 YouTube 视频。
  - **Wolfram Alpha 搜索模式：** 使用 Wolfram Alpha 回答需要计算或数据分析的查询。
  - **Reddit 搜索模式：** 搜索 Reddit 上与查询相关的讨论和观点。
- **最新信息：** 一些搜索工具可能会给你过时的信息，因为它们使用的是爬虫机器人抓取的数据，并将其转换为嵌入后存储在索引中。与它们不同，Perplexica 使用 SearxNG 这个元搜索引擎来获取结果并重新排序，以确保你始终获得最新的信息，而无需每天更新数据。
- **API**：将 Perplexica 集成到你现有的应用程序中，充分利用其功能。

它还有许多其他功能，如图像和视频搜索。一些计划中的功能详见 [即将推出的功能](#即将推出的功能)。

## 安装

安装 Perplexica 主要有两种方式：使用 Docker 或不使用 Docker。推荐使用 Docker。

### 使用 Docker 快速开始（推荐）

1. 确保你的系统上已安装并运行 Docker。
2. 克隆 Perplexica 仓库：

   ```bash
   git clone https://github.com/ItzCrazyKns/Perplexica.git
   ```

3. 克隆完成后，进入包含项目文件的目录。

4. 将 `sample.config.toml` 文件重命名为 `config.toml`。对于 Docker 安装，你只需填写以下字段：

   - `OPENAI`：你的 OpenAI API 密钥。**只有在你想使用 OpenAI 模型时才需要填写。**
   - `OLLAMA`：你的 Ollama API 地址。你应该填写为 `http://host.docker.internal:PORT_NUMBER`。如果你在端口 11434 上安装了 Ollama，请使用 `http://host.docker.internal:11434`。如果使用其他端口，请相应调整。**只有在你想使用 Ollama 模型而不是 OpenAI 模型时才需要填写。**
   - `GROQ`：你的 Groq API 密钥。**只有在你想使用 Groq 托管的模型时才需要填写。**
   - `ANTHROPIC`：你的 Anthropic API 密钥。**只有在你想使用 Anthropic 模型时才需要填写。**
   - `Gemini`：你的 Gemini API 密钥。**只有在你想使用 Google 的模型时才需要填写。**
   - `DEEPSEEK`：你的 Deepseek API 密钥。**只有在你想使用 Deepseek 模型时才需要填写。**
   - `AIMLAPI`：你的 AI/ML API 密钥。**只有在你想使用 AI/ML API 模型和嵌入时才需要填写。**

     **注意**：你可以在启动 Perplexica 后通过设置对话框更改这些字段。

   - `SIMILARITY_MEASURE`：使用的相似性度量（默认已填写；如果你不确定，可以保持默认值。）

5. 确保你位于包含 `docker-compose.yaml` 文件的目录中，然后执行：

   ```bash
   docker compose up -d
   ```

6. 等待几分钟以完成安装。你可以在浏览器中访问 http://localhost:3000 来使用 Perplexica。

**注意**：容器构建完成后，你可以直接从 Docker 启动 Perplexica，而无需打开终端。

### 非 Docker 安装

1. 安装 SearXNG 并在 SearXNG 设置中启用 `JSON` 格式。
2. 克隆仓库并将 `sample.config.toml` 文件重命名为 `config.toml` 放在根目录中。确保填写该文件中的所有必填字段。
3. 填写配置后运行 `npm i`。
4. 安装依赖项后执行 `npm run build`。
5. 最后通过运行 `npm run start` 启动应用。

**注意**：推荐使用 Docker，因为它简化了设置过程，尤其是在管理环境变量和依赖项方面。

有关更多信息（如更新等），请参阅 [安装文档](https://github.com/ItzCrazyKns/Perplexica/tree/master/docs/installation)。

### Ollama 连接错误

如果你遇到 Ollama 连接错误，可能是由于后端无法连接到 Ollama 的 API。要解决此问题，你可以：

1. **检查你的 Ollama API 地址：** 确保在设置菜单中正确设置了 API 地址。
2. **根据操作系统更新 API 地址：**

   - **Windows：** 使用 `http://host.docker.internal:11434`
   - **Mac：** 使用 `http://host.docker.internal:11434`
   - **Linux：** 使用 `http://<主机私有IP>:11434`

   如果你使用了不同的端口，请相应调整。

3. **Linux 用户 - 将 Ollama 暴露给网络：**

   - 在 `/etc/systemd/system/ollama.service` 文件中，你需要添加 `Environment="OLLAMA_HOST=0.0.0.0:11434"`。（如果你使用了不同的端口，请相应更改。）然后使用 `systemctl daemon-reload` 重新加载 systemd 管理器配置，并通过 `systemctl restart ollama` 重启 Ollama。更多信息请参阅 [Ollama 文档](https://github.com/ollama/ollama/blob/main/docs/faq.md#setting-environment-variables-on-linux)

   - 确保端口（默认为 11434）未被你的防火墙阻止。

## 作为搜索引擎使用

如果你想将 Perplexica 用作传统搜索引擎（如 Google 或 Bing）的替代品，或者希望从浏览器搜索栏中快速访问它，请按照以下步骤操作：

1. 打开浏览器设置。
2. 导航到“搜索引擎”部分。
3. 添加一个新的站点搜索，使用以下 URL：`http://localhost:3000/?q=%s`。如果 Perplexica 不是本地运行的，请将 `localhost` 替换为你的 IP 地址或域名，并将 `3000` 替换为相应的端口号。
4. 点击添加按钮。现在，你可以直接从浏览器搜索栏使用 Perplexica。

## 使用 Perplexica 的 API

Perplexica 还为希望将其强大的搜索引擎集成到自己应用程序中的开发者提供了 API。你可以运行搜索、使用多个模型并获取查询的答案。

更多详情，请查看完整文档 [这里](https://github.com/ItzCrazyKns/Perplexica/tree/master/docs/API/SEARCH.md)。

## 将 Perplexica 暴露给网络

Perplexica 基于 Next.js 构建，处理所有 API 请求。它在同一网络中立即可用，并且即使使用端口转发也保持可访问。

## 一键部署

[![部署到 Sealos](https://raw.githubusercontent.com/labring-actions/templates/main/Deploy-on-Sealos.svg)](https://usw.sealos.io/?openapp=system-template%3FtemplateName%3Dperplexica)
[![部署到 RepoCloud](https://d16t0pc4846x52.cloudfront.net/deploylobe.svg)](https://repocloud.io/details/?app_id=267)
[![在 ClawCloud 上运行](https://raw.githubusercontent.com/ClawCloud/Run-Template/refs/heads/main/Run-on-ClawCloud.svg)](https://template.run.claw.cloud/?referralCode=U11MRQ8U9RM4&openapp=system-fastdeploy%3FtemplateName%3Dperplexica)

## 即将推出的功能

- [x] 添加设置页面
- [x] 添加对本地 LLMs 的支持
- [x] 历史记录保存功能
- [x] 引入各种聚焦模式
- [x] 添加 API 支持
- [x] 添加发现功能
- [ ] 完成助手模式

## 支持我们

如果你觉得 Perplexica 有用，请在 GitHub 上给我们一个星标。这有助于更多人发现 Perplexica，并支持新功能的开发。我们非常感谢你的支持。

### 捐赠

我们也接受捐赠以帮助维持我们的项目。如果你想贡献，请使用以下选项进行捐赠。感谢你的支持！

| 以太坊                                              |
| ----------------------------------------------------- |
| 地址: `0xB025a84b2F269570Eb8D4b05DEdaA41D8525B6DD` |

## 贡献

Perplexica 建立在 AI 和大型语言模型应易于所有人使用的理念之上。如果你发现了 bug 或有想法，请通过 GitHub Issues 与我们分享。有关如何为 Perplexica 做出贡献的更多信息，请阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 文件。

## 帮助与支持

如果你有任何问题或反馈，请随时与我们联系。你可以在 GitHub 上创建一个问题，或加入我们的 Discord 服务器。在那里，你可以与其他用户交流，分享你的体验和评价，并获得更个性化的帮助。[点击此处](https://discord.gg/EFwsmQDgAu) 加入 Discord 服务器。如需讨论常规支持之外的问题，欢迎通过 Discord 联系我，我的用户名是 `itzcrazykns`。

感谢你探索 Perplexica，这款由人工智能驱动的搜索引擎，旨在提升你的搜索体验。我们一直在努力改进 Perplexica 并扩展其功能。我们非常重视你的反馈和贡献，这些帮助我们使 Perplexica 更加完善。别忘了定期查看更新和新功能！