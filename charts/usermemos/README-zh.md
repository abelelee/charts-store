# Memos

<img align="right" height="96px" src="https://www.usememos.com/logo-rounded.png" alt="Memos" />

一个现代、开源、自托管的知识管理和笔记记录平台，专为注重隐私的用户和组织设计。Memos 提供了一个轻量但功能强大的解决方案，支持全面的 Markdown 格式，便于跨平台访问，帮助您高效记录、整理和分享想法。

<div align="center">

[![首页](https://img.shields.io/badge/Home-www.usememos.com-blue)](https://www.usememos.com)
[![文档](https://img.shields.io/badge/Docs-可用-green)](https://www.usememos.com/docs)
[![在线演示](https://img.shields.io/badge/Demo-立即体验-orange)](https://demo.usememos.com/)
[![博客](https://img.shields.io/badge/Blog-阅读更多-lightblue)](https://www.usememos.com/blog)

[![Docker 下载量](https://img.shields.io/docker/pulls/neosmemo/memos.svg)](https://hub.docker.com/r/neosmemo/memos)
[![Docker 镜像大小](https://img.shields.io/docker/image-size/neosmemo/memos?sort=semver)](https://hub.docker.com/r/neosmemo/memos)
[![Discord](https://img.shields.io/badge/discord-聊天-5865f2?logo=discord&logoColor=f5f5f5)](https://discord.gg/tfPJa4UmAv)

</div>

![Memos 应用截图](https://www.usememos.com/demo.png)

## 目录

- 概述
- 主要特性
- 快速开始
- 安装方式
- 开发环境设置
- 贡献指南
- 许可证

## 概述

Memos 是一个轻量级、自托管的云笔记服务替代方案。它以隐私和性能为核心设计原则，为个人知识管理提供了一个全面的平台，同时不牺牲数据所有权或安全性。

## 主要特性

### 数据隐私与安全

- **完整数据所有权**：所有应用数据存储在您选择的本地数据库中
- **自托管架构**：完全掌控数据基础设施和访问策略
- **无外部依赖**：运行时无需第三方服务或云端连接

### 内容创建与管理

- **纯文本高效输入**：简洁的文本输入界面，支持即时保存
- **高级 Markdown 支持**：全面的 Markdown 渲染与语法高亮
- **富媒体集成**：支持图片、链接和嵌入内容

### 技术优势

- **高性能后端**：使用 Go 构建，资源利用高效且可扩展
- **现代化前端**：基于 React.js 的响应式用户界面
- **轻量级部署**：系统资源占用低，运行效率高
- **跨平台兼容性**：支持 Linux、macOS、Windows 和容器化环境

### 可定制性与扩展性

- **可配置界面**：支持自定义服务器品牌标识、主题和界面元素
- **API 优先设计**：提供完善的 RESTful API 文档，便于第三方集成
- **多数据库支持**：兼容 SQLite、PostgreSQL 和 MySQL 数据库

### 成本效益

- **开源许可**：采用 MIT 许可证，源代码完全开放
- **零许可费用**：无订阅费用、使用限制或付费高级版
- **社区驱动开发**：活跃的社区贡献和透明的开发流程

## 快速开始

### 前提条件

- 系统上已安装 [Docker](https://www.docker.com/) 或 Docker Compose
- 最低 512MB RAM 和 1GB 可用磁盘空间

### Docker 部署

使用 Docker 以生产模式部署 Memos：

```bash
# 创建数据目录
mkdir -p ~/.memos

# 运行 Memos 容器
docker run -d \
  --name memos \
  --restart unless-stopped \
  -p 5230:5230 \
  -v ~/.memos:/var/opt/memos \
  neosmemo/memos:stable
```

访问 `http://localhost:5230` 并完成初始设置流程。

### Docker Compose 部署

对于高级配置，使用 Docker Compose：

```yaml
# docker-compose.yml
version: "3.8"
services:
  memos:
    image: neosmemo/memos:stable
    container_name: memos
    restart: unless-stopped
    ports:
      - "5230:5230"
    volumes:
      - ./data:/var/opt/memos
    environment:
      - MEMOS_MODE=prod
      - MEMOS_PORT=5230
```

使用以下命令部署：

```bash
docker-compose up -d
```

> **注意**：数据目录（`~/.memos/` 或 `./data/`）存储了所有应用数据，包括数据库、上传文件和配置。请确保将此目录纳入您的备份策略中。
>
> **平台兼容性**：上述命令针对类 Unix 系统（Linux、macOS）进行了优化。对于 Windows 部署，请参阅 [Windows 专用文档](https://www.usememos.com/docs/install/container-install#docker-on-windows)。

## 安装方式

Memos 支持多种安装方式，以适应不同的部署场景：

### 容器部署

- **Docker Hub**：官方镜像位于 `neosmemo/memos`
- **GitHub 容器注册表**：提供相同版本的替代镜像
- **Kubernetes**：提供 Helm 图表和 YAML 清单用于集群部署

### 二进制安装

- **预编译二进制文件**：可在 [发布页面](https://github.com/usememos/memos/releases) 获取适用于 Linux、macOS 和 Windows 的版本

### 源码安装

- **Go 编译**：使用 Go 1.24 或更高版本从源码编译
- **开发模式**：支持热重载的本地开发环境

详细安装说明请参阅 [完整安装指南](https://www.usememos.com/docs/install)。

## 开发环境设置

### 前提条件

- [Go 1.24](https://go.dev/) 或更高版本
- [Node.js 22+](https://nodejs.org/en) 和 [pnpm](https://pnpm.io/)
- [Git](https://git-scm.com/) 用于版本控制

### 后端开发

```bash
# 克隆仓库
git clone https://github.com/usememos/memos.git
cd memos

# 安装 Go 依赖
go mod download

# 运行后端服务器
go run ./bin/memos/main.go --mode dev --port 8081
```

### 前端开发

```bash
# 进入前端目录
cd web

# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev
```

开发服务器将在以下地址可用：

- 后端 API：`http://localhost:8081`
- 前端：`http://localhost:3001`

## 贡献指南

Memos 是一个开源项目，欢迎全球开发者、设计师和用户参与贡献。我们维护一个协作和包容的开发环境，重视质量、创新和社区反馈。

### 贡献方式

- **代码贡献**：修复 bug、实现新功能、优化性能
- **文档**：编写 API 文档、用户指南和技术规范
- **测试**：质量保证、测试用例开发和 bug 报告
- **本地化**：提供多语言和地区翻译支持
- **社区支持**：在 Discord、GitHub 讨论区和论坛中帮助用户

## 许可证

Memos 采用 MIT 许可证发布，为个人和商业用途提供最大灵活性。该许可证允许：

- **商业用途**：无需许可费用即可在商业环境中部署 Memos
- **修改**：根据特定需求修改和定制代码
- **分发**：分享修改版本，同时保留许可证声明
- **私有使用**：内部使用无需公开代码

完整的许可条款请参阅 LICENSE 文件。

## 项目状态

> **开发状态**：Memos 正在积极维护并持续开发中。虽然核心功能已经稳定并可用于生产环境，但用户应预期会有定期更新、功能添加以及随着项目演进而可能的破坏性变更。
>
> **版本兼容性**：我们尽可能保持数据存储和 API 接口的向后兼容性。对于重大版本升级，我们提供迁移指南。

## 支持与社区

- **文档**：[官方文档](https://www.usememos.com/docs)
- **社区交流**：[Discord 服务器](https://discord.gg/tfPJa4UmAv)
- **问题追踪**：[GitHub Issues](https://github.com/usememos/memos/issues)
- **讨论区**：[GitHub Discussions](https://github.com/usememos/memos/discussions)

[![Star 历史图](https://api.star-history.com/svg?repos=usememos/memos&type=Date)](https://star-history.com/#usememos/memos&Date)