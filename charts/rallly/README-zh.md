<div align="center">

<img src="./assets/images/logo-color.svg" width="200px" alt="Rallly" />

</div>
<br />
<div align="center">

[![Actions 状态](https://github.com/lukevella/rallly/actions/workflows/ci.yml/badge.svg)](https://github.com/lukevella/rallly/actions)
[![Crowdin](https://badges.crowdin.net/rallly/localized.svg)](https://crowdin.com/project/rallly)
[![许可证: AGPL v3](https://img.shields.io/badge/许可证-AGPL_v3-orange.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![Discord](https://img.shields.io/badge/-加入聊天-7289DA?logo=discord&logoColor=white)](https://discord.gg/uzg4ZcHbuM)
[![捐赠](https://img.shields.io/badge/-使用Paypal捐赠-white?logo=paypal)](https://www.paypal.com/donate/?hosted_button_id=7QXP2CUBLY88E)

</div>

![截图](https://github.com/user-attachments/assets/baafea52-c4da-43bb-96ef-50840f1c0c03)

与朋友、同事和团队安排小组会议。创建会议投票，根据参与者的可用时间找到最佳的会议日期和时间。节省时间，避免来回邮件沟通。

本项目使用 [Next.js](https://github.com/vercel/next.js/)、[Prisma](https://github.com/prisma/prisma)、[tRPC](https://github.com/trpc/trpc) 和 [TailwindCSS](https://github.com/tailwindlabs/tailwindcss) 构建。

## 自托管

如需了解如何运行你自己的 Rallly 实例，请查看 [自托管文档](https://support.rallly.co/self-hosting)。

## 本地安装

以下是在本地开发环境中运行项目的步骤：

1. 克隆仓库并进入项目目录

   ```bash
   git clone https://github.com/lukevella/rallly.git
   cd rallly
   ```

2. 安装依赖项

   ```bash
   pnpm install
   ```

3. 配置环境变量

   通过复制 `.env.development` 创建 `.env` 文件。你可以在此文件中设置你的[配置选项](https://support.rallly.co/self-hosting/configuration-options)。

   ```bash
   cp .env.development .env
   ```

   **注意：** `.env.development` 文件已预配置了开发环境的默认值。本地开发时可直接使用这些默认值。

4. 生成 Prisma 客户端

   ```bash
   pnpm db:generate
   ```

5. 设置数据库

   你需要安装并运行 [Docker](https://docs.docker.com/get-docker/)，以便使用提供的 docker-compose 文件启动数据库。

   启动数据库：

   ```bash
   pnpm docker:up
   ```

   接下来运行以下命令来初始化数据库：

   ```bash
   pnpm db:reset
   ```

   此操作将：

   - 删除现有数据库（如果存在）
   - 运行迁移脚本以创建新的数据库结构
   - 使用测试用户和随机数据填充数据库

6. 启动 Next.js 服务器

   ```bash
   pnpm dev
   ```

## 贡献者

请阅读我们的 贡献指南 了解如何为本项目做贡献。

### 翻译者 🌐

你可以通过阅读我们的 [翻译者指南](https://support.rallly.co/contribute/translations) 来帮助将 Rallly 翻译成其他语言。

## 许可证

Rallly 遵循 GNU Affero 通用公共许可证第 3 版（AGPLv3）或其后续版本。详情请参阅 LICENSE 文件。

## 赞助商

感谢以下赞助商对本项目的资助。

<a href="https://github.com/coderabbitai" target="_blank"><img src="https://avatars.githubusercontent.com/u/132028505?s=200&v=4" width="48" height="48" /></a>&nbsp;
<a href="https://github.com/cpnielsen" target="_blank"><img src="https://avatars.githubusercontent.com/u/1258576?v=4" width="48" height="48" /></a>&nbsp;
<a href="https://github.com/iamericfletcher" target="_blank"><img src="https://avatars.githubusercontent.com/u/64165327?v=4" width="48" height="48" /></a>&nbsp;
<a href="https://github.com/arcticFox-git" target="_blank"><img src="https://avatars.githubusercontent.com/u/86988982?v=4" width="48" height="48" /></a>&nbsp;
<a href="https://github.com/zakwear" target="_blank"><img src="https://avatars.githubusercontent.com/u/55545774?v=4" width="48" height="48" /></a>&nbsp;
<a href="https://github.com/jonnymarshall" target="_blank"><img src="https://avatars.githubusercontent.com/u/42963069?v=4" width="48" height="48" /></a>&nbsp;
<a href="https://github.com/maximelouet" target="_blank"><img src="https://avatars.githubusercontent.com/u/8074940?v=4" width="48" height="48" /></a>&nbsp;

[成为赞助商 &rarr;](https://github.com/sponsors/lukevella)

同时感谢以下公司对本项目的支持。

<p>
<a href="https://appwrite.io?utm_source=rallly"><img src="./assets/images/appwrite.svg" alt="appwrite" height="24" /></a>&nbsp;&nbsp;&nbsp;<!--
--><a href="https://vercel.com/?utm_source=rallly&utm_campaign=oss"><img src="./assets/images/vercel-logotype-dark.svg#gh-light-mode-only" alt="由 Vercel 提供支持" height="24" /></a>&nbsp;&nbsp;&nbsp;<!--
--><a href="https://ura.design?utm_source=rallly"><img height="24" alt="Ura Design" src="./assets/images/ura-logo-blue.svg"></a>
</p>
<p>
<a href="https://m.do.co/c/f91efc9c9e50"><img src="./assets/images/digitalocean-logo.svg" alt="Digital Ocean" height="24" /></a>&nbsp;&nbsp;&nbsp;<!--
--><a href="https://sentry.io?utm_source=rallly"><img src="./assets/images/sentry.svg" alt="Sentry" height="24" /></a>&nbsp;&nbsp;&nbsp;<!--
--><a href="https://cloudron.io?utm_source=rallly"><img src="./assets/images/cloudron-logo.svg" alt="Cloudron" height="30"></a>&nbsp;&nbsp;&nbsp;<!--
--><a href="https://featurebase.app?utm_source=rallly"><img src="./assets/images/featurebase.svg" alt="Featurebase" height="28"></a>
</p>