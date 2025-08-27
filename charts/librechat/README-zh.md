<p align="center">
  <a href="https://librechat.ai">
    <img src="client/public/assets/logo.svg" height="256">
  </a>
  <h1 align="center">
    <a href="https://librechat.ai">LibreChat</a>
  </h1>
</p>

<p align="center">
  <a href="https://discord.librechat.ai"> 
    <img
      src="https://img.shields.io/discord/1086345563026489514?label=&logo=discord&style=for-the-badge&logoWidth=20&logoColor=white&labelColor=000000&color=blueviolet">
  </a>
  <a href="https://www.youtube.com/@LibreChat"> 
    <img
      src="https://img.shields.io/badge/YOUTUBE-red.svg?style=for-the-badge&logo=youtube&logoColor=white&labelColor=000000&logoWidth=20">
  </a>
  <a href="https://docs.librechat.ai"> 
    <img
      src="https://img.shields.io/badge/DOCS-blue.svg?style=for-the-badge&logo=read-the-docs&logoColor=white&labelColor=000000&logoWidth=20">
  </a>
  <a aria-label="Sponsors" href="https://github.com/sponsors/danny-avila">
    <img
      src="https://img.shields.io/badge/SPONSORS-brightgreen.svg?style=for-the-badge&logo=github-sponsors&logoColor=white&labelColor=000000&logoWidth=20">
  </a>
</p>

<p align="center">
<a href="https://railway.app/template/b5k2mn?referralCode=HI9hWz">
  <img src="https://railway.app/button.svg" alt="Deploy on Railway" height="30">
</a>
<a href="https://zeabur.com/templates/0X2ZY8">
  <img src="https://zeabur.com/button.svg" alt="Deploy on Zeabur" height="30"/>
</a>
<a href="https://template.cloud.sealos.io/deploy?templateName=librechat">
  <img src="https://raw.githubusercontent.com/labring-actions/templates/main/Deploy-on-Sealos.svg" alt="Deploy on Sealos" height="30">
</a>
</p>

<p align="center">
  <a href="https://www.librechat.ai/docs/translation">
    <img 
      src="https://img.shields.io/badge/dynamic/json.svg?style=for-the-badge&color=2096F3&label=locize&query=%24.translatedPercentage&url=https://api.locize.app/badgedata/4cb2598b-ed4d-469c-9b04-2ed531a8cb45&suffix=%+translated" 
      alt="Translation Progress">
  </a>
</p>

# ✨ 功能

- 🖥️ **UI 与体验**：灵感来自 ChatGPT，具有增强的设计和功能

