# openHAB 插件

<img align="right" width="220" src="logo.png" alt="openHAB logo" />

[![GitHub Actions Build Status](https://github.com/openhab/openhab-addons/actions/workflows/ci-build.yml/badge.svg?branch=main)](https://github.com/openhab/openhab-addons/actions/workflows/ci-build.yml)
[![Jenkins Build Status](https://ci.openhab.org/job/openHAB-Addons/badge/icon)](https://ci.openhab.org/job/openHAB-Addons/)
[![EPL-2.0](https://img.shields.io/badge/license-EPL%202-green.svg)](https://opensource.org/licenses/EPL-2.0)
[![Crowdin](https://badges.crowdin.net/openhab-addons/localized.svg)](https://crowdin.com/project/openhab-addons)

本仓库包含基于 openHAB 核心 API 实现的官方插件集合。
被接受加入本仓库的插件将由 [openHAB 插件维护者](https://github.com/orgs/openhab/teams/add-ons-maintainers) 进行维护（例如适配新的核心 API）。

如需开始开发插件，请参考我们的指南和教程：<https://www.openhab.org/docs/developer>。

如果您对 openHAB 核心开发感兴趣，欢迎访问：<https://github.com/openhab/openhab-core>。

## 其他仓库中的插件

一些插件不在本仓库中，但仍然是官方 [openHAB 发行版](https://github.com/openhab/openhab-distro) 的一部分。
以下列出了一些其他仓库（不完整列表）：

- <https://github.com/openhab/org.openhab.binding.zwave>
- <https://github.com/openhab/org.openhab.binding.zigbee>
- <https://github.com/openhab/openhab-webui>

## 开发 / 仓库结构

openHAB 插件是 [Java](https://en.wikipedia.org/wiki/Java_(programming_language)) `.jar` 文件。

openHAB 构建系统基于 [Maven](https://maven.apache.org/what-is-maven.html)。
官方推荐的集成开发环境（IDE）是 Eclipse。

仓库结构如下所示：

```text
.
+-- bom       Maven 构建系统：物料清单
|   +-- openhab-addons  列出所有扩展供其他仓库引用
|   +-- ...             其他 bom
|
+-- bundles   官方 openHAB 扩展
|   +-- org.openhab.binding.airquality
|   +-- org.openhab.binding.astro
|   +-- ...
|
+-- features  运行时依赖解析器的一部分（"Karaf 特性"）
|
+-- itests    集成测试。这些测试需要框架的部分组件运行。
|   +-- org.openhab.binding.astro.tests
|   +-- org.openhab.binding.avmfritz.tests
|   +-- ...
|
+-- src/etc   辅助构建系统文件：例如自动检查的许可证头部
+-- tools     静态代码分析器说明
|
+-- CODEOWNERS  该文件将人员分配到目录，以便在拉取请求修改其插件时通知他们。
```

### 命令行构建

要从命令行构建所有插件，请输入：

```shell
mvn clean install
```

大多数情况下，您不需要构建所有绑定，而只需构建您正在开发的绑定。
要仅构建您的绑定，请使用 `-pl` 选项。
例如，仅构建 astro 绑定：

```shell
mvn clean install -pl :org.openhab.binding.astro
```

如果您的绑定在 feature.xml 中指定了动态依赖项，则可以创建 `.kar` 文件而不是 `.jar` 文件。
`.kar` 文件将包含 feature.xml，并且在添加到 openHAB 时会加载并激活 feature.xml 中指定的依赖项。
要创建 `.kar` 文件，请使用目标 `karaf:kar` 运行 Maven：

```shell
mvn clean install karaf:kar -pl :org.openhab.binding.astro
```

为了提高构建速度，可以在命令中添加以下选项：

| 选项                        | 描述                                         |
| ----------------------------- | --------------------------------------------------- |
| `-DskipChecks`                | 跳过静态分析（Checkstyle、FindBugs）     |
| `-DskipTests`                 | 跳过测试执行                         |
| `-Dmaven.test.skip=true`      | 跳过测试编译和执行         |
| `-Dfeatures.verify.skip=true` | 跳过 Karaf 特性验证                 |
| `-Dspotless.check.skip=true`  | 跳过 Spotless 代码风格检查                 |
| `-o`                          | 离线工作，Maven 不会下载任何更新 |
| `-T 1C`                       | 并行构建，每个核心使用 1 个线程          |
| `-pl :<插件目录>`             | 构建单个插件                               |

例如，在开发期间可以跳过检查和测试：

```shell
mvn clean install -DskipChecks -DskipTests -pl :org.openhab.binding.astro
```

添加这些选项可以提高构建速度，但可能会隐藏代码中的问题。
并行构建也更难调试，增加的负载可能导致对时间敏感的测试失败。

#### 翻译

插件翻译通过 [Crowdin](https://crowdin.com/project/openhab-addons) 管理。
英文翻译取自 openHAB-addons GitHub 仓库，并在英文 i18n 属性文件发生更改时自动导入 Crowdin。
当在 Crowdin 中添加或更新翻译并获得批准后，Crowdin 会自动创建一个拉取请求。
因此，翻译不应在 openHAB-addons 仓库中编辑，而应仅在 Crowdin 中进行。
否则翻译将被自动流程覆盖。

要填充英文属性文件，请在插件上运行以下 Maven 命令：

```shell
mvn i18n:generate-default-translations
```

当添加或更新 things 或 channel 时，该命令也可以更新文件。

在某些情况下，该命令无法工作，需要使用完整的插件名称。
此时请使用：

```shell
mvn org.openhab.core.tools:i18n-maven-plugin:5.0.0:generate-default-translations
```

#### 代码质量

要检查代码是否符合 [代码风格](https://www.openhab.org/docs/developer/guidelines.html#b-code-formatting-rules-style)，请运行：

```shell
mvn spotless:check
```

要重新格式化代码以符合代码风格，请运行：

```shell
mvn spotless:apply
```

### 集成测试

如果您的插件在 `itests` 目录中也有集成测试，则在 Maven 依赖项更改时，可能需要更新 `itest.bndrun` 文件中的 runbundles。
Maven 可以通过执行以下命令自动解析集成测试依赖项：

```shell
mvn clean install -DwithResolver -DskipChecks
```

构建会在相应 bundle 的 `/target` 目录下生成每个 bundle 的 `.jar` 文件。

### 如何通过集成开发环境（IDE）进行开发

我们在开发者文档网站上为不同的 IDE 准备了一些分步指南：

<https://www.openhab.org/docs/developer/#setup-the-development-environment>

祝您编码愉快！