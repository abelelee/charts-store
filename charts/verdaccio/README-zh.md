[![BannerHelp](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/banner-uk.svg)](https://u24.gov.ua)

> Verdaccio 代表 **和平**，停止战争，在实现和平之前，我们将一直是黄色/蓝色 🇺🇦。

![verdaccio logo](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/verdaccio_2x.png)

![verdaccio gif](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/readme-website.png)

# 版本 Next（开发分支）

> 寻找 Verdaccio 版本 5 或 6？版本 6 是最新版本，并且是版本 5 的继任者。版本 6 需要 Node.js 18 或更高版本，并在 `6.x` 分支中维护。

> 版本 5 和 6 的插件位于 [`verdaccio/monorepo`](https://github.com/verdaccio/monorepo) 仓库中。`next-8` 版本的插件托管在本项目下的 `./packages/plugins` 文件夹中。

> 请注意，根据分支不同，贡献指南可能会有所不同。

[Verdaccio](https://verdaccio.org/) 是一个简单、**无需配置的本地私有 npm 仓库**。  
无需整个数据库即可开始使用！Verdaccio 自带**一个小型数据库**，并具备代理其他仓库（例如 npmjs.org）的能力，缓存下载的模块。  
对于希望扩展存储能力的用户，Verdaccio **支持各种社区开发的插件，可以连接到 Amazon S3、Google Cloud Storage** 等服务，或者您可以自行开发插件。

[![Verdaccio 主页](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/Homepage-Verdaccio-405236.svg)](https://verdaccio.org)
[![MIT 许可证](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/verdaccio.svg)](https://github.com/verdaccio/verdaccio/blob/master/LICENSE)
[![Verdaccio 最新版本](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/verdaccio.svg)](https://github.com/verdaccio/verdaccio)

[![文档](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/Help-Verdaccio.svg)](https://verdaccio.org/docs)
[![Discord](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/Chat-Discord.svg)](https://discord.com/channels/388674437219745793)
[![Bluesky](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/Follow-Bluesky.svg)](https://bsky.app/profile/verdaccio.org)
[![支持者](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/verdaccio.svg)](https://opencollective.com/verdaccio/contribute)
[![赞助商](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/verdaccio.svg)](https://opencollective.com/verdaccio/contribute)

[![Verdaccio 下载量](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/verdaccio.svg)](https://www.npmjs.com/package/verdaccio)
[![Docker 拉取量](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/verdaccio.svg)](https://hub.docker.com/r/verdaccio/verdaccio)
[![GitHub 星标数](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/verdaccio.svg)](https://github.com/verdaccio/verdaccio/stargazers)

[![StandWithUkraine](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/StandWithUkraine.svg)](https://github.com/vshymanskyy/StandWithUkraine/blob/main/docs/README.md)

## 版本

您可以在 [版本历史](VERSIONS.md) 中找到关于 Verdaccio 不同版本的详细信息、最低要求，以及相关的 npm 包和 Docker 镜像链接。

## 安装

> 最低需要 Node.js v18

使用 npm 安装：

```bash
npm install -g verdaccio@next-8
```

使用 `yarn`

```bash
yarn global add verdaccio@next-8
```

使用 `pnpm`

```bash
pnpm i -g verdaccio@next-8
```

或者

```bash
docker pull verdaccio/verdaccio:nightly-master
```

或者使用 _helm_ [官方图表](https://github.com/verdaccio/charts)。

```bash
helm repo add verdaccio https://charts.verdaccio.org
helm repo update
helm install verdaccio/verdaccio
```

此外，您可以阅读 [**调试指南**](https://github.com/verdaccio/verdaccio/wiki/Debugging-Verdaccio) 和 [**Docker 示例**](https://github.com/verdaccio/verdaccio/tree/master/docker-examples) 以获取更高级的开发信息。

## 插件

您可以使用 [verdaccio 生成器](https://github.com/verdaccio/generator-verdaccio-plugin) 开发自己的 [插件](https://verdaccio.org/docs/plugins)。需要安装 [Yeoman](https://yeoman.io/)。

```
npm install -g yo
npm install -g generator-verdaccio-plugin
```

了解更多 [这里](https://verdaccio.org/docs/dev-plugins) 如何开发插件。与社区分享您的插件。

## 端到端测试

在我们的兼容性测试项目中，我们致力于确保您最喜爱的命令在不同版本的 npm、pnpm 和 Yarn 中都能无缝运行。从发布包到管理依赖项。
我们的目标是让您有信心使用您偏好的包管理器而不会遇到任何问题。所以请深入查看我们的矩阵，看看您的命令在各个平台上的表现！

[了解更多或参与贡献](https://github.com/verdaccio/verdaccio/tree/master/e2e/cli)

### 命令

| cmd       | npm6 | npm7 | npm8 | npm9 | npm10 | npm11 | pnpm8 | pnpm9 | pnpm10 | yarn1 | yarn2 | yarn3 | yarn4 |
| --------- | ---- | ---- | ---- | ---- | ----- | ----- | ----- | ----- | ------ | ----- | ----- | ----- | ----- |
| publish   | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ✅    | ✅    | ✅    | ✅    |
| unpublish | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ❌    | ❌    | ❌    | ❌    |
| info      | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ✅    | ✅    | ✅    | ✅    |
| audit     | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ✅    | ✅    | ✅    | ❌    |
| install   | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ✅    | ✅    | ✅    | ✅    |
| deprecate | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ⛔    | ⛔    | ⛔    | ⛔    |
| ping      | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ⛔    | ⛔    | ⛔    | ⛔    |
| search    | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ⛔    | ⛔    | ⛔    | ⛔    |
| star      | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ⛔    | ⛔    | ⛔    | ⛔    |
| stars     | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ⛔    | ⛔    | ⛔    | ⛔    |
| dist-tag  | ✅   | ✅   | ✅   | ✅   | ✅    | ✅    | ✅    | ✅    | ✅     | ✅    | ❌    | ❌    | ❌    |

<!--          n6      n7     n8      n9     n10      n11     p8       p9      p10       y1      y2       y3      y4 -->

> 说明：
>
> - yarn 的 search 命令在 _modern_ 中存在，但它不使用搜索注册表端点。
> - yarn _modern_ 有两个 info 命令，这里使用的是 `yarn npm info`

❌ = 未测试
✅ = 已测试
⛔ = 不支持

## 捐赠

Verdaccio 由 **志愿者** 运营；没有人全职从事该项目。如果您觉得这个项目很有用，并希望支持其开发，请考虑进行长期支持性捐赠 —— **您的标志将出现在本 README 的这一部分中。**

**[捐赠](https://github.com/sponsors/verdaccio)** 💵👍🏻 从 _$1/月_ 起，或进行一次性捐赠。

## Verdaccio 能为我做什么？

### 使用私有包

如果您希望在公司内部利用 npm 包系统的全部优势，而无需将所有代码公开，并且希望像使用公共包一样轻松地使用私有包。

### 缓存 npmjs.org 仓库

如果您有多台服务器需要安装包，您可能希望使用此功能来减少延迟（假设“缓慢”的 npmjs.org 将仅每包/版本连接一次）并提供有限的故障转移（如果 npmjs.org 宕机，我们仍可能在缓存中找到有用的内容），或避免类似 _[How one developer just broke Node, Babel and thousands of projects in 11 lines of JavaScript](https://www.theregister.co.uk/2016/03/23/npm_left_pad_chaos/)_、_[Many packages suddenly disappeared](https://github.com/npm/registry-issue-archive/issues/255)_ 或 _[Registry returns 404 for a package I have installed before](https://github.com/npm/registry-issue-archive/issues/329)_ 的问题。

### 链接多个仓库

如果您在组织中使用多个仓库，并且需要在一个项目中从多个来源获取包，您可以利用 Verdaccio 的上行链路功能，链接多个仓库并从一个端点获取包。

### 覆盖公共包

如果您想使用某个第三方包的修改版本（例如，您发现了一个 bug，但维护者尚未接受 pull request），您可以将您的版本以相同名称本地发布。详见 [此处](https://verdaccio.org/docs/en/best#override-public-packages)。

### 端到端测试

Verdaccio 被证明是一个轻量级的注册表，可以在几秒钟内启动，足以用于任何 CI。许多开源项目使用 Verdaccio 进行端到端测试，例如 **create-react-app**、**mozilla neutrino**、**pnpm**、**storybook**、**babel.js**、**angular-cli** 或 **docusaurus**。您可以在此处 [了解更多](https://verdaccio.org/docs/e2e)。

此外，这里有一些启动示例：

- [e2e-ci-example-gh-actions](https://github.com/juanpicado/e2e-ci-example-gh-actions)
- [verdaccio-end-to-end-tests](https://github.com/juanpicado/verdaccio-end-to-end-tests)
- [verdaccio-fork](https://github.com/juanpicado/verdaccio-fork)

## 观看我们的视频

**Node 2022，2022 年 2 月，在线免费**

<div>
   <a href="https://portal.gitnation.org/contents/five-ways-of-taking-advantage-of-verdaccio-your-private-and-proxy-nodejs-registry">
     <img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/nodejscongress2022.jpg" alt="nodejs" width="200"/>
  </a>
</div>

您还可以查看我们之前的演讲：

- [使用 Docker 和 Verdaccio 简化集成测试 - **Docker All Hands #4 2021 年 12 月**](https://www.youtube.com/watch?v=zRI0skF1f8I)
- [**Juan Picado** – 通过在私有仓库中发布测试 React 组件的完整性 - React Finland - 2021](https://www.youtube.com/watch?v=bRKZbrlQqLY&t=16s&ab_channel=ReactFinland)
- [BeerJS Cba Meetup No. 53 2021 年 5 月 - **Juan Picado**](https://www.youtube.com/watch?v=6SyjqBmS49Y&ab_channel=BeerJSCba)
- [Node.js 依赖混淆攻击 - 2021 年 4 月 - **Juan Picado**](https://www.youtube.com/watch?v=qTRADSp3Hpo)
- [**OpenJS World 2020** 关于 \*使用多功能轻量级 Node.js 注册表保护您的项目 - **Juan Picado**](https://www.youtube.com/watch?v=oVCjDWeehAQ)
- [ViennaJS Meetup - **Priscila Olivera** 和 **Juan Picado** 介绍 Verdaccio](https://www.youtube.com/watch?v=hDIFKzmoCa)
- [Open Source? trivago - Verdaccio (**Ayush** 和 **Juan Picado**) 2020 年 1 月](https://www.youtube.com/watch?v=A5CWxJC9xzc)
- [GitNation Open Source Stage - 我们如何用 React 构建一个 Node.js 注册表 - **Juan Picado** 2019 年 12 月](https://www.youtube.com/watch?v=gpjC8Qp9B9A)
- [Verdaccio - 一个用 Node.js 构建的轻量级私有代理注册表 | **Juan Picado** 在 The Destro Dev Show 上](https://www.youtube.com/watch?reload=9&v=P_hxy7W-IL4&ab_channel=TheDestroDevShow)

## 开始使用

在终端中运行：

```bash
verdaccio
```

您需要设置一些 npm 配置，这是可选的。

```bash
npm set registry http://localhost:4873/
```

对于一次性命令或避免全局设置注册表：

```bash
NPM_CONFIG_REGISTRY=http://localhost:4873 npm i
```

现在您可以访问 [http://localhost:4873/](http://localhost:4873/)，您的本地包将在此列出并可搜索。

> 警告：Verdaccio [目前不支持 PM2 的集群模式](https://github.com/verdaccio/verdaccio/issues/1301#issuecomment-489302298)，使用集群模式运行可能会导致未知行为。

## 发布

#### 1. 创建用户并登录

```bash
npm adduser --registry http://localhost:4873
```

> 如果您使用 HTTPS，请添加适当的 CA 信息（"null" 表示从操作系统获取 CA 列表）

```bash
npm set ca null
```

#### 2. 发布您的包

```bash
npm publish --registry http://localhost:4873
```

这将提示您输入用户凭据，这些凭据将保存在 `verdaccio` 服务器上。

## Docker

以下是常用信息，Docker 和 verdaccio 的各个方面都有 [单独文档](https://www.verdaccio.org/docs/en/docker.html)

```
docker pull verdaccio/verdaccio:nightly-master
```

作为 [标签](https://hub.docker.com/r/verdaccio/verdaccio/tags/) 提供。

### 使用 Docker 运行 Verdaccio

运行 Docker 容器：

```bash
docker run -it --rm --name verdaccio -p 4873:4873 verdaccio/verdaccio
```

Docker 示例可在 [本仓库](https://github.com/verdaccio/verdaccio/tree/master/docker-examples) 中找到。

## 兼容性

Verdaccio 旨在支持标准 npm 客户端的所有功能，这些功能在私有仓库中支持是有意义的。不幸的是，并不总是可能的。

### 基本功能

- 安装包 (`npm install`, `npm update` 等) - **支持**
- 发布包 (`npm publish`) - **支持**

### 高级包控制

- 取消发布包 (`npm unpublish`) - **支持**
- 标签 (`npm dist-tag`) - **支持**
- 弃用 (`npm deprecate`) - **支持**

### 用户管理

- 注册新用户 (`npm adduser {newuser}`) - **支持**
- 修改密码 (`npm profile set password`) - **支持**
- 转移所有权 (`npm owner`) - **支持**
- Token (`npm token`) - **支持**

### 其他

- 搜索 (`npm search`) - **支持** (cli / 浏览器)
- Ping (`npm ping`) - **支持**
- 收藏 (`npm star`, `npm unstar`, `npm stars`) - **支持**

### 安全

- 审计 (`npm/yarn audit`) - **支持**

## 报告漏洞

如果您想报告一个安全漏洞，请按照我们在 [安全策略](https://github.com/verdaccio/verdaccio/security/policy) 中为您定义的步骤进行操作。

## 特别感谢

感谢以下公司通过提供免费开源许可证帮助我们实现目标。每家公司都提供了足够的资源来推动该项目前进。

| 公司         | 标志                                                                                                                                   | 许可证                                                                           |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| JetBrains    | [![jetbrain](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/logo.png)](https://www.jetbrains.com/) | JetBrains 为活跃维护者提供产品许可证，每年可续订                                  |
| Crowdin      | [![crowdin](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/logo.png)](https://crowdin.com/)          | Crowdin 提供翻译平台                                                              |
| BrowserStack | [![browserstack](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/browserstack_logo.png)](https://www.browserstack.com/)                                | BrowserStack 提供计划用于 UI 的端到端测试                                         |
| Netlify      | [![netlify](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/netlify-color-accent.svg)](https://www.netlify.com/)                              | Netlify 提供网站部署的 Pro 计划                                                   |
| Algolia      | [![algolia](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/logo.png)](https://algolia.com/)                                             | Algolia 提供网站搜索服务                                                          |
| Docker       | [![docker](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/verdaccio/image/docker.png)](https://www.docker.com/community/open-source/application)         | Docker 提供无限拉取和无限出站流量给所有用户                                       |

## 维护者

| [Juan Picado](https://github.com/juanpicado)                                   | [Ayush Sharma](https://github.com/ayusharma)                             | [Sergio Hg](https://github.com/sergiohgz)                                 |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| ![jotadeveloper](https://avatars3.githubusercontent.com/u/558752?s=120&v=4)    | ![ayusharma](https://avatars2.githubusercontent.com/u/6918450?s=120&v=4) | ![sergiohgz](https://avatars2.githubusercontent.com/u/14012309?s=120&v=4) |
|                                                                                | [@ayusharma\_](https://twitter.com/ayusharma_)                           | [@sergiohgz](https://twitter.com/sergiohgz)                               |
| [Priscila Oliveria](https://github.com/priscilawebdev)                         | [Daniel Ruf](https://github.com/DanielRuf)                               |
| ![priscilawebdev](https://avatars2.githubusercontent.com/u/29228205?s=120&v=4) | ![DanielRuf](https://avatars3.githubusercontent.com/u/827205?s=120&v=4)  |
| [@priscilawebdev](https://twitter.com/priscilawebdev)                          | [@DanielRufde](https://twitter.com/DanielRufde)                          |

您可以在 Discord 上与他们聊天，点击 [这里](http://chat.verdaccio.org)。

## 谁在使用 Verdaccio？

- [create-react-app](https://github.com/facebook/create-react-app/blob/master/CONTRIBUTING.md#customizing-e2e-registry-configuration) _(+86.2k ⭐️)_
- [Grafana](https://github.com/grafana/grafana/search?q=verdaccio) _(+54.9k ⭐️)_
- [Gatsby](https://github.com/gatsbyjs/gatsby) _(+49.2k ⭐️)_
- [Babel.js](https://github.com/babel/babel) _(+38.5k ⭐️)_
- [Docusaurus](https://github.com/facebook/docusaurus) _(+34k ⭐️)_
- [Vue CLI](https://github.com/vuejs/vue-cli) _(+27.4k ⭐️)_
- [Angular CLI](https://github.com/angular/angular-cli) _(+24.3k ⭐️)_
- [Uppy](https://github.com/transloadit/uppy) _(+23.8k ⭐️)_
- [bit](https://github.com/teambit/bit) _(+13k ⭐️)_
- [Aurelia Framework](https://github.com/aurelia/framework) _(+11.6k ⭐️)_
- [pnpm](https://github.com/pnpm/pnpm) _(+10.1k ⭐️)_
- [ethereum/web3.js](https://github.com/ethereum/web3.js) _(+9.8k ⭐️)_
- [Webiny CMS](https://github.com/webiny/webiny-js) _(+6.6k ⭐️)_
- [NX](https://github.com/nrwl/nx) _(+6.1k ⭐️)_
- [Mozilla Neutrino](https://github.com/neutrinojs/neutrino) _(+3.7k ⭐️)_
- [workshopper how to npm](https://github.com/workshopper/how-to-npm) _(+1k ⭐️)_
- [Amazon SDK for JavaScript (v3)](https://github.com/aws/aws-sdk-js-v3)
- [Amazon Encryption SDK for Javascript](https://github.com/aws/aws-encryption-sdk-javascript)

🤓 不要害羞，把自己添加到这个 README 中。

## 常见问题 / 联系 / 故障排除

如果您遇到任何问题，可以尝试以下选项。不要犹豫提问或查看我们的问题数据库。也许有人已经问过您正在寻找的问题。

- [博客](https://verdaccio.org/blog/)
- [捐赠](https://github.com/sponsors/verdaccio)
- [报告问题](https://github.com/verdaccio/verdaccio/issues/new/choose)
- [正在进行的讨论](https://github.com/orgs/verdaccio/discussions)
- [聊天](https://discord.gg/7qWJxBf)
- [标志](https://verdaccio.org/docs/logo)
- [Docker 示例](https://github.com/verdaccio/verdaccio/tree/master/docker-examples)
- [常见问题](https://github.com/verdaccio/verdaccio/discussions/categories/q-a)

## 许可证

Verdaccio 是 [MIT 许可证](https://github.com/verdaccio/verdaccio/blob/master/LICENSE)

Verdaccio 文档和标志（不包括 /thanks 中的内容，例如 /assets 文件夹中的 .md、.png、.sketch 文件）是 [Creative Commons 许可证](https://creativecommons.org/licenses/by/4.0/)。