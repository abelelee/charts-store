---
<p align="center">
    <img src="https://user-images.githubusercontent.com/8983173/130322857-185831e2-f041-46eb-a17f-0a69d066c4e5.png" alt="Gotenberg Logo" width="150" height="150" />
    <h3 align="center">Gotenberg</h3>
    <p align="center">一个用于无缝 PDF 转换的容器化 API</p>
    <p align="center">
        <a href="https://hub.docker.com/r/gotenberg/gotenberg"><img alt="总下载量 (gotenberg/gotenberg)" src="https://img.shields.io/docker/pulls/gotenberg/gotenberg"></a>
        <a href="https://hub.docker.com/r/thecodingmachine/gotenberg"><img alt="总下载量 (thecodingmachine/gotenberg)" src="https://img.shields.io/docker/pulls/thecodingmachine/gotenberg"></a>
        <a href="https://github.com/gotenberg/gotenberg/actions/workflows/continuous-integration.yml"><img alt="持续集成" src="https://github.com/gotenberg/gotenberg/actions/workflows/continuous-integration.yml/badge.svg"></a>
        <a href="https://pkg.go.dev/github.com/gotenberg/gotenberg/v8"><img alt="Go 参考文档" src="https://pkg.go.dev/badge/github.com/gotenberg/gotenberg.svg"></a>
    </p>
    <p align="center">
        <a href="https://trendshift.io/repositories/2996"><img src="https://trendshift.io/api/badge/repositories/2996" alt="gotenberg%2Fgotenberg | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
    </p>
    <p align="center"><a href="https://gotenberg.dev/docs/getting-started/introduction">文档</a> &#183; <a href="https://gotenberg.dev/docs/getting-started/installation#live-demo-">在线演示</a> 🔥</p>
</p>

---

**Gotenberg** 提供了一个面向开发者的友好 API，用于与 Chromium 和 LibreOffice 等强大工具交互，将多种文档格式（HTML、Markdown、Word、Excel 等）转换为 PDF 文件，功能远不止于此！

## 快速开始

打开终端并运行以下命令：

```
docker run --rm -p 3000:3000 gotenberg/gotenberg:8
```

或者，使用来自我们的赞助商 [TheCodingMachine](https://www.thecodingmachine.com) 的历史 Docker 仓库：

```
docker run --rm -p 3000:3000 thecodingmachine/gotenberg:8
```

现在，API 已在你的主机上 http://localhost:3000 可用。

前往 [文档](https://gotenberg.dev/docs/getting-started/introduction) 学习如何与其交互 🚀

## 赞助商

<p align="center">
    <a href="https://thecodingmachine.com">
        <img src="https://user-images.githubusercontent.com/8983173/130324668-9d6e7b35-53a3-49c7-a574-38190d2bd6b0.png" alt="TheCodingMachine Logo" width="333" height="163" />
    </a>
    <a href="https://pdfme.com?utm_source=gotenberg_github&utm_medium=website" target="_blank">
        <img src="https://github.com/user-attachments/assets/2a75dd40-ca18-4d34-acd5-5dd474595168" alt="pdfme Logo" width="333" height="163" />
    </a>
</p>

赞助有助于 Gotenberg 的维护和改进 —— [成为赞助商](https://github.com/sponsors/gulien) ❤️