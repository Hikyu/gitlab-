# 更新本地代码

合并请求[^1]（Merge Request）是在 GitLab 上进行代码协作的基础。合并请求，即：请求将一个分支（源分支）合并到另一个分支（目的分支）。

在[工作流](/workflow/workflow.md)章节中，已经列举了日常修改代码的流程。可知，源分支即自己命名空间下群组内项目的 fork 版本中的分支；目的分支即群组内项目中的分支。

每次发起 Merge Request 时，就是从 fork 版本的分支合并到群组内项目的分支上。

在提交 Merge Request 之前，有可能有其他的组员已经合并了代码到目的分支上，而此时我们源分支的代码已经落后于目的分支，此时提交 Merge Request 就会引起[冲突](https://about.gitlab.com/2016/09/06/resolving-merge-conflicts-from-the-gitlab-ui/)。

所以，在**修改本地代码之前**，我们应该先检查一下目的分支的代码是否有更新，若有更新，则同步到本地代码，这是一个好的习惯。

## 配置远程仓库 URL

想要追踪目的分支的代码，首先需要在 SourceTree 中配置远程仓库 URL。打开  SourceTree，点击`工具栏->仓库->仓库设置`：

![](/assets/sourcetree-add-url.png)

点击添加按钮：

![](/assets/sourcetree-url-detail.png)

配置好目的分支的URL，即群组内项目的仓库地址，并为该远程仓库起一个名字。

点击确定完成添加。

点击工具栏 `拉取` 按钮，弹出对话框：

![](/assets/sourcetree-pull.png)

选择远程仓库（群组内项目的仓库）和要拉取的分支（目的分支），点击`确定`

[^1]: 类似于 Starteam review request，即提交代码评审.




