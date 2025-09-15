# OpenUI

<p align="center">
  <img src="./assets/openui.png" width="150" alt="OpenUI" />
</p>

构建UI组件可能是一项枯燥的工作。OpenUI旨在让这个过程变得有趣、快速且灵活。这也是我们在 [W&B](https://wandb.com) 用来测试和原型设计下一代工具的工具，用于在LLM基础上构建强大应用程序。

## 概览

![Demo](./assets/demo.gif)

OpenUI 让你可以用你的想象力来描述UI，然后实时看到它的渲染效果。你可以要求更改，并将HTML转换为React、Svelte、Web组件等。它类似于 [v0](https://v0.dev)，但它是开源的，而且没有那么完善 :stuck_out_tongue_closed_eyes:。

## 在线演示

[尝试演示](https://openui.fly.dev)

## 本地运行

OpenUI 支持 [OpenAI](https://platform.openai.com/api-keys)、[Groq](https://console.groq.com/keys) 和任何 [LiteLLM](https://docs.litellm.ai/docs/) 支持的模型，例如 [Gemini](https://aistudio.google.com/app/apikey) 或 [Anthropic (Claude)](https://console.anthropic.com/settings/keys)。以下环境变量是可选的，但需要在你的环境中设置它们，以便替代模型能够工作：

- **OpenAI** `OPENAI_API_KEY`
- **Groq** `GROQ_API_KEY`
- **Gemini** `GEMINI_API_KEY`
- **Anthropic** `ANTHROPIC_API_KEY`
- **Cohere** `COHERE_API_KEY`
- **Mistral** `MISTRAL_API_KEY`
- **OpenAI Compatible** `OPENAI_COMPATIBLE_ENDPOINT` 和 `OPENAI_COMPATIBLE_API_KEY`

例如，如果你正在运行像 [localai](https://localai.io/) 这样的工具，你可以设置 `OPENAI_COMPATIBLE_ENDPOINT` 和可选的 `OPENAI_COMPATIBLE_API_KEY`，以便在UI的模型选择器下的LiteLLM中列出可用模型。

### Ollama

你也可以使用 [Ollama](https://ollama.com) 提供的模型。[安装Ollama](https://ollama.com/download) 并拉取一个模型，比如 [Llava](https://ollama.com/library/llava)。如果Ollama不在 http://127.0.0.1:11434 上运行，你可以将 `OLLAMA_HOST` 环境变量设置为你的Ollama实例的主机和端口。例如，在Docker中运行时，你需要将其指向 http://host.docker.internal:11434，如下所示。

### Docker（推荐）

以下命令会将指定的API密钥从你的shell环境转发，并告诉Docker使用你机器上运行的Ollama实例。

```bash
export ANTHROPIC_API_KEY=xxx
export OPENAI_API_KEY=xxx
docker run --rm --name openui -p 7878:7878 -e OPENAI_API_KEY -e ANTHROPIC_API_KEY -e OLLAMA_HOST=http://host.docker.internal:11434 ghcr.io/wandb/openui
```

现在你可以访问 [http://localhost:7878](http://localhost:7878) 并生成新的UI！

### 源码/Python

假设你已经安装了git和 [uv](https://github.com/astral-sh/uv)：

```bash
git clone https://github.com/wandb/openui
cd openui/backend
uv sync --frozen --extra litellm
source .venv/bin/activate
# 设置你想要使用的任何LLM的API密钥
export OPENAI_API_KEY=xxx
python -m openui
```

## LiteLLM

[LiteLLM](https://docs.litellm.ai/docs/) 可以用来连接基本上任何可用的LLM服务。我们根据你的环境变量自动生成一个配置。你可以创建自己的 [代理配置](https://litellm.vercel.app/docs/proxy/configs) 来覆盖此行为。我们在以下位置查找自定义配置：

1. 当前目录中的 `litellm-config.yaml`
2. 在Docker容器中运行时的 `/app/litellm-config.yaml`
3. 由 `OPENUI_LITELLM_CONFIG` 环境变量指定的任意路径

例如，在Docker中使用自定义配置可以运行：

```bash
docker run -n openui -p 7878:7878 -v $(pwd)/litellm-config.yaml:/app/litellm-config.yaml ghcr.io/wandb/openui
```

从源码使用litellm可以运行：

```bash
pip install .[litellm]
export ANTHROPIC_API_KEY=xxx
export OPENAI_COMPATIBLE_ENDPOINT=http://localhost:8080/v1
python -m openui --litellm
```

## Groq

要使用超快速的 [Groq](https://groq.com) 模型，请将 `GROQ_API_KEY` 设置为你的Groq API密钥，你可以在[这里](https://console.groq.com/keys) 找到它。要使用其中一个Groq模型，请点击导航栏中的设置图标。

### Docker Compose

> **免责声明：** 这可能会非常慢。如果你有GPU，可能需要将 `ollama` 容器的标签更改为支持GPU的标签。如果你在Mac上运行，请按照上面的说明原生运行Ollama以利用M1/M2芯片。

从根目录你可以运行：

```bash
docker-compose up -d
docker exec -it openui-ollama-1 ollama pull llava
```

如果你已经在环境中设置了 `OPENAI_API_KEY`，只需从 `OPENAI_API_KEY` 行中删除 `=xxx`。你也可以将上面命令中的 `llava` 替换为你选择的开源模型（目前 [llava](https://ollama.com/library/llava) 是唯一支持图像的Ollama模型）。你现在应该能够通过 [http://localhost:7878](http://localhost:7878) 访问OpenUI。

*如果你对前端或后端进行了更改，你需要运行 `docker-compose build` 以使更改在服务中生效。*

## 开发

本仓库中配置了一个 [开发容器](https://github.com/wandb/openui/blob/main/.devcontainer/devcontainer.json)，这是最快捷的入门方式。

### Codespace

<img src="./assets/codespace.png" alt="New with options..." width="500" />

创建Codespace时选择更多选项，然后选择 **New with options...**。如果你希望启动速度快，可以选择US West区域。你还需要配置你的 `OPENAI_API_KEY` 密钥，或者如果你想尝试Ollama，只需将其设置为 `xxx`（你至少需要16GB的内存）。

进入代码空间后，你可以在一个终端中运行服务器：`python -m openui --dev`。然后在新终端中：

```bash
cd /workspaces/openui/frontend
npm run dev
```

这将在端口5173上打开另一个服务，那就是你想要访问的服务。对前端和后端的所有更改都会自动重新加载并在你的浏览器中反映出来。

### Ollama

代码空间会自动安装Ollama并下载 `llava` 模型。你可以使用 `ollama list` 验证Ollama是否正在运行，如果失败，请打开一个新终端并运行 `ollama serve`。在代码空间中，我们在启动时拉取llava，因此你应该在列表中看到它。你可以从应用程序左上角的设置齿轮图标中选择Ollama模型。你拉取的任何模型，例如 `ollama pull llama`，都会显示在设置模态中。

<img src="./assets/ollama.png" width="500" alt="选择Ollama模型" />

### Gitpod

你可以通过Gitpod轻松使用Open UI，它已经预配置了Open AI。

[![在Gitpod中打开](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/wandb/openui)

启动时，Open UI会自动安装并启动。

在使用Gitpod之前：

* 确保你有一个Gitpod账户。
* 要使用Open AI模型，请在你的Gitpod [用户账户](https://gitpod.io/user/variables) 中设置 `OPENAI_API_KEY` 环境变量。将作用域设置为 `wandb/openui`（或者如果你分叉了它，则为你自己的仓库）。

> 注意：其他（本地）模型也可以通过更大的Gitpod实例类型使用。Gitpod中没有预配置所需的模型，但可以轻松按照上面的说明添加。

### 资源

请参阅 前端 和 后端 目录中的readme文件。