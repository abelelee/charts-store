## LanguageTool

**LanguageTool** 是一个开源的校对软件，支持英语、西班牙语、法语、德语、葡萄牙语、波兰语、荷兰语，以及[超过 20 种其他语言](https://languagetool.org/languages/)。
它能够发现许多简单拼写检查器无法检测到的错误。

* [LanguageTool 论坛](https://forum.languagetool.org)
* [如何运行你自己的 LanguageTool 服务器](https://dev.languagetool.org/http-server)
* [HTTP API 文档](https://languagetool.org/http-api/swagger-ui/#!/default/post_check)
* [如何通过 HTTP 使用我们的公共服务器](https://dev.languagetool.org/public-http-api)
* [如何从 Java 使用 LanguageTool](https://dev.languagetool.org/java-api) ([Javadoc](https://languagetool.org/development/api/index.html?org/languagetool/JLanguageTool.html))

更多信息，请查看我们的主页 https://languagetool.org，
[this README](https://github.com/languagetool-org/languagetool/blob/master/languagetool-standalone/README.md)，
以及 [CHANGES](https://github.com/languagetool-org/languagetool/blob/master/languagetool-standalone/CHANGES.md)。

LanguageTool 核心（本仓库）根据 LGPL 2.1 或更高版本自由分发。

## Docker

以下是一些社区贡献的 Docker 配置项目：

- https://github.com/meyayl/docker-languagetool ([Docker Hub](https://hub.docker.com/r/meyay/languagetool))
- https://github.com/Erikvl87/docker-languagetool ([Docker Hub](https://hub.docker.com/r/erikvl87/languagetool))
- https://github.com/silvio/docker-languagetool ([Docker Hub](https://hub.docker.com/r/silviof/docker-languagetool))

## 贡献

[开发概览](https://dev.languagetool.org/development-overview) 页面描述了如何贡献错误检测规则。

更多技术细节，请参阅 [我们的开发页面](https://dev.languagetool.org)。

## 脚本化安装与构建
要使用脚本进行安装或构建，请运行以下命令：
```bash
curl -L https://raw.githubusercontent.com/languagetool-org/languagetool/master/install.sh | sudo bash <options>
```

如需更多选项，请下载 `install.sh` 脚本。使用选项如下：

```bash
sudo bash install.sh <options>

Usage: install.sh <option> <package>
选项:
   -h --help                   显示帮助信息
   -b --build                  从 LanguageTool 的最新开发版本构建包
   -c --command <command>      指定安装后运行的命令（默认在检测到屏幕时运行 gui）
   -q --quiet                  安静模式！只显示重要信息！
   -t --text <file>            指定 LanguageTool 命令行要拼写检查的文本（默认 spellcheck.txt）
   -d --depth <value>          指定自行构建 LanguageTool 时的克隆深度（默认 1）
   -p --package <package>      指定构建时安装的包（默认 all）
   -o --override <OS>          使用 <OS> 覆盖自动检测到的操作系统
   -a --accept                 接受 http://java.com/license 的许可协议。仅在你已阅读并同意其条款时运行！
   -r --remove <all/partial>   卸载 LanguageTool 安装。<all> 会卸载自动安装的依赖项（默认 partial）

包（仅在指定 -b 时有效）:
   standalone                  安装独立包
   wikipedia                   安装维基百科包
   office-extension            安装 LibreOffice/OpenOffice 扩展包

命令:
   GUI                         运行 LanguageTool 的图形界面版本
   commandline                 运行 LanguageTool 的命令行版本
   server                      运行 LanguageTool 的服务器版本
```

## 从源代码构建的另一种方式

开始前：你需要从 GitHub 克隆代码，并安装 Java 17 和 Apache Maven。

警告：完整克隆需要下载超过 500 MB 的数据，并占用超过 1500 MB 的磁盘空间。
如果你只需要主分支的最近几次提交，可以通过创建浅层克隆来减少占用：

    git clone --depth 5 https://github.com/languagetool-org/languagetool.git

浅层克隆仅需下载不到 60 MB 的数据，占用磁盘空间小于 200 MB。

在项目根目录运行：

    mvn clean test

（有时重复构建时可以跳过 Maven 步骤）

    ./build.sh languagetool-standalone package -DskipTests

在 `languagetool-standalone/target/` 中测试结果。

    ./build.sh languagetool-wikipedia package -DskipTests

在 `languagetool-wikipedia/target` 中测试结果。

现在你可以使用最新的 LanguageTool 开发版本的 `*.jar` 文件，但请注意它可能包含回归错误。

### 如何在 Mac M1 或 M2 上运行

1. 为 Rosetta 安装 Brew: `arch -x86_64 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`
2. 为 Rosetta 安装 openjdk: `arch -x86_64 brew install openjdk`
3. 为 Rosetta 安装 Maven: `arch -x86_64 brew install maven`
4. 现在运行构建脚本

### 许可证

除非另有说明，本软件（LanguageTool 核心）根据 LGPL 分发，请参阅文件 [COPYING.txt](https://github.com/languagetool-org/languagetool/blob/master/COPYING.txt)。