以下是你提供的 Markdown 内容的中文翻译，保留了原始格式：

---

<p align="center">
  <img src="docs/logo.svg" width="300px"></img>
</p>
<p align="center">
  <img alt="Docker Pulls" src="https://img.shields.io/docker/pulls/dullage/flatnotes?style=for-the-badge">
</p>

一个自托管、无数据库的笔记类网页应用，使用扁平的 Markdown 文件夹进行数据存储。

登录 [演示站点](https://demo.flatnotes.io) 浏览一下。*注意：该站点每 15 分钟重置一次。*

## 目录

* [设计理念](#design-principle)
* [功能特性](#features)
* [快速开始](#getting-started)
  * [托管部署](#hosted)
  * [自托管部署](#self-hosted)
* [路线图](#roadmap)
* [参与贡献](#contributing)
* [赞助支持](#sponsorship)
* [致谢](#thanks)

## 设计理念

flatnotes 被设计为一个无干扰的笔记应用，专注于你的笔记内容本身。这意味着：

* 简洁、简单的用户界面。
* 没有文件夹、笔记本等结构，只有你的所有笔记，并通过强大的搜索和标签功能进行支持。
* 从应用的任何位置快速访问全文搜索功能（快捷键为“/”）。

另一个关键的设计理念是：不会将你的笔记锁定在应用中。你的笔记只是普通的 Markdown 文件。没有数据库、没有专有格式、没有复杂的文件夹结构。你随时可以将这些文件迁移到其他地方，并使用其他应用进行管理。

同样，flatnotes 仅缓存搜索索引，并且该索引会在每次搜索时（以及 flatnotes 启动时）进行增量同步。这意味着即使 flatnotes 正在运行，你也可以在外部自由地添加、编辑和删除 Markdown 文件。

## 功能特性

* 响应式设计的网页界面，支持移动端。
* 支持原始 Markdown 编辑与所见即所得编辑模式。
* 强大的搜索功能。
* 笔记“标签”功能。
* 可自定义的首页。
* 支持 Wikilink 链接格式，便于在笔记之间快速链接（`[[My Other Note]]`）。
* 支持浅色/深色主题。
* 多种认证方式（无认证、只读模式、用户名/密码、双因素认证）。
* 提供 RESTful API。

更多详情请参阅 [wiki 页面](https://github.com/dullage/flatnotes/wiki)。

## 快速开始

### 托管部署

快速开始使用 flatnotes 的一种方式是将其部署在 PikaPods 上。点击下方按钮并按照提示操作即可。

[![PikaPods](https://www.pikapods.com/static/run-button-34.svg)](https://www.pikapods.com/pods?run=flatnotes)

### 自托管部署

如果你希望自行托管 flatnotes，推荐使用 Docker。

### 示例 Docker 启动命令

```shell
docker run -d \
  -e "PUID=1000" \
  -e "PGID=1000" \
  -e "FLATNOTES_AUTH_TYPE=password" \
  -e "FLATNOTES_USERNAME=user" \
  -e 'FLATNOTES_PASSWORD=changeMe!' \
  -e "FLATNOTES_SECRET_KEY=aLongRandomSeriesOfCharacters" \
  -v "$(pwd)/data:/data" \
  -p "8080:8080" \
  dullage/flatnotes:latest
```

### 示例 Docker Compose 配置

```yaml
version: "3"

services:
  flatnotes:
    container_name: flatnotes
    image: dullage/flatnotes:latest
    environment:
      PUID: 1000
      PGID: 1000
      FLATNOTES_AUTH_TYPE: "password"
      FLATNOTES_USERNAME: "user"
      FLATNOTES_PASSWORD: "changeMe!"
      FLATNOTES_SECRET_KEY: "aLongRandomSeriesOfCharacters"
    volumes:
      - "./data:/data"
      # 可选项：允许你将搜索索引保存在不同的位置：
      # - "./index:/data/.flatnotes"
    ports:
      - "8080:8080"
    restart: unless-stopped
```

完整的配置选项请参阅 wiki 中的 [环境变量](https://github.com/dullage/flatnotes/wiki/Environment-Variables) 文档。

## 路线图

我希望 flatnotes 保持尽可能简单和无干扰，因此新功能将受到限制。尽管如此，我仍然欢迎反馈和建议。

## 参与贡献

如果你有兴趣为 flatnotes 做出贡献，请阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 文件。

## 赞助支持

如果你觉得这个项目对你有帮助，请考虑请我喝杯啤酒。这会让我非常开心。

[![Sponsor](https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/Dullage)

## 致谢

特别感谢两个出色的开源项目，它们使 flatnotes 成为可能：

* [Whoosh](https://whoosh.readthedocs.io/en/latest/intro.html) - 一个快速的纯 Python 搜索引擎库。
* [TOAST UI Editor](https://ui.toast.com/tui-editor) - 一个支持 GFM Markdown 和所见即所得编辑的浏览器端编辑器。