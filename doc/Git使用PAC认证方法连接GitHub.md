# Git配置

当下载完Git，安装好以后，需要对git进行一个基本的配置。才能完成跟GitHub的交互。
## 新建一个仓库
去GitHub新建一个仓库，如[HelloWorld](https://github.com/Jeffrey-D/HelloWorld.git)
然后复制仓库的链接，到安装好Git客户端的命令行执行`clone`命令。
```
git clone https://github.com/Jeffrey-D/HelloWorld.git
```
## Config基本配置
进入此项目，执行以下命令，并做一些基本的配置

```shell
cd HelloWorld  # 进入项目目录

# 个人信息配置
git config --global user.name "ishland"
git config --global user.email "example@example.com"
```
上面配置了提交的用户名和邮箱。**注意，个人邮箱要与GitHub个人信息界面的邮箱列表中的邮箱一致**，然后对项目做一些修改，比如修改[README](../README.md)等等。输入以下命令提交修改。
```shell
git add . # 将修改做一次stage，也就是记录

# 对上面的add做一次提交，也就是一次快照，使用-m 指定本次的提交说明信息
# 此时只是给你的修改"拍了照片"，只是记录了下来，并没有提交你的GitHub仓库上。
git commit -m "update readme" 

# 提交到远程仓库，直接使用git push
git push
```
上面可以直接使用git push的原因是这是clone的项目，在项目的根目录下已经存放好了一个隐藏文件，内包含了项目的信息，所以使用git push会直接提交clone时的默认的分支，也就是main。

首次使用git push时，会让你输入PAC(`Personal Access Token`)密钥,在个人设置setting->developer settings->personal access token 下可以创建生成，每个PAC都只会在创建的时候可见，所以第一次创建的时候最好记住。


## Origin修改
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

