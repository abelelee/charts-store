# 视频转流器（Restreamer）

datarhei/Restreamer 提供智能免费的视频流服务。可将 IP 摄像头的 H.264 视频实时推流到您的网站。您还可以将实时视频上传到 [YouTube-Live](https://www.youtube.com/)、[IBM Watson](https://video.ibm.com/)、[Twitch](https://www.twitch.tv/)、[Vimeo](https://livestream.com/) 或其他流媒体平台，例如 [Wowza-Streaming-Engine](https://www.wowza.com/)。我们的 [Docker 镜像](https://hub.docker.com/search/?q=restreamer&page=1&isAutomated=0&isOfficial=0&starCount=0&pullCount=0) 安装简单，支持 Linux、MacOS 和 Windows 系统。datarhei/Restreamer 可与 [Raspberry Pi](https://www.raspberrypi.org/) 和 [Odroid](http://www.hardkernel.com/main/main.php) 等单板计算机完美配合使用。它是免费的（采用 Apache 2.0 许可证），可用于任何用途，包括个人和商业用途。

## 功能特性

- 包含登录安全机制的用户界面
- JSON / HTTP API
- 使用 <a target="_blank" href="http://ffmpeg.org/">FFmpeg</a> 进行视频/摄像头流的流化/编码、生成快照或推流到外部流媒体端点
- 使用 <a target="_blank" href="http://nginx.org/">NGINX</a> 及其 <a target="_blank" href="https://github.com/sergey-dryabzhinsky/nginx-rtmp-module">RTMP 模块</a> 作为流媒体后端和 HLS 服务器
- 使用 <a target="_blank" href="https://github.com/clappr/clappr">Clappr 播放器</a> 将您的流嵌入到网站中
- 支持 <a target="_blank" href="https://www.docker.com/">Docker</a> 和 <a target="_blank" href="https://kitematic.com/">Kitematic (Docker-Toolbox)</a>，安装非常简便

## 文档

文档可在 [Datarhei/Restreamer GitHub 页面](https://datarhei.github.io/restreamer/) 上找到。  
我们提供了大量信息，包括设置摄像头、将播放器嵌入网站、推流到 YouTube-Live、Ustream 和 Livestream.com 等服务的详细说明。

关于流媒体、摄像头等内容的更多信息，请参阅我们的 [Wiki](https://datarhei.github.com/restreamer/wiki)。

## 开发

#### 构建自己的 Docker 镜像：

```sh
$ git clone https://github.com/datarhei/restreamer
$ docker build -t restreamer .
```

*需要 Docker 版本 >= 17.05*

## 帮助 / 报告错误

如果您遇到问题或发现 bug，请随时在 <a target="_blank" href="https://github.com/datarhei/restreamer/issues">Github 问题管理页面</a> 创建新 issue。

想要与我们交流？请发送邮件至 <a href="mailto:open@datarhei.org?subject=Datarhei/Restreamer">open@datarhei.org</a>，或在我们的 (<a target="_blank" href="https://groups.google.com/forum/#!forum/datarhei">论坛</a>) 上提问。

## 作者

datarhei/Restreamer 由 [Julius Eitzen](https://github.com/jeitzen)、[Sven Erbeck](https://github.com/svenerbeck)、[Christoph Johannsdotter](https://github.com/christophjohannsdotter) 和 [Jan Stabenow](https://github.com/jstabenow) 创建。

特别感谢 [Andrew Shulgin](https://github.com/andrew-shulgin) 对本项目的支持。

## 版权

代码采用 [Apache 许可证](LICENSE) 发布。图片版权归 datarhei.org 所有。