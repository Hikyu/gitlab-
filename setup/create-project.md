# 创建项目

Gitlab 支持创建项目，这里的项目对应 Starteam 中的视图，用于存放对应工程的代码文件。

项目成员可以将项目代码[克隆到本地](/setup/clone.md)，修改代码并[提交代码评审](/review/local-modify.md)。

> **[danger] 注意**
>
> 创建项目的工作必须由项目组长创建，严禁个人在Gitlab上创建项目！
> 创建某个项目时，必须指定其所在的群组。严禁在 Gitlab 根路径下创建项目！

## 创建项目

进入 Gitlab，点击工具栏 `Groups` 按钮：

![](/assets/new-group.png)

进入到项目对应的群组或子组，点击按钮 `New project`，进入创建项目页面：

![](/assets/create-project.png)

填写项目名称、项目描述并为项目设置可见性。

项目可见性分为三种：Private、Internal 和 Public，其含义与[群组](/setup/create-group.md)可见性相同。需要注意的是，群组下的项目的可见性只能比所属群组的可见性程度低，不得高于群组可见性。

点击 `Create project` 按钮完成创建。

## 初始化项目

### 复制远程仓库 URL

项目创建完成，页面自动跳转到项目主页：

![](/assets/copy-url.png)

页面中间显示了项目在 Gitlab 上仓库的地址，选择 `SSH` 协议，点击地址右侧复制按钮复制该URL。

### 初始化本地仓库

打开自己的电脑，进入项目工程代码根目录，比如：`D:\jdbc`。

若该项目已经是 Git 项目（根目录下有 .git 文件夹），则直接进行下一步，否则：

空白处右键，选择 `Git Bash Here`。

在打开的 shell 中输入 `git init`：

![](/assets/git-init.png)

此时，项目已经被成功初始化成为 Git 项目。

> **[warning] 注意**
>
> Git 项目初始化完毕，还应该[创建 .gitignore文件](/others/ignore.md)忽略那些不需要纳入版本管理的临时文件。

### 配置 SourceTree

为了简化我们使用 Git 的流程，降低使用难度，我们选择一款 [Git GUI](https://git-scm.com/download/gui/windows) 客户端来进行本地 Git 操作。在此，推荐使用 [SourceTree](https://www.sourcetreeapp.com/) 或 [TortoiseGit](https://tortoisegit.org/download/) 作为 GUI 客户端（篇幅有限，下面的操作以 SourceTree 为例）：

> SourceTree 是 Windows 和Mac OS X 下免费的 Git 和 Hg 客户端管理工具，同时也是Mercurial和Subversion版本控制系统工具。支持创建、克隆、提交、push、pull 和合并等操作。
SourceTree拥有一个精美简洁的界面，大大简化了开发者与代码库之间的Git操作方式，这对于那些不熟悉Git命令的开发者来说非常实用。

关于如何下载和安装配置 SourceTree，不再赘述。可以参考 [Source Tree 官方文档](https://confluence.atlassian.com/get-started-with-sourcetree)。

> **[warning] 注意**
>
> 安装完毕后，使用 SourceTree 之前需要注册一个 atlassian 账号进行授权，该注册过程可能**需要代理**。跳过 atlassian 账号授权，参考 [SourceTree 免登录跳过初始设置](https://www.cnblogs.com/xiofee/p/sourcetree_pass_initialization_setup.html)
> 

打开 SourceTree，点击工具栏 `工具` 按钮，选择 `添加SSH密钥`；

在弹出的文件选择对话框中，选择之前在[创建账户](/setup/create-project.md)中已经生成的SSH密钥 `id_rsa`，点击 `打开` 按钮，弹出命令行对话框，填入SSH密钥的密码，密钥配置成功。

### 导入项目，配置远程仓库地址

打开 SourceTree，按下 `Ctrl + O` 快捷键，在弹出的对话框中选择刚刚初始化完成的 Git 项目文件夹：

![](/assets/select-repo.png)

进入仓库之后，点击工具栏 `仓库` 按钮，选择 `仓库设置`：

![](/assets/repo-config.png)

点击 `添加` 按钮，配置远程仓库地址：

![](/assets/url-config.png)

远端名称：为远程仓库地址起一个别名

URL/路径：填入前面步骤中复制的远程仓库 URL

点击确定按钮，返回到仓库设置对话框，再次点击确定，添加远程仓库地址成功。

### 推送代码到远程仓库

![](/assets/commit.png)

如图，点击 `暂存所有` 按钮将文件暂存，在下方文本框中填写提交信息，点击 `提交` 按钮进行一次本地代码提交。

双击左侧 `分支->master`，查看此次提交：

![](/assets/show-commit.png)

点击 `推送` 按钮，弹出推送对话框：

![](/assets/push.png)

点击 `推送` 按钮，将代码推送到远程仓库。

再次打开 Gitlab，打开对应的项目进行查看：

![](/assets/show-remote.png)

发现本地代码已经成功推送到了远程仓库。

至此，项目的创建以及初始化工作完成。