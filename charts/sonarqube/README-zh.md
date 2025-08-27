# SonarQube [![构建状态](https://api.cirrus-ci.com/github/SonarSource/sonarqube.svg?branch=master)](https://cirrus-ci.com/github/SonarSource/sonarqube) [![质量门状态](https://next.sonarqube.com/sonarqube/api/project_badges/measure?project=sonarqube&metric=alert_status&token=d95182127dd5583f57578d769b511660601a8547)](https://next.sonarqube.com/sonarqube/dashboard?id=sonarqube) [![AI代码保障](https://next.sonarqube.com/sonarqube/api/project_badges/ai_code_assurance?project=org.sonarsource.sonarqube%3Asonarqube-private&token=sqb_c0e2fa9ac4ef89f9a8403c6ba235e108ceb1dce1)](https://next.sonarqube.com/sonarqube/dashboard?id=sonarqube)

## 持续检查

SonarQube 不仅可以展示应用程序的健康状况，还可以突出显示新引入的问题。通过设置质量门禁，您可以[实现整洁代码](https://www.sonarsource.com/solutions/clean-code/)，从而系统性地提升代码质量。

## 链接

- [网站](https://www.sonarsource.com/products/sonarqube)
- [下载](https://www.sonarsource.com/products/sonarqube/downloads)
- [文档](https://docs.sonarsource.com/sonarqube)
- [Web应用源代码](https://github.com/SonarSource/sonarqube-webapp)
- [X](https://twitter.com/SonarQube)
- [SonarSource](https://www.sonarsource.com)，SonarQube 的作者
- [问题跟踪](https://jira.sonarsource.com/browse/SONAR/)，只读。只有 SonarSourcers 可以创建工单。
- [负责任的漏洞披露](https://community.sonarsource.com/t/responsible-vulnerability-disclosure/9317)
- 下一版本 SonarQube 的 [测试实例](https://next.sonarqube.com/sonarqube)

## 有疑问或反馈？

对于支持类问题（“我该如何做？”、“我遇到了这个错误，为什么？”等），请先阅读[文档](https://docs.sonarsource.com/sonarqube)，然后前往 [SonarSource 社区](https://community.sonarsource.com/c/help/sq/10)。您的问题很可能已经被解答过了！🤓

请注意，这个论坛是一个社区，因此需要遵循基本的礼貌用语（“你好”、“谢谢”等）。如果您在论坛中发帖后没有收到回复，请至少等待三天后再回复催促。这里没有专人实时在线。😄

## 贡献

如果您希望看到新功能或报告一个 bug，请在我们的[论坛](https://community.sonarsource.com/c/sq/10)中创建新主题。

请注意，我们不会主动寻求功能贡献。实际上，对于 SonarSource 以外的人员来说，要符合我们的路线图和期望是非常困难的。因此，我们通常只接受微小的外观修改和拼写错误修复。

考虑到这一点，如果您希望提交代码贡献，请为此仓库创建一个 pull request。请说明您提交此更改的动机：您试图修复什么问题，或进行什么改进。

请确保遵循我们的 [代码风格](https://github.com/SonarSource/sonar-developer-toolset#code-style)，并且所有测试都通过（每个 pull request 都会执行 Travis 构建）。

愿意为 SonarSource 产品做贡献吗？我们正在寻找聪明、热情且技术过硬的人才，一起打造世界级的代码质量解决方案。查看我们当前的[职位招聘](https://www.sonarsource.com/company/jobs/)！

## 构建

要在本地构建源代码，请按照以下说明操作。

### 构建并运行单元测试

从项目根目录执行：

    ./gradlew build

zip 格式的分发文件会生成在 `sonar-application/build/distributions/` 中。解压后执行以下命令启动服务器：

    # Linux 上
    bin/linux-x86-64/sonar.sh start
    # 或者 MacOS 上
    bin/macosx-universal-64/sonar.sh start
    # 或者 Windows 上
    bin\windows-x86-64\StartSonar.bat

### 在 IDE 中打开

如果项目尚未构建过，请先正常构建（见上一节），或者使用更快的命令：

    ./gradlew ide

然后在 IntelliJ 或 Eclipse 中将根文件 `build.gradle` 作为项目打开。

### Gradle 使用提示

| ./gradlew 命令                | 描述                               |
| ----------------------------- | ---------------------------------- |
| `dependencies`                | 列出依赖项                         |
| `licenseFormat --rerun-tasks` | 根据 HEADER.txt 修复源文件头信息   |
| `wrapper --gradle-version 5.2.1` | 升级 wrapper                      |

## 包含 UI 修改的构建

SonarQube 的前端（我们称之为 webapp）位于另一个仓库中：[sonarqube-webapp](https://github.com/SonarSource/sonarqube-webapp)。

在构建 `sonarqube` 仓库时，webapp 会自动从 Maven Central 下载为依赖项，这使得您可以轻松地进行后端修改，而无需关心前端部分。

但如果您所做的贡献也包含前端修改，则必须克隆 `sonarqube-webapp` 仓库，在其中进行修改，本地构建后，再通过设置 `WEBAPP_BUILD_PATH` 环境变量来指向您自定义构建的前端版本，再构建 `sonarqube` 仓库。

示例如下：

```bash
cd /path/to/sonarqube-webapp/server/sonar-web
# 进行您的修改

# 安装依赖，仅首次需要
yarn

# 构建前端
yarn build


cd /path/to/sonarqube

# 使用自定义构建的前端构建 sonarqube 仓库
WEBAPP_BUILD_PATH=/path/to/sonarqube-webapp/server/sonar-web/build/webapp ./gradlew build
```

您也可以通过修改 `./gradle.properties` 文件中的 `webappVersion` 属性来指定特定版本的前端，然后正常构建 `sonarqube` 仓库。

## 翻译文件

过去我们的翻译文件存储在 `sonar-core/src/main/resources/org/sonar/l10n/core.properties` 中，但该文件现已弃用，不再更新。
默认翻译（英文）现在定义在前端仓库中，地址如下：
https://github.com/SonarSource/sonarqube-webapp/blob/master/libs/sq-server-shared/src/l10n/default.ts

虽然格式发生了变化，但您仍可以通过以下命令生成兼容的 `.properties` 文件：

```bash
cd /path/to/sonarqube-webapp/server/sonar-web

# 安装依赖，仅首次需要
yarn

# 生成向后兼容的 .properties 文件，包含所有翻译键
yarn generate-translation-keys
```

请注意，对于翻译成其他语言的扩展贡献，其方式与之前相同。只是默认翻译的来源发生了变化。

## 许可证

版权所有 © 2008-2025 SonarSource。

本项目使用 [GNU Lesser General Public License 3.0](https://www.gnu.org/licenses/lgpl.txt) 开源许可证。