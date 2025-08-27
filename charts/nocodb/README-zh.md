以下是你提供的 Markdown 内容的中文翻译，保留了原始格式：

---

<h1 align="center" style="border-bottom: none">
<div>
    <a style="color:#36f" href="https://www.nocodb.com">
        <img src="/packages/nc-gui/assets/img/brand/nocodb-full.png" height="80" />
        <br>
一个开源的 Airtable 替代方案
    </a>
    <br>
</div>
</h1>

<p align="center">
NocoDB 是在线构建数据库最快、最简单的方式。
</p>

<p align="center">
    <a href="http://www.nocodb.com"><b>官网</b></a> •
    <a href="https://discord.gg/5RgZmkW"><b>Discord</b></a> •
    <a href="https://community.nocodb.com/"><b>社区</b></a> •
    <a href="https://twitter.com/nocodb"><b>推特</b></a> •
    <a href="https://www.reddit.com/r/NocoDB/"><b>Reddit</b></a> •
    <a href="https://docs.nocodb.com/"><b>文档</b></a>
</p>

![video avi](https://github.com/nocodb/nocodb/assets/86527202/e2fad786-f211-4dcb-9bd3-aaece83a6783)

<div align="center">

[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263434-75fe793d-42af-49e4-b964-d70920e41655.png">](markdown/readme/languages/chinese.md)
[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263474-787d71e7-3a87-42a8-92a8-be1d1f55413d.png">](markdown/readme/languages/french.md)
[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263531-fae58600-6616-4b43-95a0-5891019dd35d.png">](markdown/readme/languages/german.md)
[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263589-3dbeda9a-0d2e-4bbd-b1fc-691404bb74fb.png">](markdown/readme/languages/spanish.md)
[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263669-f567196a-d4e8-4143-a80a-93d3be32ba90.png">](markdown/readme/languages/portuguese.md)
[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263707-ba4e04a4-268a-4626-91b8-048e572fd9f6.png">](markdown/readme/languages/italian.md)
[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263770-38e3e79d-11d4-472e-ac27-ae0f17cf65c4.png">](markdown/readme/languages/japanese.md)
[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263822-28fce9de-915a-44dc-962d-7a61d340e91d.png">](markdown/readme/languages/korean.md)
[<img height="38" src="https://user-images.githubusercontent.com/61551451/135263888-151d4ad1-7084-4943-97c9-56f28cd40b80.png">](markdown/readme/languages/russian.md)

</div>

<p align="center"><a href="markdown/readme/languages/README.md"><b>查看其他语言 »</b></a></p>

<img src="https://static.scarf.sh/a.png?x-pxid=c12a77cc-855e-4602-8a0f-614b2d0da56a" />

# 加入我们的社区

<a href="https://discord.gg/5RgZmkW" target="_blank">
<img src="https://discordapp.com/api/guilds/661905455894888490/widget.png?style=banner3" alt="">
</a>

[![Stargazers repo roster for @nocodb/nocodb](http://reporoster.com/stars/nocodb/nocodb)](https://github.com/nocodb/nocodb/stargazers)

# 安装

## 使用 SQLite 的 Docker

```bash 
docker run -d \
  --name noco \
  -v "$(pwd)"/nocodb:/usr/app/data/ \
  -p 8080:8080 \
  nocodb/nocodb:latest
  ```

## 使用 PostgreSQL 的 Docker
```bash
docker run -d \
  --name noco \
  -v "$(pwd)"/nocodb:/usr/app/data/ \
  -p 8080:8080 \
  -e NC_DB="pg://host.docker.internal:5432?u=root&p=password&d=d1" \
  -e NC_AUTH_JWT_SECRET="569a1821-0a93-45e8-87ab-eb857f20a010" \
  nocodb/nocodb:latest
```

## Nix

```
nix run github:nocodb/nocodb
```

## NixOS
要将 NocoDB 作为 NixOS 模块使用，flake.nix 应如下所示：

```
{
  description = "Bane 的 NixOS 配置";

  inputs = {
    nixpkgs.url = "github:nixos/nixpkgs/nixos-unstable";
    nocodb.url = "github:nocodb/nocodb";
  };

  outputs = inputs@{ nixpkgs, nocodb, ... }: {
    nixosConfigurations = {
      hostname = nixpkgs.lib.nixosSystem {
        system = "x86_64-linux";
        modules = [
          ./configuration.nix
          nocodb.nixosModules.nocodb

          {
            services.nocodb.enable = true;
          }
        ];
      };
    };
  };
}
```

## 自动安装
自动安装是一个命令，用于在服务器上设置 NocoDB 以供生产环境使用。
在后台，它会为你自动生成 docker-compose 配置。

```bash
bash <(curl -sSL http://install.nocodb.com/noco.sh) <(mktemp)
```

自动安装会执行以下操作： 🕊
- 🐳 自动安装所有前置依赖，如 Docker 和 Docker Compose
- 🚀 使用 Docker Compose 自动安装 NocoDB，包括 PostgreSQL、Redis、Minio 和 Traefik 网关 🐘 🗄️ 🌐
- 🔄 当你再次运行该命令时，会自动将 NocoDB 升级到最新版本
- 🔒 自动配置 SSL 并自动续期。安装时需要输入一个域名或子域名
> install.nocodb.com/noco.sh 脚本可以在 [我们的 GitHub](https://raw.githubusercontent.com/nocodb/nocodb/develop/docker-compose/1_Auto_Upstall/noco.sh) 找到

## 其他安装方式

> 二进制文件仅用于本地快速测试。

| 安装方式                    | 安装命令                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 🍏 MacOS arm64 <br>(二进制) | `curl http://get.nocodb.com/macos-arm64 -o nocodb -L && chmod +x nocodb && ./nocodb`                                                                                                                                                                                                                                                                                       |
| 🍏 MacOS x64 <br>(二进制)   | `curl http://get.nocodb.com/macos-x64 -o nocodb -L && chmod +x nocodb && ./nocodb`                                                                                                                                                                                                                                                                                         |
| 🐧 Linux arm64 <br>(二进制) | `curl http://get.nocodb.com/linux-arm64 -o nocodb -L && chmod +x nocodb && ./nocodb`                                                                                                                                                                                                                                                                                       |
| 🐧 Linux x64 <br>(二进制)   | `curl http://get.nocodb.com/linux-x64 -o nocodb -L && chmod +x nocodb && ./nocodb`                                                                                                                                                                                                                                                                                         |
| 🪟 Windows arm64 <br>(二进制)| `iwr http://get.nocodb.com/win-arm64.exe -OutFile Noco-win-arm64.exe && .\Noco-win-arm64.exe`                                                                                                                                                                                                                                                                              |
| 🪟 Windows x64 <br>(二进制) | `iwr http://get.nocodb.com/win-x64.exe -OutFile Noco-win-x64.exe && .\Noco-win-x64.exe`                                                                                                                                                                                                                                                                                    |

> 本地运行后，访问 [http://localhost:8080/dashboard](http://localhost:8080/dashboard) 即可使用 NocoDB

更多安装方式，请参考 [我们的文档](https://docs.nocodb.com/category/installation)

# 截图
![2](https://github.com/nocodb/nocodb/assets/86527202/a127c05e-2121-4af2-a342-128e0e2d0291)
![3](https://github.com/nocodb/nocodb/assets/86527202/674da952-8a06-4848-a0e8-a7b02d5f5c88)
![4](https://github.com/nocodb/nocodb/assets/86527202/cbc5152a-9caf-4f77-a8f7-92a9d06d025b)
![5](https://github.com/nocodb/nocodb/assets/86527202/dc75dfdc-c486-4f5a-a853-2a8f9e6b569a)

![5](https://user-images.githubusercontent.com/35857179/194844886-a17006e0-979d-493f-83c4-0e72f5a9b716.png)
![7](https://github.com/nocodb/nocodb/assets/86527202/be64e619-7295-43e2-aa95-cace4462b17f)
![8](https://github.com/nocodb/nocodb/assets/86527202/4538bf5a-371f-4ec1-a867-8197e5824286)

![8](https://user-images.githubusercontent.com/35857179/194844893-82d5e21b-ae61-41bd-9990-31ad659bf490.png)
![9](https://user-images.githubusercontent.com/35857179/194844897-cfd79946-e413-4c97-b16d-eb4d7678bb79.png)
![10](https://user-images.githubusercontent.com/35857179/194844902-c0122570-0dd5-41cf-a26f-6f8d71fefc99.png)
![11](https://user-images.githubusercontent.com/35857179/194844903-c1e47f40-e782-4f5d-8dce-6449cc70b181.png)
![12](https://user-images.githubusercontent.com/35857179/194844907-09277d3e-cbbf-465c-9165-6afc4161e279.png)

# 功能特性

### 丰富的电子表格界面

- ⚡ &nbsp;基本操作：创建、读取、更新和删除表、列和行
- ⚡ &nbsp;字段操作：排序、筛选、分组、隐藏/取消隐藏列
- ⚡ &nbsp;多种视图类型：网格（默认）、画廊、表单、看板和日历视图
- ⚡ &nbsp;视图权限类型：协作视图和锁定视图
- ⚡ &nbsp;共享数据库/视图：可设为公开或私有（带密码保护）
- ⚡ &nbsp;多种单元格类型：ID、链接、查找、汇总、单行文本、附件、货币、公式、用户等
- ⚡ &nbsp;基于角色的访问控制：在不同层级提供细粒度的访问控制
- ⚡ &nbsp;更多功能...

### 工作流自动化的应用商店

我们在三个主要类别中提供了不同的集成。详见 <a href="https://docs.nocodb.com/account-settings/oss-specific-details/#app-store" target="_blank">应用商店</a>。

- ⚡ &nbsp;聊天：Slack、Discord、Mattermost 等
- ⚡ &nbsp;邮件：AWS SES、SMTP、MailerSend 等
- ⚡ &nbsp;存储：AWS S3、Google Cloud Storage、Minio 等

### 编程访问

我们提供以下方式让用户通过编程调用操作。你可以使用令牌（JWT 或社交认证）对请求进行签名，以授权访问 NocoDB。

- ⚡ &nbsp;REST API
- ⚡ &nbsp;NocoDB SDK

# 贡献

请参考 [贡献指南](https://github.com/nocodb/nocodb/blob/master/.github/CONTRIBUTING.md)。

# 我们为什么开发这个项目？

大多数互联网企业使用电子表格或数据库来满足业务需求。每天有数十亿人协作使用电子表格。然而，我们在数据库方面的工作效率远远不及电子表格，尽管数据库在计算能力上更加强大。尝试通过 SaaS 解决方案来解决这个问题往往带来糟糕的访问控制、供应商锁定、数据锁定、价格突变，以及最重要的——未来可能性的天花板。

# 我们的使命

我们的使命是为全球每一个互联网企业提供一个最强大的开源无代码数据库界面。这不仅将使强大的计算工具民主化，还将带来数十亿具有激进“DIY”精神的互联网用户。

# 许可证

<p>
本项目采用 <a href="./LICENSE">AGPLv3</a> 许可证。
</p>

# 贡献者

感谢你们的贡献！我们非常感激社区的所有贡献。

<a href="https://github.com/nocodb/nocodb/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=nocodb/nocodb" />
</a>