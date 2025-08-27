# Heimdall

[![Heimdall_Banner](https://i.imgur.com/iuV8w3y.png)](https://heimdall.site)

[![Discord](https://img.shields.io/discord/354974912613449730.svg)](https://discord.gg/CCjHKn4)
[![Docker Pulls](https://img.shields.io/docker/pulls/linuxserver/heimdall.svg)](https://hub.docker.com/r/linuxserver/heimdall/)
[![firsttimersonly](https://img.shields.io/badge/first--timers--only-friendly-blue.svg)](https://www.firsttimersonly.com/)
[![Paypal](https://heimdall.site/img/paypaldonate.svg)](https://www.paypal.me/heimdall)

___

访问官网 - https://heimdall.site
___

## 关于
顾名思义，Heimdall Application Dashboard 是所有 Web 应用程序的仪表板。它不仅限于应用程序，你也可以添加指向任何内容的链接。

Heimdall 是整理所有 Web 应用程序的优雅解决方案。它专注于此目的，因此你不会在书签的海洋中丢失你的链接。

为什么不将其用作浏览器的起始页面？它甚至可以包含一个搜索栏，支持 Google、Bing 或 DuckDuckGo。

![Heimdall 演示动画](https://i.imgur.com/MrC4QpN.gif)

## 视频
如果你想观看使用演示视频，请访问 https://youtu.be/GXnnMAxPzMc

## 支持的应用程序
你可以使用该应用链接到任何网站或应用程序，但 Foundation 应用会自动填充应用图标并为磁贴提供默认颜色。此外，Enhanced 应用允许你提供应用程序 API 的详细信息，从而可以直接在仪表板上查看实时状态。例如，NZBGet 和 Sabnzbd 的 Enhanced 应用将显示队列大小和下载速度。

支持的应用程序通过添加应用程序时在标题字段中输入的标题名称来识别。例如，要添加指向 pfSense 的链接，请在标题字段中键入 "p"，然后从支持的应用程序列表中选择 "pfSense"。

[![enhancedapps](https://img.shields.io/badge/dynamic/json.svg?label=Enhanced%20Apps&url=https%3A%2F%2Fapps.heimdall.site%2Fstats&query=enhanced_apps&colorB=3f8483&style=for-the-badge&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABwAAAAjCAMAAACw/5reAAAAnFBMVEUAAADu7u7u7u7u7u7u7u7x8fHu7u7u7u7u7u7u7u7u7u7u7u7r6+vu7u7v7+/u7u7t7e3v7+/v7+/u7u7u7u7u7u7u7u7u7u7u7u7u7u7v7+/u7u7p6ent7e3v7+/v7+/v7+/u7u7u7u7u7u7u7u7t7e3////u7u7u7u7u7u7u7u7w8PDw8PDt7e3u7u7t7e3s7Ozu7u7t7e3u7u4TnCP6AAAAM3RSTlMA+9n3phHw3czC088M5Y5zG6mflWdJFumyfj4sB2NeTi7hiWlDOQPGt5lsMiG9hFQntpFqxQJtAAABnElEQVQoz2WRh3KrQAxFtYWO6ZhucItrynv6/3/LFnA24c6wurpnYBkJZvXduNix6+GXTo8qWnxUPU4m2w0O1ktTozPsftiZpejGlm7C2MWUnRcWOohIo36+PaKyDZdLUOgDXvqQfaT9kwkfvP3AN18E7Kl8hkJHMHSXSSadxaTtTNjJhMkfjFHKMqGlolg4T7mtCbcq8gBCotxkwklFLIQSlQoTHnVWQqzNxYQuzpfmqGVMc5ijHK5yAuIhxbZ5p/S92RZkjv5BKs6aosSIr0JrcXBo1FtICVINKRKK6u0GnraoN84O5KbhjRwYzxCJnQCMtotkdNxjq2F7dJ2RoGuXIBTvc3ROthdmat6hZ7cOyfcxKGV+wTxBkxQxTQTzWOFny/7qS2nzx37T7nbtZj9xu7zUr/323nVy0sQnhwMJktSZrl5v7CjgSQmWi+haUCY8sH4tyc/FGSKGouS+WqBJm8U2NIE/+nLu2tzpF/xVNGy02QzRClafC/ysVpDzQJuA8xXsKl8bv+pgpXz57H9Yy3J1lQNY62wUrW+mdzrylWS0QwAAAABJRU5ErkJggg==)](https://apps.heimdall.site/applications/enhanced)

[![foundationapps](https://img.shields.io/badge/dynamic/json.svg?label=Foundation%20Apps&url=https%3A%2F%2Fapps.heimdall.site%2Fstats&query=foundation_apps&colorB=3f8483&style=for-the-badge&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABwAAAAjCAMAAACw/5reAAAAnFBMVEUAAADu7u7u7u7u7u7u7u7x8fHu7u7u7u7u7u7u7u7u7u7u7u7r6+vu7u7v7+/u7u7t7e3v7+/v7+/u7u7u7u7u7u7u7u7u7u7u7u7v7+/u7u7p6ent7e3v7+/v7+/v7+/u7u7u7u7u7u7u7u7t7e3////u7u7u7u7u7u7u7u7w8PDw8PDt7e3u7u7t7e3s7Ozu7u7t7e3u7u4TnCP6AAAAM3RSTlMA+9n3phHw3czC088M5Y5zG6mflWdJFumyfj4sB2NeTi7hiWlDOQPGt5lsMiG9hFQntpFqxQJtAAABnElEQVQoz2WRh3KrQAxFtYWO6ZhucItrynv6/3/LFnA24c6wurpnYBkJZvXduNix6+GXTo8qWnxUPU4m2w0O1ktTozPsftiZpejGlm7C2MWUnRcWOohIo36+PaKyDZdLUOgDXvqQfaT9kwkfvP3AN18E7Kl8hkJHMHSXSSadxaTtTNjJhMkfjFHKMqGlolg4T7mtCbcq8gBCotxkwklFLIQSlQoTHnVWQqzNxYQuzpfmqGVMc5ijHK5yAuIhxbZ5p/S92RZkjv5BKs6aosSIr0JrcXBo1FtICVINKRKK6u0GnraoN84O5KbhjRwYzxCJnQCMtotkdNxjq2F7dJ2RoGuXIBTvc3ROthdmat6hZ7cOyfcxKGV+wTxBkxQxTQTzWOFny/7qS2nzx37T7nbtZj9xu7zUr/323nVy0sQnhwMJktSZrl5v7CjgSQmWi+haUCY8sH4tyc/FGSKGouS+WqBJm8U2NIE/+nLu2tzpF/xVNGy02QzRClafC/ysVpDzQJuA8xXsKl8bv+pgpXz57H9Yy3J1lQNY62wUrW+mdzrylWS0QwAAAABJRU5ErkJggg==)](https://apps.heimdall.site/applications/foundation)

## 安装
除了 Laravel 的依赖项（即 PHP >= 7.2.5、BCMath PHP 扩展、Ctype PHP 扩展、Fileinfo PHP 扩展、JSON PHP 扩展、Mbstring PHP 扩展、OpenSSL PHP 扩展、PDO PHP 扩展、Tokenizer PHP 扩展、XML PHP 扩展）之外，Heimdall 还需要 sqlite 支持和 zip 支持（php-zip）。

如果你发现无法更改背景，请确保在 php.ini 中启用了 `php_fileinfo`。我认为默认情况下它是启用的，但有一位用户在 Windows 系统上遇到了这个问题。

安装非常简单，只需将仓库克隆到某个位置，或下载并解压 zip/tar 文件，然后将你的 httpd 文档根目录指向 `/public` 文件夹，接着创建 `.env` 文件并生成加密密钥（使用 Docker 时，这些都会自动为你完成）。

```
cd /path/to/heimdall
cp .env.example .env
php artisan key:generate
```

为了简单测试，你可以进入文件夹并输入 `php artisan serve`。

还有一个支持 x86-64、armhf 和 arm64 架构的多架构 Docker 镜像，使用说明请参见：

- https://hub.docker.com/r/linuxserver/heimdall/

## 更新
要更新你的实例，只需克隆此仓库或下载新的 zip/tar 文件并将其覆盖到旧的安装目录中即可。

## 搜索提供程序
v2.3.0 版本增加了用户自定义搜索选项的功能。

选项存储在 `/storage/app/searchproviders.yaml` 中（Docker 安装时为 `/config/www/searchproviders.yaml`），你可以随意重新排列选项、添加新选项、删除不使用的选项等。

欢迎为 https://github.com/linuxserver/Heimdall/discussions/categories/search-providers 贡献内容，以帮助他人添加新选项。

列表顶部的 `Tiles` 项允许你通过名称搜索仪表板上的应用程序，当你拥有大量图标时非常有用。

## 新背景图片未生效
如果你使用的是 Docker 镜像或默认的 PHP 安装，可能会发现超过 2MB 的图片无法设置为背景图片，你需要在 php.ini 中修改 `upload_max_filesize`。

如果你使用的是 linuxserver.io 的 Docker 镜像，只需编辑 `/path/to/config/php/php-local.ini` 并在末尾添加 `upload_max_filesize = 30M`。

## Docker 和增强型应用
如果你正在运行 Docker，并且使用的 EnhancedApps 也在 Docker 中，可能需要使用 Docker 的网络地址与它们通信。

你可以在配置部分使用 `http(s)://docker_name:port`。你也可以使用内部 Docker IP 地址，通常以 `172.` 开头。

## 语言
该应用已被翻译成多种语言；然而，翻译质量还有待改进。如果你想改进它们，或者帮助翻译其他语言，翻译文件存储在 `/resources/lang/` 中。

要创建新的语言翻译，请创建一个以 ISO 3166-1 alpha-2 代码命名的新文件夹，将 `/resources/lang/en/app.php` 中的 `app.php` 复制到你的新文件夹中，并替换英文字符串。

完成后，创建一个 Pull Request。

目前已添加的语言有：

- 英语
- 德语
- 芬兰语
- 法语
- 瑞典语
- 西班牙语
- 土耳其语
- 俄语

## Web 服务器配置

### Apache
应用附带了一个 `.htaccess` 文件，但许多 Apache 安装默认禁止 `.htaccess` 文件。
你会注意到一些链接无法正常工作，例如 `/settings`。
此外，如果尚未启用，需要启用 mod-rewrite。

#### 修复和解决方法
##### - Apache 全局允许 .htaccess
在 Apache 配置中找到 `AllowOverride None` 行，并将其更改为 `AllowOverride All`

##### - Apache vhost 配置允许 .htaccess
在 Apache vhost 配置中的 `<Directory />` 块中添加 `AllowOverride All`

##### - 在 Apache 配置中添加 .htaccess 内容
你可以将完整的 `.htaccess` 内容添加到 Apache 配置中，这样就不需要允许 `.htaccess` 文件。
你甚至可以将 `.htaccess` 内容缩短为以下内容：
```
Options +FollowSymLinks
RewriteEngine On

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]
```
#### 更多信息
关于 `AllowOverride` 的更多信息请参见：
https://httpd.apache.org/docs/2.4/mod/core.html#allowoverride

### Nginx
如果你使用的是 Nginx，以下指令将把所有请求定向到 `index.php` 前端控制器：

```
location / {
    try_files $uri $uri/ /index.php?$query_string;
}
```
有人使用相同的 Nginx 设置来运行此应用并反向代理 Plex，Plex 从 `/web` 提供服务，因此他们的 location 与 `/webfonts` 冲突了。

因此，如果你的字体未显示，因为你有一个 `/web` 的 location，请添加以下内容：
```
location /webfonts {
    try_files $uri $uri/;
}
```
如果还有其他 location 可能干扰 `/public` 文件夹中的任何文件夹，则可能也需要对这些文件夹进行相同操作，但这属于非常边缘的情况。

### 反向代理
如果你希望反向代理此应用，我们建议使用我们的 letsencrypt/nginx Docker 镜像：[SWAG - Secure Web Application Gateway](https://hub.docker.com/r/linuxserver/swag)
你可以从根位置反向代理，或从子域名反向代理（目前不支持子文件夹方法）。对于 HTTPS 代理，请确保使用 Heimdall Web 服务器的 HTTPS 端口，否则某些链接可能会失效。你可以通过 `.htpasswd` 添加安全性：

```
location / {
    auth_basic "Restricted";
    auth_basic_user_file /config/nginx/.htpasswd;
    include /config/nginx/proxy.conf;
    proxy_set_header X-Forwarded-Proto https;
    proxy_pass http://heimdall;
}
```

### 自签名证书和本地 CA
默认情况下，Heimdall 使用标准证书包文件 (`ca-certificates.crt`) 来验证 HTTPS 站点，并将忽略放置在 `/etc/ssl/certs` 中的额外证书。如果你希望使用带有自签名证书或使用你自己的本地 CA 签发的 HTTPS 站点的 Enhanced Apps，你可以覆盖默认包：

- 创建一个统一的证书 `.pem` 文件，其中包含 Heimdall 需要验证的所有 CA 和证书。例如，如果你同时使用 LetsEncrypt 和本地 CA 来为内部应用签发证书，请将 LetsEncrypt 中间 CA（通过浏览器导出）和你的本地 CA `cert.pem`（或任意数量的自签名证书）合并到一个 `heimdall.pem` 文件中。
- 将 `heimdall.pem` 放入容器中（如果你使用 Docker），例如将其放在映射到 `/config` 的路径下。确保 Heimdall 用户具有读取权限 (`chmod a+r`)。
- 在 `/config/php/php-local.ini` 中设置 `openssl.cafile` 指向你的证书包：

```
# /config/php/php-local.ini
openssl.cafile = /config/heimdall.pem
```

重启容器后，Enhanced Apps 现在应该能够访问你的本地 HTTP 网站。此配置在更新或重新创建 Heimdall 容器时仍然有效。

## 支持
https://discord.gg/CCjHKn4 或通过 GitHub issues

## 捐赠
如果你想表达你的感谢，请使用以下链接。

[![PayPal](https://heimdall.site/img/paypaldonate.svg)](https://www.paypal.me/heimdall)

## 致谢
- PHP 框架 - [Laravel](https://laravel.com/)
- 图标 - [FontAwesome 5](https://fontawesome.com/)
- JavaScript - [jQuery](https://jquery.com/)
- 颜色选择器 - [Huebee](http://huebee.buzz/)
- 背景图片 - [pexels](https://www.pexels.com)
- Linuxserver.io 的所有人，感谢他们对应用的帮助，当然不要忘记 IronicBadger 提出的以下问题，正是这个问题促成了这一切：
```
you know, i would love something like this landing page for all my servers apps
that gives me the ability to pin favourites
and / or search
@Stark @Kode do either of you think you'd be able to rustle something like this up ?
```

## 许可证

本应用是开源软件，采用 [MIT 许可证](https://opensource.org/licenses/MIT) 授权。