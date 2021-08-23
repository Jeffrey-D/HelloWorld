# Origin修改
正常情况下，`git push` 会有两个参数，分别是远程连接名和分支名。如 `git push origin main`,意思就是将修改提交到远程连接名为origin的main分支。

origin是给某个远程仓库的链接指定一个名字，可以使用命令行修改远程连接的名字
```
$ git remote -v
# 查看现有远程
> origin  https://github.com/OWNER/REPOSITORY.git (fetch)
> origin  https://github.com/OWNER/REPOSITORY.git (push)

$ git remote rename origin destination
# 将远程名称从 'origin' 更改为 'destination'

$ git remote -v
# 验证远程的新名称
> destination  https://github.com/OWNER/REPOSITORY.git (fetch)
> destination  https://github.com/OWNER/REPOSITORY.git (push)
```
origin所指定的远程链接也可以修改
```
$ git remote -v
> origin  git@github.com:USERNAME/REPOSITORY.git (fetch)
> origin  git@github.com:USERNAME/REPOSITORY.git (push)
$ git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
$ git remote -v
# Verify new remote URL
> origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
> origin  https://github.com/USERNAME/REPOSITORY.git (push)
```

# 远程仓库部分
前文描述了如何修改了本地指定的远程仓库的名字以及链接

