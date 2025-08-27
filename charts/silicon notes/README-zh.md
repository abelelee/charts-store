以下是你提供的Markdown内容的中文翻译，保留了原始格式：

---

[![集成测试](https://github.com/cu/silicon/actions/workflows/tests.yaml/badge.svg)](https://github.com/cu/silicon/actions/workflows/tests.yaml)

# 这到底是什么东西？！

Silicon Notes：一个轻量级、低摩擦的个人知识库。

![silicon logo](https://gist.githubusercontent.com/cu/addb3a5f6ba1de11b8fb5eedd212d82a/raw/b56dfbf4cd3ac77487e61cfbdeba7519d8b4f487/favicon-view-192.png)

功能特性：

* 使用 Markdown 编辑，渲染为 HTML
* 渲染 HTML 中的代码语法高亮
* 页面之间的双向关联
* 强大的全文和页面标题搜索
* 页面历史记录
* 左侧边栏中的目录（这才是它该在的地方）
* 可用性较强的移动端布局
* 内建文档
* 简洁的用户界面
* 不依赖大型框架，仅使用少量小型依赖

关于为何创建此项目以及某些设计决策背后的理由，请参阅[这篇博客文章](https://blog.bityard.net/articles/2022/December/the-design-of-silicon-notes-with-cartoons)。

<a href="https://gist.githubusercontent.com/cu/addb3a5f6ba1de11b8fb5eedd212d82a/raw/58e80468acbdd832d012fd776afac6d58357cbb3/view_full.png">
  <img src="https://gist.githubusercontent.com/cu/addb3a5f6ba1de11b8fb5eedd212d82a/raw/58e80468acbdd832d012fd776afac6d58357cbb3/view_full.png" width="400" height="275">
</a>

<a href="https://gist.githubusercontent.com/cu/addb3a5f6ba1de11b8fb5eedd212d82a/raw/bd5c9022462fe6aa6fd239b07a56777275bccf85/view_full_codemirror.png">
  <img src="https://gist.githubusercontent.com/cu/addb3a5f6ba1de11b8fb5eedd212d82a/raw/bd5c9022462fe6aa6fd239b07a56777275bccf85/view_full_codemirror.png" width="400" height="275">
</a>

<a href="https://gist.githubusercontent.com/cu/addb3a5f6ba1de11b8fb5eedd212d82a/raw/58e80468acbdd832d012fd776afac6d58357cbb3/view_mobile.png">
  <img src="https://gist.githubusercontent.com/cu/addb3a5f6ba1de11b8fb5eedd212d82a/raw/58e80468acbdd832d012fd776afac6d58357cbb3/view_mobile.png" width="248" height="275">
</a>

# 技术栈

我们依赖并感谢以下项目：

* [Python](https://www.python.org/)，当然。
* [uv](https://github.com/astral-sh/uv) 用于项目管理。
* [Flask](https://flask.palletsprojects.com/)，轻量级框架。
* [Mistune](https://github.com/lepture/mistune) 将 Markdown 渲染为 HTML。
* [Pygments](https://pygments.org/) 用于代码块的语法高亮。
* [python-slugify](https://github.com/un33k/python-slugify) 从字符串生成 URL 友好型“slug”。
* [python-dotenv](https://github.com/theskumar/python-dotenv) 用于配置管理。
* [Gunicorn](https://gunicorn.org/) 用于部署。
* [Pytest](https://pytest.org/) 和 [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/) 用于功能测试。
* [CodeMirror](https://codemirror.net/)（可选）用于编辑器语法高亮。

# 快速开始

## 本地运行

有关在本地运行应用的步骤，请参见下面的“开发”部分。

对于生产环境，该项目的配置和部署方式与任何其他 Flask 项目类似。详细信息请参阅 [Flask 配置处理文档]。

[Flask 配置处理文档]: https://flask.palletsprojects.com/en/stable/config/

## Docker 或 Podman

如果你更倾向于使用容器，以下命令可以帮助你启动应用。你显然需要安装 [Docker](https://www.docker.com)。（如果你使用 [Podman](https://podman.io)，只需将 `docker` 替换为 `podman`。）

```sh
docker run \
  -ti \
  --rm \
  -p 127.0.0.1:5000:5000 \
  -v silicon_instance:/home/silicon/instance \
  docker.io/bityard/silicon
```

然后在本地浏览器中打开 http://localhost:5000/。

你也可以使用 `docker-compose`（或 `docker compose`）启动：

```sh
cd deploy/docker-local
docker-compose up
```

如果你想构建镜像，项目中提供了 `Dockerfile` 和 `docker-compose.yaml` 文件，你可以使用以下命令构建容器：

```sh
docker build -t docker.io/bityard/silicon .
```

或者使用 buildah：

```sh
buildah build --format docker -t docker.io/bityard/silicon .
```

Silicon 将监听端口 5000（明文 HTTP），并将所有应用数据存储在 `/home/silicon/instance` 中。

# 开发

## 前提条件

本仓库在工具和工作流方面尽量保持灵活性。然而，在推荐路径上，你将使用 Python 3.9（或更高版本）、`uv`、Docker/Podman 和 `npm` 的组合。

如有需要，请安装 [uv](https://github.com/astral-sh/uv)。如果你不喜欢使用 curlpipes 安装方式，还有其他多种安装方法：

* `pip install --user uv`
* `pipx install uv`
* 从 [最新发布版本](https://github.com/astral-sh/uv) 下载二进制文件

## 设置

某些设置可以作为环境变量设置，也可以写入项目根目录下的 `.env` 文件中。开发环境下，以下设置即可满足需求：

```sh
WERKZEUG_DEBUG_PIN=off
```

你可以设置 Flask 或 Werkzeug 文档中提到的任何环境变量，但以下是一些你可能关心的变量：

* `FLASK_RUN_HOST`：默认为 `127.0.0.1`
* `FLASK_RUN_PORT`：默认为 `5000`
* `INSTANCE_PATH`：用于存储 Silicon 数据（特别是数据库）
* `WERKZEUG_DEBUG_PIN`：启用 Werkzeug 调试控制台的 PIN。设为 "off" 可以禁用它，前提是你可以确认应用仅监听在 localhost 上。
* `SECRET_KEY`：用于会话 cookie 的字符串。开发环境下可以是任意字符串，但生产环境下应使用 16 字节（或更大）的随机字符。如果未设置，应用会自动生成一个（并写入 `INSTANCE_PATH` 下的文件）。
* `SILICON_EDITOR`：当设置为 `textarea` 时，编辑页面时将禁用 CodeMirror 文本编辑器，改用标准的 textarea 元素。

在配置设置完成后，运行以下命令初始化数据库。它将在项目根目录下创建一个 `instance` 目录，并从 `schema.sql` 初始化 SQLite 数据库。

```sh
uv run flask --app silicon init-db
```

## 运行 Silicon

通过 `flask` 开发服务器运行项目：

```sh
uv run flask --app silicon run --debug
```

除非你更改了默认设置，否则你应该可以通过 http://localhost:5000/ 访问 UI。

## 运行测试和 flake8

运行测试：

```sh
uv run pytest
```

如果你使用 tmpfs 文件系统，可以设置 `TMP` 环境变量，使测试数据库创建在内存中（更快，减少磁盘磨损）：

```sh
TMP=/dev/shm uv run pytest
```

确保所有代码符合 flake8 标准，运行：

```sh
uv run flake8 --exclude .venv
```

# 生产部署

Silicon Notes 是一个相当简单的 Web 应用程序，**完全不包含内置的身份验证或授权机制**。如果单独部署该应用，应仅将其部署在受信任的私有网络中，例如通过防火墙或 VPN 与公共互联网隔离的本地局域网。**如果部署在公共服务器上，你有责任确保所有访问都是安全的。**

`deploy` 目录包含一些可用于生产部署的示例配置，可作为起点。

通常，最简单的方式是将此类应用托管在自己的域名或子域名下，例如 https://silicon.example.com/。如果你想将其托管在某个路径下（例如 https://example.com/silicon），请参阅 [此 issue](https://github.com/cu/silicon/issues/3) 获取相关提示。

# 配置 CodeMirror 编辑器

默认情况下，[CodeMirror](https://codemirror.net) 作为文本编辑器被包含在内。它确实增加了 UI 的“重量”，主要是因为它需要为每个指定的语言和插件发起单独的网络请求。要使用它，你还需要运行以下**任意一个**命令来安装第三方 JavaScript/CSS 静态包：

```sh
# 如果你本地已安装 `npm`
(cd silicon/static && npm ci)
```

或者：

```sh
# 如果你已安装 `docker`
docker run -ti --rm -v $PWD/silicon/static:/app -w /app node:alpine npm ci
```

目前仅启用了少量语言的语法高亮。如果你想根据需要修改列表，可以编辑 `silicon/static/js/edit.js`。你可以在 [这里](https://codemirror.net/mode/) 查看支持的语言列表。

要禁用 CodeMirror 并改用标准的 textarea，可在 `.env` 文件或环境中添加以下内容：

```sh
SILICON_EDITOR=textarea
```

# 数据导出与导入

## SQL

如果需要进行数据库迁移，请按以下步骤操作：

1. 停止 Silicon 实例。
2. 拉取本仓库的最新版本。
3. 运行 `scripts/dump.sh > silicon_data.sql`。

导入数据：

4. 如果存在旧的 `instance/silicon.sqlite` 文件，请移动或重命名。
5. 运行 `uv run flask --app silicon init-db`。
6. 运行 `sqlite3 instance/silicon.sqlite < silicon_data.sql`。
7. 启动 Silicon 实例。

确认没有问题后，可以归档（或删除）旧的 `silicon.sqlite` 文件和 `silicon_data.sql`。

## JSON

如果你想将数据导出为 JSON（可能用于导入其他系统或使用自己的工具处理），以下脚本未经充分测试，但可能可以完成任务。

导出：

```sh
#!/usr/bin/env sh

DB=instance/silicon.sqlite

for table in pages relationships; do
    sqlite3 $DB -cmd '.mode json' "select * from $table;" > $table.json
done
```

导入：

```sh
#!/usr/bin/env sh

sqlite3 instance/silicon.sqlite << EOF
INSERT INTO pages (revision, title, body)
SELECT
    json_extract(value, '$.revision'),
    json_extract(value, '$.title'),
    json_extract(value, '$.body')
FROM json_each(readfile('pages.json'));

INSERT INTO relationships
SELECT
    json_extract(value, '$.title_a'),
    json_extract(value, '$.title_a')
FROM json_each(readfile('relationships.json'));
EOF
```

# 建议的贡献方向

## 整理 CSS

当前的样式表是通过不断试错得到的。如果你能帮助将样式规则组织得更清晰、更可扩展，将非常感谢。

## 暗色主题

如果 CSS 能根据用户在浏览器中设置的偏好自动切换为暗色主题就更好了。这应该不难实现，因为几乎所有的颜色都定义在一个文件中。

## 整理 JavaScript

坦率地说，我的 JS 技能并不出色。如果你能对现有代码提出改进建议，或者指出更好的组织方式，我将非常感激。不过，我不会引入任何 JavaScript 的“构建”工具作为项目依赖。

## 版本差异对比

在类似 Wiki 的应用中，版本差异对比是一个很常见的功能，虽然对我来说不是关键功能，但我还没有鼓起勇气去实现它。（这可能还需要引入一个 diff 库作为依赖。）

## 草稿功能 / 自动保存 / 冲突检测

为了防止在编辑过程中丢失未保存的更改，我们在页面加载后如果编辑区域发生更改，会使用浏览器的“你确定要离开？”提示。然而，仍然存在（至少）两种可能丢失工作的情况：

1. 浏览器崩溃。
2. 在不同标签页或窗口中同时编辑同一页面。

第一种情况很少见，第二种情况也不太严重，因为两个版本都会被保存。但目前需要用户自行识别发生了什么，并手动修复。

这三个功能在技术上是独立的，但如果一起实现，它们之间会紧密耦合。

## 优化测试

`tests` 目录中包含了被认为最重要的功能测试。但它们可以更好地组织和优化/灵活化。代码覆盖率可能不高。有些测试缺失或不完整，因为我还没找到测试某些功能的正确方法。

## 为标题添加锚点

在各种 CMS 中，标题锚点是一个很常见的功能。它们允许你直接链接到某个标题，例如：

http://example.com/view/page_title#some-section

## 实现一个（更好）的任务列表插件

Mistune（Markdown 到 HTML 渲染器）自带了一个 [task_lists 插件]。它功能正常，但它将任务列表项渲染为普通 `<ul>` 中的另一种列表项。这意味着任务列表项前面会同时显示项目符号和复选框。在我看来，这不太美观，任务列表项应该用复选框替代项目符号。

[task_lists 插件]: https://mistune.readthedocs.io/en/latest/plugins.html#task-lists

我认为任务列表应该是一种独立的列表类型，而不是普通列表中的一种项类型。使用 Mistune 插件应该可以实现这一点。

# 发布流程

1. 在 `pyproject.toml` 中设置 `version` 字符串为要发布的版本号。
1. 运行 `uv lock`。
1. 提交 `pyproject.toml` 和 `uv.lock`。
1. 推送一个仅包含版本号的标签。必须在发布前推送标签。GitHub 将使用标签名作为发布名称，因此像 `release-1.2.3` 这样的前缀将不被接受。
   ```
   git log -1
   git tag <version> <commit>
   git push origin <version>
   ```
1. 这将触发一个动作，为每个架构构建容器并打标签/推送：
   * `latest`
   * major.minor.patch
1. 在 GitHub 上创建一个发布版本，包含指向 Docker 镜像的 URL。