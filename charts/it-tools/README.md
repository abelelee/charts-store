<picture>
    <source srcset="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/logo-dark.png" media="(prefers-color-scheme: light)">
    <source srcset="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/logo-white.png" media="(prefers-color-scheme: dark)">
    <img src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/logo-dark.png" alt="logo">
</picture>

Useful tools for developer and people working in IT. [Have a look !](https://it-tools.tech).

## Functionalities and roadmap

Please check the [issues](https://github.com/CorentinTh/it-tools/issues) to see if some feature listed to be implemented.

You have an idea of a tool? Submit a [feature request](https://github.com/CorentinTh/it-tools/issues/new/choose)!

## Self host

Self host solutions for your homelab

**From docker hub:**

```sh
docker run -d --name it-tools --restart unless-stopped -p 8080:80 corentinth/it-tools:latest
```

**From github packages:**

```sh
docker run -d --name it-tools --restart unless-stopped -p 8080:80 ghcr.io/corentinth/it-tools:latest
```

**Other solutions:**

- [Cloudron](https://www.cloudron.io/store/tech.ittools.cloudron.html)
- [Tipi](https://www.runtipi.io/docs/apps-available)
- [Unraid](https://unraid.net/community/apps?q=it-tools)

## Contribute

### Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) with the following extensions:

- [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur)
- [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [i18n Ally](https://marketplace.visualstudio.com/items?itemName=lokalise.i18n-ally)

with the following settings:

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

### Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin) to make the TypeScript language service aware of `.vue` types.

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented a [Take Over Mode](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669) that is more performant. You can enable it by the following steps:

1. Disable the built-in TypeScript Extension
   1. Run `Extensions: Show Built-in Extensions` from VSCode's command palette
   2. Find `TypeScript and JavaScript Language Features`, right click and select `Disable (Workspace)`
2. Reload the VSCode window by running `Developer: Reload Window` from the command palette.

### Project Setup

```sh
pnpm install
```

### Compile and Hot-Reload for Development

```sh
pnpm dev
```

### Type-Check, Compile and Minify for Production

```sh
pnpm build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
pnpm test
```

### Lint with [ESLint](https://eslint.org/)

```sh
pnpm lint
```

### Create a new tool

To create a new tool, there is a script that generate the boilerplate of the new tool, simply run:

```sh
pnpm run script:create:tool my-tool-name
```

It will create a directory in `src/tools` with the correct files, and a the import in `src/tools/index.ts`. You will just need to add the imported tool in the proper category and develop the tool.

## Contributors

Big thanks to all the people who have already contributed!

[![contributors](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/68747470733a2f2f636f6e747269622e726f636b732f696d6167653f7265706f3d636f72656e74696e74682f69742d746f6f6c7326726566726573683d31.svg)](https://github.com/corentinth/it-tools/graphs/contributors)

## Credits

Coded with ❤️ by [Corentin Thomasset](https://corentin.tech?utm_source=it-tools&utm_medium=readme).

This project is continuously deployed using [vercel.com](https://vercel.com).

Contributor graph is generated using [contrib.rocks](https://contrib.rocks/preview?repo=corentinth/it-tools).

<a href="https://www.producthunt.com/posts/it-tools?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-it&#0045;tools" target="_blank"><img alt="IT&amp;#0032;Tools - Collection&amp;#0032;of&amp;#0032;handy&amp;#0032;online&amp;#0032;tools&amp;#0032;for&amp;#0032;devs&amp;#0044;&amp;#0032;with&amp;#0032;great&amp;#0032;UX | Product Hunt" height="54" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/68747470733a2f2f6170692e70726f6475637468756e742e636f6d2f776964676574732f656d6265642d696d6167652f76312f66656174757265642e7376673f706f73745f69643d333435373933267468656d653d6c69676874.svg" width="250"/></a>
<a href="https://www.producthunt.com/posts/it-tools?utm_source=badge-top-post-badge&utm_medium=badge&utm_souce=badge-it&#0045;tools" target="_blank"><img alt="IT&amp;amp;#0032;Tools - Collection&amp;amp;#0032;of&amp;amp;#0032;handy&amp;amp;#0032;online&amp;amp;#0032;tools&amp;amp;#0032;for&amp;amp;#0032;devs&amp;amp;#0044;&amp;amp;#0032;with&amp;amp;#0032;great&amp;amp;#0032;UX | Product Hunt" height="54" src="https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/it-tools/image/68747470733a2f2f6170692e70726f6475637468756e742e636f6d2f776964676574732f656d6265642d696d6167652f76312f746f702d706f73742d62616467652e7376673f706f73745f69643d333435373933267468656d653d6c6967687426706572696f643d6461696c79.svg" width="250"/></a>

## License

This project is under the [GNU GPLv3](LICENSE).
