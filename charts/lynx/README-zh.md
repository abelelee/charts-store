---
    > [!WARNING]  
> 自 2024-06-19 起，Lynx 将不再添加新功能，更多信息请阅读[公告](https://github.com/Lynx-Shortener/Lynx/discussions/155)

<p align="center">
<img alt="" src="frontend/public/logo.png" height="300px">
</p>
<p align="center">
<a href="https://hub.docker.com/r/jackbailey/lynx">
    <img alt="Image Size" src="https://img.shields.io/docker/image-size/jackbailey/lynx?label=docker%20image%20size">
</a>
<a href="https://hub.docker.com/r/jackbailey/lynx">
    <img alt="Docker Pulls" src="https://img.shields.io/docker/pulls/jackbailey/lynx?label=docker%20pulls">
</a>
<a href="https://github.com/Lynx-Shortener/Lynx">
    <img alt="Image Size" src="https://img.shields.io/github/license/jackbailey/lynx?label=license">
</a>
<a href="https://github.com/Lynx-Shortener/Lynx">
    <img alt="Lines of code" src="https://www.aschey.tech/tokei/github/JackBailey/Lynx?category=code">
</a>
<a href="https://docs.getlynx.dev">
    <img alt="Docs" src="https://img.shields.io/badge/read%20the-docs-blue">
</a>
</p>

# Lynx

![link list](https://cdn.jackbailey.dev/screenshots/lynx.png)

## 关于

这是一个使用 MEVN 技术栈的全栈应用程序，用于缩短你的 URL。

我尝试过多种 URL 缩短工具，但没有找到满足我所需功能的，所以我决定自己开发一个。

我的主要需求包括：

- 管理界面
- 可选的根路径重定向
- 简洁的用户界面

此仓库的镜像可在 [git.jackbailey.uk](https://git.jackbailey.uk/Lynx-Shortener/Lynx) 找到。

## 安装

安装指南已移至[文档页面](https://docs.getlynx.dev/installation/installation)。

## 开发与贡献

我正在积极使用 Lynx，并尝试为其添加功能和修复错误，但由于时间有限，进展可能较慢。

欢迎你提交 Pull Request 来添加功能或修复问题，我会进行合并。

项目路线图可在此处访问：[路线图链接](https://github.com/orgs/Lynx-Shortener/projects/2)

## 命名说明

每个包含 slug、目标地址和 ID 的条目被称为 [`Link`](src/db/models/link.js)，复数形式为 links。

每个链接都有一个 `slug`，这是源 URL 中的路径部分。例如 `example.com/2dch89772` 的 slug 是 `2dch89772`。

每个包含用户名和密码的条目被称为 [`Account`](src/db/models/account.js)，复数形式为 accounts。