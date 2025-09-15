# Isso – 一个类似于 Disqus 的评论服务器

Isso（德语“否则我会喊”）是一个用 Python 和 JavaScript 编写的轻量级评论服务器。它的目标是作为 [Disqus](http://disqus.com) 的直接替代方案。

## 功能特性

- **支持 Markdown 格式的评论**  
  用户可以编辑或删除自己的评论（默认在 15 分钟内）。审核队列中的评论在激活前不会公开显示。
- **SQLite 后端数据库**  
  *因为评论并不是大数据。*
- **支持 Disqus 与 WordPress 评论导入**  
  你可以轻松迁移已有的 Disqus 或 WordPress 评论。
- **可配置的 JS 客户端**  
  只需嵌入一个 JS 文件，大小为 65KB（压缩后约 20KB），即可完成集成。

访问 **[isso-comments.de](https://isso-comments.de/)** 查看**在线演示**、更多详情以及[文档](https://isso-comments.de/docs/)。

## 截图

![Isso in Action](https://user-images.githubusercontent.com/10212877/167268553-3f30b448-25ff-4850-afef-df2f2e599c93.png)

## 快速开始

### 系统要求

- Python 3.8+（包含开发头文件）
- SQLite 3.3.8 或更高版本
- 一个可用的 C 编译器

你可以通过 [PyPi](https://pypi.python.org/pypi/isso/) 安装 Isso：

```console
pip install isso
```

然后，请参考 [快速入门指南](https://isso-comments.de/docs/guides/quickstart/)。

如果你遇到问题，请参考 [安装指南](https://isso-comments.de/docs/reference/installation/)，查看[常见问题](https://isso-comments.de/docs/guides/troubleshooting/)并浏览[完整文档](https://isso-comments.de/docs/)。

## Docker 支持

> [!NOTE]  
> 自 2024 年 3 月起，稳定版本的 Docker 镜像标签从 `:latest` 更改为 `:release`  
> ([#970](https://github.com/isso-comments/isso/pull/970), [#1012](https://github.com/isso-comments/isso/issues/1012))

最新稳定版本的 [Docker 镜像](https://github.com/isso-comments/isso/pkgs/container/isso) 可在 `ghcr.io/isso-comments/isso:release` 获取，而 `isso:latest` 则会在每次提交到 `master` 分支时重新构建。详见 [使用 Docker](https://isso-comments.de/docs/reference/installation/#using-docker)。

维护者建议将镜像固定到一个[发布标签](https://github.com/isso-comments/isso/pkgs/container/isso)，例如 `isso:0.13.0`。

## 贡献代码

- 非常欢迎提交 Pull Request！你可以从这些 [适合初学者的问题](https://github.com/isso-comments/isso/labels/good-first-issue) 开始。
- 参见 [贡献方式](https://isso-comments.de/docs/contributing/)
- [参与翻译](https://isso-comments.de/docs/contributing/#translations)

### 开发相关

<!-- TODO 等新文档上传后，也提及“开发与测试”章节 -->
请参考文档中的 [从源码安装](https://isso-comments.de/docs/reference/installation/#install-from-source) 部分。

### 寻求帮助

- 加入 IRC 频道 `#isso`，通过 [Libera.Chat](https://libera.chat/) 连接
- 在 [GitHub Discussions](https://github.com/isso-comments/isso/discussions) 提问

## 许可证

MIT，详见 LICENSE。