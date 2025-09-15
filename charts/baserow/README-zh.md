---
## Baserow 是一个开源的无代码数据库工具，也是 Airtable 的替代方案。

无需技术经验即可创建自己的在线数据库。我们这款用户友好的无代码工具，让您无需离开浏览器即可拥有开发人员般的能力。

* 一种结合了易用性和强大数据组织能力的电子表格与数据库混合体。
* 可轻松自托管，无存储限制；也可以不注册直接访问 https://baserow.io 立即开始使用。
* Airtable 的替代方案。
* 开源核心，所有非高级版和非企业版功能均采用 [MIT License](https://choosealicense.com/licenses/mit/) 授权，允许商业和私人使用。
* 无头架构，以 API 为优先。
* 使用了 [Django](https://www.djangoproject.com/)、[Vue.js](https://vuejs.org/) 和 [PostgreSQL](https://www.postgresql.org/) 等流行框架和工具。

[![部署到 Heroku](https://www.herokucdn.com/deploy/button.svg)](https://www.heroku.com/deploy/?template=https://github.com/bram2w/baserow/tree/master)

```bash
docker run -v baserow_data:/baserow/data -p 80:80 -p 443:443 baserow/baserow:1.34.5
```

![Baserow 截图](docs/assets/screenshot.png "Baserow 截图")

## 参与进来

**我们正在远程招聘**！更多信息请访问 https://baserow.io/jobs。

加入我们的论坛：https://community.baserow.io/。有关如何成为贡献者，请参阅 CONTRIBUTING.md。

## 安装方式

* **Docker**
* **Ubuntu**
* **Docker Compose** 
* **Heroku**：在 Heroku 上轻松安装并扩展 Baserow。
* **Render**：在 Render 上轻松安装并扩展 Baserow。
* **Digital Ocean**：在 Digital Ocean 上轻松安装并扩展 Baserow。
* **Cloudron**：在您自己的 Cloudron 服务器上安装和更新 Baserow。
* **Railway**：通过 Railway 安装 Baserow。
* [**Elestio**：由 Elestio 全面托管。](https://elest.io/open-source/baserow)

## 官方文档

官方文档可在网站 https://baserow.io/docs/index 或仓库内的 此处 找到。API 文档可在 https://api.baserow.io/api/redoc/ 查看，如果您需要 OpenAPI 模式，请访问 https://api.baserow.io/api/schema.json。

## 成为赞助商

如果您希望更快地获得新功能，可以考虑成为赞助商。成为赞助商后，我们可以投入更多时间在 Baserow 上，从而加快开发进度。

[成为 GitHub 赞助商](https://github.com/sponsors/bram2w)

## 开发环境

如果您想为 Baserow 做出贡献，可以按如下方式搭建开发环境：

```
$ git clone https://gitlab.com/baserow/baserow.git
$ cd baserow
$ ./dev.sh --build
```

现在 Baserow 的开发环境已经运行起来了。  
在浏览器中访问 [http://localhost:3000](http://localhost:3000)，即可看到一个启用了热重载和其他开发功能的开发模式运行版本。

更详细的说明以及关于开发环境的更多信息，请参阅  
https://baserow.io/docs/development/development-environment。

## 插件开发

得益于 Baserow 的模块化架构，您可以创建插件。您可以开发自己的字段、视图、应用、页面或端点。我们还提供了一个插件样板，帮助您快速上手。更多信息请参阅  
插件介绍 和  
插件样板文档。

## 元信息

由 Baserow B.V. 创建 - bram@baserow.io。

以 MIT 许可证发布。更多信息请参阅 `LICENSE` 文件。

版本：1.34.5

官方仓库地址：https://gitlab.com/baserow/baserow。

更新日志请参阅 此处。

成为 GitHub 赞助商请访问 [此处](https://github.com/sponsors/bram2w)。