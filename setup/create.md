# 创建账户

## 生成 SSH 密钥

【注意】以下操作需要在自己的机器上安装 [Git](https://git-scm.com/)，默认已经安装。

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

## 注册 Gitlab 账户

访问 Gitlab web 登录注册页面 [192.168.1.101:8899](http://192.168.1.170:8899/users/sign_in)：

![](/assets/register.png)

【注意】`Email` 须填写自己的**外网邮箱账号**！

## 配置 Gitlab SSH Key

注册成功后，页面自动跳转到个人账户页面：

![](/assets/settings.png)

如上图所示，点击 `Settings` 进入个人账户设置页面，点击页面左侧 `SSH keys` 进入 SSH keys 管理页面：

![](/assets/add-sshkey.png)

将前面步骤中复制的 id_rsa.pub 的内容粘贴到 `Key` 文本框，同时在 `Title` 文本框中为 Key 起一个名字(任意)，最后点击 `Add key` 按钮，完成配置。





