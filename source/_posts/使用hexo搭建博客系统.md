---
title: 使用Hexo + GitHub搭建博客系统
date: 2017-10-22 03:17:56
tags:
---
## 准备工作
1.进入用户目录~下, 新建一个文件夹a用于存放hexo文件
2.在GitHub上新建一个空的repo, repo的名称设置为用户名.github.io, 这个repo将用于让hexo部署博客

## 安装hexo
### 1.进入新建的文件夹, 运行以下命令安装hexo
    npm install -g hexo-cli

### 2.使用hexo生成一个子目录myBlog
    hexo init myBlog
    cd myBlog
    npm i

## 生成,配置和部署博客
### 1.生成和编辑一片博客
1. 使用命令: hexo new '博客名' 创建一篇博客. 这个命令会生成一个 .md 文件, 并返回一个路径, 就是我们的博客文件所在位置
    hexo new 第一篇博客

2. 使用 start 或 open(mac) 命令打开和编辑生成的博客文件
    start '博客文件的路径'

### 2.编辑网站配置
1. 返回到myBlog目录, 编辑网站配置文件 _config.yml
    start _config.yml

2. 修改以下配置:
+   title 修改为你想要的title
+   author 修改为博客的作者
+   type 修改为type: git (冒号后面应有一个空格)
+   type的下一行添加 repo: 仓库地址 (用户名.github.io的仓库地址)

### 3.安装git部署插件, 部署博客
    npm install hexo-deployer-git --save
    hexo deploy

### 4.进入博客所在的仓库, 打开GitHub Pages, 点击链接进入刚刚创建的博客.

### 5.更换博客的主题
1. 在这个页面: https://github.com/hexojs/hexo/wiki/Themes 有主题合集.
2. 选择并通过git clone命令克隆一个主题到myBlog文件夹的themes文件夹
3. 配置 _config.yml文件, 将 theme: 更改为 theme: 你使用的主题名
4. 使用一下命令生成博客文件
    hexo generate
5. 部署博客
    hexo deploy

### 6.至此, 使用Hexo在github上搭建博客就已经完成, 刷新博客页面.

## 博客代码的备份
1. 在GitHub上新建一个仓库, 将生成博客的代码备份到GitHub. 
2. 每次编辑完博客, 还要 add/ commit /push, 将更改提交到GitHub仓库.