<picture>
    <source srcset="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/logo-dark.png" media="(prefers-color-scheme: light)">
    <source srcset="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/logo-white.png" media="(prefers-color-scheme: dark)">
    <img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/logo-dark.png" alt="logo">
</picture>

面向开发者和 IT 从业者的实用工具。[点击看看！](https://it-tools.tech)

## 功能与路线图

请查看 [issues](https://github.com/CorentinTh/it-tools/issues)，了解计划实现的功能列表。

你有新的工具想法吗？提交一个 [功能请求](https://github.com/CorentinTh/it-tools/issues/new/choose)！

## 自托管

适用于你的家庭实验室的自托管方案。

**从 Docker Hub 获取：**

```sh
docker run -d --name it-tools --restart unless-stopped -p 8080:80 corentinth/it-tools:latest
```

**从 GitHub Packages 获取：**

```sh
docker run -d --name it-tools --restart unless-stopped -p 8080:80 ghcr.io/corentinth/it-tools:latest
```

**其他方案：**

- [Cloudron](https://www.cloudron.io/store/tech.ittools.cloudron.html)
- [Tipi](https://www.runtipi.io/docs/apps-available)
- [Unraid](https://unraid.net/community/apps?q=it-tools)

## 贡献代码

### 推荐的 IDE 设置

使用 [VSCode](https://code.visualstudio.com/) 并安装以下扩展：

- [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)（并禁用 Vetur）
- [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [i18n Ally](https://marketplace.visualstudio.com/items?itemName=lokalise.i18n-ally)

建议设置如下：

```json
{
  "editor.formatOnSave": false,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "i18n-ally.localesPaths": ["locales", "src/tools/*/locales"],
  "i18n-ally.keystyle": "nested"
}
```

### 在 TypeScript 中支持 `.vue` 文件的类型

TypeScript 默认无法处理 `.vue` 文件的类型信息，因此我们使用 `vue-tsc` 替代 `tsc` 进行类型检查。在编辑器中，我们需要安装 [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin)，以使 TypeScript 语言服务能够识别 `.vue` 类型。

如果你觉得独立的 TypeScript 插件不够快，Volar 还实现了更高效的 [接管模式（Take Over Mode）](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669)。你可以通过以下步骤启用它：

1. 禁用内置的 TypeScript 扩展
   1. 在 VSCode 的命令面板中运行 `Extensions: Show Built-in Extensions`
   2. 找到 `TypeScript and JavaScript Language Features`，右键选择 `Disable (Workspace)`
2. 在命令面板中运行 `Developer: Reload Window` 以重新加载 VSCode 窗口。

### 项目设置

```sh
pnpm install
```

### 开发环境编译和热重载

```sh
pnpm dev
```

### 类型检查、编译并为生产环境打包

```sh
pnpm build
```

### 使用 [Vitest](https://vitest.dev/) 运行单元测试

```sh
pnpm test
```

### 使用 [ESLint](https://eslint.org/) 进行代码检查

```sh
pnpm lint
```

### 创建新工具

要创建一个新工具，可以运行以下命令生成工具模板：

```sh
pnpm run script:create:tool my-tool-name
```

该命令将在 `src/tools` 下创建一个新目录，并包含必要的文件，同时在 `src/tools/index.ts` 中自动导入。你只需将新工具添加到正确的分类中并开发其功能。

## 贡献者

感谢所有已经做出贡献的人！

[![contributors](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/68747470733a2f2f636f6e747269622e726f636b732f696d6167653f7265706f3d636f72656e74696e74682f69742d746f6f6c7326726566726573683d31.svg)](https://github.com/corentinth/it-tools/graphs/contributors)

## 致谢

由 [Corentin Thomasset](https://corentin.tech?utm_source=it-tools&utm_medium=readme) 编写 ❤️。

本项目使用 [vercel.com](https://vercel.com) 进行持续部署。

贡献图由 [contrib.rocks](https://contrib.rocks/preview?repo=corentinth/it-tools) 生成。

<a href="https://www.producthunt.com/posts/it-tools?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-it&#0045;tools" target="_blank"><img alt="IT&amp;#0032;Tools - Collection&amp;#0032;of&amp;#0032;handy&amp;#0032;online&amp;#0032;tools&amp;#0032;for&amp;#0032;devs&amp;#0044;&amp;#0032;with&amp;#0032;great&amp;#0032;UX | Product Hunt" height="54" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/68747470733a2f2f6170692e70726f6475637468756e742e636f6d2f776964676574732f656d6265642d696d6167652f76312f66656174757265642e7376673f706f73745f69643d333435373933267468656d653d6c69676874.svg" width="250"/></a>
<a href="https://www.producthunt.com/posts/it-tools?utm_source=badge-top-post-badge&utm_medium=badge&utm_souce=badge-it&#0045;tools" target="_blank"><img alt="IT&amp;amp;#0032;Tools - Collection&amp;amp;#0032;of&amp;amp;#0032;handy&amp;amp;#0032;online&amp;amp;#0032;tools&amp;amp;#0032;for&amp;amp;#0032;devs&amp;amp;#0044;&amp;amp;#0032;with&amp;amp;#0032;great&amp;amp;#0032;UX | Product Hunt" height="54" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/68747470733a2f2f6170692e70726f6475637468756e742e636f6d2f776964676574732f656d6265642d696d6167652f76312f746f702d706f73742d62616467652e7376673f706f73745f69643d333435373933267468656d653d6c6967687426706572696f643d6461696c79.svg" width="250"/></a>

## 许可证

本项目采用 [GNU GPLv3](LICENSE) 许可证。