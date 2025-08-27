以下是你提供的Markdown内容的中文翻译，保持了原始格式和结构：

---

[![Docker Image Build and Push to Dockerhub - CI/CD](https://github.com/KlausSchaefers/quant-ux/actions/workflows/docker.yml/badge.svg)](https://github.com/KlausSchaefers/quant-ux/actions/workflows/docker.yml)

# Quant-UX - 原型设计、测试与学习

Quant UX 是一个用于快速测试设计并获取数据驱动洞察的研究、可用性与原型设计工具。  
本仓库包含前端代码。你可以在 https://quant-ux.com/#/ 找到可用的演示版本。

![Alt text](docs/release.png?raw=true "Quant-UX 预览")

## 开发环境搭建
### 前提条件
```
npm install
```

### 在主机上本地运行

#### 编译并热加载用于开发
```
npm run serve
```

#### 编译并压缩用于生产环境
```
npm run build
```

#### 运行单元测试
```
npm run test:unit
```

#### 检查并修复文件
```
npm run lint
```

### 在 Docker 容器中开发
如果你想通过 Docker 来进行开发，可以使用以下命令构建开发镜像：
```bash
make build-dev
```
这将创建一个标签为 `quant-ux` 的 Docker 镜像。你可以在 docker-compose 文件中将 `klausenschaefersinho/quant-ux` 替换为新构建的 `quant-ux` 镜像。替换镜像后请记得挂载源代码。

如果你使用的是提供的 `docker/docker-compose.yml` 文件，可以简单地在 qux-fe 服务中添加以下卷挂载：
```yml
    volumes:
      - ../src:/home/node/src
```

然后你可以使用以下 Makefile 命令快速设置和销毁 Docker 环境：
```bash
# docker compose up - 指向 docker/docker-compose.yml
make up

# docker compose down - 指向 docker/docker-compose.yml
make down
```

# 安装

最简单的启动并运行你自己的 Quant-UX 安装方式是使用 [Brian McGonagill](https://github.com/bmcgonag) 提供的预构建 Docker 镜像。你可以在 https://github.com/bmcgonag/quant-ux-docker/ 找到相关仓库和安装说明。

## 手动安装

Quant-UX 包含两个组件：前端（本包）和后端（qux-java）。前端需要安装 Node.js (> 12)，后端需要 MongoDB、邮件服务器（SMTP）和 Java (> 1.8)。前端自带一个小型 Web 服务器，其中还包含一个代理，用于将所有请求重定向到正确的后端。

## Docker

启动你自己的 Quant-UX 安装最简单的方式是使用 Docker 镜像。

1) 创建一个 docker compose 文件 (`docker-compose.yaml`) 并设置环境变量。

```yaml
version: '3'

services:
  mongo:
    restart: always
    container_name: quant-ux-mongo
    image: mongo
    volumes:
      - ./data:/data/db        # 左边为宿主机存储路径，右边为容器内路径
  qux-fe:
    restart: always
    container_name: quant-ux-frontend
    image: klausenschaefersinho/quant-ux
    environment:
      - QUX_PROXY_URL=http://quant-ux-backend:8080        # 前端用于与后端通信的路径
      - QUX_AUTH=qux
      - QUX_KEYCLOAK_REALM=
      - QUX_KEYCLOAK_CLIENT=
      - QUX_KEYCLOAK_URL=
      - QUX_WS_URL=ws://127.0.0.1:8086        # 外部访问时请更改为 WebSocket 服务器地址
    links:
      - mongo
      - qux-be
    ports:
      - 8082:8082        # 如果宿主机已占用 8082 端口，请更改左侧端口号
    depends_on:
      - qux-be
  qux-be:
    restart: always
    container_name: quant-ux-backend
    image: klausenschaefersinho/quant-ux-backend
    volumes:
      - ./quant-ux-data:/app-data
    environment:
      - QUX_HTTP_HOST=http://quant-ux-frontend:8082   # 用于邮件中的 URL，例如密码重置
      - QUX_HTTP_PORT=8080  # 后端使用的端口
      - QUX_MONGO_DB_NAME=quantux  # MongoDB 中的数据库/集合名称
      - QUX_MONGO_TABLE_PREFIX=quantux  # MongoDB 中的表/文档前缀
      - QUX_MONGO_CONNECTION_STRING=mongodb://quant-ux-mongo:27017 # 假设你的 MongoDB 容器在 docker-compose 文件中名为 "quant-ux-mongo"
      - QUX_MAIL_USER=mail_admin@example.com        # SMTP 邮箱用户名
      - QUX_MAIL_PASSWORD=sTr0ngPa55w0Rd        # SMTP 邮箱密码
      - QUX_MAIL_HOST=mail.example.com        # SMTP 邮箱服务器地址
      - QUX_JWT_PASSWORD=some-long-string-of-mix-case-chars-and-nums        # 请设置一个强 JWT 密钥
      - QUX_IMAGE_FOLDER_USER=/app-data/qux-images        # 该文件夹应映射到卷中
      - QUX_IMAGE_FOLDER_APPS=/app-data/qux-image-apps        # 该文件夹应映射到卷中
      - TZ=America/Chicago        # 更改为你的时区
      - QUX_AUTH_SERVICE=qux
      - QUX_KEYCLOAK_SERVER= # Keycloak 主机和端口
      - QUX_KEYCLOAK_REALM=
      - QUX_USER_ALLOW_SIGNUP=true # 设置为 false 以禁止用户注册
      - QUX_USER_ALLOWED_DOMAINS=* # 逗号分隔的域名列表，例如 'my-server.com' 或 '*' 表示所有域名
    depends_on:
      - mongo
  qux-ws:
    restart: always
    container_name: quant-ux-websocket-server
    image: klausenschaefersinho/quant-ux-websocket
    environment:
      - QUX_SERVER=http://quant-ux-backend:8080/
      - QUX_SERVER_PORT=8086
    ports:
      - 8086:8086
    links:
      - qux-be
    depends_on:
      - qux-be
```

请务必更新 `QUX_JWT_PASSWORD` 环境变量以确保安装安全。  
同时更新 `QUX_HTTP_HOST`、`QUX_MAIL_USER`、`QUX_MAIL_PASSWORD` 和 `QUX_MAIL_HOST` 以确保邮件功能正常。

2) 使用以下命令启动容器：

```bash
docker compose up
```

## 一键部署

### Elestio
你可以通过几次点击和最小配置，在任意云服务提供商上部署 Quant UX 实例。

[![Deploy on Elestio](https://elest.io/images/logos/deploy-to-elestio-btn.png)](https://elest.io/open-source/quant-ux)

### RepoCloud.io
你可以通过一键部署在 RepoCloud 上部署 Quant UX 实例。

[![Deploy](https://d16t0pc4846x52.cloudfront.net/deploylobe.svg)](https://repocloud.io/details/?app_id=302)

## Kubernetes

你可以在以下地址找到 Kubernetes 配置：https://github.com/engmsilva/quant-ux-k8s/tree/master/k8s

### 后端

- 安装 MongoDB (> 4.4)

- 安装 Java (1.8)

- 克隆后端代码

```
git clone https://github.com/KlausSchaefers/qux-java.git
```

- release 文件夹中已包含编译好的后端版本

- 编辑 matc.conf 文件以配置正确的 MongoDB 和邮件服务器信息。更多详情请参考：https://github.com/KlausSchaefers/qux-java

- 启动服务器，或在 Linux 中作为服务安装

```
java -jar release/matc.jar -Xmx2g -conf matc.conf -instances 1
```

### 前端

- 安装 Node.js (> 12)

- 克隆仓库

```
git clone https://github.com/KlausSchaefers/quant-ux.git
```

- 安装依赖

```
npm install
```

- 构建

```
npm run build
```

### 配置前端

- 设置代理服务器地址为环境变量

```
export QUX_PROXY_URL=https://your.quant-ux.server.com // 后端主机地址

export QUX_WS_URL= wss.quant-ux.server.com // WebSocket 服务器地址
```

- 启动

```
node server/start.js
```

### 反向代理

现在你应该已经有一个运行中的系统，但尚未启用安全保护。建议使用 NGINX 反向代理来处理 SSL。

- https://www.scaleway.com/en/docs/tutorials/nginx-reverse-proxy/

你可以使用 https://letsencrypt.org/ 创建 SSL 证书