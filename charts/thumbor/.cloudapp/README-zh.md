---
<h4 align="center">加入 <a href="https://github.com/thumbor/thumbor-bootcamp">thumbor-bootcamp</a>，与 thumbor 团队一起体验充满 ❤️ 与 🤗 的学习与贡献之旅</h4>

<p align="center">
  <a href="http://www.thumbor.org">
    <img title="thumbor" alt="thumbor" src="https://github.com/thumbor/thumbor/blob/readme/docs/thumbor-logo.png?raw=true" />
  </a>
</p>

<h3 align="center">
裁剪、调整大小、转换等操作，全部按需提供并由 AI 驱动
</h3>

<p align="center">
  <img src='https://github.com/thumbor/thumbor/workflows/build/badge.svg' />
  <a href='https://coveralls.io/github/thumbor/thumbor?branch=master' target='_blank'>
    <img src='https://coveralls.io/repos/thumbor/thumbor/badge.svg?branch=master&service=github'/>
  </a>
  <a href='https://codeclimate.com/github/thumbor/thumbor' target='_blank'>
    <img src='https://codeclimate.com/github/thumbor/thumbor/badges/gpa.svg'/>
  </a>
  <a href='https://pypi.python.org/pypi/thumbor' target='_blank'>
    <img src='https://img.shields.io/pypi/v/thumbor.svg'/>
  </a>
  <br />
  <a href='https://github.com/thumbor/thumbor/pulls' target='_blank'>
    <img src='https://img.shields.io/github/issues-pr-raw/thumbor/thumbor.svg'/>
  </a>
  <a href='https://github.com/thumbor/thumbor/issues' target='_blank'>
    <img src='https://img.shields.io/github/issues-raw/thumbor/thumbor.svg'/>
  </a>
  <a href='https://pypi.python.org/pypi/thumbor' target='_blank'>
    <img src='https://img.shields.io/pypi/dm/thumbor.svg'/>
  </a>
  <a href='https://www.bountysource.com/trackers/257692-globocom-thumbor?utm_source=257692&utm_medium=shield&utm_campaign=TRACKER_BADGE' target='_blank'>
    <img src='https://www.bountysource.com/badge/tracker?tracker_id=257692'/>
  </a>
</p>

<h4 align="center">全球数百家公司信赖 thumbor</h4>
<p align="center">
  <img src="./docs/wikipedia.png" alt="Wikipedia 信任 thumbor" title="Wikipedia 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/globocom.png?raw=true" alt="Globo.com 信任 thumbor" title="Globo.com 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/vox.png?raw=true" alt="Vox Media 信任 thumbor" title="Vox Media 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/forbes-logo.png?raw=true" alt="Forbes 信任 thumbor" title="Forbes 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/squareup.png?raw=true" alt="Square 信任 thumbor" title="Square 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/deliveroo.png?raw=true" alt="Deliveroo 信任 thumbor" title="Deliveroo 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/canalplus.png?raw=true" alt="Canal+ 信任 thumbor" title="Canal+ 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/terra.png?raw=true" alt="Terra 信任 thumbor" title="Terra 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/nrc.png?raw=true" alt="nrc 信任 thumbor" title="nrc 信任 thumbor" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/webdev.png?raw=true" alt="web.dev 推荐 thumbor 用于高性能网站" title="web.dev 推荐 thumbor 用于高性能网站" width="128" height="128" />&nbsp;
  <img src="https://github.com/thumbor/thumbor/blob/readme/docs/aws.png?raw=true" alt="aws 推荐 thumbor 用于无服务器图像处理" title="aws 推荐 thumbor 用于无服务器图像处理" width="128" height="128" />
  <br />
  还有更多！
</p>

thumbor 是一个智能图像服务，支持按需进行 [裁剪、调整大小、应用滤镜和优化](http://thumbor.readthedocs.io/en/latest/crop_and_resize_algorithms.html) 图像。

自动裁剪照片可能会令人沮丧，因为有时会把人的头部裁掉。thumbor 使用 [AI 进行智能检测](http://thumbor.readthedocs.io/en/latest/detection_algorithms.html)。

thumbor 是一个 HTTP 服务器，你可以通过修改路径参数来生成任意数量的不同图像：

```
http://<thumbor-server>/300x200/smart/thumbor.readthedocs.io/en/latest/_images/logo-thumbor.png
```

你应该能看到一张 thumbor 标志的 300x200 图像。

了解更多关于 thumbor 的功能，请查看 [thumbor 的文档](http://thumbor.readthedocs.io/en/latest/index.html "thumbor 文档")。

## ⚙️ 安装

选择你想要使用的安装方式。

### 选项 1: pip

```bash
# 仅安装 thumbor 的主要依赖
pip install thumbor

# 安装带有 OpenCV 依赖的 thumbor
pip install thumbor[opencv]

# 安装带有所有依赖的 thumbor
pip install thumbor[all]
```

### 选项 2: 二进制安装

```bash
sudo add-apt-repository ppa:thumbor/ppa
sudo aptitude update
sudo aptitude install thumbor
```

更多安装方式，请查看 [安装指南](https://thumbor.readthedocs.io/en/latest/installing.html)。

### 运行

运行它非常简单，只需执行：

```bash
thumbor
```

之后，你可以通过访问 http://localhost:8888/unsafe/https://raw.githubusercontent.com/thumbor/thumbor/master/example.jpg 查看。

### 遇到问题？

如果你遇到任何问题，可以尝试运行：

```bash
thumbor-doctor
```

如果你有 `thumbor.conf` 配置文件，可以将其提供给 thumbor-doctor：

```bash
thumbor-doctor -c thumbor.conf
```

如果你仍需要帮助，请 [提交问题](https://github.com/thumbor/thumbor/issues)。请记得在提交问题时附上 `thumbor-doctor` 的输出：

```bash
thumbor-doctor --nocolor -c thumbor.conf
```

## 🎯 特性

- 开箱即用，支持所有常见图像格式
- [智能裁剪和调整大小](http://thumbor.readthedocs.io/en/latest/detection_algorithms.html)
- 利用缓存实现极速响应
- 支持多种存储方式（本地存储、AWS S3、Rackspace、Ceph 等）
- 基于人脸和特征检测（眼镜、兴趣点等）的 AI 裁剪功能
- 集成多种编程语言和框架 <img src="https://www.python.org/favicon.ico" width="16" height="16" /><img src="https://nodejs.org/static/images/favicons/favicon.png" width="16" height="16" /><img src="https://rubygems.org/favicon.ico" width="16" height="16" /> 等等...
- [高度可扩展](https://thumbor.readthedocs.io/en/latest/customizing.html)

## 🌟 精彩扩展

[awesome-thumbor](https://github.com/thumbor/awesome-thumbor) 是一个精心整理的 thumbor 相关资源列表。你可以在其中找到滤镜、存储、引擎、加载器、Docker 镜像、你喜爱的语言和框架的扩展等等。

所有项目都标明了其质量等级。尽情享受吧！

## 👍 贡献

thumbor 是一个拥有众多贡献者的开源项目。欢迎你加入他们，[贡献代码](https://github.com/thumbor/thumbor/blob/master/CONTRIBUTING.md) 或 [贡献文档](https://github.com/thumbor/thumbor/blob/master/CONTRIBUTING.md)。

如果你使用了 thumbor，请花 1 分钟填写 [这份调查问卷](http://t.co/qPBLXJX0mi)？只有两个问题！

加入聊天室：https://gitter.im/thumbor/thumbor

## 👀 演示

你可以在 http://thumborize.me/ 看到 thumbor 的实际效果。