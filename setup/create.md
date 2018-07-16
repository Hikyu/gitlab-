# 创建账户

## 注册 Gitlab 账户

> **[danger] 注意**
>
> 研发部门和测试部门成员的 Gitlab 账户已注册完毕，用户名为姓名拼音，密码默认为12345678。直接登录即可。
>
> 用户`Email` 统一为自己的**内网邮箱账号**！
>
> 为了安全和管理方便起见，已经关闭gitlab的注册功能。如需注册新账户，请联系管理员。
>
> ---
>
>下文【生成 SSH 密钥】和【配置 Gitlab SSH Key】是可选内容，主要用于使用ssh协议克隆代码和身份认证。
>
>在gitlab中已经关闭了ssh协议，建议使用http协议克隆代码。故以下操作可省略。

## 生成 SSH 密钥

> **[info] 注意**
>
> 以下操作需要在自己的机器上安装 [Git](https://git-scm.com/)，默认已经安装。

在任意文件夹空白处，右键，选择 `Git GUI Here`：

![](/assets/gitgui.png)

弹出 `Git Gui` 程序框：

![](/assets/show-ssh.png)

选择 Help->Show SSH Key

如果未检测到已经存在 SSH 密钥，则点击 `Generate Key` 生成一个：

 ![](/assets/generate-ssh.png) 
 
设置 SSH 密钥的密码，点击 `OK` 按钮，会再次弹出对话框，**再次输入相同密码**，点击 `OK` 即可：

![](/assets/copy-ssh.png)

此时 SSH 密钥已经生成并存储在 `~/.ssh` 目录下。点击 `Copy To Clipboard` 复制 `id_rsa.pub` 的内容。


## 配置 Gitlab SSH Key

注册成功后，页面自动跳转到个人账户页面：

![](/assets/settings.png)

如上图所示，点击 `Settings` 进入个人账户设置页面，点击页面左侧 `SSH keys` 进入 SSH keys 管理页面：

![](/assets/add-sshkey.png)

将前面步骤中复制的 id_rsa.pub 的内容粘贴到 `Key` 文本框，同时在 `Title` 文本框中为 Key 起(任意)一个名字，最后点击 `Add key` 按钮，完成配置。

至此，你已经创建好了 Gitlab 账户，并成功配置好自己机器的 SSH 密钥。
