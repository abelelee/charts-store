# Open WebUI 👋

![GitHub 星标数](https://img.shields.io/github/stars/open-webui/open-webui?style=social)
![GitHub 分叉数](https://img.shields.io/github/forks/open-webui/open-webui?style=social)
![GitHub 关注者数](https://img.shields.io/github/watchers/open-webui/open-webui?style=social)
![GitHub 仓库大小](https://img.shields.io/github/repo-size/open-webui/open-webui)
![GitHub 编程语言数量](https://img.shields.io/github/languages/count/open-webui/open-webui)
![GitHub 主要语言](https://img.shields.io/github/languages/top/open-webui/open-webui)
![GitHub 最后提交](https://img.shields.io/github/last-commit/open-webui/open-webui?color=red)
[![Discord](https://img.shields.io/badge/Discord-Open_WebUI-blue?logo=discord&logoColor=white)](https://discord.gg/5rJgQTnV4s)
[![](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/tjbck)

**Open WebUI 是一个可扩展的、功能丰富且用户友好的本地 AI 平台，专为完全离线运行而设计。** 它支持多种 LLM 运行器，如 **Ollama** 和 **兼容 OpenAI 的 API**，并内置用于 RAG 的推理引擎，使其成为一款**强大的 AI 部署解决方案**。

热爱开源 AI？[加入我们的团队 →](https://careers.openwebui.com/)

![Open WebUI 演示](./demo.gif)

> [!TIP]  
> **正在寻找[企业计划](https://docs.openwebui.com/enterprise)？** – **[立即联系我们的销售团队！](mailto:sales@openwebui.com)**
>
> 获取**增强功能**，包括**自定义主题和品牌标识**、**服务等级协议 (SLA) 支持**、**长期支持 (LTS) 版本**以及**更多功能！**

如需更多信息，请务必查看我们的 [Open WebUI 文档](https://docs.openwebui.com/)。

## Open WebUI 的主要功能 ⭐

- 🚀 **轻松安装**：使用 Docker 或 Kubernetes（kubectl、kustomize 或 helm）无缝安装，提供对 `:ollama` 和 `:cuda` 标签镜像的支持，体验无烦恼的部署。

- 🤝 **Ollama/OpenAI API 集成**：轻松集成兼容 OpenAI 的 API，与 Ollama 模型进行多用途对话。自定义 OpenAI API URL 以连接 **LMStudio、GroqCloud、Mistral、OpenRouter 等平台**。

- 🛡️ **细粒度权限和用户组**：管理员可创建详细的用户角色和权限，确保安全的用户环境。这种细粒度控制不仅增强了安全性，还允许定制化的用户体验，增强用户的责任感和归属感。

- 📱 **响应式设计**：在台式机、笔记本电脑和移动设备上享受无缝体验。

- 📱 **适用于移动设备的渐进式 Web 应用 (PWA)**：通过我们的 PWA 在移动设备上获得类似原生应用的体验，提供本地主机上的离线访问和流畅的用户界面。

- ✒️🔢 **完整的 Markdown 和 LaTeX 支持**：通过全面的 Markdown 和 LaTeX 功能提升您的 LLM 体验，实现更丰富的交互。

- 🎤📹 **免提语音/视频通话**：通过集成的免提语音和视频通话功能，实现无缝通信，打造更动态和互动的聊天环境。

- 🛠️ **模型构建器**：通过 Web UI 轻松创建 Ollama 模型。创建并添加自定义角色/代理，自定义聊天元素，并通过 [Open WebUI 社区](https://openwebui.com/) 集成轻松导入模型。

- 🐍 **原生 Python 函数调用工具**：通过工具工作区中的内置代码编辑器支持增强您的 LLM。只需添加您自己的纯 Python 函数即可实现与 LLM 的无缝集成。

- 📚 **本地 RAG 集成**：通过突破性的检索增强生成 (RAG) 支持，进入聊天交互的未来。该功能将文档交互无缝集成到您的聊天体验中。您可以将文档直接加载到聊天中，或将其添加到文档库中，并在查询前使用 `#` 命令轻松访问它们。

- 🔍 **RAG 的网络搜索**：使用 `SearXNG`、`Google PSE`、`Brave Search`、`serpstack`、`serper`、`Serply`、`DuckDuckGo`、`TavilySearch`、`SearchApi` 和 `Bing` 等提供商执行网络搜索，并将结果直接注入到您的聊天体验中。

- 🌐 **网页浏览功能**：使用 `#` 命令后跟 URL，将网站无缝集成到您的聊天体验中。此功能允许您将网页内容直接整合到对话中，增强交互的丰富性和深度。

- 🎨 **图像生成集成**：使用 AUTOMATIC1111 API 或 ComfyUI（本地）以及 OpenAI 的 DALL-E（外部）等选项无缝集成图像生成功能，丰富您的聊天体验。

- ⚙️ **多模型对话**：轻松同时与多种模型交互，利用它们的独特优势获得最佳响应。通过并行使用多种模型提升您的体验。

- 🔐 **基于角色的访问控制 (RBAC)**：通过受限权限确保安全访问；只有授权人员才能访问您的 Ollama，管理员独享模型创建/拉取权限。

- 🌐🌍 **多语言支持**：通过我们的国际化 (i18n) 支持，以您喜欢的语言体验 Open WebUI。加入我们，共同扩展支持的语言！我们正在积极招募贡献者！

- 🧩 **管道和 Open WebUI 插件支持**：使用 [Pipelines 插件框架](https://github.com/open-webui/pipelines) 将自定义逻辑和 Python 库无缝集成到 Open WebUI 中。启动您的 Pipelines 实例，将 OpenAI URL 设置为 Pipelines URL，探索无限可能。[示例](https://github.com/open-webui/pipelines/tree/main/examples) 包括 **函数调用**、用户 **速率限制** 以控制访问、使用 Langfuse 进行 **使用情况监控**、使用 LibreTranslate 进行 **实时翻译** 以支持多语言、**有毒消息过滤** 等等。

- 🌟 **持续更新**：我们致力于定期更新、修复和添加新功能以改进 Open WebUI。

想了解更多 Open WebUI 的功能？请查看我们的 [Open WebUI 文档](https://docs.openwebui.com/features) 以获取全面概述！

## 赞助商 🙌

#### 祖母绿赞助商

<table>
  <tr>
    <td>
      <a href="https://n8n.io/" target="_blank">
        <img src="https://docs.openwebui.com/sponsors/logos/n8n.png" alt="n8n" style="width: 8rem; height: 8rem; border-radius: .75rem;" />
      </a>
    </td>
    <td>
      <a href="https://n8n.io/">n8n</a> • 您的界面有后端了吗？<br>试试 <a href="https://n8n.io/">n8n</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://tailscale.com/blog/self-host-a-local-ai-stack/?utm_source=OpenWebUI&utm_medium=paid-ad-placement&utm_campaign=OpenWebUI-Docs" target="_blank">
        <img src="https://docs.openwebui.com/sponsors/logos/tailscale.png" alt="Tailscale" style="width: 8rem; height: 8rem; border-radius: .75rem;" />
      </a>
    </td>
    <td>
      <a href="https://tailscale.com/blog/self-host-a-local-ai-stack/?utm_source=OpenWebUI&utm_medium=paid-ad-placement&utm_campaign=OpenWebUI-Docs">Tailscale</a> • 使用 Tailscale 将自托管 AI 连接到任何设备
    </td>
  </tr>
</table>

---

我们非常感谢赞助商的慷慨支持。他们的贡献帮助我们维护和改进项目，确保我们能够继续为社区提供高质量的工作。谢谢！

## 如何安装 🚀

### 通过 Python pip 安装 🐍

Open WebUI 可以使用 pip（Python 包安装工具）进行安装。在继续之前，请确保您使用的是 **Python 3.11** 以避免兼容性问题。

1. **安装 Open WebUI**：
   打开终端并运行以下命令以安装 Open WebUI：

   ```bash
   pip install open-webui
   ```

2. **运行 Open WebUI**：
   安装完成后，可以通过执行以下命令启动 Open WebUI：

   ```bash
   open-webui serve
   ```

这将启动 Open WebUI 服务器，您可以通过 [http://localhost:8080](http://localhost:8080) 访问它。

### 使用 Docker 快速启动 🐳

> [!NOTE]  
> 请注意，对于某些 Docker 环境，可能需要额外的配置。如果您遇到任何连接问题，请参考我们的详细指南 [Open WebUI 文档](https://docs.openwebui.com/)。

> [!WARNING]
> 使用 Docker 安装 Open WebUI 时，请确保在 Docker 命令中包含 `-v open-webui:/app/backend/data`。这一步至关重要，因为它确保了数据库正确挂载，防止数据丢失。

> [!TIP]  
> 如果您希望在使用 Open WebUI 时包含 Ollama 或使用 CUDA 加速，我们建议使用官方镜像，其标签为 `:cuda` 或 `:ollama`。要启用 CUDA，您必须在 Linux/WSL 系统上安装 [Nvidia CUDA 容器工具包](https://docs.nvidia.com/dgx/nvidia-container-runtime-upgrade/)。

### 使用默认配置安装

- **如果 Ollama 在您的计算机上**，请使用以下命令：

  ```bash
  docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

- **如果 Ollama 在另一台服务器上**，请使用以下命令：

  要连接到另一台服务器上的 Ollama，请将 `OLLAMA_BASE_URL` 更改为服务器的 URL：

  ```bash
  docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

- **要在支持 Nvidia GPU 的情况下运行 Open WebUI**，请使用以下命令：

  ```bash
  docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:cuda
  ```

### 仅用于 OpenAI API 使用的安装

- **如果您仅使用 OpenAI API**，请使用以下命令：

  ```bash
  docker run -d -p 3000:8080 -e OPENAI_API_KEY=your_secret_key -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

### 安装带有集成 Ollama 支持的 Open WebUI

此安装方法使用一个将 Open WebUI 与 Ollama 打包在一起的容器镜像，允许通过单条命令进行简化设置。根据您的硬件配置选择适当的命令：

- **启用 GPU 支持**：
  运行以下命令以利用 GPU 资源：

  ```bash
  docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
  ```

- **仅使用 CPU**：
  如果您不使用 GPU，请使用以下命令：

  ```bash
  docker run -d -p 3000:8080 -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
  ```

以上两个命令都便于内置、无麻烦地安装 Open WebUI 和 Ollama，确保您可以快速启动并运行。

安装完成后，您可以通过 [http://localhost:3000](http://localhost:3000) 访问 Open WebUI。享受吧！ 😄

### 其他安装方法

我们提供多种安装选项，包括非 Docker 原生安装方法、Docker Compose、Kustomize 和 Helm。请访问我们的 [Open WebUI 文档](https://docs.openwebui.com/getting-started/) 或加入我们的 [Discord 社区](https://discord.gg/5rJgQTnV4s) 以获取全面指导。

有关设置本地开发环境的说明，请参阅 [本地开发指南](https://docs.openwebui.com/getting-started/advanced-topics/development)。

### 故障排除

遇到连接问题？我们的 [Open WebUI 文档](https://docs.openwebui.com/troubleshooting/) 提供了全面帮助。如需进一步协助并加入我们的活跃社区，请访问 [Open WebUI Discord](https://discord.gg/5rJgQTnV4s)。

#### Open WebUI：服务器连接错误

如果您遇到连接问题，通常是因为 WebUI Docker 容器无法在容器内部访问 Ollama 服务器 127.0.0.1:11434（host.docker.internal:11434）。请在 Docker 命令中使用 `--network=host` 标志以解决此问题。请注意，端口从 3000 更改为 8080，因此链接为：`http://localhost:8080`。

**示例 Docker 命令**：

```bash
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

在命令的最后部分，如果容器名称不同，请将 `open-webui` 替换为您的容器名称。

检查我们的更新指南，可在 [Open WebUI 文档](https://docs.openwebui.com/getting-started/updating) 中找到。

### 保持 Docker 安装最新 🌙

> [!WARNING]
> `:dev` 分支包含最新的不稳定功能和更改。使用时需自行承担风险，因为它可能存在错误或未完成的功能。

如果您想尝试最新的前沿功能并接受偶尔的不稳定，可以使用 `:dev` 标签，如下所示：

```bash
docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui --add-host=host.docker.internal:host-gateway --restart always ghcr.io/open-webui/open-webui:dev
```

### 离线模式

如果您在离线环境中运行 Open WebUI，可以将 `HF_HUB_OFFLINE` 环境变量设置为 `1`，以防止尝试从互联网下载模型。

```bash
export HF_HUB_OFFLINE=1
```

## 接下来是什么？ 🌟

在 [Open WebUI 文档](https://docs.openwebui.com/roadmap/) 中查看我们的路线图上的即将功能。

## 许可证 📜

本项目采用 Open WebUI 许可证，这是对 BSD-3-Clause 许可证的修订版本。您将获得与经典 BSD-3 许可证相同的全部权利：您可以使用、修改和分发该软件，包括在专有和商业产品中，限制极少。唯一额外的要求是保留 "Open WebUI" 品牌标识，详细说明请参见 LICENSE 文件。完整条款请参阅 LICENSE 文档。📄

## 支持 💬

如果您有任何问题、建议或需要帮助，请提交 issue 或加入我们的 [Open WebUI Discord 社区](https://discord.gg/5rJgQTnV4s) 与我们联系！🤝

## 星标历史

<a href="https://star-history.com/#open-webui/open-webui&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=open-webui/open-webui&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=open-webui/open-webui&type=Date" />
    <img alt="星标历史图表" src="https://api.star-history.com/svg?repos=open-webui/open-webui&type=Date" />
  </picture>
</a>

---

由 [Timothy Jaeryang Baek](https://github.com/tjbck) 创建 - 让我们一起让 Open WebUI 更加出色！💪