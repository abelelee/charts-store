---
<p align="center">
    <a href="https://pocketbase.io" target="_blank" rel="noopener">
        <img src="https://i.imgur.com/5qimnm5.png" alt="PocketBase - 单文件开源后端" />
    </a>
</p>

<p align="center">
    <a href="https://github.com/pocketbase/pocketbase/actions/workflows/release.yaml" target="_blank" rel="noopener"><img src="https://github.com/pocketbase/pocketbase/actions/workflows/release.yaml/badge.svg" alt="构建" /></a>
    <a href="https://github.com/pocketbase/pocketbase/releases" target="_blank" rel="noopener"><img src="https://img.shields.io/github/release/pocketbase/pocketbase.svg" alt="最新发布版本" /></a>
    <a href="https://pkg.go.dev/github.com/pocketbase/pocketbase" target="_blank" rel="noopener"><img src="https://godoc.org/github.com/pocketbase/pocketbase?status.svg" alt="Go 包文档" /></a>
</p>

[PocketBase](https://pocketbase.io) 是一个开源的 Go 后端，包含以下功能：

- 嵌入式数据库（_SQLite_）并支持**实时订阅**
- 内置的**文件和用户管理**
- 方便使用的**管理仪表板界面**
- 以及简单的 **REST-ish API**

**有关文档和示例，请访问 https://pocketbase.io/docs。**

> [!WARNING]
> 请注意，PocketBase 仍在积极开发中，因此在发布 v1.0.0 之前，不能保证完全的向后兼容性。

## API SDK 客户端

要与 PocketBase Web API 进行交互，最简单的方式是使用以下官方 SDK 客户端：

- **JavaScript - [pocketbase/js-sdk](https://github.com/pocketbase/js-sdk)** (_浏览器、Node.js、React Native_)
- **Dart - [pocketbase/dart-sdk](https://github.com/pocketbase/dart-sdk)** (_Web、移动端、桌面端、CLI_)

你也可以查看 https://pocketbase.io/docs/how-to-use/ 中的推荐内容。

## 概述

### 作为独立应用使用

你可以从 [Releases 页面](https://github.com/pocketbase/pocketbase/releases) 下载适用于你平台的预编译可执行文件。
下载后，解压归档文件并在解压后的目录中运行 `./pocketbase serve`。

这些预编译可执行文件基于 [`examples/base/main.go` 文件](https://github.com/pocketbase/pocketbase/blob/master/examples/base/main.go)，并默认启用了 JS VM 插件，允许你使用 JavaScript 扩展 PocketBase（_更多详情请参阅 [使用 JavaScript 扩展](https://pocketbase.io/docs/js-overview/)_）。

### 作为 Go 框架/工具包使用

PocketBase 以标准 Go 库包的形式发布，允许你构建自己的自定义业务逻辑，同时最终仍能生成一个便携的单一可执行文件。

以下是一个最小示例：

0. [安装 Go 1.23+](https://go.dev/doc/install)（_如果尚未安装_）

1. 创建一个新的项目目录，并在其中创建以下 `main.go` 文件：
    ```go
    package main

    import (
        "log"

        "github.com/pocketbase/pocketbase"
        "github.com/pocketbase/pocketbase/core"
    )

    func main() {
        app := pocketbase.New()

        app.OnServe().BindFunc(func(se *core.ServeEvent) error {
            // 注册新的 "GET /hello" 路由
            se.Router.GET("/hello", func(re *core.RequestEvent) error {
                return re.String(200, "Hello world!")
            })

            return se.Next()
        })

        if err := app.Start(); err != nil {
            log.Fatal(err)
        }
    }
    ```

2. 初始化依赖：运行 `go mod init myapp && go mod tidy`。

3. 启动应用：运行 `go run main.go serve`。

4. 构建静态链接的可执行文件：运行 `CGO_ENABLED=0 go build`，然后通过 `./myapp serve` 启动生成的可执行文件。

_更多详情请参阅 [使用 Go 扩展](https://pocketbase.io/docs/go-overview/)_。

### 构建并运行仓库中的 main.go 示例

要构建像发布页面中提供的那种最小独立可执行文件，只需在 `examples/base` 目录中运行 `go build`：

0. [安装 Go 1.23+](https://go.dev/doc/install)（_如果尚未安装_）
1. 克隆/下载仓库
2. 进入 `examples/base` 目录
3. 运行 `GOOS=linux GOARCH=amd64 CGO_ENABLED=0 go build`
   (_https://go.dev/doc/install/source#environment_)
4. 通过运行 `./base serve` 启动生成的可执行文件。

请注意，目前纯 Go SQLite 驱动支持的构建目标包括：

```
darwin  amd64
darwin  arm64
freebsd amd64
freebsd arm64
linux   386
linux   amd64
linux   arm
linux   arm64
linux   ppc64le
linux   riscv64
linux   s390x
windows amd64
windows arm64
```

### 测试

PocketBase 包含了单元测试和集成测试的组合。
要运行这些测试，请使用标准的 `go test` 命令：

```sh
go test ./...
```

还可以查看 [测试指南](http://pocketbase.io/docs/testing)，学习如何编写你自己的自定义应用测试。

## 安全

如果你在 PocketBase 中发现安全漏洞，请发送电子邮件至 **support at pocketbase.io**。

所有报告将被及时处理，并且你将在修复版本的发布说明中获得致谢。

## 贡献

PocketBase 是一个基于 [MIT License](LICENSE.md) 的免费开源项目。
你可以自由地使用它，甚至可以将其作为付费服务提供。

你可以通过以下方式帮助继续开发：

- [贡献源代码](CONTRIBUTING.md)
- [提出新功能建议和报告问题](https://github.com/pocketbase/pocketbase/issues)

欢迎提交新 OAuth2 提供商、Bug 修复、代码优化和文档改进的 PR。

但请在未事先讨论实现细节的情况下，不要提交新**功能**的 PR。
PocketBase 有 [路线图](https://github.com/orgs/pocketbase/projects/2)，我会按照特定顺序处理问题，而此类 PR 往往会打乱原有的计划，导致不必要的来回沟通。

如果你的 PR 被关闭，即使它编写得很好并经过测试，也请不要沮丧。这并不意味着它永远不会被合并。
我们可以在将来处理相关问题时参考你的 PR，或使用其中的部分实现（不用担心，你将在发布说明中获得致谢）。