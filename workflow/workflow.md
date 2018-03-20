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

1. 项目组长将 Master 分支和 Production 分支设置为保护分支。只允许 Master 合并到这两个分支，不允许任何人推送到这两个分支；

2. 项目成员将项目代码 clone 到本地或拉取最新代码；

3. **从开发分支**创建临时分支并检出到新分支；

3. 针对需求或者 BUG，修改代码，推送新分支到远程仓库；

4. 发起 [Merge Request](/review/local-modify.md)，请求合并代码到 Master 分支（或其他分支）；

5. 项目组长评审代码，进行讨论，最终评审通过，代码被项目组长合并到 Master 分支；

6. 2-4 步反复进行；

7. 到了发布日，项目组长将 Master 分支的代码合并到 Production 分支；

8. 发布系统拉取 Production 代码进行编译发布。