# PsiTransfer

[![当前版本](https://img.shields.io/github/release/psi-4ward/psitransfer.svg)](https://github.com/psi-4ward/psitransfer/releases)
[![依赖项](https://david-dm.org/psi-4ward/psitransfer.svg)](https://david-dm.org/psi-4ward/psitransfer)
[![已知漏洞](https://snyk.io/test/github/psi-4ward/psitransfer/badge.svg)](https://snyk.io/test/github/psi-4ward/psitransfer)
[![GitHub 星标](https://img.shields.io/github/stars/psi-4ward/psitransfer.svg?style=social&label=Star)](https://github.com/psi-4ward/psitransfer)
[![Docker 星标](https://img.shields.io/docker/stars/psitrax/psitransfer.svg)](https://hub.docker.com/r/psitrax/psitransfer/)
[![镜像大小](https://images.microbadger.com/badges/image/psitrax/psitransfer.svg)](https://microbadger.com/images/psitrax/psitransfer)
[![Docker 下载量](https://img.shields.io/docker/pulls/psitrax/psitransfer.svg)](https://hub.docker.com/r/psitrax/psitransfer/)
[![Docker 自动构建](https://img.shields.io/docker/automated/psitrax/psitransfer.svg)](https://hub.docker.com/r/psitrax/psitransfer/)
[![捐赠](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RTWDCH74TJN54&item_name=psitransfer)

一个简单的开源自托管文件共享解决方案。
它是 Dropbox、WeTransfer 等付费服务的替代方案。

* 无需账号，无需登录
* 移动端友好的响应式界面
* 支持多个且非常大的文件（流式传输优势）
* 支持断点续传上传和下载 ([tus.io](https://tus.io))
* 设置上传存储桶的过期时间
* 一次性下载
* 将所有文件下载为 zip/tar.gz 压缩包
* 模态风格的文件预览
* 需要 Node >=7.4 或使用 `--harmony-async-await` 参数
* 下载列表支持密码保护 ([AES](https://zh.wikipedia.org/wiki/高级加密标准))
* `/admin` 页面列出存储桶信息，[截图](https://raw.githubusercontent.com/psi-4ward/psitransfer/master/docs/PsiTransfer-Admin.png)（_在你设置 `adminPass` 配置值之前禁用_）
* 基于轻量级 [Vue](https://vuejs.org) 的前端应用，启用 Gzip 压缩后小于 100KB
* 使用查询参数 `sid=<myBucketID>` 明确命名存储桶 ID

**关于 PsiTransfer 的博客文章请参见：https://psi.cx/tags/PsiTransfer/，并查看 [文档](https://github.com/psi-4ward/psitransfer/tree/master/docs)**

![截图](https://raw.githubusercontent.com/psi-4ward/psitransfer/master/docs/psitransfer.gif)


## 快速开始

### Docker
```bash
$ docker run -p 0.0.0.0:3000:3000 -e PSITRANSFER_ADMIN_PASS=secret -v $PWD/data:/data psitrax/psitransfer
# 数据卷需要 UID 1000
$ sudo chown -R 1000 $PWD/data
```

通过使用 [镜像标签](https://hub.docker.com/r/psitrax/psitransfer/tags/) 指定版本，例如：
* `latest`：对应 master 分支
* `2`：最新的稳定版 `2.x.x`
* `1.1`：最新的稳定版 `1.1.x`
* `1.0.0`：确切版本

### 手动安装，使用预编译包

```bash
# 确保已安装 NodeJS >= 12
$ node -v
v12.4.0

# 从以下地址下载并解压最新发布包
# https://github.com/psi-4ward/psitransfer/releases

# 安装依赖并启动应用
$ NODE_ENV=production npm install
$ npm start
```

### 手动安装，从源码编译

```bash
# 编译前端应用
$ cd app
$ npm install
$ npm run build

# 安装依赖
$ cd ..
$ npm install
$ npm start
```

### 配置

`config.js` 中有一些配置项如端口和数据目录。
你可以：
* 编辑 `config.js` **(不推荐)**
* 添加一个 `config.production.js`，其中 `production` 是 `NODE_ENV` 的值
  参见 `config.dev.js`
* 定义环境变量如 `PSITRANSFER_UPLOAD_DIR` 来设置上传目录
* 如果 PsiTransfer 暴露在互联网上，为防止未经授权的上传，可以使用 `PSITRANSFER_UPLOAD_PASS` 环境变量

### 自定义

`public/pug/upload.pug` 和 `download.pug` 保持简洁。
你可以修改这些文件并添加你的 logo 和样式。
请保留类似 *由 PsiTransfer 提供支持* 的脚注 :)

### 调试

PsiTransfer 使用 [debug](https://github.com/visionmedia/debug)：

```bash
DEBUG=psitransfer:* npm start
```

## 其他说明

* **目前尚无（端到端）负载加密（暂未实现）**。
* “下载全部为 ZIP”功能不支持断点续传下载。

:star2: 非常欢迎贡献代码 :metal:

想表示感谢并请我喝杯啤酒吗？[![捐赠](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RTWDCH74TJN54&item_name=psitransfer)


## 许可证

[BSD](LICENSE)