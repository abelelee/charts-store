---
    <h1 align="center">
    <br>
    <a href="https://easyappointments.org">
        <img src="https://raw.githubusercontent.com/alextselegidis/easyappointments/develop/logo.png" alt="Easy!Appointments" width="150">
    </a>
    <br>
    Easy!Appointments
    <br>
</h1>

<br>

<h4 align="center">
    一个功能强大的开源预约调度系统，可安装在您的服务器上。
</h4>

<p align="center">
  <img alt="GitHub" src="https://img.shields.io/github/license/alextselegidis/easyappointments?style=for-the-badge">
  <img alt="GitHub release (latest by date)" src="https://img.shields.io/github/v/release/alextselegidis/easyappointments?style=for-the-badge">
  <img alt="GitHub All Releases" src="https://img.shields.io/github/downloads/alextselegidis/easyappointments/total?style=for-the-badge">
  <a href="https://discord.com/invite/UeeSkaw">
    <img alt="Chat On Discord" src="https://img.shields.io/badge/chat-on%20discord-7289da?style=for-the-badge&logo=discord&logoColor=white">
  </a>
</p>

<p align="center">
  <a href="#about">关于</a> •
  <a href="#features">功能</a> •
  <a href="#setup">设置</a> •
  <a href="#installation">安装</a> •
  <a href="#license">许可协议</a>
</p>

![screenshot](screenshot.png)

## 关于

**Easy!Appointments** 是一个高度可定制的 Web 应用程序，允许客户通过复杂的 Web 界面与您预约。此外，它还提供了与 Google 日历同步数据的功能，以便您可以将数据用于其他服务。这是一个开源项目，您可以下载并安装它，**甚至可用于商业用途**。Easy!Appointments 可以与您现有的网站无缝协作，因为它可以安装在服务器的单个文件夹中，并且当然可以共享现有的数据库。

## 功能

该应用程序设计灵活，能够处理任何企业的业务流程。

* 客户和预约管理。
* 服务与服务人员管理。
* 工作计划和预约规则。
* Google 日历同步功能。
* 邮件通知系统。
* 自托管安装。
* 多语言用户界面。
* 用户社区支持。

## 设置

要克隆并运行此应用程序，您需要在计算机上安装 [Git](https://git-scm.com)、[Node.js](https://nodejs.org/en/download/)（包含 [npm](http://npmjs.com)）和 [Composer](https://getcomposer.org)。从命令行中执行以下命令：

```bash
# 克隆仓库
$ git clone https://github.com/alextselegidis/easyappointments.git

# 进入仓库目录
$ cd easyappointments

# 安装依赖
$ npm install && composer install

# 启动文件监视器
$ npm start
```

注意：如果您使用的是 Windows 上的 Linux Bash，请[参考此指南](https://www.howtogeek.com/261575/how-to-run-graphical-linux-desktop-applications-from-windows-10s-bash-shell/)或在命令提示符中使用 `node`。

您可以通过运行 `npm run build` 来构建文件。此命令会将所有内容打包到 `build` 目录中。

## 安装

要在您的服务器上安装此应用程序，您需要完成以下步骤：

* 确保您的服务器上安装了 Apache/Nginx、PHP（8.2+）和 MySQL。
* 创建一个新的数据库（或者使用现有数据库）。
* 将 "easyappointments" 源文件夹复制到您的服务器上。
* 确保 "storage" 目录具有写入权限。
* 将 "config-sample.php" 文件重命名为 "config.php"，并根据您的环境更新其内容。
* 在浏览器中打开 Easy!Appointments 的 URL，并按照安装指南进行操作。

完成以上步骤后，您就可以随意使用 Easy!Appointments 了。

最新版本可在 [easyappointments.org](https://easyappointments.org) 获取。
如果您在安装或配置应用程序时遇到问题，请访问[官方支持组](https://groups.google.com/forum/#!forum/easy-appointments)。
您也可以在 [问题页面](https://github.com/alextselegidis/easyappointments/issues) 上报告问题，以帮助项目开发进展。

## 许可协议 

代码采用 [GPL v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html) 授权 | 内容采用 [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/)

---

网站 [alextselegidis.com](https://alextselegidis.com) &nbsp;&middot;&nbsp;
GitHub [alextselegidis](https://github.com/alextselegidis) &nbsp;&middot;&nbsp;
Twitter [@alextselegidis](https://twitter.com/AlexTselegidis)

###### 更多 GitHub 项目
###### ⇾ [Plainpad &middot; 自托管笔记应用](https://github.com/alextselegidis/plainpad)
###### ⇾ [Questionful &middot; 简单易用的网页问卷系统](https://github.com/alextselegidis/questionful)
###### ⇾ [Integravy &middot; 触手可及的服务编排](https://github.com/alextselegidis/integravy)