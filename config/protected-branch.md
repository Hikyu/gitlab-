# 创建保护分支

为了禁止项目成员随意提交代码造成提交历史混乱，同时也为了防止有未评审的代码提交到项目仓库，可以设置保护分支达到这个目的。

【注意】保护分支由项目组长在项目创建完毕时进行配置。

保护分支的配置至少需要 Master 级别的权限，master 分支已经默认被设置为了保护分支。

配置保护分支可以做到：

- 禁止任何人对保护分支进行强制推送

- 禁止任何人删除保护分支

- 配置保护分支至少需要 Master 级别的权限可以推送代码

- 配置保护分支至少需要 Master 级别的权限可以合并代码

打开 Gitlab，进入到项目主页。点击左侧列表 `Settings->Repository`；

找到 `Protected Branches` 部分，点击 `Expand` 按钮；

从 Branch 下拉列表中，选择需要保护的分支，同时选择 `Allowed to merge` 和 `Allowed to push` 为 Masters，点击 `Protect` 按钮。

![](/assets/protected-branch.png)

【注意】对于[开发分支和发布分支](/workflow/workflow.md)，必须设置`Allowed to merge` 和 `Allowed to push` 为 Masters。即项目组长才有权限合并代码到这两个分支。