# Kener - 精美的状态页面

<p align="center">
	<img src="https://kener.ing/newbg.png?v=1" width="100%" height="auto" class="rounded-lg shadow-lg" alt="kener 示例插图">
</p>

<p align="center">
	<img alt="GitHub 仓库星标数" src="https://img.shields.io/github/stars/rajnandan1/kener?label=Star%20Repo&style=social">
	<a href="https://github.com/ivbeg/awesome-status-pages"><img src="https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg" alt="Awesome 状态页面" /></a>
    <a href="https://awesome-selfhosted.net/tags/status--uptime-pages.html#kener"><img src="https://awesome.re/mentioned-badge.svg" alt="Awesome 自托管" /></a>
</p>

<p align="center">
  <a href="https://hub.docker.com/r/rajnandan1/kener"><img src="https://img.shields.io/docker/pulls/rajnandan1/kener" alt="Docker Kener" /></a>
  <a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=latest"><img alt="Docker 镜像大小" src="https://img.shields.io/docker/image-size/rajnandan1/kener/latest?logo=docker&logoColor=white&label=debian" /></a>
  <a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=alpine"><img alt="Docker 镜像大小" src="https://img.shields.io/docker/image-size/rajnandan1/kener/alpine?logo=docker&logoColor=white&label=alpine" /></a>
</p>

<p align="center">
  <a href="https://github.com/rajnandan1/kener/actions/workflows/publish-images.yml"><img alt="GitHub 工作流状态" src="https://img.shields.io/github/actions/workflow/status/rajnandan1/kener/publish-images.yml" /></a>
  <a href="https://github.com/rajnandan1/kener/commit/HEAD"><img src="https://img.shields.io/github/last-commit/rajnandan1/kener/main" alt="" /></a>
  <a href="https://github.com/rajnandan1/kener/issues"><img alt="GitHub 问题数" src="https://img.shields.io/github/issues/rajnandan1/kener.svg" /></a>
</p>

<p align="center">
	<a href="https://www.producthunt.com/posts/kener-2" target="_blank">
		<img src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=kener-2&theme=light" alt="Kener 在 Product Hunt 上">
	</a>
</p>

<p align="center">
	<picture>
		<source srcset="https://fonts.gstatic.com/s/e/notoemoji/latest/1f514/512.webp" type="image/webp">
		<img src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f514/512.gif" alt="🔔" width="32" height="32">
	</picture>
	<picture>
		<source srcset="https://fonts.gstatic.com/s/e/notoemoji/latest/1f680/512.webp" type="image/webp">
		<img src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f680/512.gif" alt="🚀" width="32" height="32">
	</picture>
	<picture>
		<source srcset="https://fonts.gstatic.com/s/e/notoemoji/latest/1f6a7/512.webp" type="image/webp">
		<img src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f6a7/512.gif" alt="🚧" width="32" height="32">
	</picture>
</p>

