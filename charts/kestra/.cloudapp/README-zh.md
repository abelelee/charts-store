以下是你提供的Markdown内容的中文翻译版本，保留了原始的Markdown格式和结构：

---

<p align="center">
  <a href="https://www.kestra.io">
    <img src="https://kestra.io/banner.png"  alt="Kestra 工作流编排器" />
  </a>
</p>

<h1 align="center" style="border-bottom: none">
    事件驱动的声明式编排平台
</h1>

<div align="center">
 <a href="https://github.com/kestra-io/kestra/releases"><img src="https://img.shields.io/github/tag-pre/kestra-io/kestra.svg?color=blueviolet" alt="最新版本" /></a>
  <a href="https://github.com/kestra-io/kestra/blob/develop/LICENSE"><img src="https://img.shields.io/github/license/kestra-io/kestra?color=blueviolet" alt="许可证" /></a>
  <a href="https://github.com/kestra-io/kestra/stargazers"><img src="https://img.shields.io/github/stars/kestra-io/kestra?color=blueviolet&logo=github" alt="GitHub 星标" /></a> <br>
<a href="https://kestra.io"><img src="https://img.shields.io/badge/Website-kestra.io-192A4E?color=blueviolet" alt="Kestra 无限可扩展的编排与调度平台"></a>
<a href="https://kestra.io/slack"><img src="https://img.shields.io/badge/Slack-加入社区-blueviolet?logo=slack" alt="Slack"></a>
</div>

<br />

<p align="center">
    <a href="https://x.com/kestra_io"><img height="25" src="https://kestra.io/twitter.svg" alt="X（原 Twitter）" /></a> &nbsp;
    <a href="https://www.linkedin.com/company/kestra/"><img height="25" src="https://kestra.io/linkedin.svg" alt="LinkedIn" /></a> &nbsp;
    <a href="https://www.youtube.com/@kestra-io"><img height="25" src="https://kestra.io/youtube.svg" alt="YouTube" /></a> &nbsp;
</p>

<p align="center">
  <a href="https://trendshift.io/repositories/2714" target="_blank">
    <img src="https://trendshift.io/api/badge/repositories/2714" alt="kestra-io%2Fkestra | Trendshift" width="250" height="55"/>
  </a>
  <a href="https://www.producthunt.com/posts/kestra?embed=true&utm_source=badge-top-post-badge&utm_medium=badge&utm_souce=badge-kestra" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/top-post-badge.svg?post_id=612077&theme=light&period=daily&t=1740737506162" alt="Kestra - 一体化自动化与编排平台 | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" /></a>
</p>

<p align="center">
    <a href="https://go.kestra.io/video/product-overview" target="_blank">
        <img src="https://kestra.io/startvideo.png" alt="4 分钟内上手 Kestra" width="640px" />
    </a>
</p>
<p align="center" style="color:grey;"><i>点击图片，学习如何在 4 分钟内上手 Kestra。</i></p>

## 🌟 什么是 Kestra？

Kestra 是一个开源的事件驱动编排平台，让**定时**和**事件驱动**的工作流变得简单。通过将**基础设施即代码**的最佳实践引入数据、流程和微服务的编排中，你可以直接在 UI 中使用几行 YAML 构建可靠的工作流。

**主要特性：**
- **一切皆为代码，且支持 UI 操作：** 即使是通过 UI 构建工作流，也能通过集成 **Git 版本控制** 实现 **工作流即代码**。
- **事件驱动与定时工作流：** 通过简单的 `trigger` 定义，自动化 **定时** 和 **实时事件驱动** 的工作流。
- **声明式 YAML 接口：** 使用内置代码编辑器中的简单配置定义工作流。
- **丰富的插件生态系统：** 内置数百个插件，可从任意数据库、云存储或 API 提取数据，并支持用任意语言运行脚本。
- **直观的 UI 与代码编辑器：** 在 UI 中构建和可视化工作流，支持语法高亮、自动补全和实时语法校验。
- **可扩展性：** 设计用于处理数百万个工作流，具备高可用性和容错能力。
- **支持版本控制：** 从内置代码编辑器编写工作流并直接推送到你选择的 Git 分支，实现 CI/CD 流水线和版本控制系统最佳实践。
- **结构化与弹性：** 通过 **命名空间**、**标签**、**子流程**、**重试**、**超时**、**错误处理**、**输入输出**（在 UI 中生成工件）、**变量**、**条件分支**、**高级调度**、**事件触发器**、**回填**、**动态任务**、**顺序与并行任务** 等功能，控制混乱并增强工作流的弹性。你也可以通过设置 `disabled` 标志为 `true` 来跳过任务或触发器。

