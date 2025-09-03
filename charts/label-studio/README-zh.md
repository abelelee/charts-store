<img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/ls_github_header.png"/>

![GitHub](https://img.shields.io/github/license/heartexlabs/label-studio?logo=heartex) ![label-studio:build](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/badge.svg) ![GitHub release](https://img.shields.io/github/v/release/heartexlabs/label-studio?include_prereleases)

[官网](https://labelstud.io/) • [文档](https://labelstud.io/guide/) • [Twitter](https://twitter.com/heartexlabs) • [加入Slack社区 <img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/slack-mini.png" width="18px"/>](https://slack.labelstudio.heartex.com/?source=github-1)

## 什么是 Label Studio？

Label Studio 是一个开源的数据标注工具。它允许你使用简单直观的界面对音频、文本、图像、视频和时间序列等多种数据类型进行标注，并导出为多种模型格式。你可以使用它来准备原始数据或改进现有训练数据，从而获得更精确的机器学习模型。

- [尝试 Label Studio](#try-out-label-studio)
- [Label Studio 能为你带来什么](#what-you-get-from-label-studio)
- [Label Studio 中包含的数据标注模板](#included-templates-for-labeling-data-in-label-studio)
- [使用 Label Studio 设置机器学习模型](#set-up-machine-learning-models-with-Label-Studio)
- [将 Label Studio 与现有工具集成](#integrate-label-studio-with-your-existing-tools)

![Label Studio 标注不同类型数据的GIF](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/annotation_examples.gif)

如果你有自定义数据集？你可以根据需求定制 Label Studio。阅读这篇[介绍性博客文章](https://towardsdatascience.com/introducing-label-studio-a-swiss-army-knife-of-data-labeling-140c1be92881)了解更多。

## 尝试 Label Studio

你可以在本地安装 Label Studio，也可以将其部署在云实例中。还可以尝试 [Label Studio Teams](https://app.heartex.com)。

- [使用 Docker 本地安装](#install-locally-with-docker)
- [使用 Docker Compose 运行（Label Studio + Nginx + PostgreSQL）](#run-with-docker-compose)
- [使用 pip 本地安装](#install-locally-with-pip)
- [使用 Anaconda 本地安装](#install-locally-with-anaconda)
- [为本地开发安装](#install-for-local-development)
- [在云实例中部署](#deploy-in-a-cloud-instance)

### 使用 Docker 本地安装

官方 Label Studio Docker 镜像位于 [这里](https://hub.docker.com/r/heartexlabs/label-studio)，可以通过 `docker pull` 命令下载。运行 Label Studio 容器后，可以通过 `http://localhost:8080` 访问。

```bash
docker pull heartexlabs/label-studio:latest
docker run -it -p 8080:8080 -v `pwd`/mydata:/label-studio/data heartexlabs/label-studio:latest
```

你可以在 `./mydata` 目录中找到所有生成的资源，包括 SQLite3 数据库文件 `label_studio.sqlite3` 和上传的文件。

#### 覆盖默认的 Docker 安装配置

你可以通过附加新参数来覆盖默认的启动命令：

```bash
docker run -it -p 8080:8080 -v `pwd`/mydata:/label-studio/data heartexlabs/label-studio:latest label-studio --log-level DEBUG
```

#### 使用 Docker 构建本地镜像

如果你想构建本地镜像，可以运行：

```bash
docker build -t heartexlabs/label-studio:latest .
```

### 使用 Docker Compose 运行

Docker Compose 脚本提供了一个生产就绪的堆栈，包含以下组件：

- Label Studio
- [Nginx](https://www.nginx.com/) - 用于加载各种静态数据（包括上传的音频、图片等）的代理 Web 服务器
- [PostgreSQL](https://www.postgresql.org/) - 性能更强的生产级数据库，替代 SQLite3

要从 `http://localhost` 开始使用应用，请运行：

```bash
docker-compose up
```

### 使用 pip 本地安装

```bash
# 需要 Python >=3.7 <=3.9
pip install label-studio

# 在 http://localhost:8080 启动服务
label-studio
```

### 使用 Anaconda 本地安装

```bash
conda create --name label-studio
conda activate label-studio
pip install label-studio
```

### 为本地开发安装

你可以在不使用 pip 安装的情况下运行最新的 Label Studio 版本：

```bash
# 安装所有依赖包
pip install -e .
# 运行数据库迁移
python label_studio/manage.py migrate
# 在开发模式下启动服务，地址为 http://localhost:8080
python label_studio/manage.py runserver
```

### 在云实例中部署

你可以通过一键部署将 Label Studio 部署到 Heroku、Microsoft Azure 或 Google Cloud Platform：

[<img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/button.svg" height="30px">](https://heroku.com/deploy?template=https://github.com/heartexlabs/label-studio/tree/heroku-persistent-pg)
[<img src="https://aka.ms/deploytoazurebutton" height="30px">](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fheartexlabs%2Flabel-studio%2Fmaster%2Fazuredeploy.json)
[<img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/button.svg" height="30px">](https://deploy.cloud.run)

#### 应用前端更改

Label Studio 的前端部分位于 `frontend/` 文件夹中，使用 React JSX 编写。如果你进行了修改，在构建或启动实例前需要运行以下命令：

```
cd label_studio/frontend/
npm ci
npx webpack
cd ../..
python label_studio/manage.py collectstatic --no-input
```

### 安装问题排查

如果安装过程中出现错误，尝试重新安装：

```bash
pip install --ignore-installed label-studio
```

#### 在 Windows 上安装依赖

要在 Windows 上运行 Label Studio，请从 [Gohlke 构建页面](https://www.lfd.uci.edu/~gohlke/pythonlibs) 下载并安装以下 wheel 包，确保你使用的是正确的 Python 版本：
- [lxml](https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml)

```bash
# 升级 pip
pip install -U pip

# 如果你使用的是 Win64 和 Python 3.8，请安装从 Gohlke 下载的包：
pip install lxml‑4.5.0‑cp38‑cp38‑win_amd64.whl

# 安装 label-studio
pip install label-studio
```

#### 运行测试套件

```bash
pip install -r deploy/requirements-test.txt
cd label_studio

# 使用 PostgreSQL（假设默认的 postgres 用户、数据库、密码）
DJANGO_DB=default DJANGO_SETTINGS_MODULE=core.settings.label_studio python -m pytest -vv -n auto

# 使用 SQLite3
DJANGO_DB=sqlite DJANGO_SETTINGS_MODULE=core.settings.label_studio python -m pytest -vv -n auto
```

## Label Studio 能为你带来什么

![Label Studio 数据管理器网格视图截图（显示图像）](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/labelstudio-ui.gif)

- **多用户标注**：支持注册和登录，你的标注会与你的账户绑定。
- **多个项目**：在一个实例中管理所有数据集。
- **简洁的设计**：帮助你专注于任务，而不是学习如何使用软件。
- **可配置的标签格式**：可以自定义界面以满足特定的标注需求。
- **支持多种数据类型**：包括图像、音频、文本、HTML、时间序列和视频。
- **支持从文件或云存储导入**：支持 Amazon AWS S3、Google Cloud Storage、JSON、CSV、TSV、RAR 和 ZIP 等格式。
- **与机器学习模型集成**：可以可视化并比较不同模型的预测结果，并进行预标注。
- **嵌入到数据管道中**：REST API 使得它易于集成到你的数据流程中。

## Label Studio 中包含的数据标注模板

Label Studio 提供了多种模板来帮助你标注数据，你也可以使用专门设计的配置语言创建自己的模板。最常见的模板和使用场景包括：

<img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/templates-categories.jpg" />

## 使用 Label Studio 设置机器学习模型

使用 Label Studio 的机器学习 SDK 连接你最喜欢的机器学习模型。请按照以下步骤操作：

1. 启动你自己的机器学习后端服务器。详见 [更详细的说明](https://github.com/heartexlabs/label-studio-ml-backend)。
2. 在项目设置中的模型页面上将 Label Studio 连接到该服务器。

这将使你能够：

- **预标注**：使用模型预测对数据进行标注。
- **在线学习**：在创建新标注的同时重新训练模型。
- **主动学习**：仅标注数据中最复杂的示例。

## 将 Label Studio 与现有工具集成

你可以将 Label Studio 作为机器学习工作流中的独立部分使用，或将前端或后端集成到现有工具中。

* 使用 [Label Studio 前端](https://github.com/heartexlabs/label-studio-frontend) 作为一个独立的 React 库。详见 [前端库文档](https://labelstud.io/guide/frontend.html)。

## 生态系统

| 项目 | 描述 |
|---|---|
| label-studio | 作为 pip 包分发的服务器 |
| [label-studio-frontend](https://github.com/heartexlabs/label-studio-frontend) | React 和 JavaScript 前端，可在浏览器中独立运行或嵌入到你的应用中 |
| [data-manager](https://github.com/heartexlabs/dm2) | 用于管理数据的 React 和 JavaScript 前端。包含 Label Studio 前端，依赖 label-studio 服务器或具有预期 API 方法的自定义后端 |
| [label-studio-converter](https://github.com/heartexlabs/label-studio-converter) | 将标签编码为你喜欢的机器学习库所需的格式 |
| [label-studio-transformers](https://github.com/heartexlabs/label-studio-transformers) | 已连接并配置好用于 Label Studio 的 Transformers 库 |

## 路线图

你想使用 **最酷的功能 X**，但 Label Studio 当前不支持？请查看 [我们的公开路线图](roadmap.md)！

## 引用

```tex
@misc{Label Studio,
  title={{Label Studio}: 数据标注软件},
  url={https://github.com/heartexlabs/label-studio},
  note={开源软件，可从 https://github.com/heartexlabs/label-studio 获取},
  author={
    Maxim Tkachenko 和
    Mikhail Malyuk 和
    Andrey Holmanyuk 和
    Nikolai Liubimov},
  year={2020-2022},
}
```

## 许可证

本软件采用 [Apache 2.0 许可证](/LICENSE) 授权 © [Heartex](https://www.heartex.ai/)。2020-2021

<img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/label-studio/image/opossum_looking.png" title="大家好！" height="140" width="140" />