| [🌍 实时服务器](https://kener.ing) | [🎉 快速开始](https://kener.ing/docs/quick-start) | [🗄 文档](https://kener.ing/docs/home) |
| ---------------------------------- | -------------------------------------------------- | -------------------------------------- |

## 什么是 Kener？

**Kener** 是一个使用 **SvelteKit** 和 **NodeJS** 构建的简洁轻量级状态页面系统。它并不是要取代 Datadog 或 Atlassian 这样的重量级工具，而是提供一种简单、现代且无麻烦的方式来轻松搭建外观精美的状态页面。

Kener 以**易用性**和**可定制性**为核心设计理念，提供了状态页面所需的所有基本功能——而无需复杂的操作。

### 为什么选择 Kener？

✅ &nbsp;低开销 &ndash; 使用干净现代的 UI 快速搭建<br>
✅ &nbsp;可定制 &ndash; 轻松根据您的品牌进行定制<br>
✅ &nbsp;开源且免费 &ndash; 因为优秀的工具应该人人可用

### 名字的由来

“Kener” 的灵感来自阿萨姆语单词 _“Kene”_，意思是 _“最近怎么样？”_。加上 _‘.ing’_ 是因为……这个域名可用。😄

## 安装

### 手动安装

```shell
# 克隆仓库
git clone https://github.com/rajnandan1/kener.git
cd kener
npm install
cp .env.example .env
npm run dev
```

### Docker 安装

**Kener** 的官方 Docker 镜像可在 [Docker Hub](https://hub.docker.com/r/rajnandan1/kener) 上找到。我们维护了多个版本以支持不同的使用场景。

<a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=3.2.18"><img src="https://img.shields.io/badge/Latest_Stable_Release-3.2.18-blue" alt="Kener 最新稳定版本：3.2.18" /></a>

#### 可用标签

<table>
	<tr>
		<th>镜像标签</th>
		<th>描述</th>
	</tr>
	<tr>
		<td align="left" colspan="2" style="color:#A81D33;text-align:left;">Debian 12 <small>(Bookwork Slim)</small> 搭配 Node.js v23.7.0 &nbsp;<strong><em>(默认)</em></strong></td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=latest" target="_blank"><code>latest</code></td>
		<td>最新稳定版本（即 3.2.18）</td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=3.2.18" target="_blank"><code>3.2.18</code></a></td>
		<td>特定版本</td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=3.2" target="_blank"><code>3.2</code></a></td>
		<td>指向该次版本（3.2.x）中最新补丁版本（3.2.18）的主次版本标签</td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=3" target="_blank"><code>3</code></a></td>
		<td>指向该主版本（3.x.x）中最新稳定版本（3.2.18）的主版本标签</td>
	</tr>
	<tr>
		<td align="left" colspan="2" style="color:#0D597F;text-align:left;">Alpine Linux 3.21 搭配 Node.js v23.7.0 &nbsp;<strong><em>（最小镜像大小）</em></strong></td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=alpine" target="_blank"><code>alpine</code></td>
		<td>最新稳定版本（即 3.2.18）</td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=3.2.18-alpine" target="_blank"><code>3.2.18-alpine</code></a></td>
		<td>特定版本</td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=3.2-alpine" target="_blank"><code>3.2-alpine</code></a></td>
		<td>指向该次版本（3.2.x）中最新补丁版本（3.2.18）的主次版本标签</td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/r/rajnandan1/kener/tags?page=1&ordering=last_updated&name=3-alpine" target="_blank"><code>3-alpine</code></a></td>
		<td>指向该主版本（3.x.x）中最新稳定版本（3.2.18）的主版本标签</td>
	</tr>
</table>

#### 使用方法

拉取最新稳定版本：

```sh
docker pull rajnandan1/kener:latest
```

或者使用更小的基于 Alpine 的镜像：

```sh
docker pull rajnandan1/kener:alpine
```

对于生产环境部署，请参考示例 [docker-compose.yml](https://github.com/rajnandan1/kener/blob/main/docker-compose.yml) 文件。

### 一键部署

[![在 Railway 上部署](https://railway.com/button.svg)](https://railway.com/template/spSvic?referralCode=1Pn7vs)

## 功能特性

以下是一些开箱即用的功能。请阅读文档了解如何使用它们。

### 📊 &nbsp;监控与追踪

- 高级 **应用性能监控** 工具
- **实时网络监控** 功能
- 支持 **轮询 HTTP 端点** 或通过 REST API **推送数据**
- **自动调整访客时区**
- 将监控项组织为 **自定义分组**
- **基于 Cron 的调度**（最小间隔：**每分钟一次**）
- **创建复杂的 API 轮询**（支持链式调用、密钥等）
- 为监控项设置 **默认状态**
- 支持 **Kubernetes (k8s) 中的 basePath 托管**
- 提供 **预构建的 Docker 镜像** 以便快速部署

### 🎨 &nbsp;定制与品牌化

- 完全 **可定制的状态页面**
- 支持生成状态和运行时间的 **徽章**
- 支持 **自定义域名**
- 将监控项作为 **iframe 或小部件** 嵌入
- 支持 **浅色与深色模式**
- 支持 **国际化 (i18n)**
- **美观、精心设计的用户界面**

### 🚨 &nbsp;事件管理

- **事件追踪与沟通** 工具
- 提供 **全面的事件管理 API**

### 🧑‍💻 &nbsp;用户体验与设计

- **易用且用户友好的界面**
- **快速且简单的安装**
- **响应式设计** 适配所有设备
- **自动 SEO 优化与社交媒体适配**
- **服务端渲染 (SSR)** 提升性能

<div align="left">
    <img alt="访问统计" src="https://widgetbite.com/stats/rajnandan"/>
</div>

## 使用的技术

-   [SvelteKit](https://kit.svelte.dev/)
-   [shadcn-svelte](https://www.shadcn-svelte.com/)

## 支持我

如果您喜欢 Kener 并希望支持其开发，请考虑在 GitHub 上赞助我，或者请我喝杯咖啡。您的支持有助于项目的持续发展！🚀

[Sponsor Me Using Github](https://github.com/sponsors/rajnandan1)

☕ &nbsp;[Buy Me a Coffee](https://www.buymeacoffee.com/rajnandan1)

![image](https://badges.pufler.dev/visits/rajnandan1/kener)

## 贡献

如果您希望为 Kener 做出贡献，请阅读 [贡献指南](https://github.com/rajnandan1/kener/blob/main/.github/CONTRIBUTING.md)。

## 星标历史

[![Star History Chart](https://api.star-history.com/svg?repos=rajnandan1/kener&type=Date)](https://star-history.com/#rajnandan1/kener&Date)