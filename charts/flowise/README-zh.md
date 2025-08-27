请将以下Markdown格式的文本内容翻译成中文。
请注意：
1. 保持原始的Markdown格式不变，例如标题、列表、代码块等。
2. 翻译要自然、流畅，符合技术文档的语境。
3. 不要添加任何与原文无关的评论或解释。

原文如下：
---
<!-- markdownlint-disable MD030 -->

<p align="center">
<img src="https://github.com/FlowiseAI/Flowise/blob/main/images/flowise_white.svg#gh-light-mode-only">
<img src="https://github.com/FlowiseAI/Flowise/blob/main/images/flowise_dark.svg#gh-dark-mode-only">
</p>

<div align="center">

[![Release Notes](https://img.shields.io/github/release/FlowiseAI/Flowise)](https://github.com/FlowiseAI/Flowise/releases)
[![Discord](https://img.shields.io/discord/1087698854775881778?label=Discord&logo=discord)](https://discord.gg/jbaHfsRVBW)
[![Twitter Follow](https://img.shields.io/twitter/follow/FlowiseAI?style=social)](https://twitter.com/FlowiseAI)
[![GitHub star chart](https://img.shields.io/github/stars/FlowiseAI/Flowise?style=social)](https://star-history.com/#FlowiseAI/Flowise)
[![GitHub fork](https://img.shields.io/github/forks/FlowiseAI/Flowise?style=social)](https://github.com/FlowiseAI/Flowise/fork)

English | [繁體中文](./i18n/README-TW.md) | [简体中文](./i18n/README-ZH.md) | [日本語](./i18n/README-JA.md) | [한국어](./i18n/README-KR.md)

</div>

<h3>以可视化方式构建AI代理</h3>
<a href="https://github.com/FlowiseAI/Flowise">
<img width="100%" src="https://github.com/FlowiseAI/Flowise/blob/main/images/flowise_agentflow.gif?raw=true"></a>

## 📚 目录

- [⚡ 快速开始](#-快速开始)
- [🐳 Docker](#-docker)
- [👨‍💻 开发者](#-开发者)
- [🌱 环境变量](#-环境变量)
- [📖 文档](#-文档)
- [🌐 自托管](#-自托管)
- [☁️ Flowise Cloud](#️-flowise-cloud)
- [🙋 支持](#-支持)
- [🙌 贡献](#-贡献)
- [📄 许可证](#-许可证)

## ⚡ 快速开始

下载并安装 [NodeJS](https://nodejs.org/en/download) >= 18.15.0

1. 安装 Flowise
    ```bash
    npm install -g flowise
    ```
2. 启动 Flowise

    ```bash
    npx flowise start
    ```

3. 打开 [http://localhost:3000](http://localhost:3000)

## 🐳 Docker

### Docker Compose

1. 克隆 Flowise 项目
2. 进入项目根目录下的 `docker` 文件夹
3. 复制 `.env.example` 文件，粘贴到相同位置并重命名为 `.env`
4. `docker compose up -d`
5. 打开 [http://localhost:3000](http://localhost:3000)
6. 可以通过 `docker compose stop` 停止容器

### Docker 镜像

1. 在本地构建镜像：
   
    ```bash
    docker build --no-cache -t flowise .
    ```
2. 运行镜像：
   
    ```bash
    docker run -d --name flowise -p 3000:3000 flowise
    ```

3. 停止镜像：
   
    ```bash
    docker stop flowise
    ```

## 👨‍💻 开发者

Flowise 在一个单一仓库中包含三个不同的模块。

-   `server`: 提供 API 逻辑的 Node 后端
-   `ui`: React 前端
-   `components`: 第三方节点集成
-   `api-documentation`: 从 express 自动生成的 swagger-ui API 文档

### 前提条件

-   安装 [PNPM](https://pnpm.io/installation)
    ```bash
    npm i -g pnpm
    ```

### 设置

1.  克隆仓库：

    ```bash
    git clone https://github.com/FlowiseAI/Flowise.git
    ```

2.  进入仓库文件夹：

    ```bash
    cd Flowise
    ```

3.  安装所有模块的依赖：

    ```bash
    pnpm install
    ```

4.  构建所有代码：

    ```bash
    pnpm build
    ```

    <details>
    <summary>退出代码 134 (JavaScript 堆内存不足)</summary>  
      如果在运行上述 `build` 脚本时出现此错误，请尝试增加 Node.js 堆大小并重新运行脚本：

        export NODE_OPTIONS="--max-old-space-size=4096"
        pnpm build

    </details>

5.  启动应用：

    ```bash
    pnpm start
    ```

    现在可以在 [http://localhost:3000](http://localhost:3000) 访问该应用

6.  开发版本构建：

    -   在 `packages/ui` 中创建 `.env` 文件并指定 `VITE_PORT`（参考 `.env.example`）
    -   在 `packages/server` 中创建 `.env` 文件并指定 `PORT`（参考 `.env.example`）
    -   运行:

        ```bash
        pnpm dev
        ```

    任何代码更改都会自动在 [http://localhost:8080](http://localhost:8080) 上重新加载应用

## 🌱 环境变量

Flowise 支持多种环境变量来配置您的实例。您可以在 `packages/server` 文件夹中的 `.env` 文件中指定以下变量。阅读 [更多](https://github.com/FlowiseAI/Flowise/blob/main/CONTRIBUTING.md#-env-variables)

## 📖 文档

您可以在此处查看 Flowise 文档 [这里](https://docs.flowiseai.com/)

## 🌐 自托管

在您现有的基础设施上部署 Flowise 自托管，我们支持多种[部署方式](https://docs.flowiseai.com/configuration/deployment)

-   [AWS](https://docs.flowiseai.com/configuration/deployment/aws)
-   [Azure](https://docs.flowiseai.com/configuration/deployment/azure)
-   [Digital Ocean](https://docs.flowiseai.com/configuration/deployment/digital-ocean)
-   [GCP](https://docs.flowiseai.com/configuration/deployment/gcp)
-   [阿里云](https://computenest.console.aliyun.com/service/instance/create/default?type=user&ServiceName=Flowise社区版)
-   <details>
      <summary>其他</summary>

    -   [Railway](https://docs.flowiseai.com/configuration/deployment/railway)

        [![在Railway上部署](https://railway.app/button.svg)](https://railway.app/template/pn4G8S?referralCode=WVNPD9)

    -   [Render](https://docs.flowiseai.com/configuration/deployment/render)

        [![部署到Render](https://render.com/images/deploy-to-render-button.svg)](https://docs.flowiseai.com/configuration/deployment/render)

    -   [HuggingFace Spaces](https://docs.flowiseai.com/deployment/hugging-face)

        <a href="https://huggingface.co/spaces/FlowiseAI/Flowise"><img src="https://huggingface.co/datasets/huggingface/badges/raw/main/open-in-hf-spaces-sm.svg" alt="HuggingFace Spaces"></a>

    -   [Elestio](https://elest.io/open-source/flowiseai)

        [![在Elestio上部署](https://elest.io/images/logos/deploy-to-elestio-btn.png)](https://elest.io/open-source/flowiseai)

    -   [Sealos](https://template.sealos.io/deploy?templateName=flowise)

        [![在Sealos上部署](https://sealos.io/Deploy-on-Sealos.svg)](https://template.sealos.io/deploy?templateName=flowise)

    -   [RepoCloud](https://repocloud.io/details/?app_id=29)

        [![在RepoCloud上部署](https://d16t0pc4846x52.cloudfront.net/deploy.png)](https://repocloud.io/details/?app_id=29)

      </details>

## ☁️ Flowise Cloud

通过 [Flowise Cloud](https://flowiseai.com/) 开始使用。

## 🙋 支持

如有任何问题、需要解决问题或请求新功能，请在 [讨论区](https://github.com/FlowiseAI/Flowise/discussions) 随时提问。

## 🙌 贡献

感谢这些出色的贡献者

<a href="https://github.com/FlowiseAI/Flowise/graphs/contributors">
<img src="https://contrib.rocks/image?repo=FlowiseAI/Flowise" />
</a><br><br>

查看 [贡献指南](CONTRIBUTING.md)。如有任何问题或疑问，请在 [Discord](https://discord.gg/jbaHfsRVBW) 联系我们。

[![Star History Chart](https://api.star-history.com/svg?repos=FlowiseAI/Flowise&type=Timeline)](https://star-history.com/#FlowiseAI/Flowise&Date)

## 📄 许可证

本仓库中的源代码根据 [Apache License Version 2.0](LICENSE.md) 授权。