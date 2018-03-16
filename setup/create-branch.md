# 创建分支

灵活的分支是 Git 的一大优势。

在使用[工作流](/workflow/workflow.md)的方式下，对于同一个项目，需要创建多个不同功能的分支。比如，master 分支用于平常的开发，release 分支则用于版本发布。

对于一些不体现在主线的临时版本代码，也可以通过创建分支的方式储存这部分代码。

【注意】严禁开发人员在 Gitlab 上随意创建分支！创建分支需要由项目组长或相关成员操作。

打开 Gitlab web 界面，进入到项目主页：

![](/assets/new-branchs.png)

如图，点击左侧列表 `Repository` 选项，在下拉菜单中选择 `New branch` 选项：

![](/assets/create-branch.png)

打开创建分支页面，输入分支名称，选择要从哪个分支创建新分支，点击 `Create branch` 完成创建。

返回到项目主页，可以看到新分支创建成功：

![](/assets/show-branch.png)