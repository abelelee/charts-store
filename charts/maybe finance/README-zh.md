<img width="1190" alt="maybe_hero" src="https://github.com/user-attachments/assets/5ed08763-a9ee-42b2-a436-e05038fcf573" />

# Maybe：面向所有人的个人理财应用

> [!IMPORTANT]
> 本仓库已不再积极维护。您可以在我们的[最终版本发布说明](https://github.com/maybe-finance/maybe/releases/tag/v0.6.0)中了解更多相关信息。

## Maybe 的托管

Maybe 是一个功能完整的个人理财应用，可以通过 [Docker 自托管](docs/hosting/docker.md)。

## 分叉与署名

本仓库已不再维护。您可以根据 AGPLv3 协议自由分叉。为确保合规并避免商标问题：

- 请务必包含原始的 [AGPLv3 许可证](https://github.com/maybe-finance/maybe/blob/main/LICENSE)，并在您的 README 文件中明确声明您的分叉版本基于 Maybe Finance，但 **不隶属于或受 Maybe Finance Inc. 认可**。
- “Maybe” 是 Maybe Finance Inc. 的注册商标，因此在分叉的仓库中（或图标中）**不得** 使用该名称。

## 本地开发环境配置

**如果您是想 _自建托管_ Maybe 应用，请停止阅读此处。您应该[阅读这篇入门指南](docs/hosting/docker.md)。**

以下说明适用于希望为本项目贡献代码的开发者。

### 系统要求

- Ruby 版本请参见 `.ruby-version` 文件
- PostgreSQL >9.3（建议使用最新稳定版本）

克隆仓库后，基本的设置命令如下：

```sh
cd maybe
cp .env.local.example .env.local
bin/setup
bin/dev

# 可选地，加载演示数据
rake demo_data:default
```

然后访问 http://localhost:3000 查看应用。您可以使用以下凭据登录（由数据库种子数据生成）：

- 邮箱：`user@maybe.local`
- 密码：`password`

更多操作说明，请参考下方的指南。

### 配置指南

- [Mac 开发环境配置指南](https://github.com/maybe-finance/maybe/wiki/Mac-Dev-Setup-Guide)
- [Linux 开发环境配置指南](https://github.com/maybe-finance/maybe/wiki/Linux-Dev-Setup-Guide)
- [Windows 开发环境配置指南](https://github.com/maybe-finance/maybe/wiki/Windows-Dev-Setup-Guide)
- 开发容器 —— 请访问 [此指南](https://code.visualstudio.com/docs/devcontainers/containers) 了解更多详情

## 版权与许可

Maybe 遵循 [AGPLv3 许可证](https://github.com/maybe-finance/maybe/blob/main/LICENSE) 发布。  
“Maybe” 是 Maybe Finance, Inc. 的注册商标。