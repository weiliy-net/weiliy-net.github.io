---
author: Weili
comments: true
date: 2015-12-26 16:21:16+08:00
layout: post
title: 从Wordpress迁移到Jekyll+Github
categories:
- 博客建造
tags:
- blog
- Jeklly
- Wordpress
---

## 背景

这个博客是今年初开始的，起初的名字是温和派，建立在Azure＋Wordpress。但有些问题:

- 我写的东西很少
- 访问量也很少
- Azure利用率在个位数以下
- Wordpress 在web上写东西很不习惯

## 新选择

首先在很久之前，通过[《内河恐慌》](http://ipn.li/kernelpanic/)（一档播客节目）知道了[静态网站生成器](http://ipn.li/kernelpanic/3/)，然后现在有以上的矛盾之后，[Jekyll](https://github.com/jekyll/jekyll)就是新的选择。

- 偏向技术方向，架构简单直接，比WP更容易也直接将正在学的前端应用上来
- 使用Github来托管，成本0，受众访问率也有保障（大家肯定能访问Github）
- 比较喜欢用Markdown来写东西

## Jeklly

Jeklly 是静态网站生成器，可以将使用Markdown或者其他格式的文本套用各种模版生成网页的系统。具体使用可以通过官方的介绍（[中文](http://jekyllcn.com/docs/home/)／[English](http://jekyllrb.com/docs/home/))，下面只简单说明下主要步骤。

### 安装

Jeklly 使用ruby写成，安装通过Gem安装

    gem install jeklly

这里只安装了一个管理和翻译你的文章的软件，要使用它你还需要建立一个站点

### 新建一个本地站点

安装好Jeklly之后便可以使用Jeklly相关的命令，这里第一件事情是创建一个Jeklly本地站点的目录

    jeklly new **your-site-name**
    # 会在当前路径下新建一个以**your-site-name**的名字的文件家

    # 如果需要把当前目录变为Jeklly的目录则运行
    jeklly new .

### 配置和写播客

进入站点的目录，便可开始配置和写新博客了

- `_config.yml`，全局配置文件参考文档（[中文](http://jekyllcn.com/docs/configuration/)/[英文](http://jekyllrb.com/docs/configuration/))来设置
- `_posts`, 博客目录，将写好的Markdown放在这里面，便可有Jellky来转换，参考：[中文](http://jekyllrb.com/docs/posts/) ／ [英文](http://jekyllcn.com/docs/posts/)

### 生成

完成相应的配置之后，就可以让Jeklly来生成最终的站点了。切换当前目录到站点的根目录，然后执行

    jeklly build

生成的站点默认会存放到`_site`下面，另外这个命令还可以添加`-d dest_dir`来指定将站点生成到哪儿

完成生成之后，可以用jeklly内置的web服务来检查效果

    jeklly server

如果如果目标目录在其他地方，也可以用python的自带的web服务器

    cd dest_dir
    python -m SimpleHTTPServer

### 域名配置

域名配置，直接参考Github上的文档：

1. [Adding a CNAME file to your repository](https://help.github.com/articles/adding-a-cname-file-to-your-repository/)
2. [Tips for configuring an A record with your DNS provider](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider/)

## 不止云

博客的名字更新了：不止云
稍微搜索了下也没有同名的博客

我在Github上放了两个repo

- [weiliy/blog-build](https://github.com/weiliy/blog-build) 存放Jeklly的目录，用作生成
- [weiliy/weiliy.github.io](https://github.com/weiliy/weiliy.github.io) 存放生成的站点，作为实际访问

其实Github可以自动生成，不需要两个部分，但我分开也是有原因的:

- 使用自己机器上的版本生成可以对最终网站外观有确信的控制器
- 以后转到自己的服务器上，工作流可以不用改变
- 我试了一下，但没成功

## 终

初始Jeklly。只能简单描述一些我使用当中的一些要点。之后若有更高的修为，也会写新的文章来描述。
