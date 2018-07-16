# 克隆项目

## 两种协议

gitlab 支持两种协议克隆代码和身份认证，分别是`SSH`协议和`HTTP`协议。SSH协议需要在本地和 gitlab 上分别配置SSH密钥，简单起见，推荐使用HTTP协议对代码进行克隆，其认证方式将使用 gitlab 账户密码进行认证。

## 复制远程仓库地址

打开 gitlab 项目主页：

![](/assets/clone.png)

选择 HTTP 协议，点击仓库地址右侧按钮，复制仓库地址。

## 克隆代码到本地

打开 SourceTree，按下 `Ctrl + N` 快捷键，打开克隆仓库页面：

![](/assets/sourcetree-clone.png)

输入上述步骤复制的仓库地址，选择本地克隆仓库位置，点击 `克隆` 按钮，完成克隆。

> **[info] 注意**
>
> git clone 默认会把远程仓库整个给clone下来，但只会在本地默认创建一个master分支。可以使用`git checkout -t`命令在本地建立一个和远程分支名字一样的分支，该分支会追踪同名的远程分支。比如：需要切换到JDBC4.0分支，执行`git checkout -t origin/JDBC4.0`