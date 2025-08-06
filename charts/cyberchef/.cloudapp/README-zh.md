# CyberChef

[![](https://github.com/gchq/CyberChef/workflows/Master%20Build,%20Test%20&%20Deploy/badge.svg)](https://github.com/gchq/CyberChef/actions?query=workflow%3A%22Master+Build%2C+Test+%26+Deploy%22)
[![npm](https://img.shields.io/npm/v/cyberchef.svg)](https://www.npmjs.com/package/cyberchef)
[![](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://github.com/gchq/CyberChef/blob/master/LICENSE)
[![Gitter](https://badges.gitter.im/gchq/CyberChef.svg)](https://gitter.im/gchq/CyberChef?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

#### *网络瑞士军刀*

CyberChef 是一个简单、直观的网页应用，可在浏览器中执行各种“网络”操作。这些操作包括简单的编码（如 XOR 和 Base64）、更复杂的加密（如 AES、DES 和 Blowfish）、创建二进制和十六进制转储、数据压缩与解压缩、计算哈希值和校验和、IPv6 和 X.509 解析、更改字符编码等，功能非常丰富。

该工具旨在让技术人员和非技术人员都能以复杂的方式操作数据，而无需处理复杂的工具或算法。它由一名分析师在几年的时间里利用其 10% 的创新时间构思、设计、开发并逐步改进。

## 在线演示

CyberChef 仍在积极开发中。因此，它不应被视为一个完成的产品。仍然需要进行测试和修复错误、添加新功能以及编写更多文档。欢迎贡献！

CyberChef 中的加密操作不应被依赖于提供任何情况下的安全性。我们不对其正确性提供任何保证。

[在线演示地址][1] - 玩得开心！

## 使用 Docker 本地运行

**前提条件**

- [Docker](https://www.docker.com/products/docker-desktop/)
  - Docker Desktop 必须在您的机器上打开并运行

#### 选项 1：自行构建 Docker 镜像

1. 构建 docker 镜像
```bash
docker build --tag cyberchef --ulimit nofile=10000 .
```
2. 运行 docker 容器
```bash
docker run -it -p 8080:80 cyberchef
```
3. 在浏览器中访问 `http://localhost:8080`

#### 选项 2：使用预构建的 Docker 镜像

如果您希望跳过构建过程，可以使用预构建的镜像

```bash
docker run -it -p 8080:80 ghcr.io/gchq/cyberchef:latest
```

同样，在浏览器中访问 `http://localhost:8080`。

该镜像是通过我们的 [GitHub 工作流](.github/workflows/releases.yml) 构建并发布的。

## 工作原理

CyberChef 主要包含四个区域：

 1. 右上角的 **输入** 框，您可以在此粘贴、输入或拖入要操作的文本或文件。
 2. 右下角的 **输出** 框，用于显示处理结果。
 3. 最左侧的 **操作** 列表，您可以在分类列表中或通过搜索找到 CyberChef 支持的所有操作。
 4. 中间的 **配方** 区域，您可以在此拖动所需的操作，并指定参数和选项。

您可以以简单或复杂的方式使用任意数量的操作。以下是一些示例：

 - [解码一个 Base64 编码的字符串][2]
 - [将日期和时间转换为不同的时区][3]
 - [解析一个 Teredo IPv6 地址][4]
 - [将数据从十六进制转储转换，然后解压缩][5]
 - [解密并反汇编 shellcode][6]
 - [将多个时间戳显示为完整日期][7]
 - [对不同类型的数据执行不同的操作][8]
 - [使用输入的一部分作为操作的参数][9]
 - [执行 AES 解密，并从密文流的开头提取 IV][10]
 - [自动检测多层嵌套编码][12]

## 特性

 - 拖放功能
     - 操作可以自由拖入、拖出或重新排序。
     - 最大 2GB 的文件可以直接拖放到输入框中加载到浏览器。
 - 自动烘焙
     - 当您修改输入或配方时，CyberChef 会自动“烘焙”并立即生成输出。
     - 如果影响性能（例如输入非常大），可以关闭此功能并手动操作。
 - 自动编码检测
     - CyberChef 使用 [多种技术](https://github.com/gchq/CyberChef/wiki/Automatic-detection-of-encoded-data-using-CyberChef-Magic) 尝试自动检测数据所使用的编码方式。如果找到合适的操作可以解析您的数据，输出字段中会显示“魔法”图标，点击即可解码。
 - 断点
     - 您可以在配方中的任何操作上设置断点，以在执行前暂停。
     - 您还可以逐个操作逐步执行，查看每个阶段的数据状态。
 - 保存和加载配方
     - 如果您创建了一个很棒的配方，只需点击“保存配方”即可将其保存到本地存储中，下次访问 CyberChef 时仍然可用。
     - 您也可以复制包含配方和输入的 URL，方便与他人分享。
 - 搜索
     - 如果您知道所需操作的名称或相关词汇，只需在搜索框中输入，匹配的操作会立即显示。
 - 高亮显示
     - 当您在输入或输出中高亮文本时，会显示偏移量和长度值，并且如果可能，相应的数据会在输出或输入中高亮显示（例如：[在输入中高亮“question”一词以查看其在输出中的位置][11]）。
 - 保存到文件和从文件加载
     - 您可以随时将输出保存为文件，或者通过拖放操作将文件加载到输入字段中。支持最大约 2GB 的文件（取决于您的浏览器），但对如此大的数据执行某些操作可能会非常耗时。
 - CyberChef 完全基于客户端
     - 请注意，您的配方配置或输入（文本或文件）不会发送到 CyberChef 的服务器 - 所有处理都在您的浏览器中本地完成。
     - 由于此特性，CyberChef 可以下载并在本地运行。您可以使用应用左上角的链接下载完整的 CyberChef，放入虚拟机、与他人共享，或在封闭网络中托管。

## 深度链接

通过操作 CyberChef 的 URL 哈希，您可以更改页面打开时的初始设置。
格式为：`https://gchq.github.io/CyberChef/#recipe=Operation()&input=...`

支持的参数有 `recipe`、`input`（Base64 编码）和 `theme`。

## 浏览器支持

CyberChef 支持以下浏览器：

 - Google Chrome 50+
 - Mozilla Firefox 38+

## Node.js 支持

CyberChef 完全支持 Node.js `v16`。更多信息请参见 ["Node API" wiki 页面](https://github.com/gchq/CyberChef/wiki/Node-API)

## 贡献

向 CyberChef 贡献新操作非常简单！快速入门脚本将引导您完成整个过程。如果您能编写基本的 JavaScript，就可以编写 CyberChef 操作。

安装指南、添加新操作和主题的教程、仓库结构描述、可用数据类型和编码规范都可以在 ["贡献" wiki 页面](https://github.com/gchq/CyberChef/wiki/Contributing) 找到。

 - 将您的更改推送到您的 fork。
 - 提交一个拉取请求。如果是第一次提交，您将在拉取请求中被提示通过 CLA 助手签署 [GCHQ 贡献者许可协议](https://cla-assistant.io/gchq/CyberChef)。这还将询问您是否愿意让 GCHQ 联系您以表达对贡献的感谢或提供 GCHQ 的工作机会。

## 许可协议

CyberChef 发布于 [Apache 2.0 许可证](https://www.apache.org/licenses/LICENSE-2.0)，并受 [英国皇家版权](https://www.nationalarchives.gov.uk/information-management/re-using-public-sector-information/uk-government-licensing-framework/crown-copyright/) 保护。

  [1]: https://gchq.github.io/CyberChef
  [2]: https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true)&input=VTI4Z2JHOXVaeUJoYm1RZ2RHaGhibXR6SUdadmNpQmhiR3dnZEdobElHWnBjMmd1
  [3]: https://gchq.github.io/CyberChef/#recipe=Translate_DateTime_Format('Standard%20date%20and%20time','DD/MM/YYYY%20HH:mm:ss','UTC','dddd%20Do%20MMMM%20YYYY%20HH:mm:ss%20Z%20z','Australia/Queensland')&input=MTUvMDYvMjAxNSAyMDo0NTowMA
  [4]: https://gchq.github.io/CyberChef/#recipe=Parse_IPv6_address()&input=MjAwMTowMDAwOjQxMzY6ZTM3ODo4MDAwOjYzYmY6M2ZmZjpmZGQy
  [5]: https://gchq.github.io/CyberChef/#recipe=From_Hexdump()Gunzip()&input=MDAwMDAwMDAgIDFmIDhiIDA4IDAwIDEyIGJjIGYzIDU3IDAwIGZmIDBkIGM3IGMxIDA5IDAwIDIwICB8Li4uLi6881cu/y7HwS4uIHwKMDAwMDAwMTAgIDA4IDA1IGQwIDU1IGZlIDA0IDJkIGQzIDA0IDFmIGNhIDhjIDQ0IDIxIDViIGZmICB8Li7QVf4uLdMuLsouRCFb/3wKMDAwMDAwMjAgIDYwIGM3IGQ3IDAzIDE2IGJlIDQwIDFmIDc4IDRhIDNmIDA5IDg5IDBiIDlhIDdkICB8YMfXLi6+QC54Sj8uLi4ufXwKMDAwMDAwMzAgIDRlIGM4IDRlIDZkIDA1IDFlIDAxIDhiIDRjIDI0IDAwIDAwIDAwICAgICAgICAgICB8TshObS4uLi5MJC4uLnw
  [6]: https://gchq.github.io/CyberChef/#recipe=RC4(%7B'option':'UTF8','string':'secret'%7D,'Hex','Hex')Disassemble_x86('64','Full%20x86%20architecture',16,0,true,true)&input=MjFkZGQyNTQwMTYwZWU2NWZlMDc3NzEwM2YyYTM5ZmJlNWJjYjZhYTBhYWJkNDE0ZjkwYzZjYWY1MzEyNzU0YWY3NzRiNzZiM2JiY2QxOTNjYjNkZGZkYmM1YTI2NTMzYTY4NmI1OWI4ZmVkNGQzODBkNDc0NDIwMWFlYzIwNDA1MDcxMzhlMmZlMmIzOTUwNDQ2ZGIzMWQyYmM2MjliZTRkM2YyZWIwMDQzYzI5M2Q3YTVkMjk2MmMwMGZlNmRhMzAwNzJkOGM1YTZiNGZlN2Q4NTlhMDQwZWVhZjI5OTczMzYzMDJmNWEwZWMxOQ
  [7]: https://gchq.github.io/CyberChef/#recipe=Fork('%5C%5Cn','%5C%5Cn',false)From_UNIX_Timestamp('Seconds%20(s)')&input=OTc4MzQ2ODAwCjEwMTI2NTEyMDAKMTA0NjY5NjQwMAoxMDgxMDg3MjAwCjExMTUzMDUyMDAKMTE0OTYwOTYwMA
  [8]: https://gchq.github.io/CyberChef/#recipe=Fork('%5C%5Cn','%5C%5Cn',false)Conditional_Jump('1',false,'base64',10)To_Hex('Space')Return()Label('base64')To_Base64('A-Za-z0-9%2B/%3D')&input=U29tZSBkYXRhIHdpdGggYSAxIGluIGl0ClNvbWUgZGF0YSB3aXRoIGEgMiBpbiBpdA
  [9]: https://gchq.github.io/CyberChef/#recipe=Register('key%3D(%5B%5C%5Cda-f%5D*)',true,false)Find_/_Replace(%7B'option':'Regex','string':'.*data%3D(.*)'%7D,'$1',true,false,true)RC4(%7B'option':'Hex','string':'$R0'%7D,'Hex','Latin1')&input=aHR0cDovL21hbHdhcmV6LmJpei9iZWFjb24ucGhwP2tleT0wZTkzMmE1YyZkYXRhPThkYjdkNWViZTM4NjYzYTU0ZWNiYjMzNGUzZGIxMQ
  [10]: https://gchq.github.io/CyberChef/#recipe=Register('(.%7B32%7D)',true,false)Drop_bytes(0,32,false)AES_Decrypt(%7B'option':'Hex','string':'1748e7179bd56570d51fa4ba287cc3e5'%7D,%7B'option':'Hex','string':'$R0'%7D,'CTR','Hex','Raw',%7B'option':'Hex','string':''%7D)&input=NTFlMjAxZDQ2MzY5OGVmNWY3MTdmNzFmNWI0NzEyYWYyMGJlNjc0YjNiZmY1M2QzODU0NjM5NmVlNjFkYWFjNDkwOGUzMTljYTNmY2Y3MDg5YmZiNmIzOGVhOTllNzgxZDI2ZTU3N2JhOWRkNmYzMTFhMzk0MjBiODk3OGU5MzAxNGIwNDJkNDQ3MjZjYWVkZjU0MzZlYWY2NTI0MjljMGRmOTRiNTIxNjc2YzdjMmNlODEyMDk3YzI3NzI3M2M3YzcyY2Q4OWFlYzhkOWZiNGEyNzU4NmNjZjZhYTBhZWUyMjRjMzRiYTNiZmRmN2FlYjFkZGQ0Nzc2MjJiOTFlNzJjOWU3MDlhYjYwZjhkYWY3MzFlYzBjYzg1Y2UwZjc0NmZmMTU1NGE1YTNlYzI5MWNhNDBmOWU2MjlhODcyNTkyZDk4OGZkZDgzNDUzNGFiYTc5YzFhZDE2NzY3NjlhN2MwMTBiZjA0NzM5ZWNkYjY1ZDk1MzAyMzcxZDYyOWQ5ZTM3ZTdiNGEzNjFkYTQ2OGYxZWQ1MzU4OTIyZDJlYTc1MmRkMTFjMzY2ZjMwMTdiMTRhYTAxMWQyYWYwM2M0NGY5NTU3OTA5OGExNWUzY2Y5YjQ0ODZmOGZmZTljMjM5ZjM0ZGU3MTUxZjZjYTY1MDBmZTRiODUwYzNmMWMwMmU4MDFjYWYzYTI0NDY0NjE0ZTQyODAxNjE1YjhmZmFhMDdhYzgyNTE0OTNmZmRhN2RlNWRkZjMzNjg4ODBjMmI5NWIwMzBmNDFmOGYxNTA2NmFkZDA3MWE2NmNmNjBlNWY0NmYzYTIzMGQzOTdiNjUyOTYzYTIxYTUzZg
  [11]: https://gchq.github.io/CyberChef/#recipe=XOR(%7B'option':'Hex','string':'3a'%7D,'Standard',false)To_Hexdump(16,false,false)&input=VGhlIGFuc3dlciB0byB0aGUgdWx0aW1hdGUgcXVlc3Rpb24gb2YgbGlmZSwgdGhlIFVuaXZlcnNlLCBhbmQgZXZlcnl0aGluZyBpcyA0Mi4
  [12]: https://gchq.github.io/CyberChef/#recipe=Magic(3,false,false)&input=V1VhZ3dzaWFlNm1QOGdOdENDTFVGcENwQ0IyNlJtQkRvREQ4UGFjZEFtekF6QlZqa0syUXN0RlhhS2hwQzZpVVM3UkhxWHJKdEZpc29SU2dvSjR3aGptMWFybTg2NHFhTnE0UmNmVW1MSHJjc0FhWmM1VFhDWWlmTmRnUzgzZ0RlZWpHWDQ2Z2FpTXl1QlY2RXNrSHQxc2NnSjg4eDJ0TlNvdFFEd2JHWTFtbUNvYjJBUkdGdkNLWU5xaU45aXBNcTFaVTFtZ2tkYk51R2NiNzZhUnRZV2hDR1VjOGc5M1VKdWRoYjhodHNoZVpud1RwZ3FoeDgzU1ZKU1pYTVhVakpUMnptcEM3dVhXdHVtcW9rYmRTaTg4WXRrV0RBYzFUb291aDJvSDRENGRkbU5LSldVRHBNd21uZ1VtSzE0eHdtb21jY1BRRTloTTE3MkFQblNxd3hkS1ExNzJSa2NBc3lzbm1qNWdHdFJtVk5OaDJzMzU5d3I2bVMyUVJQ