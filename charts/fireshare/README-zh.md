---
<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/ShaneIsrael/fireshare">
    <img src="app/client/src/assets/logo.png" alt="Logo" width="120" height="160">
  </a>

  <h1 align="center">Fireshare</h1>

  <p align="center">
    通过唯一链接分享你的游戏片段、视频或其他媒体。
    <br />
    <br />
    <a href="https://github.com/shaneisrael/fireshare/actions">
      <img alt="Docker Build" src="https://github.com/shaneisrael/fireshare/actions/workflows/docker-publish-main.yml/badge.svg" />
    </a>
    <a href="https://hub.docker.com/r/shaneisrael/fireshare">
      <img alt="Docker Pulls" src="https://img.shields.io/docker/pulls/shaneisrael/fireshare?label=docker%20pulls">
    </a>
    <a href="https://hub.docker.com/r/shaneisrael/fireshare/tags?page=1&ordering=last_updated">
      <img alt="GitHub tag (latest SemVer)" src="https://img.shields.io/github/v/tag/shaneisrael/fireshare?label=版本">
    </a>
    <a href="https://github.com/shaneisrael/fireshare/stargazers">
      <img alt="GitHub stars" src="https://img.shields.io/github/stars/shaneisrael/fireshare">
    </a>
    <br />
    <br />
    <a href="https://v.fireshare.net">在线演示</a>
    ·
    <a href="https://github.com/ShaneIsrael/fireshare/issues">报告错误</a>
    ·
    <a href="https://www.paypal.com/paypalme/shaneisrael">请我们喝杯咖啡！</a>
  </p>
</p>

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>目录</summary>
  <ol>
    <li>
      <a href="#about-the-project">关于本项目</a>
      <ul>
        <li><a href="#built-with">使用的技术</a></li>
      </ul>
    </li>
    <li><a href="#changelog">更新日志</a></li>
    <li>
      <a href="#installation">安装</a>
      <ul>
        <li><a href="#configurable-settings">可配置设置</a></li>
      </ul>
    </li>
    <li>
      <a href="#local-development">本地开发</a>
      <ul>
        <li><a href="#setup">设置</a></li>
      </ul>
    </li>
    <li><a href="#contributing">贡献指南</a></li>
    <li>
      <a href="#frequently-asked-questions">常见问题</a>
      <ul>
        <li><a href="#playback-issues">播放问题</a></li>
      </ul>
    </li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->

# 关于本项目

我经常使用像NVIDIA Shadowplay这样的工具创建游戏片段，其中很多是15-30秒的短片段，我想要与朋友分享，但又不想花时间上传到YouTube，等待YouTube处理视频，然后才能发送链接。

我想应该有一个简单的解决方案，可以让我自行托管这些片段并通过生成的链接与朋友分享。不幸的是，我找到的工具都不完全符合我的需求。于是在朋友的帮助下，我们快速构建了Fireshare来实现这个目标。

Fireshare的目标是提供一种非常简单易用的方式，让你通过唯一链接分享任何视频。你只需要将视频放入一个文件夹，Fireshare会处理其余的事情。

![login-screen]

<h2 align="center">仪表盘</h2>
<p align="center">在这里你可以看到你所有的视频，并可以编辑它们的标题、描述以及是否显示在公共信息流中。</p>

![card-view]

<p align="center">也许卡片视图不是你的风格？Fireshare也支持列表视图。</p>

![list-view]

<h2 align="center">文件夹分类</h2>
<p align="center">Fireshare将使用你视频所在的最上层目录，作为你按自定义类别组织视频的简便方式。</p>

![folders]

<h2 align="center">上传功能</h2>
<p align="center">允许你的社区或公众上传视频。当然，此功能可以禁用或仅限管理员访问。</p>

![uploading]

<h2 align="center">编辑视频详情</h2>
<p align="center">点击“铅笔”图标，可以访问一个用于编辑视频标题和描述的基本弹窗。</p>

![edit-details]

