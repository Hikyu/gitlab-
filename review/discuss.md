# 查看评审并评论

## 评论评审

开发人员提交评审后，项目组长和被`@`到的组员都会收到邮件提醒。

打开 Gitlab，进入项目主页，点击左侧 `Merge Requests`，可以看到所有的 Merge Request：

![](/assets/gitlab-mr-all.png)

可以根据 Merge Request 的状态进行过滤，或者直接进行搜索。点击 Merge Request 标题查看 Merge Request：

![](/assets/gitlab-mr-show.png)

可以看到 Merge Request 的详细内容[^1]。在页面下方，`Changes` 标签页可以看到代码修改前后的变化。移动鼠标到代码行，点击行首的 :speech_balloon: 按钮，可以针对该行进行点评：

![](/assets/gitlab-mr-diss-inline.png)

每个组内成员都可以对提交的评审进行点评，并且所有的相关人员都会收到邮件提醒。

如果同意该评审的修改，组员可以点击 :+1: 表示自己赞同该评审的修改内容。

如果项目组长认为此次的 Merge Request 是多余的或者没有意义的，也可以点击 `Close merge request`关闭 Merge Request。

## 更新 Merge Request

提交评审的组员收到组长或其他人的评论之后，发现了自己代码中的问题，此时他需要更新 Merge Request。

只需以下操作：

1. 再次修改本地代码

2. 暂存修改并提交

3. 再次推送代码到远程仓库

Gitlab 会跟踪这条远程分支的变动，当代码再次推送到远程仓库后，Merge Request 状态**自动更新**，并发送邮件提醒所有相关人员。

> **[danger] 注意**
>
> 此时并不需要再次提交新的 Merge Request！

相关人员可以再次查看该 Merge Request，并做出评论。

以上过程可以进行多次。直到认为代码没有问题，评审通过。


[^1]: 对于没有 Merge 权限的人员，`Merge` 按钮是灰色不可点击的。