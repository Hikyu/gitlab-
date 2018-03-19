# 创建群组

使用 [Gitlab 群组](https://docs.gitlab.com/ce/user/group/index.html) 功能，我们可以：

 - 为我们提供了将相关项目关联到一起的功能（相关项目在同一命名空间下），有利于项目划分
 
 - 可以一次性授予开发人员访问多个项目的权限
 
 - 可以一次性`@`组内全部成员，在阅读评审或讨论交流的时候，这一点非常有用
 
## 创建群组
 
进入 Gitlab web 页面，点击工具栏 `Groups` 按钮：

![](/assets/create-group.png)

点击 `New groups` 按钮，进入创建群组页面：

![](/assets/group-ok.png)

`Group path` 设置群组命名空间，所有属于该组项目的 URL 都将位于此命名空间下。

[`Visiblility Level`](https://docs.gitlab.com/ce/public_access/public_access.html) 设置了群组的可见性，有三个选项：

- Private：群组和群组中的项目仅对组内成员可见

- Internal：群组和群组中的 Internal 项目仅对已登录人员可见

- Public：群组和群组中的 Public 项目对任何人都可见

按实际情况进行选择，一般选择 `Private` 或 `Internal`。

点击 `Create groups` 完成创建。

## 创建子组

群组还支持创建子组。比如，天津 java 研发部负责的内容有：JDBC驱动、前台工具、DBStudio 和其他工具等。可以为这些模块创建子组：

![](/assets/subgroup.png)

比如，在 java 群组下创建 jdbc 子组：

![](/assets/create-subgroup.png)

与创建群组的过程基本一致，注意到 jdbc 子组的命名空间是在 java 群组下的。

## 添加成员

为群组添加成员，进入群组页面，点击左侧列表 `Members` 选项：

![](/assets/add-member.png)

选择要添加的成员，为成员分配相应的角（参考[角色与权限](/setup/permission.md)），同时设置过期时间，超过该时间则该成员被移出群组，不设置则**默认没有过期时间**。点击 `Add to group` 完成。

一旦将成员添加进组并分配了角色，则默认该成员对组内**所有项目**具有了该角色对应的权限。

若要为成员对组内**指定的项目**重新分配角色，可以将成员添加到具体的项目中再行分配。

> **[warning] 注意**
>
> 项目组长预先将群组建好，并在组内创建项目，然后添加成员。