🧑‍💻 每当你通过 UI 或 API 调用修改工作流时，YAML 定义会自动调整。因此，编排逻辑始终通过代码以声明式方式管理，即使你通过其他方式（UI、CI/CD、Terraform、API 调用）修改工作流也是如此。

<p align="center">
  <img src="https://kestra.io/adding-tasks.gif" alt="在 UI 中添加新任务">
</p>

---

## 🚀 快速入门

### 5 分钟内本地启动 Kestra

#### 使用 Docker 启动 Kestra

确保 Docker 正在运行。然后，使用一条命令启动 Kestra：

```bash
docker run --pull=always --rm -it -p 8080:8080 --user=root \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /tmp:/tmp kestra/kestra:latest server local
```

如果你使用的是 Windows 并使用 PowerShell：
```powershell
docker run --pull=always --rm -it -p 8080:8080 --user=root `
    -v "/var/run/docker.sock:/var/run/docker.sock" `
    -v "C:/Temp:/tmp" kestra/kestra:latest server local
```

如果你使用的是 Windows 并使用命令提示符（CMD）：
```cmd
docker run --pull=always --rm -it -p 8080:8080 --user=root ^
    -v "/var/run/docker.sock:/var/run/docker.sock" ^
    -v "C:/Temp:/tmp" kestra/kestra:latest server local
```

如果你使用的是 Windows 并使用 WSL（Windows 中的 Linux 环境）：
```bash
docker run --pull=always --rm -it -p 8080:8080 --user=root \
    -v "/var/run/docker.sock:/var/run/docker.sock" \
    -v "C:/Temp:/tmp" kestra/kestra:latest server local
```

