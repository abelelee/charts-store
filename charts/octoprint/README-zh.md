<p align="center"><img src="https://octoprint.org/assets/img/logo.png" alt="OctoPrint的标志" /></p>

<h1 align="center">OctoPrint</h1>

<p align="center">
  <img src="https://img.shields.io/github/v/release/OctoPrint/OctoPrint?logo=github&logoColor=white" alt="GitHub发布版本"/>
  <img src="https://img.shields.io/pypi/v/OctoPrint?logo=python&logoColor=white" alt="PyPI"/>
  <img src="https://img.shields.io/github/actions/workflow/status/OctoPrint/OctoPrint/build.yml?branch=master" alt="构建状态"/>
  <a href="https://community.octoprint.org"><img src="https://img.shields.io/discourse/users?label=论坛&logo=discourse&logoColor=white&server=https%3A%2F%2Fcommunity.octoprint.org" alt="社区论坛"/></a>
  <a href="https://discord.octoprint.org"><img src="https://img.shields.io/discord/704958479194128507?label=discord&logo=discord&logoColor=white" alt="Discord"/></a>
  <a href="https://octoprint.org/conduct/"><img src="https://img.shields.io/badge/Contributor%20Covenant-v2.0%20采用-ff69b4.svg" alt="贡献者公约"/></a>
  <a href="https://github.com/astral-sh/ruff"><img src="https://img.shields.io/badge/代码风格-ruff-261230" alt="代码检查与格式化：ruff"/></a>
  <a href="https://github.com/prettier/prettier"><img src="https://img.shields.io/badge/代码风格-prettier-ff69b4.svg" alt="代码风格：prettier"/></a>
  <a href="https://github.com/pre-commit/pre-commit"><img src="https://img.shields.io/badge/pre--commit-已启用-brightgreen?logo=pre-commit&logoColor=white" alt="pre-commit"/></a>
</p>

