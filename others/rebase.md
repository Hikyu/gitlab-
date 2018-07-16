# 变基

在 Git 中整合来自不同分支的修改主要有两种方法：merge 以及 rebase。

假设我们有两个分支 master 和 experiment，并在这两个分支上分别进行了提交：

![](/assets/basic-rebase-1.png)

现在我们希望把 experiment 上面的修改合并到 master 上去：

- 执行 merge 命令。 它会把两个分支的最新快照（C3 和 C4）以及二者最近的共同祖先（C2）进行三方合并，合并的结果是生成一个新的快照（合并提交）。

  ```
  git checkout master 
  git merge experiment
  ```
  
  ![](/assets/basic-rebase-2.png)
  
- 还有一种合并方法：变基，将提交到 experiment 分支上的所有修改都移至 master 分支上：提取在 C4 中引入的修改，然后在 C3 的基础上应用一次：
  
  ```
  git checkout experiment
  git rebase master
  ```
  
  ![](/assets/basic-rebase-3.png)
  
  它的原理是首先找到这两个分支（即当前分支 experiment、变基操作的目标基底分支 master）的最近共同祖先 C2，然后对比当前分支相对于该祖先的【历次提交】，提取相应的修改并存为临时文件，然后将当前分支指向目标基底 C3, 最后以此将之前另存为临时文件的修改【依序应用】。

  所以，变基的过程中，历次提交对于同一文件的修改可能产生冲突，如果遇到冲突，则[解决冲突](/others/merge-conflict.md)，然后执行：
  
  ```
  git add .
  git rebase --continue
  ```
  
  如果想要跳过这个 patch，则执行 git rebase --skip。意味着这次提交将被抛弃。

  直到所有 patch 应用完毕。

  现在回到 master 分支，进行一次 fast-forward 合并。
  
  ```
  git checkout master
  git merge experiment
  ```
  
  ![](/assets/basic-rebase-4.png)
  
  此时，C4’ 指向的快照就和上面使用 merge 命令的例子中 C5 指向的快照一模一样了。变基的目的是为了确保在向远程分支推送时能保持提交历史的整洁,提交历史是一条直线没有分叉。
