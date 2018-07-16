# 更新本地代码

## Fork项目并克隆到本地

项目成员将公共仓库代码 [fork](/setup/fork.md) 到自己的命名空间下，并将自己命名空间下的项目 [clone](/setup/clone.md) 到本地。

## 跟踪公共仓库开发分支

想要追踪公共仓库开发分支的代码，首先需要在 SourceTree 中配置远程仓库 URL。打开本地仓库，点击`工具栏->仓库->仓库设置`：

![](/assets/sourcetree-add-url.png)

点击添加按钮：

![](/assets/sourcetree-url-detail.png)

配置好目的分支的URL，即公共仓库的地址，并为该远程仓库起一个名字。

点击确定完成添加。

## 拉取更新

在提交 Merge Request 之前，有可能有其他的组员已经合并了代码到目的分支上，而此时我们源分支的代码已经落后于目的分支，此时提交 Merge Request 就会引起[冲突](https://about.gitlab.com/2016/09/06/resolving-merge-conflicts-from-the-gitlab-ui/)。

所以，在**修改本地代码之前**，我们应该先检查一下公共仓库开发分支的代码是否有更新，若有更新，则同步到本地代码，这是一个好的习惯。

点击工具栏 `拉取` 按钮，弹出对话框：

![](/assets/sourcetree-pull.png)

选择公共仓库和要拉取的分支，点击`确定`。

如果本地代码就是远程分支的祖先提交，那么远程分支的代码顺利更新到本地；如果已经手动更新了本地代码，再拉取远端代码，则会发生冲突，参考[解决冲突](/others/merge-conflict)。

> **[info] 建议**
>
> 为了避免解决冲突的麻烦，建议不要直接在本地开发分支上做修改，而应该创建一个新的分支去做修改；

## 创建新分支

修改代码需要在一个新的临时分支上进行。
 
打开 SourceTree，点击工具栏 `分支` 按钮：

![](/assets/sourcetree-check-branch.png)

在弹出的对话框中填写新分支的名称（建议格式为 `fix_bugXXX_name`），如果勾选了 `检出新分支`，则点击 `创建分支` 按钮后自动检出到新分支。

![](/assets/sourcetree-show-newbranch.png)

可以看到，新分支已经创建完成并检出（加粗分支为检出分支）。






