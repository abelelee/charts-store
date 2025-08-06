ToolJet 是一个**开源低代码框架**，可让您以最小的工程投入构建和部署内部工具。ToolJet 的拖放式前端构建器允许您在几分钟内创建复杂且响应式的前端界面。此外，您还可以集成多种数据源，包括 PostgreSQL、MongoDB 和 Elasticsearch 等数据库；支持 OpenAPI 规范和 OAuth2 的 API 接口；Stripe、Slack、Google Sheets、Airtable 和 Notion 等 SaaS 工具；以及 S3、GCS 和 Minio 等对象存储服务，以读取和写入数据。

 :star: 如果您觉得 ToolJet 有用，请考虑在 GitHub 上给我们一个 Star！您的支持帮助我们持续创新并推出令人期待的新功能。

![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/tooljet/tooljet-ce)
![GitHub 贡献者数量](https://img.shields.io/github/contributors/tooljet/tooljet)
[![GitHub 上的未解决问题数量](https://img.shields.io/github/issues/ToolJet/ToolJet)](https://github.com/ToolJet/ToolJet/issues)
[![GitHub Star 数量](https://img.shields.io/github/stars/ToolJet/ToolJet)](https://github.com/ToolJet/ToolJet/stargazers)
![GitHub 已关闭的问题数量](https://img.shields.io/github/issues-closed/tooljet/tooljet)
![GitHub 上的未合并 Pull Request 数量](https://img.shields.io/github/issues-pr-raw/tooljet/tooljet)
![GitHub 最新发布版本](https://img.shields.io/github/v/release/tooljet/tooljet)
![GitHub 提交活跃度](https://img.shields.io/github/commit-activity/m/tooljet/tooljet)
[![GitHub 使用的 AGPL 许可证](https://img.shields.io/github/license/ToolJet/ToolJet)](https://github.com/ToolJet/ToolJet)
[![在 X（原 Twitter）上关注我们](https://img.shields.io/twitter/follow/ToolJet?style=social)](https://twitter.com/ToolJet)

<p align="center">
    <img src="https://user-images.githubusercontent.com/7828962/211444352-4d6d2e4a-13c9-4980-9e16-4aed4af9811b.png" alt="显示库存和订单的 Tooljet 仪表板"/>
</p>

<p align="center">
    <img src="https://github.com/ToolJet/ToolJet/assets/25361949/0e711f3a-edb7-496b-8833-107de3826933"/>
</p>

## 所有功能

- **可视化应用构建器：** 45+ 内置响应式组件，包括表格、图表、列表、表单和进度条。
- **ToolJet 数据库：** 内置的无代码数据库。
- **多页面：** 构建包含多个页面的应用程序。
- **多人协作编辑：** 支持多名开发者同时构建应用。
- **50+ 数据源：** 可集成外部数据库、云存储和 API。
- **桌面与移动端：** 自定义布局宽度以适配各种屏幕尺寸。
- **自托管：** 支持 Docker、Kubernetes、AWS EC2、Google Cloud Run 等。
- **协作：** 在画布任意位置添加评论并@团队成员。
- **插件扩展：** 使用我们的 [命令行工具](https://www.npmjs.com/package/@tooljet/cli) 轻松创建新连接器。
- **版本控制：** 通过结构化发布周期管理多个应用版本。
- **运行 JS 与 Python 代码：** 执行自定义的 JavaScript 和 Python 代码片段。
- **细粒度访问控制：** 支持在组和应用级别设置权限。
- **低代码：** 几乎可在构建器的任何地方使用 JS 代码，例如使用 `status === 'success' ? 'green' : 'red'` 设置文本颜色。
- **无代码查询编辑器：** 所有支持的数据源均提供查询编辑器。
- **连接与转换数据：** 使用 JavaScript 或 Python 代码转换查询结果。
- **安全：** 所有凭据均使用 `aes-256-gcm` 安全加密。
- **数据隐私：** ToolJet 仅作为代理，不存储任何数据。
- **SSO：** 支持多种单点登录提供商。

<hr>

## 快速开始
使用 ToolJet 的最简单方法是创建一个 [ToolJet Cloud](https://tooljet.ai) 账户。ToolJet Cloud 提供了托管版本的 ToolJet。如果您希望自托管 ToolJet，请参考 [部署文档](https://docs.tooljet.ai/docs/setup/)。

### 使用 Docker 快速体验
想要在本地快速运行 ToolJet？您可以在终端中运行以下命令，立即启动 ToolJet。

```bash
docker run \
  --name tooljet \
  --restart unless-stopped \
  -p 80:80 \
  --platform linux/amd64 \
  -v tooljet_data:/var/lib/postgresql/13/main \
  tooljet/try:ee-lts-latest
```

*对于需要升级 ToolJet 版本的用户，我们建议选择 LTS 版本而非最新版本。LTS 版本确保了生产环境下的稳定性，包括 bug 修复、安全补丁和性能优化。*

## 教程与示例

[时间追踪应用](https://docs.tooljet.ai/docs/#quickstart-guide)<br>
[使用低代码构建自己的 CMS](https://blog.tooljet.ai/build-cms-using-lowcode-and-mongodb/)<br>
[AWS S3 浏览器](https://blog.tooljet.ai/build-an-aws-s3-broswer-with-tooljet/)<br>

## 文档
文档地址：https://docs.tooljet.ai

- [入门指南](https://docs.tooljet.ai)<br>
- [数据源参考](https://docs.tooljet.ai/docs/data-sources/airtable/)<br>
- [组件参考](https://docs.tooljet.ai/docs/widgets/button)

## 自托管
您可以使用 ToolJet Cloud 获取完全托管的解决方案。如果您希望自托管 ToolJet，我们提供了在 Kubernetes、AWS EC2、Docker 等平台上的部署指南。

| 提供商  | 文档 |
| :------------- | :------------- |
| Digital Ocean | [链接](https://docs.tooljet.ai/docs/setup/digitalocean)  |
| Docker  | [链接](https://docs.tooljet.ai/docs/setup/docker)   |
| AWS EC2 | [链接](https://docs.tooljet.ai/docs/setup/ec2)  |
| AWS ECS | [链接](https://docs.tooljet.ai/docs/setup/ecs)   |
| OpenShift | [链接](https://docs.tooljet.ai/docs/setup/openshift)   |
| Helm | [链接](https://docs.tooljet.ai/docs/setup/helm)   |
| AWS EKS (Kubernetes) | [链接](https://docs.tooljet.ai/docs/setup/kubernetes)   |
| GCP GKE (Kubernetes) | [链接](https://docs.tooljet.ai/docs/setup/kubernetes-gke)   |
| Azure AKS (Kubernetes) | [链接](https://docs.tooljet.ai/docs/setup/kubernetes-aks)   |
| Azure 容器 | [链接](https://docs.tooljet.ai/docs/setup/azure-container)   |
| Google Cloud Run  | [链接](https://docs.tooljet.ai/docs/setup/google-cloud-run)   |
| 部署 ToolJet 客户端  | [链接](https://docs.tooljet.ai/docs/setup/client)   |
| 在子路径上部署 ToolJet  | [链接](https://docs.tooljet.ai/docs/setup/tooljet-subpath/)   |

## 市场
ToolJet 现已在 AWS 和 Azure 市场上线，使访问和部署我们的应用构建平台变得更加简单。

在 AWS Marketplace 上查找 ToolJet [点击此处](https://aws.amazon.com/marketplace/pp/prodview-fxjto27jkpqfg?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)，在 Azure Marketplace 上查看无缝集成 [点击此处](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/tooljetsolutioninc1679496832216.tooljet?tab=Overview)。

## 社区支持
如需使用 ToolJet 的一般帮助，请参考官方 [文档](https://docs.tooljet.ai/docs/)。如需进一步帮助，您可以通过以下渠道提问：

- [Slack](https://tooljet.ai/slack) - 与社区和团队进行讨论。
- [GitHub](https://github.com/ToolJet/ToolJet/issues) - 报告 Bug 和提出功能请求。
- [𝕏 (Twitter)](https://twitter.com/ToolJet) - 快速获取产品更新。

## 路线图
查看我们的 [路线图](https://github.com/orgs/ToolJet/projects/15) 以了解最新发布的功能以及即将推出的内容。

## 分支模型
我们使用 git-flow 分支模型。主分支是 `develop`。如需使用稳定版本，请使用 main 分支或标记为 v1.x.x 的版本。

## 贡献
请阅读我们的 [贡献指南](CONTRIBUTING.md)，了解 ToolJet 的开发流程、如何提出 bug 修复和改进建议，以及构建和测试更改的步骤。<br>

## 贡献者
<a href="https://github.com/tooljet/tooljet/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=tooljet/tooljet&max=400&columns=20" />
  <img src="https://us-central1-tooljet-hub.cloudfunctions.net/github" width="0" height="0" />
</a>

## 许可证
ToolJet © 2023, ToolJet Solutions Inc - 遵循 GNU Affero 通用公共许可证 v3.0。