# 更新本地代码

## 跟踪远程开发分支

想要追踪目的分支的代码，首先需要在 SourceTree 中配置远程仓库 URL。打开  SourceTree，点击`工具栏->仓库->仓库设置`：

![](/assets/sourcetree-add-url.png)

点击添加按钮：

![](/assets/sourcetree-url-detail.png)

配置好目的分支的URL，即群组内项目的仓库地址，并为该远程仓库起一个名字。

点击确定完成添加。

## 拉取更新

在提交 Merge Request 之前，有可能有其他的组员已经合并了代码到目的分支上，而此时我们源分支的代码已经落后于目的分支，此时提交 Merge Request 就会引起[冲突](https://about.gitlab.com/2016/09/06/resolving-merge-conflicts-from-the-gitlab-ui/)。

所以，在**修改本地代码之前**，我们应该先检查一下目的分支的代码是否有更新，若有更新，则同步到本地代码，这是一个好的习惯。

点击工具栏 `拉取` 按钮，弹出对话框：

![](/assets/sourcetree-pull.png)

选择远程仓库和要拉取的分支，点击`确定`。

如果本地代码就是远程分支的祖先提交，那么远程分支的代码顺利更新到本地；如果已经手动更新了本地代码，再拉取远端代码，则会发生冲突，参考[解决冲突](/others/merge-conflict)。

> **[info] 建议**
>
> 为了避免解决冲突的麻烦，建议本地的修改不要直接应用到本地开发分支上；只有在拉取远端开发分支的情况下本地开发分支上的代码才会发生变动。

## 创建新分支

修改代码需要在一个新的临时分支上进行。
 
打开 SourceTree，点击工具栏 `分支` 按钮：

![](/assets/sourcetree-check-branch.png)

在弹出的对话框中填写新分支的名称（建议格式为 `fix_bugXXX_name`），如果勾选了 `检出新分支`，则点击 `创建分支` 按钮后自动检出到新分支。

![](/assets/sourcetree-show-newbranch.png)

可以看到，新分支已经创建完成并检出（加粗分支为检出分支）。






