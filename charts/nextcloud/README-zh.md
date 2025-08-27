---
<!--  
SPDX-FileCopyrightText: 2021-2024 Nextcloud GmbH und Nextcloud-Mitwirkende  
SPDX-License-Identifier: MIT  
-->  

# 本仓库包含 Nextcloud 的工作流模板  

## 在你的仓库中设置一个新模板  

当你在你的仓库中创建一个新的工作流时，你将看到来自这里的模板。  
https://github.com/nextcloud/viewer/actions/new  

![image](https://raw.githubusercontent.com/nextcloud/.github/master/screenshots/choose-a-workflow.png)  

## 自动更新仓库  

对于每个模板，你可以将它们传播到所有使用它的仓库中。  
1. 打开 https://github.com/nextcloud/.github/actions/workflows/dispatch-workflow.yml  
2. 输入你想要触发的工作流名称  
3. 输入你想要执行的页码（每页处理 100 个仓库），请查看仓库总数([number of repositories](https://github.com/orgs/nextcloud/repositories))，当前为 260 个，因此请运行页码 1、2 和 3  

  ![image](https://raw.githubusercontent.com/nextcloud/.github/master/screenshots/dispatch-a-workflow.png)  

4. 等待动作完成，并查看生成的拉取请求  

## 使用脚本更新工作流  

你也可以在本地运行以下 shell 脚本，以更新一个应用的所有工作流。该脚本应在克隆的应用仓库根目录中运行，并且需要安装 rsync。

⚠️ 提交更改前，请务必检查 diff 以避免不必要的修改，尤其是在稳定分支上更新工作流时！

```sh
#!/bin/sh

# 从 Nextcloud 模板仓库更新 GitHub 工作流。
# 该脚本应从仓库的根目录运行。

# 基本检查
[ ! -d ./.github/workflows/ ] && echo "错误：.github/workflows 不存在" && exit 1

# 克隆模板仓库
temp="$(mktemp -d)"
git clone --depth=1 https://github.com/nextcloud/.github.git "$temp"

# 更新工作流
rsync -vr \
    --existing \
    --include='*/' \
    --include='*.yml' \
    --exclude='*' \
    "$temp/workflow-templates/" \
    ./.github/workflows/

# 清理
rm -rf "$temp"
```