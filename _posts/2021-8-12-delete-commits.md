---
title: 如何删除commits
date: 2021-8-12 8:56:00
categories:
- IT
tags:
---

提交到GitHub上的项目乱糟糟的，如何删除这些提交，形成一个全新的仓库呢？

* 新建 一个空白分支

  `git checkout --orphan latest_branch`

* 添加所有文件

  `git add -A`

* 提交

  `git commit -am "."`

* 强制删除旧的分支，如果是master

  `git branch -D master`

* 将当前分支重命名为master

  `git branch -m master`

* 强制推送到远程仓库

  `git push -f origin master`

### 参考资料

[git仓库删除所有提交历史记录，成为一个干净的新仓库](https://blog.csdn.net/yc1022/article/details/56487680)

