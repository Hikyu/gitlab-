# 配置 .gitignore 文件

有些时候，必须把某些文件放到 Git 工作目录中，但又不能提交它们，比如编译代码生成的临时文件等等，每次 git status 都会显示Untracked files。如何让 Git 忽略这些文件，就需要配置 .gitignore 文件。

进入项目根目录（Git 工作目录），右键打开 `Git Bash Here`，输入命令：

```
touch .gitignore
```

就会在根目录下生成配置文件 .gitignore。

在配置该文件之前，先看一下忽略文件的规则：

1. 忽略操作系统自动生成的文件，比如缩略图等；

2. 忽略编译生成的中间文件、可执行文件等，也就是如果一个文件是通过另一个文件自动生成的，那自动生成的文件就没必要放进版本库，比如Java编译产生的.class文件；

3. 忽略你自己的带有敏感信息的配置文件，比如存放口令的配置文件。

配置语法：

```
以斜杠“/”开头表示目录；
以星号“*”通配多个字符；
以问号“?”通配单个字符
以方括号“[]”包含单个字符的匹配列表；
以叹号“!”表示不忽略(跟踪)匹配到的文件或目录；
```

示例：

```
# 忽略所有 .a 结尾的文件
*.a

# 但 lib.a 除外
!lib.a

# 仅仅忽略项目根目录下的 TODO 文件，不包括 subdir/TODO
/TODO

# 忽略 build/ 目录下的所有文件
build/

# 会忽略 doc/notes.txt 但不包括 doc/server/notes.txt
doc/notes.txt
```

配置好 .gitignore 文件后，需要将该文件提交到 Git ，方可生效：

```
git add .gitignore
git commit -m 'add .gitignore'
```

详细使用参考 [https://git-scm.com/docs/gitignore](https://git-scm.com/docs/gitignore)

