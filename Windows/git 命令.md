## git 命令

查看所有信息

```
//显示有变更的文件
 git status
 
 //显示当前分支的版本历史
  git log

```

分支

```
//列出所有本地分支
git branch

//列出所有远程分支
git branch -r

//列出所有本地分支和远程分支
git branch -a
```

增加/删除文件

```
//添加指定文件到暂存区
 git add [file1] [file2] ...
 
//添加指定目录到暂存区，包括子目录
git add [dir]

//加当前目录的所有文件到暂存区
git add .

//删除工作区文件，并且将这次删除放入暂存区
git rm [file1] [file2] ...
```

代码提交

```
//提交暂存区到仓库区
git commit -m [message]

//提交暂存区的指定文件到仓库区
git commit [file1] [file2] ... -m [message]

//提交工作区自上次commit之后的变化，直接到仓库区
git commit -a


```

远程同步

```
//下载远程仓库的所有变动
git fetch [remote]

//显示所有远程仓库
git remote -v

//取回远程仓库的变化，并与本地分支合并
git pull [remote] [branch]

//上传本地指定分支到远程仓库
git push [remote] [branch]


```

