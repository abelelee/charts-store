# 火焰（Flame）

![主页截图](.github/home.png)

## 描述

Flame 是你服务器上的自托管起始页。它的设计深受 [SUI](https://github.com/jeroenpardon/sui) 的启发（而且影响很大）。Flame 非常易于安装和使用。通过内置的编辑器，你可以直接在应用中快速搭建属于你自己的应用中心，无需手动编辑任何文件。

## 功能
- 📝 使用内置的图形界面编辑器，直接在应用中创建、更新和删除你的应用程序和书签
- 📌 将你喜爱的项目固定到主页，以便快速访问
- 🔍 集成搜索栏，支持本地过滤、11 个网页搜索引擎，以及自定义添加搜索引擎
- 🔑 认证系统，保护你的设置、应用和书签
- 🔨 提供数十种界面定制选项，包括支持自定义 CSS、15 个内置配色主题以及自定义主题构建器
- ☀️ 天气小部件，显示当前温度、云层覆盖情况和动态天气状态
- 🐳 Docker 集成，可自动根据容器标签识别并添加应用

## 安装

### 使用 Docker（推荐）

[Docker Hub 链接](https://hub.docker.com/r/pawelmalak/flame)

```sh
docker pull pawelmalak/flame

# 适用于 ARM 架构（例如 RaspberryPi）
docker pull pawelmalak/flame:multiarch

# 安装特定版本
docker pull pawelmalak/flame:2.0.0
```

#### 部署

```sh
# 运行容器
docker run -p 5005:5005 -v /path/to/data:/app/data -e PASSWORD=flame_password pawelmalak/flame
```

#### 构建镜像

```sh
# 仅构建 amd64 架构的镜像
docker build -t flame -f .docker/Dockerfile .

# 构建支持 amd64、armv7 和 arm64 的多架构镜像
# 构建过程中内存使用限制为 2GB 时可能失败，建议适当增加内存限制
docker buildx build \
  --platform linux/arm/v7,linux/arm64,linux/amd64 \
  -f .docker/Dockerfile.multiarch \
  -t flame:multiarch .
```

#### Docker-Compose

```yaml
version: '3.6'

services:
  flame:
    image: pawelmalak/flame
    container_name: flame
    volumes:
      - /path/to/host/data:/app/data
      - /var/run/docker.sock:/var/run/docker.sock # 可选，但 Docker 集成需要
    ports:
      - 5005:5005
    secrets:
      - password # 可选，但用于认证(1)
    environment:
      - PASSWORD=flame_password
      - PASSWORD_FILE=/run/secrets/password # 可选，但用于认证(1)
    restart: unless-stopped

# 可选，但用于 Docker secrets (1)
secrets:
  password:
    file: /path/to/secrets/password
```

##### Docker Secrets

所有环境变量都可以通过在变量名后添加 `_FILE` 来覆盖。例如，你可以使用 `PASSWORD_FILE` 来传入一个 Docker secret，而不是使用 `PASSWORD`。如果同时设置了 `PASSWORD` 和 `PASSWORD_FILE`，Docker secret 将优先使用。

```bash
# ./secrets/flame_password
my_custom_secret_password_123

# ./docker-compose.yml
secrets:
  password:
    file: ./secrets/flame_password
```

#### Skaffold

```sh
# 使用 skaffold
skaffold dev
```

### 不使用 Docker

请参考 Wiki 中的说明：[不使用 Docker 安装](https://github.com/pawelmalak/flame/wiki/Installation-without-docker)

## 开发

### 技术栈

- 后端
  - Node.js + Express
  - Sequelize ORM + SQLite
- 前端
  - React
  - Redux
  - TypeScript
- 部署
  - Docker
  - Kubernetes

### 创建开发环境

```sh
# 克隆仓库
git clone https://github.com/pawelmalak/flame
cd flame

# 仅需运行一次
npm run dev-init

# 启动后端和前端开发服务器
npm run dev
```

## 截图

![应用截图](.github/apps.png)

![书签截图](.github/bookmarks.png)

![设置截图](.github/settings.png)

![主题截图](.github/themes.png)

## 使用说明

### 认证

访问 [项目 Wiki](https://github.com/pawelmalak/flame/wiki/Authentication) 了解更多关于认证的信息

### 搜索栏

#### 搜索功能

默认的搜索设置是搜索你所有的应用和书签。如果你想使用特定的搜索引擎进行搜索，你需要在搜索词前加上对应的前缀。例如，使用 Google 搜索 "what is docker"，你可以输入：`/g what is docker`。

关于支持的搜索引擎列表、快捷方式及更多搜索功能，请访问 [项目 Wiki](https://github.com/pawelmalak/flame/wiki/Search-bar)。

### 设置天气模块

1. 从 [Weather API](https://www.weatherapi.com/pricing.aspx) 获取 API 密钥。
   > 免费计划每月允许 100 万次调用。Flame 每月调用次数少于 3000 次。
2. 获取你所在位置的经纬度。你可以从 [latlong.net](https://www.latlong.net/convert-address-to-lat-long.html) 获取。
3. 输入并保存数据。天气小部件现在将更新，并在主页上显示。

### Docker 集成

要使用 Docker 集成功能，每个容器必须包含以下标签：

```yml
labels:
  - flame.type=application # "app" 也可以
  - flame.name=My container
  - flame.url=https://example.com
  - flame.icon=icon-name # 可选，默认为 "docker"
# - flame.icon=custom 用于自定义图标上传
```

> 要使此功能生效，必须启用“使用 Docker API”选项。你可以在 设置 > Docker 中找到该选项。

你也可以在同一个标签中设置多个应用，使用分号 `;` 分隔。

```yml
labels:
  - flame.type=application
  - flame.name=First App;Second App
  - flame.url=https://example1.com;https://example2.com
  - flame.icon=icon-name1;icon-name2
```

如果你想使用远程 Docker 主机，请在目标主机上执行以下步骤：

- 打开文件 `/lib/systemd/system/docker.service`，查找 `ExecStart` 并修改其值：

```text
ExecStart=/usr/bin/dockerd -H tcp://0.0.0.0:${PORT} -H unix:///var/run/docker.sock
```

> 上述命令将 Docker 引擎绑定到 Unix 套接字以及你选择的 TCP 端口。"0.0.0.0" 表示 Docker 引擎接受来自所有 IP 地址的连接。

- 重启守护进程和 Docker 服务：

```shell
sudo systemctl daemon-reload
sudo service docker restart
```

- 测试是否正常工作：

```shell
curl http://${IP}:${PORT}/version
```

### Kubernetes 集成

要使用 Kubernetes 集成功能，每个 Ingress 必须包含以下注解：

```yml
metadata:
  annotations:
  - flame.pawelmalak/type=application # "app" 也可以
  - flame.pawelmalak/name=My container
  - flame.pawelmalak/url=https://example.com
  - flame.pawelmalak/icon=icon-name # 可选，默认为 "kubernetes"
```

> 要使此功能生效，必须启用“使用 Kubernetes Ingress API”选项。你可以在 设置 > Docker 中找到该选项。

### 导入 HTML 书签（实验性功能）

- 要求
  - python3
  - pip 包：Pillow, beautifulsoup4
- 在运行脚本前请备份你的 `db.sqlite`！
- 已知问题：
  - 生成的图标有时不正确

```bash
pip3 install Pillow, beautifulsoup4

cd flame/.dev
python3 bookmarks_importer.py --bookmarks <书签.html路径> --data <Flame 数据文件夹路径>
```

### 自定义 CSS 和主题

请参阅项目 Wiki 中的 [自定义 CSS](https://github.com/pawelmalak/flame/wiki/Custom-CSS) 和 [使用 CSS 自定义主题](https://github.com/pawelmalak/flame/wiki/Custom-theme-with-CSS)。