# PowerDNS-Admin

一个具有高级功能的 PowerDNS Web 界面。

[![CodeQL](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/powerdns-admin/image/badge.svg)](https://github.com/PowerDNS-Admin/PowerDNS-Admin/actions/workflows/codeql-analysis.yml)
[![Docker Image](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/powerdns-admin/image/badge.svg)](https://github.com/PowerDNS-Admin/PowerDNS-Admin/actions/workflows/build-and-publish.yml)

#### 功能特性：

- 提供正向和反向区域管理
- 提供区域模板功能
- 提供基于角色访问控制的用户管理
- 提供针对区域的访问控制
- 提供操作日志记录
- 认证方式：
  - 本地用户支持
  - SAML 支持
  - LDAP 支持：OpenLDAP / Active Directory
  - OAuth 支持：Google / GitHub / Azure / OpenID
- 支持双因素身份验证（TOTP）
- PDNS 服务配置与统计监控
- 支持 DynDNS 2 协议
- 支持便捷编辑 IPv6 PTR 记录
- 提供用于区域和记录管理等功能的 API
- 提供完整的 IDN/Punycode 支持

## [项目更新 - 请务必阅读!!!](https://github.com/PowerDNS-Admin/PowerDNS-Admin/discussions/1708)

## 运行 PowerDNS-Admin

运行 PowerDNS-Admin 有多种方式。最快捷的方式是使用 Docker。
如果你想直接在系统上安装并运行 PowerDNS-Admin，请查看
[wiki](https://github.com/PowerDNS-Admin/PowerDNS-Admin/blob/master/docs/wiki/) 获取相关方法。

### Docker

以下是使用 Docker 运行 PowerDNS-Admin 的两种选项。
如需尽快启动，请尝试选项 1；如需对配置进行修改，选项 2 可能更合适。

#### 选项 1：从 Docker Hub 运行

要使用 Docker Hub 上的最新稳定版本运行该应用，请运行以下命令：

```
$ docker run -d \
    -e SECRET_KEY='a-very-secret-key' \
    -v pda-data:/data \
    -p 9191:80 \
    powerdnsadmin/pda-legacy:latest
```

此命令将创建一个名为 `pda-data` 的卷，用于持久化保存包含应用配置的默认 SQLite 数据库。

#### 选项 2：使用 docker-compose

1. 更新配置  
   编辑 `docker-compose.yml` 文件，更新 `SQLALCHEMY_DATABASE_URI` 中的数据库连接字符串。
   其他环境变量可在 [AppSettings.defaults](https://github.com/PowerDNS-Admin/PowerDNS-Admin/blob/master/powerdnsadmin/lib/settings.py) 字典中找到。
   如需使用 Docker 风格的 secrets 机制，可以在环境变量名后添加 `_FILE`，并指定一个包含变量值的文件路径
   （例如：`SQLALCHEMY_DATABASE_URI_FILE=/run/secrets/db_uri`）。  
   请确保将环境变量 `SECRET_KEY` 设置为一个长且随机的字符串（参考：https://flask.palletsprojects.com/en/1.1.x/config/#SECRET_KEY）

2. 启动 Docker 容器
   ```
   $ docker-compose up
   ```

然后，您可以通过浏览器访问 http://localhost:9191 来打开 PowerDNS-Admin。

## 截图

![dashboard](https://edas-hz.oss-cn-hangzhou.aliyuncs.com/edas-apps/charts-store/powerdns-admin/image/dashboard.png)

## 支持

**需要帮助？** 请参考项目的
[支持指南](https://github.com/PowerDNS-Admin/PowerDNS-Admin/blob/master/.github/SUPPORT.md)，或加入我们的
[Discord 服务器](https://discord.powerdnsadmin.org)。

## 安全策略

请参阅我们的 [安全策略](https://github.com/PowerDNS-Admin/PowerDNS-Admin/blob/master/SECURITY.md)。

## 贡献

请参阅我们的 [贡献指南](https://github.com/PowerDNS-Admin/PowerDNS-Admin/blob/master/docs/CONTRIBUTING.md)。

## 行为准则

请参阅我们的 [行为准则政策](https://github.com/PowerDNS-Admin/PowerDNS-Admin/blob/master/docs/CODE_OF_CONDUCT.md)。

## 许可证

本项目采用 MIT 许可证发布。如需更多信息，请[查看完整许可证](https://github.com/PowerDNS-Admin/PowerDNS-Admin/blob/master/LICENSE)。