查看我们的 [安装指南](https://kestra.io/docs/installation) 获取其他部署方式（Docker Compose、Podman、Kubernetes、AWS、GCP、Azure 等）。

访问 [http://localhost:8080](http://localhost:8080) 上的 Kestra UI 并开始构建你的第一个流程！

#### 你的第一个 Hello World 流程

创建一个包含以下内容的新流程：

```yaml
id: hello_world
namespace: dev

tasks:
  - id: say_hello
    type: io.kestra.plugin.core.log.Log
    message: "Hello, World!"
```

运行流程并在 UI 中查看输出！

---

## 🧩 插件生态系统

Kestra 的功能通过丰富的 [插件生态系统](https://kestra.io/plugins) 得到扩展，使你可以在任何地方运行任务并使用任意语言编写代码，包括 Python、Node.js、R、Go、Shell 等。以下是 Kestra 插件如何增强你的工作流：

- **随处运行：**
  - **本地或远程执行：** 可在本地机器、通过 SSH 的远程服务器上执行任务，或使用 [任务运行器](https://kestra.io/docs/task-runners) 扩展到无服务器容器。
  - **Docker 与 Kubernetes 支持：** 无缝运行 Docker 容器或启动 Kubernetes 作业以处理计算密集型负载。

- **使用任意语言编码：**
  - **脚本支持：** 使用你偏好的编程语言编写脚本。Kestra 支持 Python、Node.js、R、Go、Shell 等，便于集成现有代码库和部署模式。
  - **灵活的自动化：** 执行 shell 命令、运行 SQL 查询连接各种数据库，或发送 HTTP 请求与 API 交互。

- **事件驱动与实时处理：**
  - **实时触发器：** 实时响应来自外部系统的事件，例如文件到达、消息总线（Kafka、Redis、Pulsar、AMQP、MQTT、NATS、AWS SQS、Google Pub/Sub、Azure Event Hubs）中的新消息等。
  - **自定义事件：** 定义自定义事件，根据特定条件或外部信号触发流程，实现高度响应的工作流。

- **云集成：**
  - **AWS、Google Cloud、Azure：** 与各种云服务集成，交互存储解决方案、消息系统、计算资源等。
  - **大数据处理：** 使用 Apache Spark 等工具运行大数据处理任务，或与 Google BigQuery 等分析平台交互。

- **监控与通知：**
  - **保持信息同步：** 向 Slack 频道发送消息、发送电子邮件通知，或在 PagerDuty 中触发警报，让你的团队随时了解工作流状态。

Kestra 的插件生态系统持续扩展，允许你根据具体需求定制平台。无论你是编排复杂的数据流水线、跨多个环境自动化脚本，还是集成云服务，很可能已有插件可以协助。如果没有，你也可以 [开发自己的插件](https://kestra.io/docs/plugin-developer-guide/) 来扩展 Kestra 的功能。

🧑‍💻 **注意：** 这只是 Kestra 插件功能的一瞥。请访问我们的 [插件页面](https://kestra.io/plugins) 查看完整列表。

---

## 📚 关键概念

- **流程（Flows）：** Kestra 中的核心单元，表示由任务组成的工作流。
- **任务（Tasks）：** 工作的独立单元，例如运行脚本、移动数据或调用 API。
- **命名空间（Namespaces）：** 用于组织和隔离流程的逻辑分组。
- **触发器（Triggers）：** 启动流程执行的调度或事件。
- **输入与变量（Inputs & Variables）：** 传递给流程和任务的参数和动态数据。

---

## 🎨 可视化构建工作流

Kestra 提供了一个直观的 UI，允许你交互式地构建和可视化你的工作流：

- **拖放界面：** 从拓扑编辑器中添加和重新排列任务。
- **实时验证：** 对工作流的语法和结构提供即时反馈，以便尽早发现错误。
- **自动补全：** 输入时提供智能建议，快速编写流程代码并避免语法错误。
- **实时拓扑视图：** 以有向无环图（DAG）形式查看你的工作流，并实时更新。

---

## 🔧 可扩展且开发者友好

### 插件开发

创建自定义插件以扩展 Kestra 的功能。请查看我们的 [插件开发指南](https://kestra.io/docs/plugin-developer-guide/) 开始。

### 基础设施即代码

- **版本控制：** 将你的流程存储在 Git 仓库中。
- **CI/CD 集成：** 使用 CI/CD 流水线自动化部署流程。
- **Terraform 提供商：** 使用 [官方 Terraform 提供商](https://kestra.io/docs/terraform/) 管理 Kestra 资源。

---

## 🌐 加入社区

保持联系并获取支持：

- **Slack：** 加入我们的 [Slack 社区](https://kestra.io/slack) 提问和分享想法。
- **LinkedIn：** 在 [LinkedIn](https://www.linkedin.com/company/kestra/) 上关注我们 —— 除了 Slack 和 GitHub，这是我们分享更新和产品公告的主要渠道。
- **YouTube：** 订阅我们的 [YouTube 频道](https://www.youtube.com/@kestra-io) 获取教育视频内容。我们每周都会发布新视频！
- **X：** 如果你仍在使用 X，请关注我们 [X](https://x.com/kestra_io)。

---

## 🤝 贡献

我们欢迎任何形式的贡献！

- **报告问题：** 发现 bug 或有功能建议？在 [GitHub 上提交问题](https://github.com/kestra-io/kestra/issues)。
- **贡献代码：** 查看我们的 [贡献者指南](https://kestra.io/docs/getting-started/contributing) 获取入门指南，并查看我们的 [适合新手的问题](https://go.kestra.io/contributing)。
- **开发插件：** 使用我们的 [插件开发指南](https://kestra.io/docs/plugin-developer-guide/) 构建和分享插件。
- **参与文档贡献：** 编辑或更新我们的 [文档](https://github.com/kestra-io/docs)，帮助我们保持文档质量。

---

## 📄 许可证

Kestra 使用 Apache 2.0 许可证 © [Kestra Technologies](https://kestra.io)。

---

## ⭐️ 保持关注

给我们的仓库加星标，以了解最新功能和更新！

[![Star the Repo](https://kestra.io/star.gif)](https://github.com/kestra-io/kestra)

---

感谢你考虑使用 Kestra 进行工作流编排。我们期待看到你将构建什么！