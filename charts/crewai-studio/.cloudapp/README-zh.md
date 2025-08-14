# CrewAI Studio

欢迎使用 CrewAI Studio！本应用程序提供了一个基于 Streamlit 的用户友好界面，用于与 CrewAI 进行交互，即使您不想编写任何代码也能轻松使用。请按照以下步骤，使用 Docker/docker-compose 或 Conda/venv 安装并运行该应用。

## 功能特性

- **多平台支持**：适用于 Windows、Linux 和 MacOS。
- **无需编码**：提供用户友好的界面与 CrewAI 交互。
- **Conda 与虚拟环境支持**：可选择使用 Conda 或 Python 虚拟环境进行安装。
- **结果历史记录**：您可以查看之前的结果。
- **知识源支持**：您可以为您的团队添加知识源。
- **CrewAI 工具**：您可以使用 crewai 工具与真实世界交互。~~CrewAI Studio 使用了 forked 版本的 crewai-tools，包含一些 bug 修复和增强功能（https://github.com/strnad/crewAI-tools）~~（bug 修复已合并至 crewai-tools）。
- **自定义工具**：支持调用 API、写入文件、增强代码解释器、增强网页爬虫等工具，未来还将添加更多功能。
- **支持的 LLM 提供商**：目前支持 OpenAI、Groq、Anthropic、ollama、Grok 和 LM Studio 后端。许多工具中仍需使用 OpenAI 密钥进行嵌入，请在使用 LM Studio 时记得加载嵌入模型。
- **单页应用导出**：可将团队导出为简单的单页 Streamlit 应用。
- **线程化运行团队**：团队可以在后台运行，并可随时停止。

## 支持 CrewAI Studio

您的支持将帮助我们项目的开发与成长，每一份贡献我们都深表感谢！

### 使用比特币捐赠
[![使用比特币捐赠](https://www.blockonomics.co/img/pay_with_bitcoin_medium.png)](https://pay-link.s3.us-west-2.amazonaws.com/index.html?uid=b14b42846ecd40fe)

### 通过 GitHub 赞助
[![在 GitHub 上赞助](https://img.shields.io/badge/Sponsor-GitHub-ff69b4?style=for-the-badge&logo=github)](https://github.com/sponsors/strnad)

## 截图

<img src="https://raw.githubusercontent.com/strnad/CrewAI-Studio/main/img/ss1.png" alt="crews definition" style="width:50%;"/><img src="https://raw.githubusercontent.com/strnad/CrewAI-Studio/main/img/ss2.png" alt="启动界面" style="width:50%;"/>
<img src="https://raw.githubusercontent.com/strnad/CrewAI-Studio/main/img/ss3.png" alt="启动界面" style="width:50%;"/><img src="https://raw.githubusercontent.com/strnad/CrewAI-Studio/main/img/ss4.png" alt="启动界面" style="width:50%;"/>
<img src="https://raw.githubusercontent.com/strnad/CrewAI-Studio/main/img/ss5.png" alt="启动界面" style="width:50%;"/><img src="https://raw.githubusercontent.com/strnad/CrewAI-Studio/main/img/ss6.png" alt="启动界面" style="width:50%;"/>

## 安装

### 使用虚拟环境

**对于虚拟环境**：请确保已安装 Python。如果没有安装 Python，可以简单使用 Conda 安装器。

#### 在 Linux 或 MacOS 上

1. **克隆仓库（或使用下载的 ZIP 文件）**：

   ```bash
   git clone https://github.com/strnad/CrewAI-Studio.git
   cd CrewAI-Studio
   ```

2. **运行安装脚本**：

   ```bash
   ./install_venv.sh
   ```

3. **运行应用程序**：

   ```bash
   ./run_venv.sh
   ```

#### 在 Windows 上

1. **克隆仓库（或使用下载的 ZIP 文件）**：

   ```powershell
   git clone https://github.com/strnad/CrewAI-Studio.git
   cd CrewAI-Studio
   ```

2. **运行 Conda 安装脚本**：

   ```powershell
   ./install_venv.bat
   ```

3. **运行应用程序**：

   ```powershell
   ./run_venv.bat
   ```

### 使用 Conda

Conda 将在项目文件夹中本地安装，无需预先安装 Conda。

#### 在 Linux 上

1. **克隆仓库（或使用下载的 ZIP 文件）**：

   ```bash
   git clone https://github.com/strnad/CrewAI-Studio.git
   cd CrewAI-Studio
   ```

2. **运行 Conda 安装脚本**：

   ```bash
   ./install_conda.sh
   ```

3. **运行应用程序**：

   ```bash
   ./run_conda.sh
   ```

#### 在 Windows 上

1. **克隆仓库（或使用下载的 ZIP 文件）**：

   ```powershell
   git clone https://github.com/strnad/CrewAI-Studio.git
   cd CrewAI-Studio
   ```

2. **运行 Conda 安装脚本**：

   ```powershell
   ./install_conda.bat
   ```

3. **运行应用程序**：

   ```powershell
   ./run_conda.bat
   ```

### 一键部署

[![部署到 RepoCloud](https://d16t0pc4846x52.cloudfront.net/deploylobe.svg)](https://repocloud.io/details/?app_id=318)

## 使用 Docker Compose 运行

要使用 Docker Compose 快速搭建并运行 CrewAI-Studio，请按照以下步骤操作：

### 前提条件

- 确保系统已安装 [Docker](https://docs.docker.com/get-docker/) 和 [Docker Compose](https://docs.docker.com/compose/install/)。

### 步骤

1. 克隆仓库：
```
git clone https://github.com/strnad/CrewAI-Studio.git
cd CrewAI-Studio
```

2. 创建配置文件 `.env`，并根据需要进行编辑：
```
cp .env_example .env
```

3. 使用 Docker Compose 启动应用：
```
docker-compose up --build
```

4. 访问应用：http://localhost:8501

## 配置

在运行应用程序之前，请确保更新 `.env` 文件，填入您的 API 密钥及其他必要配置。我们提供了示例 `.env` 文件供参考。

## 故障排查

如遇问题：
- 删除 `venv/miniconda` 文件夹并重新安装 `crewai-studio`。
- 重命名 `crewai.db`（该文件包含您的团队信息，但有时新版本可能导致兼容性问题）。
- 提交问题，我将协助您解决。

## 视频教程
Josh Poco 制作的 CrewAI Studio 视频教程

[![FREE CrewAI Studio GUI EASY AI Agent Creation!🤖 Open Source AI Agent Orchestration Self Hosted](https://img.youtube.com/vi/3Uxdggt88pY/hqdefault.jpg)](https://www.youtube.com/watch?v=3Uxdggt88pY)

## 星标历史

<a href="https://star-history.com/#strnad/CrewAI-Studio&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=strnad/CrewAI-Studio&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=strnad/CrewAI-Studio&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=strnad/CrewAI-Studio&type=Date" />
 </picture>   
</a>