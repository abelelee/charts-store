以下是你提供的 Markdown 内容的中文翻译，保留了原始格式：

---

<div align="center">
<img width="100px" alt="mcaptcha logo" src="./docs/res/icon-trans.png" />
  <h1>mCaptcha</h1>
  <p>
    <strong>
基于工作量证明、尊重隐私的 CAPTCHA 系统，具备出色的用户体验。
</strong>
  </p>

[![文档](https://img.shields.io/badge/文档-master-blue?style=flat-square)](https://mcaptcha.github.io/mCaptcha/mCaptcha/)
[![构建](https://github.com/mCaptcha/mCaptcha/actions/workflows/linux.yml/badge.svg)](https://github.com/mCaptcha/mCaptcha/actions/workflows/linux.yml)
[![Docker](https://img.shields.io/docker/pulls/mcaptcha/mcaptcha)](https://hub.docker.com/r/mcaptcha/mcaptcha)
[![依赖状态](https://deps.rs/repo/github/mCaptcha/mCaptcha/status.svg?style=flat-square)](https://deps.rs/repo/github/mCaptcha/mCaptcha)
[![代码覆盖率](https://codecov.io/gh/mCaptcha/mCaptcha/branch/master/graph/badge.svg?style=flat-square)](https://codecov.io/gh/mCaptcha/mCaptcha)
<br />
[![AGPL 许可证](https://img.shields.io/badge/许可证-AGPL-blue.svg?style=flat-square)](http://www.gnu.org/licenses/agpl-3.0)
[![聊天](https://img.shields.io/badge/matrix-+mcaptcha:matrix.batsense.net-purple?style=flat-square)](https://matrix.to/#/+mcaptcha:matrix.batsense.net)

**状态：开发中**

</div>

**跳转至 [演示](#演示)**

[mCaptcha](https://mcaptcha.org) 是一个尊重隐私的、**免费**的 CAPTCHA
系统，具备出色的用户体验。你的用户不再需要与荒谬的图片验证码交互，浪费宝贵的注意力资源。取而代之的是，你的计算机将为你完成工作，[亲自体验一下！](https://demo.mcaptcha.org/widget/?sitekey=pHy0AktWyOKuxZDzFfoaewncWecCHo23)

## 它是如何工作的？

mCaptcha 使用基于 SHA256 的工作量证明（PoW）来限制用户请求频率。

当用户想要在受 mCaptcha 保护的网站上执行操作时：

1. 他们必须生成工作量证明（即进行一系列耗时的数学计算），并将其提交给 mCaptcha。

2. 我们将验证该证明：

    - **如果验证失败**，他们将无法访问目标网站
    - **如果验证成功**，请继续阅读，

3. 他们将获得一个令牌，该令牌应与他们的请求或表单提交一起提交给目标网站。

4. 目标网站应在处理用户请求之前，使用 mCaptcha 验证用户提交的令牌。

从用户的视角来看，整个过程是自动化的。他们只需点击一个按钮即可启动流程。

mCaptcha 使得用户在计算上需要付出一定代价才能与网站交互。正常用户只会感受到轻微的延迟（在负载适中时无延迟，攻击期间最多延迟 2 秒；PoW 难度是可变的），但如果有人试图攻击你的网站，他们发送请求所需的工作量将远大于你的服务器响应请求所需的工作量。

## 为什么使用 mCaptcha？

-   [x] **自由软件，注重隐私**
-   [x] **无缝的用户体验** - 再也不用烦人的 CAPTCHA！
-   [x] **无追踪**：我们的 CAPTCHA 路由不使用 Cookie！
-   [x] **与 IP 地址无关**：你的用户在 NAT 后面？我们也能支持！
-   [x] **抗重放攻击**：工作量证明配置的生命周期很短（30 秒），且只能使用一次。如果用户提交的 PoW 使用了已用过的或过期的配置，其证明将被拒绝。

## 演示

## 客户端组件：

mCaptcha 的用户体验非常安静，解决 CAPTCHA 从未如此简单。只需点击一次，即可继续操作。
要观察 mCaptcha 的运行过程，可以打开开发者工具并监控控制台和网络活动。

1. [组件链接](https://demo.mcaptcha.org/widget/?sitekey=pHy0AktWyOKuxZDzFfoaewncWecCHo23)

2. [视频](https://github.com/mCaptcha/mCaptcha/blob/master/docs/res/widget-in-action.mp4?raw=true):

### 演示服务器地址：

-   https://demo.mcaptcha.org/
-   https://demo2.mcaptcha.org/ （运行在 Raspberry Pi 上！）

> 核心功能已经可用，但仍处于开发阶段。由于我们尚未发布稳定版本，托管的演示服务器可能比 `master` 分支落后几个版本。请查看页脚以获取构建提交信息。

注册时可以随意填写虚假信息（项目仍在开发中，数据库会定期清空）。

### 自建部署：

克隆仓库并在仓库根目录下运行以下命令：

```bash
git clone https://github.com/mCaptcha/mCaptcha.git
docker-compose up -d
```

容器启动后，访问 [http://localhost:7000](http://localhost:7000) 并使用默认凭据登录：

-   用户名：aaronsw
-   密码：password

构建镜像需要一些时间，请耐心等待 :)

有关详细的替代部署方法，请参阅 [DEPLOYMENT.md](./docs/DEPLOYMENT.md)

## 开发：

请参阅 [HACKING.md](./docs/HACKING.md)

## 部署：

请参阅 [DEPLOYMENT.md](./docs/DEPLOYMENT.md)

## 配置：

请参阅 [CONFIGURATION.md](./docs/CONFIGURATION.md)

## 资金支持

### NLnet

<div align="center">
	<img
		height="150px"
		alt="NLnet NGIZero 标志"
		src="./docs/third-party/NGIZero-green.hex.svg"
	/>
</div>

<br />

2023 年的开发资金由 [NLnet](https://nlnet.nl/) 提供，通过 [NGI0 Entrust 基金](https://nlnet.nl/entrust) 支持。详情请见 [此处](https://nlnet.nl/project/mCaptcha/)。