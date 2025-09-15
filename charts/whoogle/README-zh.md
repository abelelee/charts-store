>[!WARNING]
>
>截至2025年1月16日，Google似乎不再支持在禁用JavaScript的情况下执行搜索查询。这是Whoogle工作方式的一个基本部分——Whoogle会请求无JavaScript的搜索结果，然后过滤掉结果页面中的垃圾内容，并为用户代理所有外部内容。
>
>这可能是一个破坏性的变化，意味着Whoogle的终结。我将继续监控他们无JS结果的状态并研究可能的解决方案，如果找到解决方案（或未找到），将再发布一篇更新。

___

![Whoogle 搜索](docs/banner.png)

[![最新版本](https://img.shields.io/github/v/release/benbusby/whoogle-search)](https://github.com/benbusby/shoogle/releases)
[![许可证: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![测试](https://github.com/benbusby/whoogle-search/actions/workflows/tests.yml/badge.svg)](https://github.com/benbusby/whoogle-search/actions/workflows/tests.yml)
[![构建](https://github.com/benbusby/whoogle-search/actions/workflows/buildx.yml/badge.svg)](https://github.com/benbusby/whoogle-search/actions/workflows/buildx.yml)
[![codebeat评分](https://codebeat.co/badges/e96cada2-fb6f-4528-8285-7d72abd74e8d)](https://codebeat.co/projects/github-com-benbusby-shoogle-master)
[![Docker拉取次数](https://img.shields.io/docker/pulls/benbusby/whoogle-search)](https://hub.docker.com/r/benbusby/whoogle-search)

<table>
  <tr>
    <td><a href="https://sr.ht/~benbusby/whoogle-search">SourceHut</a></td>
    <td><a href="https://github.com/benbusby/whoogle-search">GitHub</a></td>
  </tr>
</table>

获取Google搜索结果，但无任何广告、JavaScript、AMP链接、Cookie或IP地址跟踪。可一键部署为Docker应用，并可通过单个配置文件进行自定义。在桌面和移动设备上作为主要搜索引擎的替代方案，实现快速且简单的部署。

目录
1. 功能
3. 安装/部署选项
    1. Heroku快速部署
    1. Render.com
    1. Repl.it
    1. Fly.io
    1. Koyeb
    1. pipx
    1. pip
    1. 手动安装
    1. Docker
    1. Arch/AUR
    1. Helm/Kubernetes
4. 环境变量和配置
5. 使用方法
6. 额外步骤
    1. 设置主搜索引擎
	2. 自定义重定向
	2. 自定义Bangs
    3. 防止停机（仅限Heroku）
    4. 手动HTTPS强制
    5. 与Firefox容器一起使用
    6. 反向代理
        1. Nginx
7. 贡献
8. 常见问题
9. 公共实例
10. 截图