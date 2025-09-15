# Morphic

一个由 AI 驱动、具备生成式 UI 的搜索引擎。

![capture](/public/screenshot-2025-05-04.png)

## 🗂️ 概览

- 🛠 功能
- 🧱 技术栈
- 🚀 快速开始
- 🌐 部署
- 🔎 搜索引擎
- 💙 赞助商
- 👥 贡献指南
- 📄 许可证

📝 探索 AI 生成的文档：[DeepWiki](https://deepwiki.com/miurla/morphic)

## 🛠 功能

### 核心功能

- 使用 GenerativeUI 的 AI 驱动搜索
- 自然语言问题理解
- 支持多个搜索提供商（Tavily、SearXNG、Exa）
- 从 UI 中选择模型（可在可用 AI 模型之间切换）
  - 支持推理模型并显示思考过程

### 认证功能

- 基于 [Supabase Auth](https://supabase.com/docs/guides/auth) 的用户认证
- 支持邮箱/密码注册与登录
- 支持通过 Google 进行社交登录

### 聊天与历史记录

- 聊天历史功能（可选）
- 分享搜索结果（可选）
- 支持 Redis（本地/Upstash）

### AI 提供商

支持以下 AI 提供商：

- OpenAI（默认）
- Google Generative AI
- Azure OpenAI
- Anthropic
- Ollama
- Groq
- DeepSeek
- Fireworks
- xAI（Grok）
- OpenAI 兼容接口

模型配置位于 `public/config/models.json`。每个模型都需要在环境变量中设置相应的 API 密钥。详情请参阅 配置指南。

### 搜索能力

- 支持 URL 特定搜索
- 支持视频搜索（可选）
- 集成 SearXNG：
  - 可自定义搜索深度（基础/高级）
  - 可配置搜索引擎
  - 可调整结果数量限制
  - 支持安全搜索选项
  - 支持自定义时间范围过滤

### 其他功能

- 支持 Docker 部署
- 浏览器搜索引擎集成

## 🧱 技术栈

### 核心框架

- [Next.js](https://nextjs.org/) - 使用 App Router 和 React Server Components
- [TypeScript](https://www.typescriptlang.org/) - 类型安全
- [Vercel AI SDK](https://sdk.vercel.ai/docs) - 文本流 / 生成式 UI

### 认证与授权（更新分类）

- [Supabase](https://supabase.com/) - 用户认证和后端服务

### AI 与搜索

- [OpenAI](https://openai.com/) - 默认 AI 提供商（可选：Google AI、Anthropic、Groq、Ollama、Azure OpenAI、DeepSeek、Fireworks）
- [Tavily AI](https://tavily.com/) - 默认搜索提供商
- 其他提供商：
  - [SearXNG](https://docs.searxng.org/) - 自托管搜索
  - [Exa](https://exa.ai/) - 神经搜索

### 数据存储

- [Upstash](https://upstash.com/) - 无服务器 Redis
- [Redis](https://redis.io/) - 本地 Redis 选项

### UI 与样式

- [Tailwind CSS](https://tailwindcss.com/) - 实用优先的 CSS 框架
- [shadcn/ui](https://ui.shadcn.com/) - 可复用组件
- [Radix UI](https://www.radix-ui.com/) - 无样式、可访问的组件
- [Lucide Icons](https://lucide.dev/) - 美观且一致的图标

## 🚀 快速开始

### 1. Fork 并克隆仓库

将仓库 Fork 到你的 GitHub 账户，然后运行以下命令克隆仓库：

```bash
git clone git@github.com:[YOUR_GITHUB_ACCOUNT]/morphic.git
```

### 2. 安装依赖

```bash
cd morphic
bun install
```

### 3. 配置环境变量

```bash
cp .env.local.example .env.local
```

在 `.env.local` 中填写所需的环境变量：

```bash
# 核心功能必需
OPENAI_API_KEY=     # 从 https://platform.openai.com/api-keys 获取
TAVILY_API_KEY=     # 从 https://app.tavily.com/home 获取
```

关于可选功能的配置（Redis、SearXNG 等），请参阅 CONFIGURATION.md

### 4. 本地运行应用

#### 使用 Bun

```bash
bun dev
```

#### 使用 Docker

```bash
docker compose up -d
```

在浏览器中访问 http://localhost:3000。

## 🌐 部署

你可以使用 Vercel、Cloudflare Pages 或 Docker 部署你自己的 Morphic 实例。

### Vercel

[![使用 Vercel 部署](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fmiurla%2Fmorphic&env=OPENAI_API_KEY,TAVILY_API_KEY,UPSTASH_REDIS_REST_URL,UPSTASH_REDIS_REST_TOKEN)

### Docker 预构建镜像

GitHub Container Registry 提供了预构建的 Docker 镜像：

```bash
docker pull ghcr.io/miurla/morphic:latest
```

你可以配合 docker-compose 使用：

```yaml
services:
  morphic:
    image: ghcr.io/miurla/morphic:latest
    env_file: .env.local
    ports:
      - '3000:3000'
    volumes:
      - ./models.json:/app/public/config/models.json # 可选：覆盖默认模型配置
```

默认模型配置文件位于 `public/config/models.json`。对于 Docker 部署，你可以在 `.env.local` 同级目录创建 `models.json` 文件以覆盖默认配置。

## 🔎 搜索引擎

### 在浏览器中设置搜索引擎

如果你想在浏览器中将 Morphic 作为搜索引擎使用，请按照以下步骤操作：

1. 打开浏览器设置。
2. 进入“搜索引擎”设置部分。
3. 选择“管理搜索引擎和网站搜索”。
4. 在“网站搜索”下，点击“添加”。
5. 填写以下字段：
   - **搜索引擎名称**：Morphic
   - **快捷方式**：morphic
   - **包含 %s 的查询 URL**：`https://morphic.sh/search?q=%s`
6. 点击“添加”保存新的搜索引擎。
7. 在网站搜索列表中找到“Morphic”，点击右侧的三个点，选择“设为默认”。

这样你就可以在浏览器中将 Morphic 设为默认搜索引擎。

## 💙 赞助商

本项目由以下赞助商支持：

<a href="https://vercel.com/oss">
  <img alt="Vercel OSS Program" src="https://vercel.com/oss/program-badge.svg" />
</a>

## 👥 贡献指南

我们欢迎对 Morphic 的各种贡献！无论是提交 bug 报告、功能请求，还是提交 Pull Request，我们都十分感激。

请参阅我们的 贡献指南 获取以下信息：

- 如何提交问题
- 如何提交 Pull Request
- 提交信息规范
- 开发环境搭建

## 📄 许可证

本项目采用 Apache License 2.0 许可证 — 详情请参阅 LICENSE 文件。