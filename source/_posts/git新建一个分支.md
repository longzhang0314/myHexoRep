---
title: "Git新建一个分支"
date: 2019-09-04T16:12:53+08:00
draft: true
categories:
- 工具
---

参考：[https://www.cnblogs.com/kaerxifa/p/11045573.html](https://www.cnblogs.com/kaerxifa/p/11045573.html)

1. 进入本地git仓库目录，使用git branch指令，发现只有master分支

   ```shell
   git branch
   * master
   ```

2. 使用git branch 分支名来创建分支，创建完成后再次使用git branch查看，发现本地已经多出了一个新建的分支。

   ```shell
   输入：git branch 201909
   输入：git branch
   输出：201909
       *master 
   ```

3. 此时远程仓库并没有这个分支，我们需要使用git push origin 分支名 命令将本地修改推送到远程服务器上。

   ```shell
   输入：git push origin 201909
   ```

   

4. push完成后就可以在远程服务上看到新建的分支了（原本是1 branches）。

   ```shell
   2 branchches
   ```

