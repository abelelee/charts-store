以下是保留原始 Markdown 格式并翻译为中文的内容：

---

<picture>
    <source srcset="./.github/logo-dark.png" media="(prefers-color-scheme: light)">
    <source srcset="./.github/logo-white.png" media="(prefers-color-scheme: dark)">
    <img src="./.github/logo-dark.png" alt="logo">
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

[![contributors](https://contrib.rocks/image?repo=corentinth/it-tools&refresh=1)](https://github.com/corentinth/it-tools/graphs/contributors)

## 致谢

由 [Corentin Thomasset](https://corentin.tech?utm_source=it-tools&utm_medium=readme) 编写 ❤️。

本项目使用 [vercel.com](https://vercel.com) 进行持续部署。

贡献图由 [contrib.rocks](https://contrib.rocks/preview?repo=corentinth/it-tools) 生成。

<a href="https://www.producthunt.com/posts/it-tools?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-it&#0045;tools" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=345793&theme=light" alt="IT&#0032;Tools - Collection&#0032;of&#0032;handy&#0032;online&#0032;tools&#0032;for&#0032;devs&#0044;&#0032;with&#0032;great&#0032;UX | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" /></a>
<a href="https://www.producthunt.com/posts/it-tools?utm_source=badge-top-post-badge&utm_medium=badge&utm_souce=badge-it&#0045;tools" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/top-post-badge.svg?post_id=345793&theme=light&period=daily" alt="IT&#0032;Tools - Collection&#0032;of&#0032;handy&#0032;online&#0032;tools&#0032;for&#0032;devs&#0044;&#0032;with&#0032;great&#0032;UX | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" /></a>

## 许可证

本项目采用 [GNU GPLv3](LICENSE) 许可证。