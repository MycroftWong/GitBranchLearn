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
其中`*`表示当前分支


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