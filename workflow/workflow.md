# 工作流

Git 作为一个源码管理系统，不可避免涉及到多人协作。

协作必须有一个规范的工作流程，让大家有效地合作，使得项目井井有条地发展下去。"工作流程"在英语里，叫做"workflow"或者"flow"，原意是水流，比喻项目像水流那样，顺畅、自然地向前流动，不会发生冲击、对撞、甚至漩涡。

有三种使用比较广泛的[工作流](https://docs.gitlab.com/ce/workflow/gitlab_flow.html)

- Git flow
- Github flow
- Gitlab flow

结合神通的实际情况，选择 Gitlab flow 作为日常使用的工作流：

![](/assets/workflow.png)

其中 Master 分支为开发分支，Production 分支为发布分支（根据实际情况，开发分支可能有**多个**，但发布分支只有**一个**）。Master 分支为 Production 分支的上游，只有 Master 分支的代码变化了，才可以应用到 Production 分支。

以平时开发为例：

**日常开发：**

- 组内成员反复提交 [Merge Request](/review/basis.md)，修改 Bug 或增加功能。

**发布版本：**   

- 到了发布日，项目组长将 Master 分支的代码合并到 Production 分支；

- 发布系统拉取 Production 代码进行编译发布。