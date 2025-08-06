---
<h1 align="center">Papermerge 文档管理系统</h1>

<p align="center">
<img src="./artwork/logo-w160px.png" />
</p>

Papermerge DMS，简称 Papermerge，是一款开源的文档管理系统，专为处理扫描文档（也称为数字档案）而设计。它通过 OCR 从扫描件中提取文本，对其进行索引，并为全文搜索做好准备。Papermerge 提供了现代桌面文件浏览器的外观和体验。它具备双面板文档浏览器、拖放操作、标签、分层文件夹以及全文搜索等功能，帮助你高效地存储和管理文档。

它支持 PDF、TIFF、JPEG 和 PNG 等文档格式。Papermerge 是用于文档长期存储的理想工具。

Papermerge 的主要使用场景是 **数字档案的长期存储**。

这是一个基于 Web 的软件。这意味着它没有可执行文件（即没有 .exe 文件），必须运行在 Web 服务器上并通过浏览器访问。

![Papermerge](./artwork/papermerge3-3.png)

## 仓库

**这是一个元仓库（meta-repository）** —— 这意味着应用程序的源代码并不在这里。**该仓库用于跟踪项目的存在状态、进度及其问题。**

随着应用的不断增长，有必要将其拆分为多个仓库，同时将新仓库统一移至 [Papermerge GitHub 组织](https://github.com/papermerge)。

| 仓库      | 描述 |
| :---------------|-------------|
| [ciur/papermerge](https://github.com/ciur/papermerge)| 用于跟踪项目状态、进度和问题的元仓库 |
| [papermerge/papermerge-core](https://github.com/papermerge/papermerge-core)| REST API 后端服务器的源代码，项目的核心 |
| [papermerge/documentation](https://github.com/papermerge/documentation)| 文档的源代码 |
| [papermerge/ansible](https://github.com/papermerge/ansible)| 用于远程服务器/虚拟机部署的 Ansible 脚本 |

## 其他资源

| 资源        | 描述 |
|-----------------|-------------|
|[https://docs.papermerge.io](https://docs.papermerge.io/)| 文档 |
|[https://papermerge.com](https://papermerge.com) | 主页 |
|[https://demo.papermerge.com](https://demo.papermerge.com) | 在线演示（用户名：demo，密码：demo） |
|[https://papermerge.blog](https://papermerge.blog) | 博客 |
|[YouTube 频道](https://www.youtube.com/@papermerge) | YouTube 频道 |
|[X/前 Twitter](https://twitter.com/papermerge) | X/前 Twitter |
|[Reddit](https://www.reddit.com/r/Papermerge/) | Reddit |

## 功能亮点

* 类似桌面体验的 Web UI
* 符合 OpenAPI 规范的 REST API
* 支持 PDF、JPEG、PNG 和 TIFF 文档格式
* 文档 OCR（光学字符识别）
* OCR 文本叠加层（可下载带有 OCR 文本叠加的文档）
* 扫描文档的全文搜索
* 文档版本控制
* 标签 - 可为文档或文件夹分配彩色标签
* 文档与文件夹 - 用户可将文档组织在文件夹中
* 文档类型（即分类）
* 每种文档类型的自定义字段（元数据）
* 多用户支持
* 页面管理 - 删除、重新排序、裁剪、移动、提取页面

## 捐赠、筹款、您的支持

如需捐赠，您可以使用 PayPal 或 GitHub 赞助：

* [通过 PayPal 捐赠](https://www.paypal.com/paypalme/eugenciur)
* [通过 GitHub 赞助](https://github.com/sponsors/ciur)

## 路线图 / 2025 年

关于项目 2025 年的开发计划，请查看：https://docs.papermerge.io/latest/roadmap/

## 贡献

我们欢迎任何形式的贡献！一般来说，如果改动非常小，例如修复文档中的拼写错误、删除未使用的变量或对 Docker 相关文件进行小幅调整，你可以直接提交 Pull Request。如果你的改动较小且合理，它将（极有可能）被立即接受。

对于较大的改动，例如新增功能，或对文档中整段内容的修改/添加/删除 —— 请**首先通过 GitHub Issue、Pull Request 或 [电子邮件](mailto:eugen@papermerge.com) 讨论**你希望进行的更改。

更多信息请参阅
[贡献指南](https://github.com/ciur/papermerge/blob/master/CONTRIBUTING.md)。