---
<p align="center">
  <img src="https://user-images.githubusercontent.com/31465/34380645-bd67f474-eb0b-11e7-8d03-0151c1730654.png" height="29" />
</p>
<p align="center">
  <i>一个使用 React 和 Node.js 构建的快速、协作型团队知识库。<br/>请访问 <a href="https://www.getoutline.com">www.getoutline.com</a> 使用我们提供的托管版本。</i>
  <br/>
  <img width="1640" alt="screenshot" src="https://user-images.githubusercontent.com/380914/110356468-26374600-7fef-11eb-9f6a-f2cc2c8c6590.png">
</p>
<p align="center">
  <a href="https://circleci.com/gh/outline/outline" rel="nofollow"><img src="https://circleci.com/gh/outline/outline.svg?style=shield"></a>
  <a href="http://www.typescriptlang.org" rel="nofollow"><img src="https://img.shields.io/badge/%3C%2F%3E-TypeScript-%230074c1.svg" alt="TypeScript"></a>
  <a href="https://github.com/prettier/prettier"><img src="https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat" alt="Prettier"></a>
  <a href="https://github.com/styled-components/styled-components"><img src="https://img.shields.io/badge/style-%F0%9F%92%85%20styled--components-orange.svg" alt="Styled Components"></a>
  <a href="https://translate.getoutline.com/project/outline" alt="Localized"><img src="https://badges.crowdin.net/outline/localized.svg"></a>
</p>

这是 [**Outline**](https://www.getoutline.com) 及其所有相关服务所使用的源代码。如果你只是想使用 Outline，你无需运行这些代码，我们提供了一个托管版本的应用，访问地址为 [getoutline.com](https://www.getoutline.com)。你也可以在[我们的指南](https://docs.getoutline.com/s/guide)中找到使用 Outline 的相关文档。

如果你想运行自己的 Outline 实例或参与开发，那么你来对地方了。

# 安装

关于如何在生产环境中运行 Outline 的说明，请参阅[文档](https://docs.getoutline.com/s/hosting/)。

如果你对文档有任何疑问或改进建议，请在 [GitHub Discussions](https://github.com/outline/outline/discussions) 中创建一个讨论帖。

# 开发

如果你希望为 Outline 贡献代码、修改或改进，可以参考[开发环境搭建指南](https://docs.getoutline.com/s/hosting/doc/local-development-5hEhFRXow7)。

## 贡献指南

Outline 由一个小团队开发和维护 —— 我们非常欢迎你帮助修复 bug 或添加新功能！

在提交 Pull Request 之前，请务必通过 [GitHub](https://www.github.com/outline/outline/issues) 创建或评论一个 Issue 与核心团队进行讨论；你也可以加入 [Discussions](https://www.github.com/outline/outline/discussions) 与我们交流。这样我们可以确保在编写代码之前达成一致的方案，从而提高你的代码被接受的可能性。

如果你正在寻找可以开始贡献的方向，以下是一些可以帮助我们改进 Outline 的方式：

- 将内容翻译成其他语言
- 参与标记为 [`good first issue`](https://github.com/outline/outline/labels/good%20first%20issue) 的问题
- 提升服务器端和前端的性能
- 提升开发体验和编写文档
- 修复 GitHub 上列出的 bug 和其他问题

## 架构

如果你有兴趣参与贡献或了解 Outline 的代码库，请首先阅读架构文档，以获得对应用程序整体结构的高层次了解。

## 调试

在开发环境中，Outline 会将带有分类前缀的简单日志输出到控制台。在生产环境中，它会输出 JSON 格式的日志，这些日志可以很容易地被你选择的日志采集管道解析。

HTTP 日志默认是禁用的，可以通过设置环境变量 `DEBUG=http` 来启用。

## 测试

我们力求对应用程序的关键部分进行充分的测试，但并不追求 100% 的单元测试覆盖率。所有 API 接口以及与身份验证相关的功能都应进行充分测试。

添加新测试时，请使用 [Jest](https://facebook.github.io/jest/) 编写测试代码，并在被测试代码的旁边添加 `.test.js` 扩展名的测试文件。

```shell
# 运行所有测试
make test

# 以监听模式运行后端测试
make watch
```

当使用 `make test` 创建测试数据库后，你可以单独运行前端和后端的测试。

```shell
# 运行后端测试
yarn test:server

# 运行特定的后端测试
yarn test:server myTestFile

# 运行前端测试
yarn test:app
```

## 数据库迁移

使用 Sequelize 来创建和运行迁移脚本，例如：

```shell
yarn sequelize migration:generate --name my-migration
yarn sequelize db:migrate
```

或者在测试数据库中运行迁移：

```shell
yarn sequelize db:migrate --env test
```

# 活跃度

![Alt](https://repobeats.axiom.co/api/embed/ff2e4e6918afff1acf9deb72d1ba6b071d586178.svg "Repobeats 统计图")

# 许可证

Outline 使用 BSL 1.1 许可证 进行授权。