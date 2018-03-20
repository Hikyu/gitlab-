# 合并代码

当 Merge Request 收获了一定的 :+1: 并确认评审没有任何问题后，项目组长考虑将代码合并到目标分支。

## 没有冲突时的合并

![](/assets/gitlab-mr-merge.png)

打开 Merge Request，勾选 `Remove source branch`，该操作会将在 Gitlab 上创建的临时分支删除。

点击 `Merge` 按钮即可合并代码到目标分支。

## 遇到合并冲突

如果检测到冲突，即目标分支的代码比源分支的更新，Gitlab 会阻止你进行合并：

![](/assets/gitlab-mr-conflict.png)

点击 `Resolve confilcts` 在 Gitlab 上解决冲突：

![](/assets/gitlab-mr-conflict-resolve.png)

如上图所示，可以直接选择一侧的修改，也可以点击 `Edit inline` 直接修改文本。

冲突解决完毕，填写提交信息，点击 `Commit conflict resolution` 提交。

返回到 Merge Request 页面，刷新，此时 `Merge` 已经可以点击，执行合并了。

也可以选择 `Merge locally`，在本地进行冲突解决。
