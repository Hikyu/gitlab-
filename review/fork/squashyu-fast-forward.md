# Squash 与 Fast-forward

## Squash

由于提交的 Merge Request 中可能包含有多个提交，这些提交都是开发人员在本地进行的提交。Merge Request被评审人打回，开发人员再次修改代码并push时，也会生成新的提交。

上面提到的这些零散的提交不一定与此次 Merge Request 要解决的问题相关，有些甚至是冗余的。为了做到"一个提交解决一个问题"，在合并 Merge Request 之前，需要对 Merge Request 中的提交进行一次压缩（squash），【将多个commit压缩为一个commit】。

![](/assets/mr-commits.png)

> **[info] 注意**
>
> Gitlab EE中提供了Squash这个功能，CE版本并未支持。
> 通过修改源码，现已将该功能移植到了我们正在使用的Gitlab CE版本中。
> 目前，所有Merge Request默认都会在合并前进行一次Squash。

## Fast-forward

Gitlab 在合并 Merge Request 时，默认使用了git的Merge功能：

![](/assets/mr-merge.png)

可以看到，由临时分支Merge到开发分支，会形成一个合并提交，而不是形成线性的提交历史。当多人协作，同时发起多个合并操作时，提交历史会变得混乱不堪：

![](/assets/mess-commits.jpg)

为了减少合并提交的干扰，让提交历史清晰易懂，可以使用【Fast-forward】这一功能。

如果待合并的分支在当前分支的下游，也就是说没有分叉时，会发生快速合并：

![](/assets/fast-forward.gif)

在gitlab上为某个项目开启Fast-forward：

![](/assets/gitlab-fast-foreard.png)

开启此功能后，该项目所有的 Merge request 在合并时都将先检测此次合并是否可以Fast-forward，若在合并之前目标分支已经有新的提交了，gitlab会阻止此次合并。

此时，需要开发人员在本地对源分支执行【[变基](/others/rebase.md)】，然后再次push && 合并代码。