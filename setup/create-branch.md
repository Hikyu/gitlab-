# 创建分支

灵活的分支是 Git 的一大优势。

在使用[工作流](/workflow/workflow.md)的方式下，对于同一个项目，需要创建多个不同功能的分支。比如，master 分支用于平常的开发，release 分支则用于版本发布。

对于一些不体现在主线的临时版本代码，也可以通过创建分支的方式储存这部分代码。

> **[danger] 注意**
>
> 如有需要，开发人员可以在 gitlab 上创建分支并进行推送，但不允许开发人员在gitlab 上直接对**任何分支**的代码进行编辑和删除，也不允许开发人员对项目的[保护分支](/config/protected-branch.md)进行推送和删除。

打开 Gitlab，进入到项目主页：

![](/assets/new-branchs.png)

如图，点击左侧列表 `Repository` 选项，在下拉菜单中选择 `New branch` 选项：

![](/assets/create-branch.png)

打开创建分支页面，输入分支名称，选择要从哪个分支创建新分支，点击 `Create branch` 完成创建。

返回到项目主页，可以看到新分支创建成功：

![](/assets/show-branch.png)

> **[info] 注意**
>
> 创建分支不仅可以在 gitlab 中显示创建，如同上文提到的那样；同样的，gitlab 上的分支也可以`隐式`地被创建：当你选择从本地推送一个 gitlab 上【并不存在】的分支时，gitlab会自动创建一个同名分支。