OctoPrint 提供了一个快速响应的网页界面，用于控制消费级3D打印机。它是一款自由软件，发布于 [GNU Affero 通用公共许可证 V3](https://www.gnu.org/licenses/agpl-3.0.html)[^1]。

其官方网站位于 [octoprint.org](https://octoprint.org/?utm_source=github&utm_medium=readme)。

社区论坛位于 [community.octoprint.org](https://community.octoprint.org/?utm_source=github&utm_medium=readme)，它也作为一个知识库中心。

Discord服务器的邀请链接位于 [discord.octoprint.org](https://discord.octoprint.org)。

常见问题解答页面位于 [faq.octoprint.org](https://faq.octoprint.org/?utm_source=github&utm_medium=readme)。

文档位于 [docs.octoprint.org](https://docs.octoprint.org)。

官方插件仓库位于 [plugins.octoprint.org](https://plugins.octoprint.org/?utm_source=github&utm_medium=readme)。

**OctoPrint 的开发离不开[社区的财务支持](https://octoprint.org/support-octoprint/?utm_source=github&utm_medium=readme)。如果你喜欢 OctoPrint，请考虑成为定期支持者！**

![截图](https://octoprint.org/assets/img/screenshot-readme.png)

你现在看到的是 OctoPrint 的源代码仓库。如果你已经安装了它（例如通过使用面向 Raspberry Pi 的发行版 [OctoPi](https://github.com/guysoft/OctoPi)），并且只是想了解如何使用它，那么[文档](https://docs.octoprint.org/)可能更适合你。你也可以考虑订阅[社区论坛 community.octoprint.org](https://community.octoprint.org)，那里有其他活跃用户，可能可以帮你解答问题。

[^1]: 如果某个特定文件或文件夹使用了其他许可证，该信息会在文件内部或文件夹的 README 中注明。关于链接和内嵌的第三方依赖的许可证，请参阅 THIRDPARTYLICENSES.md。

## 贡献

各种形式的贡献都欢迎，不仅限于代码方面，还包括[官方文档](https://docs.octoprint.org/)、在[问题跟踪器](https://github.com/OctoPrint/OctoPrint/issues)中提供调试帮助、在[社区论坛 community.octoprint.org](https://community.octoprint.org) 或 [官方 Discord 服务器 discord.octoprint.org](https://discord.octoprint.org) 中帮助其他用户，以及[财务支持](https://octoprint.org/support-octoprint/?utm_source=github&utm_medium=readme)。

如果你认为 OctoPrint 或其文档存在不足，请不要只是抱怨，而是以任何方式帮助改进它——毕竟这是一个开源项目 :)

关于如何提交问题报告或拉取请求的信息，请参阅项目的[贡献指南](https://github.com/OctoPrint/OctoPrint/blob/master/CONTRIBUTING.md)。

## 安装

不同操作系统的源码安装说明可以在[论坛](https://community.octoprint.org/tags/c/support/guides/15/setup)上找到。

如果你想在 Raspberry Pi 上运行 OctoPrint，建议查看 [OctoPi](https://github.com/guysoft/OctoPi)，这是一个包含 OctoPrint 及其依赖的定制 SD 卡镜像。

无论操作系统和运行环境如何，通常需要执行以下步骤（以**普通用户身份**执行，不要使用 `sudo` 命令！）——假设你已经在系统中安装了 Python 3.7+、pip 和 virtualenv 及其依赖：

1. 创建一个属于用户的虚拟环境：`virtualenv venv`。如果你想使用特定版本的 Python 而不是系统默认的版本，可以通过 `--python` 参数指定，例如：`virtualenv --python=python3 venv`。
2. 在该虚拟环境中安装 OctoPrint：`./venv/bin/pip install OctoPrint`

然后可以通过 `/path/to/OctoPrint/venv/bin/octoprint` 启动 OctoPrint 服务器，详见 使用说明。

安装完成后，请确保运行首次启动向导并根据需要设置访问控制。

## 依赖项

OctoPrint 依赖一些 Python 模块来完成其功能。这些模块会在通过 `pip` 安装 OctoPrint 时自动安装。

OctoPrint 当前支持 Python 3.7、3.8、3.9、3.10、3.11、3.12 和 3.13。

对 Python 3.7 和 3.8 的支持将在 OctoPrint 1.12.0 中被移除。

## 使用

通过以下命令安装 OctoPrint：

    pip install OctoPrint

这将在你的 Python 安装目录的脚本文件夹中安装 `octoprint` 脚本（根据你是全局安装还是安装在虚拟环境中，该脚本可能在或不在你的 `PATH` 中）。以下使用示例假设 `octoprint` 脚本已在你的 `PATH` 中。

你可以通过以下命令启动服务器：

    octoprint serve

默认情况下，它绑定到所有接口的 5000 端口（因此在浏览器中打开 `http://127.0.0.1:5000` 即可访问）。如果你想更改该设置，可以使用额外的命令行参数 `host` 和 `port`，它们分别接受绑定的主机 IP 和端口号。例如，如果你想让服务器只在本地接口的 8080 端口监听，命令应为：

    octoprint serve --host=127.0.0.1 --port=8080

或者，也可以通过配置文件定义绑定的主机和端口。

如果你想在 Linux 上将 OctoPrint 作为守护进程运行，可以使用：

    octoprint daemon {start|stop|restart} [--pid PIDFILE]

如果你没有通过 `--pid PIDFILE` 指定自定义的 pid 文件路径，它将在 `/tmp/octoprint.pid` 创建。

你也可以指定配置文件或基础目录（用于 `uploads`、`timelapse` 和 `logs` 文件夹的根目录），例如：

    octoprint serve --config /path/to/another/config.yaml --basedir /path/to/my/basedir

要以安全模式启动 OctoPrint（禁用所有非自带的第三方插件），请使用 ``--safe`` 标志：

    octoprint serve --safe

更多命令行参数信息，请运行 `octoprint --help`。

OctoPrint 的源码目录中还包含一个 `run` 脚本，你可以运行它来启动服务器。它接受与 `octoprint` 脚本相同的命令行参数。

## 配置

如果没有通过命令行指定，OctoPrint 的配置文件 `config.yaml` 应位于设置目录中。该目录在 Linux 上是 `~/.octoprint`，在 Windows 上是 `%APPDATA%/OctoPrint`，在 MacOS 上是 `~/Library/Application Support/OctoPrint`。

所有可用配置选项的详细说明可以在[文档](https://docs.octoprint.org/en/master/configuration/config_yaml.html)中找到。请注意，最常用的配置选项也可以直接在 OctoPrint 的设置对话框中轻松编辑。

## 特别致谢

跨浏览器测试服务由 [BrowserStack](https://www.browserstack.com/) 提供。

性能分析由 [PyVmMonitor](https://www.pyvmmonitor.com) 提供支持。

错误追踪由 [Sentry](https://sentry.io) 提供支持和赞助。