<div align="center">

# Botpress Cloud

[![Discord](https://img.shields.io/badge/Join_Community-white?color=7289da&label=Discord&labelColor=6a7ec1&logo=discord&logoColor=FFF)](https://discord.gg/botpress)
[![YouTube Subscribe](https://img.shields.io/badge/YouTube-red?logo=youtube&logoColor=white)](https://www.youtube.com/c/botpress)
[![Documentation](https://img.shields.io/badge/Documentation-blue?logo=typescript&logoColor=white)](https://docs.botpress.cloud)
[![@botpress/sdk](https://img.shields.io/badge/@botpress%2fsdk-black?logo=npm)](https://www.npmjs.com/package/@botpress/sdk)
[![@botpress/cli](https://img.shields.io/badge/@botpress%2fcli-black?logo=npm)](https://www.npmjs.com/package/@botpress/cli)

[Botpress](https://botpress.com) 是用于构建由 OpenAI 驱动的**下一代聊天机器人**和助手的终极平台。立即为您的项目或业务快速构建令人惊叹的助手。

[快速入门](#getting-started) •
[Cloud](https://app.botpress.cloud) •
[文档](https://botpress.com/docs) •
[集成](#integrations) •
[插件](#plugins)

<img src="https://user-images.githubusercontent.com/10071388/248040379-8aee1b03-c483-4040-8ee0-741554310e88.png" width="800">

</div>

## 本仓库

本仓库包含：

- [**集成**](#integrations) – 所有 Botpress 维护的 [Botpress Hub](https://app.botpress.cloud/hub) 上的公开集成
- [**开发工具**](#devtools) – 所有 Botpress Cloud 开发工具（CLI、SDK、API 客户端）
- [**机器人**](#bots) – 仅使用 SDK 和 CLI 创建的“代码即机器人”的示例
- [**插件**](#plugins) – 所有 [Botpress Studio](https://studio.botpress.cloud) 上的插件 **(即将推出)**

## 贡献

我们非常欢迎社区的贡献！

我们欢迎与此仓库中包含的任何代码相关的 Pull Request 和 Issue。更多详情请参见 [本仓库](#this-repository) 部分。

对于与 Botpress Cloud 相关的 bug 或功能请求，您可以在本仓库创建一个 issue，但请注意，通过 [Discord](https://discord.gg/botpress) 与我们联系可以获得更快的响应！

对于与本地部署的 Botpress v12 相关的任何问题，请参见 [Botpress v12 仓库](https://github.com/botpress/v12)。

## 集成

[`/integrations`](./integrations) 文件夹包含我们所有公开且开源的集成。我们邀请社区为我们的集成做出贡献，或向 [Botpress Hub](https://app.botpress.cloud/hub) 发布您自己的集成。

### 集成开发

要开发一个集成，请先安装 [Botpress CLI](https://www.npmjs.com/package/@botpress/cli)：

```sh
npm install -g @botpress/cli # 适用于 npm
yarn global add @botpress/cli # 适用于 yarn
pnpm install -g @botpress/cli # 适用于 pnpm
```

然后，在任意目录中创建一个新的集成：

```sh
bp init
```

该命令将根据提供的模板之一生成一个集成。

_此步骤可以在您选择的任意目录和 Git 仓库中执行，无需 fork 此仓库即可创建集成。_

随后，您可以分别在 `integration.definition.ts` 和 `src/index.ts` 文件中修改集成的定义和实现。

如需了解如何开发集成的更多信息，请参阅[文档](https://botpress.com/docs/getting-started-1)。

### 集成部署

要尝试您的集成，可以使用 Botpress CLI 将其当前版本部署到您的工作区：

```sh
bp deploy
```

这会将您的集成当前版本部署到您的工作区，并使其对所有机器人可用。如果该版本已部署，则会更新它；否则将创建一个新版本。

默认情况下，所有集成仅对部署它们的工作区可见。当您准备好与社区分享您的版本时，可以运行以下命令使其公开：

```sh
bp deploy --public
```

这将使您的集成在 [Botpress Hub](https://app.botpress.cloud/hub) 上对所有 Botpress 用户可见。一旦您的集成版本公开，将无法再次更新。

## 机器人

[`/bots`](./bots) 文件夹包含仅使用客户端、SDK 和 CLI 创建的“代码即机器人”的示例。

**这不是推荐的构建机器人方式**，也不能替代 Botpress Studio。

但对于希望以更编程化方式构建机器人的资深开发者来说，这可能很有用。

Botpress 团队内部也使用它，因为 Studio 和 SDK 都使用相同的底层原语。

## 插件

即将推出。

## 开发工具

| **包**                                                          | **描述**                                         | **文档**                                           | **代码**               |
| -------------------------------------------------------------------- | ------------------------------------------------------- | -------------------------------------------------- | ---------------------- |
| [`@botpress/cli`](https://www.npmjs.com/package/@botpress/cli)       | 构建、部署和管理机器人、集成和插件 | [文档](https://botpress.com/docs/integration/cli/) | [代码](./packages/cli) |
| [`@botpress/client`](https://www.npmjs.com/package/@botpress/client) | 类型安全的客户端，用于调用 Botpress API          | [文档]()                                           | [代码]()               |
| [`@botpress/sdk`](https://www.npmjs.com/package/@botpress/sdk)       | 用于构建集成的 SDK                       | [文档]()                                           | [代码]()               |

## 本地开发

### 前提条件

开发环境需要安装以下工具：

- [`git`](https://git-scm.com/)：Git 是一个免费且开源的分布式版本控制系统。
- [`node`](https://nodejs.org/en/)：Node.js® 是基于 Chrome V8 JavaScript 引擎构建的 JavaScript 运行时。
- [`pnpm`](https://pnpm.io/)：PNPM 是一个快速且节省磁盘空间的包管理器。

#### Windows 特定前提条件

- [Microsoft Visual C++ Redistributable for Visual Studio 2015-2022](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist#visual-studio-2015-2017-2019-and-2022)

### 从源码构建

```sh
# 克隆仓库
git clone https://github.com/botpress/botpress.git
cd botpress

# 安装依赖
pnpm install

# 构建所有包
pnpm run build

# 运行检查
pnpm run check
```

## 许可协议

本仓库中的所有包均为开源软件，采用 [MIT License](LICENSE) 授权。通过在此仓库中贡献代码，您也同意以该许可证发布您的代码。

让我们一起构建聊天机器人开发的未来！🤖🚀