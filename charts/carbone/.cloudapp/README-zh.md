以下是你提供的 Markdown 内容的中文翻译，保留了原始格式：

---

<p align="center">
  <a href="https://carbone.io/" target="_blank">
    <img alt="CarboneJS" width="100" src="https://carbone.io/img/carbone_icon_v3_github.png">
  </a>
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/carbone">
    <img src="https://badgen.net/npm/dt/carbone" alt="npm badge">
  </a>
  <a href="https://www.npmjs.com/package/carbone">
    <img src="https://badgen.net/npm/dm/carbone" alt="npm badge">
  </a>
  <a href="https://www.npmjs.com/package/carbone">
    <img src="https://badgen.net/npm/v/carbone" alt="carbone version badge">
  </a><br/>
  <a href="https://carbone.io/documentation.html">
    <img src="https://readthedocs.org/projects/ansicolortags/badge/?version=latest" alt="documentation badge">
  </a>
  <a href="https://bundlephobia.com/result?p=carbone">
    <img src="https://badgen.net/bundlephobia/minzip/carbone" alt="minizip badge">
  </a>
  <a href="https://hub.docker.com/r/carbone/carbone-ee">
    <img src="https://badgen.net/docker/pulls/carbone/carbone-ee?icon=docker" alt="docker badge">
  </a>
  <a href="https://github.com/carboneio/carbone">
    <img src="https://badgen.net/github/forks/carboneio/carbone?icon=github" alt="github fork badge">
  </a>
</p>

<p><b>⚡️ 快速、简单且强大的报表生成器</b>，支持 PDF、DOCX、XLSX、ODT、PPTX、ODS、XML、CSV 等格式，只需使用模板和 JSON 数据作为输入即可！</p>

### 最新消息 2025/03

