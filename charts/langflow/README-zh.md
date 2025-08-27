---
    <!-- markdownlint-disable MD030 -->

![Langflow logo](./docs/static/img/langflow-logo-color-black-solid.svg)


[![版本发布](https://img.shields.io/github/release/langflow-ai/langflow?style=flat-square)](https://github.com/langflow-ai/langflow/releases)
[![PyPI - 许可证](https://img.shields.io/badge/license-MIT-orange)](https://opensource.org/licenses/MIT)
[![PyPI - 下载量](https://img.shields.io/pypi/dm/langflow?style=flat-square)](https://pypistats.org/packages/langflow)
[![GitHub 星标数](https://img.shields.io/github/stars/langflow-ai/langflow?style=flat-square)](https://star-history.com/#langflow-ai/langflow)
[![问题数](https://img.shields.io/github/issues-raw/langflow-ai/langflow?style=flat-square)](https://github.com/langflow-ai/langflow/issues)
[![Twitter](https://img.shields.io/twitter/url/https/twitter.com/langflow-ai.svg?style=social&label=关注%40Langflow)](https://twitter.com/langflow_ai)
[![YouTube 频道](https://img.shields.io/youtube/channel/subscribers/UCn2bInQrjdDYKEEmbpwblLQ?label=订阅)](https://www.youtube.com/@Langflow)
[![Discord 服务器](https://img.shields.io/discord/1116803230643527710?logo=discord&style=social&label=加入)](https://discord.gg/EqksyE2EX9)
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/langflow-ai/langflow)

> [!CAUTION]
> 用户必须升级到 Langflow >= 1.3 以防止 [CVE-2025-3248](https://nvd.nist.gov/vuln/detail/CVE-2025-3248)。

[Langflow](https://langflow.org) 是一个用于构建和部署 AI 代理及工作流的强大工具。它为开发者提供了可视化编辑体验，以及内置的 API 和 MCP 服务器功能，使每个工作流都能成为可集成到基于任何框架或技术栈的应用程序中的工具。Langflow 预置了丰富的功能，支持所有主流大语言模型（LLM）、向量数据库以及不断扩展的 AI 工具库。

## ✨ 主要特性

- **可视化构建界面**，快速上手并迭代开发。
- **源代码访问**，允许使用 Python 自定义任何组件。
- **交互式测试环境**，可即时测试和优化流程，并支持逐步控制。
- **多代理编排**，支持对话管理和检索。
- **作为 API 部署**，或导出为 JSON 用于 Python 应用。
- **作为 MCP 服务器部署**，将你的流程转化为 MCP 客户端可用的工具。
- **可观测性**，支持 LangSmith、LangFuse 等集成。
- **企业级**安全性和可扩展性。

## ⚡️ 快速开始

Langflow 需要 [Python 3.10 到 3.13](https://www.python.org/downloads/release/python-3100/) 和 [uv](https://docs.astral.sh/uv/getting-started/installation/)。

1. 安装 Langflow：

```shell
uv pip install langflow -U
```

2. 运行 Langflow：

```shell
uv run langflow run
```

3. 打开默认的 Langflow 地址 `http://127.0.0.1:7860`。

如需了解更多安装选项（包括 Docker 和桌面版本），请参阅 [安装 Langflow](https://docs.langflow.org/get-started-installation)。

## 📦 部署

Langflow 完全开源，支持部署到所有主流云平台。如需了解如何使用 Docker 部署 Langflow，请参阅 [Docker 部署指南](https://docs.langflow.org/deployment-docker)。

## ⭐ 保持更新

在 GitHub 上为 Langflow 点亮星标，即可即时获取新版本通知。

![Star Langflow](https://github.com/user-attachments/assets/03168b17-a11d-4b2a-b0f7-c1cce69e5a2c)

## 👋 参与贡献

我们欢迎所有水平的开发者参与贡献。如需贡献，请查看我们的 [贡献指南](./CONTRIBUTING.md)，帮助我们让 Langflow 更加易用。

---

[![Star History Chart](https://api.star-history.com/svg?repos=langflow-ai/langflow&type=Timeline)](https://star-history.com/#langflow-ai/langflow&Date)

## ❤️ 贡献者

[![Langflow 贡献者](https://contrib.rocks/image?repo=langflow-ai/langflow)](https://github.com/langflow-ai/langflow/graphs/contributors)