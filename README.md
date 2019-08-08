# 这是一个学习git分支的Demo

没有实际的代码，只有用于区分分支的一些文件


## 一、创建工程、分享到github，创建分支

时间：2019年8月8日15:30:49

### 用到的命令 
```
-- 创建分支
git branch [branch-name]
-- 切换分支
git checkout [branch-name]

-- 查看本地分支
git branch

-- 查看远程分支
git branch -r

-- 查看所有分支
git branch -a

-- 删除分支
git branch -d [branch-name]
```

### 实际操作
1. 创建`dev`分支
`git branch dev`
2. 切换到`dev`分支
`git checkout dev`
3. 查看当前分支
```
$ git branch -a
* dev
  master
  remotes/origin/master
```
可以看到所有的分支：本地`dev`, `master`, 远程`remotes/origin/master`，其中`*`表示当前分支


## 二、将本地分支项目提交到本地主分支

时间：2019年8月8日15:34:53

### 用到的命令 
```
-- 查看当前状态
git status
-- 添加文件
git add [file-name]
-- 提交
git commit -m "comment info"
```

### 实际操作
1. 查看当前状态
```
$ git status
On branch dev
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   .idea/vcs.xml

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md
```
可以看到`Android Studio`自动创建了一个`.idea/vcs.xml`文件，等待提交，`README.md`文件修改过，等待添加、提交

2. 添加文件
`git add README.md`
添加`README.md`

3. 查看状态
```
$ git status
On branch dev
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   .idea/vcs.xml
        modified:   README.md
```
可以看到上述两个文件等待提交

4. 提交
```
$ git commit -m "测试提交dev分支"
[dev 7c5254a] 测试提交dev分支
 2 files changed, 59 insertions(+)
 create mode 100644 .idea/vcs.xml
```
提交成功

## 三、合并分支

### 用到的命令
```
-- 合并分支
git merge [branch-name]
```

### 实际操作

1. 切换到主分支
```
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```

2. 合并分支
```
$ git merge dev
Updating 57c8d40..1e0b9f7
Fast-forward
 .idea/misc.xml |  2 +-
 .idea/vcs.xml  |  6 ++++
 README.md      | 97 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 3 files changed, 104 insertions(+), 1 deletion(-)
 create mode 100644 .idea/vcs.xml
```
这就将`dev`上修改的结果，合并到了`master`

3. 查看状态
```
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
可以看到我在`dev`上的两次提交，也显示在了`master`中，并且查看文件，说明合并成功

## 四、提交本地分支到远程分支

### 用到的命令
```
-- 创建远程分支，并绑定本地分支推流
git push --set-upstream origin/[remote-branch-name] [local-branch-name]

-- 创建并提交远程分支（若没有远程分支，则会自动创建）
git push origin [local-branch-name]:[remote-branch-name]
```

### 实际操作
1. 查看当前分支
```
$ git branch -a
  dev
* master
  remotes/origin/master
```
可以看到所有的分支，当前所在分支是`master`

2. 创建远程分支`dev`
```
$ git push --set-upstream origin/dev master
```
创建时，输入账号密码，创建并提交成功
