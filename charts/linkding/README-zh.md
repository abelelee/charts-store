以下是你要求翻译的 Markdown 内容，翻译后保留了原始的 Markdown 格式，并确保语言自然流畅，符合技术文档风格：

---

<div align="center">
    <br>
    <a href="https://github.com/sissbruecker/linkding">
        <img src="assets/header.svg" height="50">
    </a>
    <br>
</div>

## 简介

linkding 是一个你可以自行托管的书签管理工具。  
它设计简洁、运行快速，并可通过 Docker 轻松部署。

名称来源如下：
- *link*，在日常语言中常作为 URL 和书签的同义词
- *Ding*，是德语中“东西”的意思
- 所以整体上就是用来管理你的链接的工具

**功能概览：**
- 简洁的界面，优化了可读性
- 使用标签组织书签
- 支持批量编辑、Markdown 笔记和稍后阅读功能
- 可与其他用户或访客共享书签
- 自动获取书签网站的标题、描述和图标
- 自动归档网站，可保存为本地 HTML 文件或上传至 Internet Archive
- 支持以 Netscape HTML 格式导入和导出书签
- 可作为渐进式网页应用（PWA）安装
- 提供 [Firefox](https://addons.mozilla.org/firefox/addon/linkding-extension/) 和 [Chrome](https://chrome.google.com/webstore/detail/linkding-extension/beakmhbijpdhipnjhnclmhgjlddhidpe) 扩展，以及书签小工具
- 支持通过 OIDC 或认证代理进行单点登录（SSO）
- 提供用于开发第三方应用的 REST API
- 管理后台支持用户自助服务和原始数据访问

**演示地址：** https://demo.linkding.link/

**截图：**

![截图](/docs/public/linkding-screenshot.png?raw=true "截图")

## 快速开始

以下链接可帮助你快速上手 linkding：
- [在你自己的服务器上安装 linkding](https://linkding.link/installation) 或 [查看托管方案](https://linkding.link/managed-hosting)
- [安装浏览器扩展](https://linkding.link/browser-extension)
- [查看社区项目](https://linkding.link/community)，包括移动应用、浏览器扩展、库等

## 文档

完整文档请访问 [linkding.link](https://linkding.link/)。

如果你想为文档做贡献，可以在 `docs` 文件夹中找到源文件。

如果你想贡献一个社区项目，欢迎 [提交 PR](https://github.com/sissbruecker/linkding/edit/master/docs/src/content/docs/community.md)。

## 贡献指南

小的改进、Bug 修复和文档优化始终欢迎。如果你打算贡献一个较大的功能，建议先提交一个 Issue 进行讨论。对于与项目目标不符或我不愿维护的功能，可能会忽略对应的 PR。

## 开发指南

本应用使用 Django Web 框架构建。你可以通过阅读优秀的 [Django 文档](https://docs.djangoproject.com/en/4.1/)开始开发。`bookmarks` 文件夹包含实际的书签应用。其他代码应为自解释的标准 Django 内容 🙂。

### 前提条件
- Python 3.12
- Node.js

### 环境设置

创建应用的虚拟环境（https://docs.python.org/3/tutorial/venv.html）：
```
python3 -m venv ~/environments/linkding
```
激活对应 shell 的虚拟环境：
```
source ~/environments/linkding/bin/activate[.csh|.fish]
```
在激活的环境中安装应用依赖（在应用目录下执行）：
```
pip3 install -r requirements.txt -r requirements.dev.txt
```
安装前端依赖：
```
npm install
```
初始化数据库：
```
mkdir -p data
python3 manage.py migrate
```
创建一个前端用户：
```
python3 manage.py createsuperuser --username=joe --email=joe@example.com
```
启动 Node.js 开发服务器（用于编译标签自动补全等 JavaScript 组件）：
```
npm run dev
```
启动 Django 开发服务器：
```
python3 manage.py runserver
```
现在可以通过 http://localhost:8000 访问前端界面

### 测试

使用 pytest 运行所有测试：
```
make test
```

### 代码格式化

使用 black 格式化 Python 代码，使用 prettier 格式化 JavaScript 代码：
```
make format
```

### DevContainers 支持

本仓库支持 DevContainers：[![Open in Remote - Containers](https://img.shields.io/static/v1?label=Remote%20-%20Containers&message=Open&color=blue&logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/sissbruecker/linkding.git)

克隆仓库后，只需运行以下命令即可开始：

创建一个前端用户：
```
python3 manage.py createsuperuser --username=joe --email=joe@example.com
```
启动 Node.js 开发服务器（用于编译标签自动补全等 JavaScript 组件）：
```
npm run dev
```
启动 Django 开发服务器：
```
python3 manage.py runserver
```
现在可以通过 http://localhost:8000 访问前端界面