<h2 align="center">视频预览弹窗</h2>
<p align="center">在公共信息流或管理仪表盘中打开的视频会显示在弹窗中。此弹窗提供了直接链接和带时间戳的分享按钮，以及“随机播放”到另一个视频的功能。作为管理员，你也可以在此弹窗中编辑视频的详细信息。</p>

![preview-modal]

<h2 align="center">观看页面</h2>
<p align="center">这是人们通过Fireshare链接看到的内容。</p>

![watch-page]

<h2 align="center">移动端支持</h2>
<p align="center">
更喜欢在移动设备上浏览？没问题。Fireshare支持移动端。
</p>

<p align="center"><img src=".github/images/mobile-view.png" width="400px"/></p>

<h2 align="center">Open Graph 支持</h2>
<p align="center">
从Fireshare的复制链接按钮复制的直接链接，将允许网站和消息应用程序读取Open Graph数据，并在你的帖子中显示标题、描述和视频缩略图。
</p>
<p align="center">
<img src=".github/images/ogg-data.png" alt="Logo">
</p>

<h2 align="center">LDAP 认证支持</h2>
<p align="center">
将Fireshare连接到中央用户目录，保持用户访问的有序管理。
</p>

### 使用的技术

- [React](https://reactjs.org/)
- [Python](https://www.python.org/)
- [Material UI](https://mui.com/)

<!--- CHANGE LOG --->

# 更新日志

## v1.2.13
```
  增加了在启动扫描时检测损坏或格式错误文件的异常处理
```

<!-- GETTING STARTED -->

# 安装

Fireshare设计为在Docker环境中运行。虽然我们推荐使用Docker Compose，但这不是必须的，也可以使用简单的`docker run`命令运行。

Fireshare需要三个卷挂载：

1. **/data** - Fireshare用来存放其内部数据库的目录
2. **/processed** - 存放Fireshare为你的视频生成的元数据（如海报、元信息）
3. **/videos** - Fireshare监控并扫描视频的目录

如果你所有的游戏片段都存储在一个名为**my_game_clips**的文件夹中，那么在你的docker compose文件（或docker run命令）中，你需要将该文件夹卷挂载到Fireshare监控的**/videos**目录。

### Docker Compose

如果你安装了docker compose，可以在项目根目录下直接运行以下命令。

> **请确保在docker-compose.yml文件中编辑卷路径和管理员密码。**

```
docker-compose up -d
```

### Docker

```
docker run --name fireshare -v $(pwd)/fireshare:/data:rw -v $(pwd)/fireshare_processed:/processed:rw -v /path/to/my_game_clips:/videos:rw -p 8080:80 -e ADMIN_PASSWORD=your-admin-password -d shaneisrael/fireshare:latest
```

启动后，在浏览器中访问 `localhost:8080`。

### 可配置设置

查看Fireshare配置Wiki：<a href="https://github.com/ShaneIsrael/fireshare/wiki/Fireshare-Configurables">链接</a>  
LDAP配置请参阅 LDAP.md

# 本地开发

如果你想通过源代码运行Fireshare以便贡献代码，你需要安装npm、Node.js和Python。我建议使用NVM安装Node.js，这样可以轻松切换Node版本。

### 设置

1. 安装Python3、NodeJS和NPM。
2. 克隆仓库
   ```sh
   $ git clone https://github.com/ShaneIsrael/fireshare.git
   ```
3. 在项目根目录下
   ```sh
   $ ./run_local.sh
   ```
4. 在新终端中，进入`app/client`并运行以下命令。
   ```JS
   $ npm i && npm start
   ```
5. 在浏览器中访问`localhost:3000`，使用admin/admin登录

<!-- CONTRIBUTING -->

# 贡献指南

如果这个项目对你来说有趣，请随时贡献或提出建议。请注意，创建Pull Request并不保证会被接受。除了明显的错误修复外，最好在开始开发任何新增功能之前先与我们沟通。

[如有问题或功能请求，请在此创建带适当标签的Issue](https://github.com/ShaneIsrael/fireshare/issues/new)

1. Fork 项目
2. 添加上游仓库 (`git remote add upstream https://github.com/ShaneIsrael/fireshare.git`)
3. 创建你的功能分支 (`git checkout -b feature/AmazingFeature`)
4. 提交你的更改 (`git commit -m 'Add some AmazingFeature'`)
5. Rebase 到上游 (`git rebase upstream/main`)
6. 解决可能出现的合并冲突
7. 推送到分支 (`git push origin feature/AmazingFeature`)
8. 向**develop**分支提交Pull Request

**更新你的分支** 我们不会为你解决合并冲突，如果你提交的Pull Request显示有冲突，请参考上面的第4和第5步。

### 更新Fireshare数据库

如果你需要更新数据库或添加新表/列，请首先修改`app/server/fireshare/models.py`文件，然后在项目根目录运行`flask db migrate -m "name of migration"`，一个新的迁移文件将被创建。前往该文件并检查是否一切正确。你可能需要手动编辑此迁移文件。

# 常见问题

### 播放问题

如果你遇到播放问题，可能有多种原因。以下是最常见的原因：

1. **文件大小**

   Fireshare直接提供你的视频。如果你的视频非常大，观看者需要足够快的下载速度才能播放。这也意味着你需要足够快的上传速度来提供这些大文件。建议使用Handbrake等工具将视频压缩为更小的尺寸。

2. **上传速度**

   你的上传速度很重要。如果你的上传速度较慢，根据你要提供的文件大小，可能无法让他人流畅地观看你的视频。建议使用Handbrake压缩视频。

3. **浏览器**

   我的测试中发现，Firefox在播放非常大的文件时存在问题，而Chrome和Edge似乎没有这个问题。

4. **不支持的文件类型**

   目前，Fireshare仅支持浏览器可以原生播放的文件类型，通常是MP4、MOV和WEBM文件。例如，h265编码的视频可以在Chrome中正常播放，但在Firefox中可能无法播放，这对观看者来说体验不好。建议尽可能使用h264编码的MP4格式。如果你的视频文件无法播放或报错，可能需要使用Handbrake等工具将其转码为h264编码的MP4。

5. **上传问题**

   上传问题通常是因为将Fireshare部署在反向代理（如Nginx）后面。默认情况下，Nginx对上传文件的大小有限制。通常问题是你的文件超过了Nginx允许的大小。你需要更新反向代理的设置以增加这些限制和超时时间。如果你使用Nginx，你可能只需要添加以下两行：

   ```
   client_max_body_size 0;
   proxy_read_timeout 999999s;
   ```

   这些设置仅适用于Nginx。将`client_max_body_size`设置为`0`表示允许任意大小的上传。我们还增加了超时限制，以防止连接超时。如果你不使用Nginx，则需要自行研究相关配置。

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/ShaneIsrael/fireshare.svg?style=for-the-badge
[contributors-url]: https://github.com/ShaneIsrael/fireshare/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/ShaneIsrael/fireshare.svg?style=for-the-badge
[forks-url]: https://github.com/ShaneIsrael/fireshare/network/members
[stars-shield]: https://img.shields.io/github/stars/ShaneIsrael/fireshare.svg?style=for-the-badge
[stars-url]: https://github.com/ShaneIsrael/fireshare/stargazers
[issues-shield]: https://img.shields.io/github/issues/ShaneIsrael/fireshare.svg?style=for-the-badge
[issues-url]: https://github.com/ShaneIsrael/fireshare/issues
[card-view]: .github/images/card-view.png
[edit-details]: .github/images/edit-details.png
[folders]: .github/images/folders.png
[login-screen]: .github/images/login-screen.png
[list-view]: .github/images/list-view.png
[preview-modal]: .github/images/preview-modal.png
[watch-page]: .github/images/watch-page.png
[ogg-data]: .github/images/ogg-data.png
[mobile-view]: .github/images/mobile-view.png
[uploading]: .github/images/uploading.png