---
title: Git常用命令
abbrlink: 423abe9e
date: 2017-05-05 23:22:37
tags:
- git
- command
- 指令集
---

> 想玩好Github开源项目，不懂Git不行，所以这里记录下，在使用中，用到的一些命令，方便自己以后去反复记忆，同时也希望能帮到一些朋友。
主要的命令记住，方便操作，其余的会查询即可。
以实际例子来说明，我在实际使用中用到的一些命令

## Getting and Creating Projects
```bash
# 创建一个空的Git仓库，或者对于已存在的仓库，进行重初始化
$ git init 

# 配置
$ git config [--global] user.name "alanhg"
$ git config [--global] user.email "i@xx.x"

```
## Clone

```
# clone仓库
$ git clone -b source git@github.com:heqiang421/heqiang421.github.io.git

```
## Basic Snapshotting

### Add
```
$ git add .

```

### Commit
```
$ git commit -m 'message'
$ git push

# 修改最新提交

```
### Reset

```
# 撤销暂存区提交，回退一个版本
$ git reset HEAD^

# 恢复到一个已知状态
# git reset --hard
```

#### rm
```
# 停止追踪指定文件，但该文件会保留在工作区
$ git rm --cached [file]

# 删除工作区文件，并且将这次删除放入暂存区
$ git rm [file1] [file2] ...

```
## Branching and Merging

### Branch
```

# 查看本地分支
$ git branch 

# 删除本地分支dev
$ git branch -d dev

# 基于之前的某个 Commit 新开分支
$ git branch <branchName> <sha1-of-commit>

# 建立追踪关系，在现有分支与指定的远程分支之间
$ git branch --set-upstream [branch] [remote-branch]

# 修改对应的远程分支
$ git branch -u origin/dev

# 本地分支重命名
$ git branch (-m | -M) [<oldbranch>] <newbranch>


```

### Checkout
```
# 切换本地分支
$ git checkout <branchName>

# 切换分支并将远程分支修改为dev
$ git checkout dev --track origin/dev
```

## Sharing and Updating Projects


### pull

```
# 拉取最新代码
$ git pull

```

### push

```
# 删除远程分支
$ git push origin --delete <branchName>

# 推送到主干
$ git push origin <branchName>

```

### remote

```
# 列出远程仓库信息,包括网址
$ git remote -v

# 添加远程仓库,支持多远程仓库地址
$ git remote add [shortname] [url]

# 修改远程仓库对应的网址
$ git remote set-url origin git@github.com:username/repo.git

```

## 常见问题

### Git: fatal: Pathspec is in submodule

 解决办法：
 
  ```
   git rm --cached directory
   git add directory
  ```

### You have not concluded your merge (MERGE_HEAD exists).

```
$ git reset --merge

```
### 每次push都提示输入用户名及密码
![](http://static.ttgg.shop/2018-07-07-031614.png)
出现这个的原因是远程库我们是以HTTPS形式设定的，修改为SSH即可
```
# 查看远程库协议
$ git remote -v

$ git remote rm origin 
$ git remote add origin git@github.com:alanhg/alanhg.github.io.git

```

### Pull is not possible because you have unmerged files.
这是因为pull拉取上游新代码时，会进行merge，有未merge的文件就会提示以上信息，要么处理了冲突`git add -u, git commit`,要么放弃本地的文件修改，执行`git reset --hard FETCH_HEAD`

### 分支部分提交导入其他分支
有时我们需要将一个分支的部分提交导入到另一个分支【这些提交在该分支下，可能不见得是最新的紧挨着的几次提交】，这个时候就可以使用cherry pick解决
我们记录下来需要导入的commitID,checkout到目标分支，执行'git cherry-pick commitID'，注意可能会有冲突，跟MR一样处理即可。

注意比如我们想导入N次提交，那么最终cherry pick过来后也会是4次提交。


## 辅助资料

+ [常用 Git 命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
+ [Git手册](https://git-scm.com/docs)
