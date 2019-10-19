---
title: "Git新建一个分支"
date: 2019-09-04T16:12:53+08:00
draft: true
---

参考：[https://www.cnblogs.com/kaerxifa/p/11045573.html](https://www.cnblogs.com/kaerxifa/p/11045573.html)

1. 进入本地git仓库目录，使用git branch指令，发现只有master分支

   ![git新建一个分支_1](http://pxjmdt63v.bkt.clouddn.com/images/blog/hugo/git%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%88%86%E6%94%AF/git%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%88%86%E6%94%AF_1.png)

2. 使用git branch 分支名来创建分支，创建完成后再次使用git branch查看，发现本地已经多出了一个新建的分支。

![git新建一个分支_2](http://pxjmdt63v.bkt.clouddn.com/images/blog/hugo/git%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%88%86%E6%94%AF/git%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%88%86%E6%94%AF_2.png)

3. 此时远程仓库并没有这个分支，我们需要使用git push origin 分支名 命令将本地修改推送到远程服务器上。

   ![git新建一个分支_3](http://pxjmdt63v.bkt.clouddn.com/images/blog/hugo/git%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%88%86%E6%94%AF/git%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%88%86%E6%94%AF_3.png)

4. push完成后就可以在远程服务上看到新建的分支了（原本是1 branches）。

   ![git新建一个分支_4](http://pxjmdt63v.bkt.clouddn.com/images/blog/hugo/git%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%88%86%E6%94%AF/git%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%88%86%E6%94%AF_4.png)

