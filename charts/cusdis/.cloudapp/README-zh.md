<p align="center"><a href="https://cusdis.com" target="_blank" rel="noopener noreferrer"><img width="100" src="/public/images/artworks/logo-256.png" alt="logo"></a></p>

Cusdis 是一个开源、轻量级（约 5KB gzip）、注重隐私的 Disqus 替代方案。

> 如果您有意购买/接手该项目，请联系我 💖

![](/public/images/landing.png)

[![在 Railway 上部署](https://railway.app/button.svg)](https://railway.app/new/template?template=https%3A%2F%2Fgithub.com%2Fdjyde%2Fcusdis&plugins=postgresql&envs=NEXTAUTH_URL%2CDB_TYPE%2CDB_URL%2CUSERNAME%2CPASSWORD%2CHOST%2CJWT_SECRET%2CPORT&NEXTAUTH_URLDesc=请勿修改&DB_TYPEDesc=请勿修改&DB_URLDesc=请勿修改&USERNAMEDesc=登录用户名&PASSWORDDesc=登录密码&HOSTDesc=请勿修改&JWT_SECRETDesc=用于加密 JWT Token 的密钥&PORTDesc=请勿修改&NEXTAUTH_URLDefault=%24%7B%7B+RAILWAY_STATIC_URL+%7D%7D&DB_TYPEDefault=pgsql&DB_URLDefault=%24%7B%7B+DATABASE_URL+%7D%7D&HOSTDefault=https%3A%2F%2F%24%7B%7B+RAILWAY_STATIC_URL+%7D%7D&PORTDefault=3000&referralCode=randyloop)

## 💝 赞助该项目

如果您喜欢 Cusdis，请考虑赞助我们，以帮助我们持续发展。

### 主要赞助商

[![Slide 16_9 - 1](https://github.com/djyde/cusdis/assets/914329/0a773f41-6baf-4bdc-897e-e96f56991acc)](https://epubkit.app)

[![贡献者](https://opencollective.com/cusdis/tiers/organization-support/0/avatar.svg)](https://opencollective.com/cusdis/tiers/organization-support/0/website)

[成为主要赞助商](https://opencollective.com/cusdis/contribute/organization-support-27992/checkout)

### 赞助商 / 支持者

[![贡献者](https://opencollective.com/cusdis/tiers/sponsor.svg?avatarHeight=50)](https://opencollective.com/cusdis)
[![贡献者](https://opencollective.com/cusdis/tiers/backer.svg?avatarHeight=50)](https://opencollective.com/cusdis)

## 功能特性

- 轻量级评论组件，支持国际化（i18n）和暗黑模式。
- 邮件通知
- Webhook
- 易于自托管
- 多种集成方式

## 文档

https://cusdis.com/doc

## 社区

[Discord](https://discord.gg/eDs5fc4Jcq)

## 常见问题

## 与 Disqus 的对比

Cusdis 并不是为了成为 Disqus 的完全替代品而设计的。它的目标是为小型网站（例如你的静态博客）实现一个极简且可嵌入的评论系统。

以下是 Cusdis 的优缺点：

### 优点

- Cusdis 是开源且可自托管的，因此你可以完全掌控自己的数据。
- SDK 非常轻量（压缩后约 5KB）。
- 用户无需登录即可发表评论。
- Cusdis 完全不使用 Cookie。

### 缺点

- Cusdis 仍处于早期开发阶段。
- 没有垃圾评论过滤机制，因此你需要手动审核评论，评论在被批准之前不会显示。
- Disqus 是一家公司，而我们不是。

## 参与贡献

[贡献指南](https://cusdis.com/doc#/contributing)

如果你打算提交 Pull Request，请记得选择 `dev` 分支作为目标分支。

# 许可证

GNU GPLv3