---
layout: post
title:  "如何建立个人博客站点，hexo+gitee，简单方便，无需准备，马上开始"
categories: hexo
tags: hexo markdown gitee
author: Ripncn
---

* content
{:toc}

## 简介

建立一个个人站点，其实是一件蛮有趣味的事情。可以 show！show！
首先这里的博客站点，明确一点是指静态博客站点。没有后台，没有数据库，也没有后台通讯。

如今博客站点 基本上都基于markdown，所以静态站点足够了！！！
可以先看看我搭建的个人站点。
## Hexo

Hexo是一个快速、简洁且高效的博客框架。Hexo在这里它可以帮我们做哪些事情呢！

    一套静态页生成框架
    可以让我们写的markdown自动生成静态页面（html）

## Gitee

Gitee Pages 这里主要为我们提供一个静态托管站点。

    这里要说明的是，选择hexo +gitee 是为了更接地气。 还有更多的其他方案可以选择。这里不做详细描述。

废话不多说，流程如下

    安装npm，node.js的包管理工具，安装node.js就会自动安装npm。或者安装visual studio code 开发工具， 也会集成npm。

    安装hexo
```
npm install -g hexo

初始化工程
$ hexo init <folder>
$ cd <folder>
$ npm install
```
    这里主要是会生成一个工程目录，然后安装所需的依赖。
```
├── _config.yml         配置目录
├── package.json    
├── scaffolds           
├── source              源文件
|   └── _posts          源文件，也就是markdown，会自动生成静态页面。默认会有一个hello world
└── themes
```
    生成以及启动服务预览
```
hexo  generate  自动编译工程，生成站点
hexo  server        启动本地服务站点预览

快捷指令
hexo g && hexo s
```
        hexo g 是hexo generate的简写 ，hexo s 是hexo server的简写

    到这里的话其实已经可以看一个成型的站点。你可以在source/_posts手动编写一个markdown，然后生成预览。是不是很简单。预览地址http://localhost:4000

对于markdown文件来说头部可以描述该文章的一点基本信息。空行和---是必要了，用来区分于内容，例子如下：
```
title: 博客标题
date: 18-10-22 17:19:55
tags: 标签
categories: 类别
subtitle: 子标题
    
---
```

    应用主题
    hexo提供的默认主题不是很美观。我们可以自定义主题。lz用到的是第三方主题，github地址如下[https://github.com/hilanmiao/hexo-theme-lanmiao]。使用步骤
    1.下载解压之后，把整个目录移到我们的工程目录中的themes之下。
    2.配置我们工程的_config.yml ，记住不是主题之下的_config.yml,添加以下配置，图片文件放在hexo-theme-lanmiao/source/image

 favicon: /image/favicon.png
 header-img: /image/header_img.jpg   
3. 应用主题，修改_config.yml配置 （hexo-theme-lanmiao 其实是目录的名称，看自己项目具体而定）
 theme: hexo-theme-lanmiao    

    4. hexo g && hexo s 生成预览

    站点部署
    上传到gitee代码托管平台，然后选择（服务-gitee pages）。顺利话的你的个人站点就已经完成了。

总结，基本流程如下。深入的还需多看看hexo的文案。 有疑问或者有错误的地方希望指正。

作者：一叶cc
链接：https://www.jianshu.com/p/ed9f89d068e5
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
