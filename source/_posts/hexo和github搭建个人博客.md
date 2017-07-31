---
title: hexo和github搭建个人博客 
date: 2017-07-26 18:39:04
tags: 博客
comments: false
---

[参照博客](http://baixin.io/2015/08/HEXO%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/)
#### 本地搭建
1. 工具  
  hexo 和 git  Node.js
2. 申请github账号  
3. git 和Node.js 安装好后可运行 如下代码安装hexo
> $ sudo npm install -g hexo  
4. 先创建文件夹在执行如下操作 （文件夹右键：git bash here） 
> $ hexo init
5. 生成静态页面
> $ hexo g
6. 本地启用服务  
> $ hexo server -p 10015  

其中10015为端口（我自己电脑4000端口已被占用），提示启动成功，浏览器输入：http://localhost:10015/ 就可看到原始页面。  
#### github部署
1. github 上建立远程仓库：自己用户名.github.io，如：sicheng1991.github.io
2. 在config.yml根目录下的 config.yml文件中修改如下：  
>deploy:
  type: git  
  repository:https://github.com/sicheng1991/sicheng1991.github.io.git  
  branch: master
3. 执行命令将项目部署到github
> npm install hexo-deployer-git --save
4. 执行命令部署  
 > hexo deploy
5. 浏览器打开 http://sicheng1991.github.io/ 
6. 如修改了东西如下操作,来重新部署
> hexo clean  
hexo generate  
hexo deploy  

7.常用命令：
> hexo new "postName" #新建文章  
hexo new page "pageName" #新建页面  
hexo generate #生成静态页面至public目录  
hexo server -p 4000 #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）  
hexo deploy #将.deploy目录部署到GitHub  
hexo help  #查看帮助  
hexo version  #查看Hexo的版本  

7 .hexo主题：[地址](https://github.com/hexojs/hexo/wiki/Themes)
 使用： 下载主题，解压后放在，themes文件夹下，再根目录下的_config.yml中将主题改未自己的主题目录，如：theme: moretwo