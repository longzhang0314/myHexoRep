---
title: "hexo搭建"
date: 2019-09-05T10:07:01+08:00
draft: true
categories:
- 工具
---

#### 1.安装依赖环境<br>
- 需要提前安装git，并拥有一个github账号。
- 安装Nodejs,npm
- node -v #查看node版本
- npm -v #查看npm版本
- npm install -g cnpm -- registry=http://registry.npm.taobao.org #安装淘宝的cnpm 管理器
- cnpm -v #查看cnpm版本
- cnpm install -g hexo-cli #安装hexo框架
- hexo -v #查看hexo版本
---
#### 2.安装本地博客<br>
- mkdir blog #创建blog目录
- cd blog #进入blog目录
- sudo hexo init #生成博客 初始化博客
- hexo s #启动本地博客服务
http://localhost:4000/ #本地访问地址
- hexo n "我的第一篇文章" #创建新的文章

#### 3.发布到github<br>
- 返回blog目录
- hexo clean #清理
- hexo g #生成
- #Github创建一个新的仓库 YourGithubName.github.io
- cnpm install --save hexo-deployer-git #在blog目录下安装git部署插件
- 配置_config.yml
- Deployment
- Docs: https://hexo.io/docs/deployment.html

- 内容
```java
deploy:
  type: git
  repo: https://github.com/YourGithubName/YourGithubName.github.io.git
  branch: master
```
- hexo d #部署到Github仓库里
- https://YourGithubName.github.io/ #访问这个地址可以查看博客

#### 4.个性化主题<br>

- git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia #下载yilia主题到本地
- 修改hexo根目录下的 _config.yml 文件 ： theme: yilia

#### 5. 每次重新发布<br>

- hexo c #清理一下
- hexo g #生成
- hexo d #部署到远程Github仓库
- https://YourGithubName.github.io/ #查看博客



