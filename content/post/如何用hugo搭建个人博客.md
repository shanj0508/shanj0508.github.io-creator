---
title: "如何用 hugo 搭建个人博客"
date: 2020-01-29T10:42:21+08:00
draft: false
---

# 如何用hugo搭建个人博客

## 安装Hugo
Hugo是go语言实现的博客生成器，js语言实现的博客生成器是Hexo(难用，不推荐)。

官方教程：https://gohugo.io/getting-started/installing

### Mac安装方式
输入命令：
* brew install hugo
* hugo version
  
### Windows安装方式
1. 访问Hugo releases页面：https://github.com/gohugoio/hugo/releases，下载hugo_xxx_Windows-64bit.zip
2. 解压，把hugo.exe放到D:\self-software\hugo\hugo.exe目录下
3. 把D:\self-software\hugo\添加到PATH
4. 重启终端，运行hugo version查看版本
   
## 快速搭建本地博客
1. 访问Hugo官网：https://gohugo.io/
2. 在官网首页点击【Quick Start】按钮快速开始
3. 按照Hugo教程完成步骤2-7(步骤1我们上面已经完成了)

   
   * hugo new site quickstart --建立新网站
   * cd quickstart
   * git init  --初始化
   * git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke  --添加主题
   * echo 'theme = "ananke"' >> config.toml  --将主题添加到站点配置中
   * hugo new posts/my-first-post.md  --添加新文件（博客文章）
```
    ---
    title: "My First Post"
    date: 2019-03-26T08:47:11+01:00
    draft: true
    ---
    这是我的第一篇博客文章
```
   * hugo server -D --重启服务
   * 将config.toml文件中的languageCode修改为："zh-Hans",title修改为“xxx的博客”
   * hugo -D
4. 执行完成上面语句后，用VScode打开我们创建的站点根目录，可以看到，文件夹下有一个public目录，这就是我们的博客站点。
5. 在根目录下新建一个.gitignore文件，将 /public/ 写入，标记为忽略文件
7. 进入public路径下，执行以下命令：
   * cd public/
   * git init
   * git add .
   * git commit
   * 输入提交理由，关闭窗口。
8. 在GitHub上新建一个仓库，名称为：github用户名.github.io
9. 执行以下命令，从命令行推送现有的仓库：
   * git remote add origin git@github.com:shanj0508/test.git
   * git push -u origin master
10. 执行后刷新github页面，则仓库下显示上传的内容
11.  点击【settings】,页面跳转后，直接下拉，找到【GitHub Pages】,可找到博客地址的访问链接进行访问。

## 新建博客的常用命令
* 在站点根目录路径下，使用命令新建文章：hugo new post/文章名称.md
* 重启服务：hugo server 或 hugo server -D
* hugo
* cd public/
* git add .
* git commit
* git push
* 在githug上的仓库页面的【settings】中找到【GitHub Pages】点击博客链接进行访问。