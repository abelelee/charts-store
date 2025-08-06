<a href="https://zerodha.tech"><img src="https://zerodha.tech/static/images/github-badge.svg" align="right" /></a>

[![listmonk-logo](https://user-images.githubusercontent.com/547147/231084896-835dba66-2dfe-497c-ba0f-787564c0819e.png)](https://listmonk.app)

listmonk 是一个独立、自托管的新闻通讯和邮件列表管理工具。它速度快、功能丰富，并被打包为单个二进制文件。它使用 PostgreSQL 数据库作为数据存储。

[![listmonk-dashboard](https://github.com/user-attachments/assets/689b5fbb-dd25-4956-a36f-e3226a65f9c4)](https://listmonk.app)

更多信息请访问 [listmonk.app](https://listmonk.app)。查看 [**在线演示**](https://demo.listmonk.app)。

## 安装

### Docker

最新镜像可在 DockerHub 上 [`listmonk/listmonk:latest`](https://hub.docker.com/r/listmonk/listmonk/tags?page=1&ordering=last_updated&name=latest) 获取。  
下载并使用示例 [docker-compose.yml](https://github.com/knadh/listmonk/blob/master/docker-compose.yml) 文件。

```shell
# 将 compose 文件下载到当前目录。
curl -LO https://github.com/knadh/listmonk/raw/master/docker-compose.yml

# 在后台启动服务。
docker compose up -d
```

访问 `http://localhost:9000`

查看 [安装文档](https://listmonk.app/docs/installation)

__________________

### 二进制文件安装
- 下载 [最新版本](https://github.com/knadh/listmonk/releases) 并解压出 listmonk 可执行文件。
- 执行 `./listmonk --new-config` 生成 config.toml 文件。编辑该文件。
- 执行 `./listmonk --install` 来初始化 PostgreSQL 数据库（或使用 `--upgrade` 来升级已有数据库。升级操作是幂等的，多次执行不会产生副作用）。
- 运行 `./listmonk` 并访问 `http://localhost:9000`

查看 [安装文档](https://listmonk.app/docs/installation)
__________________


## 开发者
listmonk 是一款自由开源软件，采用 AGPLv3 许可证发布。如果您有兴趣参与贡献，请参考 [开发者环境搭建指南](https://listmonk.app/docs/developer-setup)。后端使用 Go 编写，前端使用 Vue 和 Buefy 构建 UI。

## 许可证
listmonk 遵循 AGPL v3 许可证。