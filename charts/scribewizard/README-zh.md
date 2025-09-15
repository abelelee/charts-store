---
<h2 align="center">
 <br>
 <img src="https://i.imgur.com/scoiUgD.png" alt="Generate Organizes Notes with ScribeWizard" width="150">
 <br>
 <br>
 ScribeWizard：使用 Groq、Whisper 和 Llama3 从音频生成结构化笔记
 <br>
</h2>

<p align="center">
 <a href="https://github.com/bklieger/scribewizard/stargazers"><img src="https://img.shields.io/github/stars/bklieger/scribewizard"></a>
 <a href="https://github.com/bklieger/scribewizard/blob/main/LICENSE.md">
 <img src="https://img.shields.io/badge/License-MIT-green.svg">
 </a>
</p>

<p align="center">
 <a href="#Overview">概述</a> •
 <a href="#Features">功能</a> •
 <a href="#Quickstart">快速开始</a> •
 <a href="#Contributing">贡献</a>
</p>

<br>

[ScribeWizard 演示](https://github.com/user-attachments/assets/c222bea0-3784-4f06-b431-ef81eea5691d)
> ScribeWizard 快速转录音频并生成结构化笔记的演示

## 概述

ScribeWizard 是一个 Streamlit 应用，通过使用 Groq 的 Whisper API 将音频讲座转录为文本，并迭代地组织和生成笔记，从而帮助创建结构化的课堂笔记。该应用混合使用了 Llama3-8b 和 Llama3-70b，在生成笔记结构时使用更大的模型，而在生成内容时使用速度更快的模型。

### 功能

- 🎧 使用 Whisper-large 转录的音频和 Llama3 生成的文本创建结构化笔记
- ⚡ 使用 Groq 实现音频转录和文本生成的极速体验
- 📖 分层提示策略性地在 Llama3-70b 和 Llama3-8b 之间切换，以平衡速度与质量
- 🖊️ Markdown 样式在 Streamlit 应用中生成美观的笔记，支持表格和代码
- 📂 允许用户下载包含完整笔记内容的文本或 PDF 文件

### 示例生成笔记：

| 示例                                      | Youtube 链接                                                                                                                                |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Transformers Explained by Google Cloud Tech             |  https://www.youtube.com/watch?v=SZorAJ4I-sA                                       |
| The Essence of Calculus by 3Blue1Brown | https://www.youtube.com/watch?v=WUvTyaaNkzM                                            |

> 与所有生成式 AI 一样，内容可能包含不准确或占位信息。ScribeWizard 仍处于测试阶段，欢迎所有反馈！

---

## 快速开始

> [!IMPORTANT]
> 要使用 ScribeWizard，可以通过 [scribewizard.streamlit.app](https://scribewizard.streamlit.app) 使用托管版本。
> 或者，您可以按照以下快速开始说明，使用 Streamlit 在本地运行 ScribeWizard。

### 托管在 Streamlit 上：

要使用 ScribeWizard，可以使用托管版本 [scribewizard.streamlit.app](https://scribewizard.streamlit.app)

### 本地运行：

或者，您可以使用 Streamlit 在本地运行 ScribeWizard。

#### 步骤 1
首先，您可以在环境变量中设置您的 Groq API 密钥：

~~~
export GROQ_API_KEY="gsk_yA..."
~~~

这是一个可选步骤，允许您跳过稍后在 Streamlit 应用中设置 Groq API 密钥的步骤。

#### 步骤 2
接下来，您可以设置虚拟环境并安装依赖项。

~~~
python3 -m venv venv
~~~

~~~
source venv/bin/activate
~~~

~~~
pip3 install -r requirements.txt
~~~

#### 步骤 3
最后，您可以运行 Streamlit 应用。

~~~
python3 -m streamlit run main.py
~~~

## 详细信息

### 技术

- Streamlit
- Groq Cloud 上的 Llama3
- Groq Cloud 上的 Whisper-large

### 局限性

ScribeWizard 可能会生成不准确的信息或占位内容。该工具仅用于娱乐目的，不应作为可靠信息来源。

## 贡献

欢迎通过 PR 提出改进建议！

## 更新日志

### v0.1.0

本次发布是应用程序代码库的首次发布，包含以下功能：

🎧 使用 Whisper-large 转录的音频和 Llama3 生成的文本创建结构化笔记

⚡ 使用 Groq 实现音频转录和文本生成的极速体验

📖 分层提示策略性地在 Llama3-70b 和 Llama3-8b 之间切换，以平衡速度与质量

🖊️ Markdown 样式在 Streamlit 应用中生成美观的笔记，支持表格和代码

📂 允许用户下载包含完整笔记内容的文本或 PDF 文件

### 未来功能：

- 创建摘要版本的转录内容，按 n 个字符分批处理
- 支持上传多个音频文件