<div align="center">

[![Motor Admin](https://user-images.githubusercontent.com/5418788/140520844-a947845d-b579-4b3f-9b49-c539ad3cf580.png)](https://www.getmotoradmin.com)

# Motor Admin

### 无代码管理后台与商业智能工具

🤓 [在线演示](https://app.getmotoradmin.com/demo/) | 👀 [功能概览](https://www.youtube.com/watch?v=ZD4Six8ZEP8) | 📙 [文档](https://docs.getmotoradmin.com/guide/) | 💬 [Discord](https://discord.com/invite/mFFJKSTgw3) | ⭐ [专业版](https://www.getmotoradmin.com/pro)
</div>

通过便捷的用户界面搜索、创建、更新和删除数据条目。创建复杂的自定义操作，例如通过API集成向客户发送自动化电子邮件。使用SQL构建自定义报表并通过图表可视化结果。将多个独立报表组合成一个仪表板，并与团队共享。

## 部署方式

### Heroku

[![部署到 Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/motor-admin/motor-admin-heroku)

### Railway

[![部署到 Railway](https://railway.app/button.svg)](https://railway.app/new/template?template=https%3A%2F%2Fgithub.com%2Fmotor-admin%2Fmotor-admin-railway&plugins=postgresql&envs=SECRET_KEY_BASE&SECRET_KEY_BASEDesc=64+character+secret&PORTDefault=secret&referralCode=DSdLCm)

### Digital Ocean

[![部署到 Digital Ocean](https://www.deploytodo.com/do-btn-blue.svg)](https://cloud.digitalocean.com/apps/new?repo=https://github.com/motor-admin/motor-admin/tree/master&refcode=33c75473a82d)

### Docker

```bash
docker run -it -p 3000:3000 -v `pwd`:/app motoradmin/motoradmin:latest
```

### Docker Compose

```bash
curl https://raw.githubusercontent.com/motor-admin/motor-admin/master/docker-compose.yml  | sed "s/SECRET_KEY_BASE:/SECRET_KEY_BASE: `openssl rand -hex 64`/" > docker-compose.yml

docker compose up
```

## 功能特性

* [可定制的CRUD](#customizable-crud)
* [自定义操作](#custom-actions)
* [表单构建器](#forms-builder)
* [SQL查询](#sql-queries)
* [数据可视化](#data-visualization)
* [仪表板](#dashboards)
* [邮件告警](#email-alerts)
* [智能搜索](#intelligence-search)
* [移动端优化](#optimized-for-mobile)
* [配置同步](https://github.com/motor-admin/motor-admin/tree/master/guides/configurations_sync_between_environments.md)
* [角色与权限控制](https://docs.getmotoradmin.com/guide/roles_and_permissions.html)
* 多数据库支持
* 审计日志
* 通过Slack发送个性化报表告警

## [企业版](https://www.getmotoradmin.com/pro)

* 多因素身份验证
* SAML SSO
* 自定义样式
* [了解更多](https://www.getmotoradmin.com/pro)

### 可定制的CRUD

![资源设置](https://user-images.githubusercontent.com/5418788/119318569-2a840e80-bc82-11eb-9ba3-f3964eb6f997.png)

![设置界面](https://user-images.githubusercontent.com/5418788/119263883-90708780-bbe9-11eb-9f9f-f76fed0b7f27.png)

### 自定义操作

![自定义操作](https://user-images.githubusercontent.com/5418788/119266132-3c1dd580-bbf2-11eb-9666-09e1640eaf7b.png)

### 表单构建器

![自定义表单](https://user-images.githubusercontent.com/5418788/119264008-1391dd80-bbea-11eb-9f14-cb405e77fb60.png)

### SQL查询

![SQL查询](https://user-images.githubusercontent.com/5418788/119264127-84d19080-bbea-11eb-9903-ef465d1d2c97.png)

### 数据可视化

![motor-可视化](https://user-images.githubusercontent.com/5418788/119264625-a2075e80-bbec-11eb-986c-6106dd6e47ce.png)

### 仪表板

![仪表板](https://user-images.githubusercontent.com/5418788/119264726-f579ac80-bbec-11eb-852e-8055f8aba200.png)

### 邮件告警

![邮件告警](https://user-images.githubusercontent.com/5418788/119265049-feb74900-bbed-11eb-8070-bcc8d6113b9b.png)

### 智能搜索

![智能搜索](https://user-images.githubusercontent.com/5418788/119266559-eea26800-bbf3-11eb-8cb3-d0538aa386a9.png)

### 移动端优化

![motor-移动端](https://user-images.githubusercontent.com/5418788/119269566-03392d00-bc01-11eb-9e9d-1f6a58fe0749.png)

## 许可证

Motor Admin 采用 AGPL v3 许可证发布。