[加入我们的 Discord 频道](https://discord.gg/kKB3aPYqnh)

使用最新版本（v4+）免费体验我们的 [Docker 版本](https://hub.docker.com/r/carbone/carbone-ee)：

```sh
  docker pull carbone/carbone-ee
```

启动 [本地 Docker 版本](https://hub.docker.com/r/carbone/carbone-ee) 并使用 REST API 时无需许可证（与 [云端版本](https://carbone.io/pricing.html) 的 API 相同）。
只有在使用某些高级功能时才需要许可证。默认情况下，仅启用社区功能。

为什么这么做？我们希望尽可能优化时间。我们正在为 [期待已久的 Carbone v5](https://carbone.io/carbone-v5.html)（新编辑器、新网站、AI 等）开发许多新功能。
在 Docker 版本中启用社区功能更加简单。该版本与企业版一样，通过自动 CI 定期更新。

开源版本将在 v5 正式发布时更新到 v4。开源版本始终比企业版本落后一个主版本（v3+）。

如有进一步问题或需要**专业支持**，欢迎通过 [聊天窗口](https://carbone.io) 联系我们。

## 目录

README 语言： 🇨🇳 [简体中文](./doc/README.zh-cn.md), 🇺🇸 [English](README.md)

<!-- MarkdownTOC -->

- [功能](#features)
- [工作原理](#how-it-works)
- [最低要求](#minimum-requirements)
- [快速开始](#getting-started)
  - [基础示例](#basic-sample)
  - [PDF 生成，文档转换](#pdf-generation-document-conversion)
- [更多示例](#more-examples)
- [API 参考](#api-reference)
- [命令行工具](#command-line-tools)
- [问题反馈](#issues)
- [路线图](#roadmap)
- [性能](#performance)
- [许可与版本](#licenses-and-editions)
- [理念](#philosophy)
- [贡献者](#contributors)

<!-- /MarkdownTOC -->

## 功能

  - 🍏  **极其简单** ：使用 LibreOffice™、Google Docs、Microsoft Office™、TinyMCE、CKEditor 等创建模板
  - 🎨 **无限设计** ：文档编辑器的限制即为你的限制：分页、页眉、页脚、表格等
  - 📝 **文档转换** ：得益于内置的文档转换器
  - 📐 **独特的模板引擎** ：直接在文档中插入类 JSON 标记 `{d.companyName}`
  - ⭐️ **灵活** ：可使用任何 XML 文档作为模板：docx、odt、ods、xlsx、html、pptx、odp、自定义 XML 文件等
  - 🚀 **面向未来** ：强大的 XML 无关算法无需了解 XML 规范即可处理文档
  - 🌈 **多语言支持** ：一个模板，多种语言。自动更新翻译文件
  - 💎 **数据格式化** ：使用内置的日期和数字格式化器，或使用 JavaScript 自定义
  - 🏎 **快速** ：支持多线程 LibreOffice 文档转换，为每个报表优化代码生成

## 工作原理

Carbone 是一个类似 Mustache 的模板引擎 `{d.companyName}`。

模板语言文档：https://carbone.io/documentation.html

- 模板可以是来自 LibreOffice™ 或 Microsoft Office™ 的任意 XML 文档（如 ods、docx、odt、xlsx 等）
- 注入的数据必须是 JSON 对象或数组，例如来自你现有 API 的数据

Carbone 会分析你的模板并注入数据。生成的文档可以原样导出，也可以在系统安装了 LibreOffice 的情况下转换为其他格式（如 PDF）。
Carbone 仅在服务器端运行。

## 最低要求

- NodeJS 14.x+
- 支持 macOS、Linux（服务器和桌面）、Windows

#### 可选

- 如果你想使用文档转换器并生成 PDF，则需要安装 LibreOffice。如果没有 LibreOffice，你仍然可以生成 docx、xlsx、pptx、odt、ods、odp、html 等格式，只要你的模板是相同格式即可。

## 快速开始

### 基础示例

1 - 安装

```bash
  npm install carbone
```

2 - 将以下代码复制到一个新的 JS 文件中，并使用 node 执行

```javascript
  const fs = require('fs');
  const carbone = require('carbone');

  // 要注入的数据
  var data = {
    firstname : 'John',
    lastname : 'Doe'
  };

  // 使用 carbone 模块提供的示例模板生成报告
  // 该 LibreOffice 模板包含 "Hello {d.firstname} {d.lastname} !"
  // 当然，你可以创建自己的模板！
  carbone.render('./node_modules/carbone/examples/simple.odt', data, function(err, result){
    if (err) {
      return console.log(err);
    }
    // 写入结果
    fs.writeFileSync('result.odt', result);
  });
```

### PDF 生成，文档转换

Carbone 高效地使用 LibreOffice 进行文档转换。在所有测试过的方案中，这是目前生产环境中最可靠和稳定的解决方案。

Carbone 在后台为你做了很多事情：

- 以“服务器模式”启动 LibreOffice：无界面、无用户界面加载
- 管理多个 LibreOffice 工作进程以最大化性能（可配置的工作进程数）
- 如果 LibreOffice 崩溃或无响应，会自动重启
- 任务队列，如果发生异常会自动重试三次转换

##### 1 - 安装 LibreOffice

###### 在 macOS 上

- 从 https://www.libreoffice.org/ 下载稳定版本并正常安装

###### 在 Ubuntu 服务器 & 桌面

> 注意：通过 PPA libreoffice/ppa 提供的 LibreOffice 不包含 Python（Carbone 必需）。最佳方案是从官网下载 LibreOffice 安装包并手动安装：

```bash
  # 删除所有旧版本的 LibreOffice
  sudo apt remove --purge libreoffice*
  sudo apt autoremove --purge

  # 下载 LibreOffice Debian 安装包。根据你的操作系统选择正确的版本（64 位或 32 位）
  # 从 http://download.documentfoundation.org/libreoffice/stable 获取最新版本
  # 或下载当前 "carbone-tested" 版本：
  wget https://downloadarchive.documentfoundation.org/libreoffice/old/7.5.1.1/deb/x86_64/LibreOffice_7.5.1.1_Linux_x86-64_deb.tar.gz

  # 安装 LibreOffice 7.0+ 所需依赖
  sudo apt install libxinerama1 libfontconfig1 libdbus-glib-1-2 libcairo2 libcups2 libglu1-mesa libsm6

  # 解压安装包
  tar -zxvf LibreOffice_7.5.1.1_Linux_x86-64_deb.tar.gz
  cd LibreOffice_7.5.1.1_Linux_x86-64_deb/DEBS

  # 安装 LibreOffice
  sudo dpkg -i *.deb

  # 如果你想在报告中使用 Microsoft 字体，必须安装这些字体
  # Andale Mono, Arial Black, Arial, Comic Sans MS, Courier New, Georgia, Impact,
  # Times New Roman, Trebuchet, Verdana, Webdings
  sudo apt install ttf-mscorefonts-installer

  # 如果你想使用特殊字符，比如中文字符，必须安装支持这些字符的字体
  # 例如：
  sudo apt install fonts-wqy-zenhei
```

##### 2 - 生成 PDF

现在，你可以通过向 render 方法传递选项来使用转换器。

> 不用担心，只有第一次转换较慢，因为 LibreOffice 需要启动
> 一旦启动，LibreOffice 会保持运行以加快后续转换

```javascript
  var data = {
    firstname : 'John',
    lastname : 'Doe'
  };

  var options = {
    convertTo : 'pdf' // 也可以是 docx, txt 等
  };

  carbone.render('./node_modules/carbone/examples/simple.odt', data, options, function(err, result){
    if (err) return console.log(err);
    fs.writeFileSync('result.pdf', result);
    process.exit(); // 自动终止 LibreOffice 工作进程
  });
```

## 更多示例

##### 在 docx 文档和电子表格中嵌套重复

```javascript

  var data = [
    {
      movieName : 'Matrix',
      actors    : [{
        firstname : 'Keanu',
        lastname  : 'Reeves'
      },{
        firstname : 'Laurence',
        lastname  : 'Fishburne'
      },{
        firstname : 'Carrie-Anne',
        lastname  : 'Moss'
      }]
    },
    {
      movieName : 'Back To The Future',
      actors    : [{
        firstname : 'Michael',
        lastname  : 'J. Fox'
      },{
        firstname : 'Christopher',
        lastname  : 'Lloyd'
      }]
    }
  ];

  carbone.render('./node_modules/carbone/examples/movies.docx', data, function(err, result){
    if (err) return console.log(err);
    fs.writeFileSync('movies_result.docx', result);
  });

  carbone.render('./node_modules/carbone/examples/flat_table.ods', data, function(err, result){
    if (err) return console.log(err);
    fs.writeFileSync('flat_table_result.ods', result);
  });
```

## API 参考

如需查看 **[API 文档](https://carbone.io/documentation/developer/embedding/embedding-in-node.html)** 和 **[完整文档](https://carbone.io/documentation)**，请访问 [carbone.io](http://carbone.io)

## 命令行工具

如需查看 Carbone CLI 文档，请访问 [carbone.io](https://carbone.io/documentation/developer/embedding/embedding-in-node.html#cli)

## 问题反馈

如果你在使用社区版时遇到任何问题，请先在 [Github](https://github.com/carboneio/carbone/issues) 上搜索类似问题，确认是否已有相关 issue。如果没有，请 [创建一个 issue 帮助我们改进](https://github.com/carboneio/carbone/issues/new/choose)

## 路线图

路线图已固定在 Github issues 列表中。

## 性能

⚡️ 2023 年 2 月 14 日内部消息：我们正在开发自己的 PDF 转换器，速度是 LibreOffice 的 200 倍！敬请期待。

使用基础一页 DOCX 模板进行报表生成的速度（不包括网络延迟）：

  - ~ `10 ms / 报表` 无需文档转换（分析、注入、渲染）
  - ~ `50 ms / 报表` 需要 PDF 转换（100 次循环，3 个 LibreOffice 工作进程，非冷启动）

测试环境：MacBook Pro Mid-2015，2.2 GHz i7，16GB 内存

## 许可与版本

Carbone 有两个版本：

- Carbone 社区版：根据 [CCL 协议](LICENSE.md) 免费提供。简而言之，只要你不是将 Carbone 社区版作为托管服务（如 [Carbone Cloud](https://carbone.io/pricing.html)）提供，你可以免费使用和修改所有社区功能。
- Carbone 企业版（托管和本地）包含更多高级功能。这里是 [社区版与企业版功能对比表](https://carbone.io/documentation/design/overview/template-feature.html#template-types)

社区版始终比企业版落后一个主版本。未来可能会有变化。

## 理念

> 我们的终极目标

我们托管服务收入的 [2%](https://help.carbone.io/en-us/article/2-for-charitable-purposes-59iyg3) 将用于慈善事业

## 贡献者

感谢所有 Carbone 贡献者（随机排序）

  - Florian Bezagu
  - Matthieu Robin
  - Arnaud Lelièvre
  - Maxime Vincent
  - Enzo Ghemard
  - Jordan Nourry
  - Etienne Rouillard
  - Guillaume Chevaux
  - Fabien Bigant
  - Maxime Magne
  - Vincent Bertin
  - Léo Labruyère
  - Aurélien Kermabon
  - [Steeve Payraudeau](https://github.com/steevepay)