# 修改代码并提交评审

合并请求[^1]（Merge Request）是在 GitLab 上进行代码协作的基础。合并请求，即：请求将一个分支合并到另一个分支。

在[工作流](/workflow/workflow.md)章节中，已经列举了日常修改代码的流程，本章节详细说明一下修改代码并提交评审的细节：

## 修改代码

假定此时我们已经完成 [Fork 项目到自己的命名空间](/setup/fork.md)，同时[克隆代码到本地](/克隆)的工作，并且已经[配置好了.ignore文件](/others/ignore.md)。

### 修改并提交代码

打开 SourceTree：

![](/assets/sourcetree.png)

这是我们本地的代码，当前的工作目录是“干净”的，没有进行任何修改。

在编辑器或IDE中对本地代码进行修改，可以是修复一个 BUG，或者新增一个功能。再次打开 SourceTree：

![](/assets/sourcetree-modify.png)

在 `未暂存的文件` 一栏中，能够看到已经修改但还未暂存的文件。右侧是修改的具体细节。

选择此次修改需要提交的文件，点击 `暂存所选`：

![](/assets/sourcetree-commit.png)

可以看到，文件已经被暂存。确定无误后，在下方文本框中输入提交信息，如修改了哪些  BUG 等。点击 `提交` 按钮，完成一次本地提交。

上述步骤可反复进行，即进行多次本地提交。

### 推送代码到远程仓库

确定代码修改完成，并经过测试后，点击 SourceTree 下方 `日志/历史` 按钮：

![](/assets/sourcetree-push.png)

点击工具栏 `推送` 按钮，弹出对话框：

![](/assets/sourcetree-push1.png)

点击 `推送` 按钮，将更改推送到远程仓库。

## 提交评审

打开 Gitlab，进入到**自己命名空间**下的项目主页，点击左侧列表 `Merge Requests`，点击 `New merge request`：

![](/assets/gitlab-mr.png)

选好源分支和目的分支后，点击 `Compare branches and continue`：

![](/assets/gitlab-mr-content.png)

在 Merge Request 提交页面填写 Merge Request 的详细信息。

![](/assets/gitlab-mr-submit.png)

页面下方可以再一次浏览此次修改的详细内容。确认无误后点击 `Submit merge request` 按钮，提交 Merge Request。


[^1]: 类似于 Starteam review request，即提交代码评审.

