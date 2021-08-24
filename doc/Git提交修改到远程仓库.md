# 提交修改到仓库
使用`git push`命令,将已经`commit`的修改提交到远程仓库，本命令有两个参数：
+ 远程链接名,也就是通过`remote add`添加的远程仓库名字 如 `origin`
+ 仓库的分支名，如 `main`

连在一起就是:
```
git push origin main
```

# 重命名远程分支
分为三步，第一步是先删除远程的分支，第二步是重命名本地的分支名字，第三步将重命名的分支提交到远程仓库，
+ 删除远程分支
    ```
    git branch -r # 产看远程分支名
    
    # 删除远程分支
    git push origin :remoteBranchName  #删除远程分支,方法1
    git push --delete origin :remoteBranchName #方法2
    ```
+ 重命名本地分支
    ```
    git branch -l # 查看本地分支名

    # 将本地的branchName重命名为新的newBranchName
    git branch -m branchName newBranchName
    ```
+ 提交命名的修改
    ```
    git push origin newBranchName
    ```
通过以上的命令就可以创建新的分支。那么将修改提交到新的分支就只要用`push`命令就行了。
```
git push origin newBranchName
```
这样就只会提交到新的分支，而不会提交到旧的分支

