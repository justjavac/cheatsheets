---
title: Git branches
category: Git
layout: 2017/sheet
updated: 2017-09-20
---

## Working with branches
{: .-three-column}

### 创建

```bash
git checkout -b $branchname
git push origin $branchname --set-upstream
```

本地创建一个新的分支然后提交到远端.

### 获取远端分支

```bash
git fetch origin
git checkout --track origin/$branchname
```

获取一个远端分支.

### 删除本地的远程跟踪分支

```bash
git remote prune origin
```

删除本地副本中的origin / *分支。不影响远端。

### 列出已经合并的分支。

```bash
git branch -a --merged
```

列出已经合并到当前的分支。

### 删除远端分支

```bash
git push origin :$branchname
```

也适用于 tags！

### 获取当前的引用

```bash
git show-ref HEAD -s
```
