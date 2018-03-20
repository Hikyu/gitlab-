# 解决冲突

在拉取远程代码时，会自动将远端代码合并到当前分支。这个时候，如果本地和远端都针对同一份文件进行了修改，那么合并过程会发生冲突。

## 冲突产生

![](/assets/sourcetree-conflict.png)

发现提示有“未更改的提交”，并且有一部分分支显示为灰色，说明合并没有顺利结束，遇到了冲突。

切换到“文件状态”标签页：

![](/assets/sourcetree-conflict-detail.png)

发现代码文件 test.txt 被标注了感叹号，在右侧文本区域可以看到当前 test.txt的内容：

```
<<<<<<<< HEAD 到 ========== 之间的内容为 本地代码；
 ============ 到 >>>>>>>>>> 之间的内容为 远程仓库的代码；
```

这两部分内容发生了冲突，即在你修改本地代码的同时，fuqiuying同样修改了同一行的代码，并提交到了远程服务器。

此时你需要做的，就是解决这行代码的冲突，选择一方的修改，或者双方的修改都保留。

## 解决冲突

在解决代码冲突之前，我们需要设置好第三方工具帮助我们处理这种情况：

![](/assets/sourcetree-mergetool.png)

合并工具选择 BeyondCompare\(首先需要在本地安装BeyondCompare，安装包位于 \192.168.1.63 常用软件\)或其他你认为合适的工具。

点击确定保存修改。

在文件状态 标签页，右键发生冲突的文件 `test.txt->解决冲突->打开外部合并工具`，sourcetree会自动打开BeyondCompare工具：

![](/assets/beyondcompare-merge.png)

![](/assets/sourcetree-mergetool1.png)

我们选择保留了远程仓库上的最新代码和本地修改的代码，点击按钮进行保存，确认该文件冲突解决完毕后，点击关闭按钮退出BeyondCompare。

![](/assets/sourcetree-merge-complete.png)

从上图中可以看到，test.txt的冲突部分已经被修改。

test.txt.org文件则是解决冲突前的文件备份，确认合并结束后可以删除\(如果不想自动产生该文件，设置 `git config --global mergetool.keepBackup false`\)。

所有的冲突文件都解决完毕之后，点击`提交`按钮，完成此次合并。

切换到 `日志/历史`标签页，发现合并完成，建立了新的提交：

![](/assets/source-merge-complete1.png)