- 🤖 **AI 模型选择**：  
  - Anthropic (Claude)、AWS Bedrock、OpenAI、Azure OpenAI、Google、Vertex AI、OpenAI Responses API（包括 Azure）
  - [自定义端点](https://www.librechat.ai/docs/quick_start/custom_endpoints)：使用任何与 OpenAI 兼容的 API，无需代理
  - 兼容 [本地和远程 AI 提供商](https://www.librechat.ai/docs/configuration/librechat_yaml/ai_endpoints)：
    - Ollama、groq、Cohere、Mistral AI、Apple MLX、koboldcpp、together.ai、
    - OpenRouter、Perplexity、ShuttleAI、Deepseek、Qwen 等

- 🔧 **[代码解释器 API](https://www.librechat.ai/docs/features/code_interpreter)**： 
  - 安全的沙盒执行环境，支持 Python、Node.js（JS/TS）、Go、C/C++、Java、PHP、Rust 和 Fortran
  - 无缝文件处理：直接上传、处理和下载文件
  - 无隐私问题：完全隔离和安全的执行环境

- 🔦 **代理与工具集成**：  
  - **[LibreChat 代理](https://www.librechat.ai/docs/features/agents)**：
    - 无需编码的定制助手：构建专业的 AI 驱动助手
    - 灵活可扩展：使用 MCP 服务器、工具、文件搜索、代码执行等
    - 兼容自定义端点、OpenAI、Azure、Anthropic、AWS Bedrock、Google、Vertex AI、Responses API 等
    - 支持 [模型上下文协议 (MCP)](https://modelcontextprotocol.io/clients#librechat) 工具

- 🔍 **网络搜索**：  
  - 搜索互联网并获取相关信息以增强 AI 上下文
  - 结合搜索提供商、内容抓取器和结果重排序器以获得最佳结果
  - **[了解更多 →](https://www.librechat.ai/docs/features/web_search)**

- 🪄 **带代码工件的生成式 UI**：  
  - [代码工件](https://youtu.be/GfTj7O4gmd0?si=WJbdnemZpJzBrJo3) 允许在聊天中直接创建 React、HTML 和 Mermaid 图表

- 🎨 **图像生成与编辑**
  - 使用 [GPT-Image-1](https://www.librechat.ai/docs/features/image_gen#1--openai-image-tools-recommended) 进行文本到图像和图像到图像
  - 使用 [DALL-E (3/2)](https://www.librechat.ai/docs/features/image_gen#2--dalle-legacy)、[Stable Diffusion](https://www.librechat.ai/docs/features/image_gen#3--stable-diffusion-local)、[Flux](https://www.librechat.ai/docs/features/image_gen#4--flux) 或任何 [MCP 服务器](https://www.librechat.ai/docs/features/image_gen#5--model-context-protocol-mcp) 进行文本到图像
  - 从提示生成精美视觉效果或通过单条指令优化现有图像

- 💾 **预设与上下文管理**：  
  - 创建、保存和共享自定义预设
  - 在聊天过程中切换 AI 端点和预设
  - 编辑、重新提交和继续消息并支持对话分支
  - 使用 [消息与对话分叉](https://www.librechat.ai/docs/features/fork) 进行高级上下文控制

- 💬 **多模态与文件交互**：  
  - 使用 Claude 3、GPT-4.5、GPT-4o、o1、Llama-Vision 和 Gemini 上传并分析图像 📸  
  - 使用自定义端点、OpenAI、Azure、Anthropic、AWS Bedrock 和 Google 进行文件聊天 🗃️

- 🌎 **多语言 UI**：  
  - 英语、中文、德语、西班牙语、法语、意大利语、波兰语、巴西葡萄牙语
  - 俄语、日语、瑞典语、韩语、越南语、繁体中文、阿拉伯语、土耳其语、荷兰语、希伯来语

- 🧠 **推理 UI**：  
  - 为像 DeepSeek-R1 这样的 Chain-of-Thought/Reasoning AI 模型提供动态推理 UI

- 🎨 **可定制界面**：  
  - 可定制的下拉菜单和界面，适应高级用户和新用户

- 🗣️ **语音与音频**：  
  - 使用语音转文本和文本转语音进行免手聊天
  - 自动发送和播放音频
  - 支持 OpenAI、Azure OpenAI 和 Elevenlabs

- 📥 **导入与导出对话**：  
  - 从 LibreChat、ChatGPT、Chatbot UI 导入对话
  - 将对话导出为截图、Markdown、文本、JSON

- 🔍 **搜索与发现**：  
  - 搜索所有消息/对话

- 👥 **多用户与安全访问**：
  - 多用户、安全的身份验证，支持 OAuth2、LDAP 和邮箱登录
  - 内置审核和令牌花费工具

- ⚙️ **配置与部署**：  
  - 配置代理、反向代理、Docker 和多种部署选项
  - 可完全本地使用或部署在云端

- 📖 **开源与社区**：  
  - 完全开源并在公开环境中构建
  - 社区驱动的开发、支持和反馈

[如需详细了解我们的功能，请参阅我们的文档](https://docs.librechat.ai/) 📚

## 🪶 使用 LibreChat 进行一站式 AI 对话

LibreChat 将助手 AI 的未来与 OpenAI ChatGPT 的革命性技术结合在一起。继承原始风格，LibreChat 让您能够集成多个 AI 模型。它还集成了原始客户端功能并加以增强，例如对话和消息搜索、提示模板和插件。

使用 LibreChat，您不再需要选择 ChatGPT Plus，而是可以使用免费或按调用付费的 API。我们欢迎贡献、克隆和分叉，以增强这一先进聊天平台的能力。

[![观看视频](https://raw.githubusercontent.com/LibreChat-AI/librechat.ai/main/public/images/changelog/v0.7.6.gif)](https://www.youtube.com/watch?v=ilfwGQtJNlI)

点击缩略图打开视频☝️

---

## 🌐 资源

**GitHub 仓库：**
  - **RAG API：** [github.com/danny-avila/rag_api](https://github.com/danny-avila/rag_api)
  - **网站：** [github.com/LibreChat-AI/librechat.ai](https://github.com/LibreChat-AI/librechat.ai)

**其他：**
  - **网站：** [librechat.ai](https://librechat.ai)
  - **文档：** [librechat.ai/docs](https://librechat.ai/docs)
  - **博客：** [librechat.ai/blog](https://librechat.ai/blog)

---

## 📝 更新日志

通过访问发布页面和更新说明了解最新更新：
- [发布版本](https://github.com/danny-avila/LibreChat/releases)
- [更新日志](https://www.librechat.ai/changelog) 

**⚠️ 更新前请务必查阅 [更新日志](https://www.librechat.ai/changelog) 以了解重大变更。**

---

## ⭐ 星标历史

<p align="center">
  <a href="https://star-history.com/#danny-avila/LibreChat&Date">
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=danny-avila/LibreChat&type=Date&theme=dark" onerror="this.src='https://api.star-history.com/svg?repos=danny-avila/LibreChat&type=Date'" />
  </a>
</p>
<p align="center">
  <a href="https://trendshift.io/repositories/4685" target="_blank" style="padding: 10px;">
    <img src="https://trendshift.io/api/badge/repositories/4685" alt="danny-avila%2FLibreChat | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/>
  </a>
  <a href="https://runacap.com/ross-index/q1-24/" target="_blank" rel="noopener" style="margin-left: 20px;">
    <img style="width: 260px; height: 56px" src="https://runacap.com/wp-content/uploads/2024/04/ROSS_badge_white_Q1_2024.svg" alt="ROSS Index - 2024 年第一季度增长最快的开源初创公司 | Runa Capital" width="260" height="56"/>
  </a>
</p>

---

## ✨ 贡献

欢迎贡献、建议、报告问题和修复！

对于新功能、组件或扩展，请先创建问题并讨论，然后再提交 PR。

如果您希望帮助将 LibreChat 翻译成您的语言，我们非常欢迎您的贡献！改进我们的翻译不仅能让全球用户更容易使用 LibreChat，还能提升整体用户体验。请查看我们的 [翻译指南](https://www.librechat.ai/docs/translation)。

---

## 💖 感谢所有贡献者

本项目目前的状态得益于所有贡献者。

<a href="https://github.com/danny-avila/LibreChat/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=danny-avila/LibreChat" />
</a>

---

## 🎉 特别感谢

我们感谢 [Locize](https://locize.com) 提供翻译管理工具，支持 LibreChat 的多语言功能。

<p align="center">
  <a href="https://locize.com" target="_blank" rel="noopener noreferrer">
    <img src="https://github.com/user-attachments/assets/d6b70894-6064-475e-bb65-92a9e23e0077" alt="Locize Logo" height="50">
  </a>
</p>