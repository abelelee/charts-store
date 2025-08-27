---
<h1 align="center">欢迎使用 Peppermint 工单管理系统 🍵</h1>
<p align="center">
  <img alt="版本" src="https://img.shields.io/badge/version-0.2-blue.svg?cacheSeconds=2592000" />
  <a target="_blank">
    <img alt="Github 星标数：" src="https://img.shields.io/github/stars/jwandrews99/winter?style=social" />
  </a>
  <img src="https://img.shields.io/docker/pulls/pepperlabs/peppermint" />
</p>
<p align="center">
    <img src="./static/logo.svg" alt="Logo" height="80px" >
</p>
<p align="center">本项目由以下公司支持：</p>
<p align="center">
  <a href="https://www.digitalocean.com/">
    <img src="https://opensource.nyc3.cdn.digitaloceanspaces.com/attribution/assets/SVG/DO_Logo_horizontal_blue.svg" width="201px">
  </a>
</p>

> 工单管理系统，旨在帮助服务台和客服部门管理内部员工及客户的请求

## ✨ 功能特性

- **工单创建**：标准的工单创建功能，支持 Markdown 编辑器和文件上传
- **客户历史记录**
- **基于 Markdown 的笔记本，支持待办事项列表**
- **响应式设计**：适配从移动端到 4K 分辨率的各种屏幕尺寸
- **多部署方式**：可通过 Docker 和 pm2 快速部署
- **操作简单**：设计直观，流程清晰，易于使用

## 🐳 使用 Docker 安装

如果是首次使用 Peppermint，请参考入门指南：

```
version: "3.1"

services:
  peppermint_postgres:
    container_name: peppermint_postgres
    image: postgres:latest
    restart: always
    ports:
      - 5432:5432
    volumes:
      - pgdata:/var/lib/postgresql/data
    environment:
      POSTGRES_USER: peppermint
      POSTGRES_PASSWORD: 1234
      POSTGRES_DB: peppermint

  peppermint:
    container_name: peppermint
    image: pepperlabs/peppermint:latest
    ports:
      - 3000:3000
      - 5003:5003
    restart: always
    depends_on:
      - peppermint_postgres
    environment:
      DB_USERNAME: "peppermint"
      DB_PASSWORD: "1234"
      DB_HOST: "peppermint_postgres"
      SECRET: 'peppermint4life'

volumes:
 pgdata:

```

安装完成后，访问 compose 文件中配置的服务器 IP 地址加端口号（例如：`your-server-ip:3000`）即可登录。

默认登录凭证为：

```
admin@admin.com
1234
```

## 一键安装包

- 我们现已上线 Linode 市场，可在此查看：<a href="https://www.linode.com/marketplace/apps/peppermint-lab/peppermint/">这里</a>
- 我们还提供了适用于 Ubuntu 和 Debian 系统的一行安装命令（目前仅支持 Ubuntu 和 Debian），可在此查看：<a href="https://spearmint.sh/">这里</a>

## 文档

我们已经开始编写 Peppermint 的相关文档，涵盖开发到日常使用的各个方面。点击 <a href="https://docs.peppermint.sh">此处</a> 直接前往文档页面。

## 开发动机

- 该项目最初是为了整合我的 React 和 Node.js 技能，并为作品集提供一个展示项目
- 虽然最初界面很丑，但功能完整，最终帮助我找到了工作
- 学习并使用 Docker 进行部署
- 从零开始完全重构 UI，现在界面已经焕然一新，个人认为非常美观
- 在此基础上继续开发，打造一个功能齐全的产品，提供与大型厂商类似的功能，但相比 Zendesk 等服务具有更高的投资回报率（ROI）

如果该项目对你有帮助，请给我们一个 ⭐️！

## 星标历史

[![Star History Chart](https://api.star-history.com/svg?repos=Peppermint-Lab/peppermint&type=Date)](https://star-history.com/#Peppermint-Lab/peppermint&Date)

## 活跃度
![Alt](https://repobeats.axiom.co/api/embed/9b568eb9e41b60f60fe155836b1ef0fb2a7b93b9.svg "Repobeats analytics image")

- 官网：[peppermint.sh](https://peppermint.sh/)
- Github：[@potts99](https://github.com/potts99)
- LinkedIn：[@jack-andrews-146852131](https://linkedin.com/in/jack-andrews-146852131)