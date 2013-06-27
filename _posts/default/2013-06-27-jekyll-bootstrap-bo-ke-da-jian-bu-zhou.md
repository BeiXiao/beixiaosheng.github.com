---
layout: post
title: "jekyll bootstrap博客搭建步骤"
description: ""
category: "default"
tags: "[]"
---
{% include JB/setup %}

# 利用jekyll bottstrap在github上搭建博客

## 1.在[github](http://github.com)上创建一个代码库

在你的github中创建一个代码库repository,以USERNAME.github.com 来命名，USERNAME必须和你的用户名一样

## 2.将jekyll bootstrap Clone到你的代码库中

	git clone https://github.com/plusjade/jekyll-bootstrap.git USERNAME.github.com
	cd USERNAME.github.com
	git remote set-url origin git@github.com:USERNAME/USERNAME.github.com.git
	git push origin master

成功clone后，过几分钟，通过 (http://USERNAME.github.com) 这个网址就可以访问到你博客了

# 在本地操作jekyll bootstrap

到上一步为止，如果顺利的话你应该已经可以访问自己的博客了，在本地操作和配置jekyll bootstrap就需要继续下面的步骤。

[jekyll bottstrap](http://http://jekyllbootstrap.com) 是ruby开发，所以需要安装ruby,如果已经安装过ruby可以跳过下面两步。

## 1.安装rvm
首先安装rvm


	bash -s stable < <(curl -s https://raw.github.com/wayneeseguin/rvm/master/binscripts/rvm-installer)


设置classpath


	echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # Load RVM function' >> ~/.bash_profile  
	source ~/.bash_profile  
	If using Zsh do this instead  
	echo '[[ -s $HOME/.rvm/scripts/rvm ]] && source $HOME/.rvm/scripts/rvm' >> ~/.zshrc  
	source ~/.zshrc  


## 2.安装ruby

	rvm install 1.9.3 && rvm use 1.9.3
	rvm rubygems latest

## 3.安装jekyll
jekyll bootstrap 是基于jekyll 所以需要安装jekyll

	gem install jekyll

## 4.将github上的代码库clone到本地

	git clone https://github.com/USERNAME/USERNAME.github.com.git
	cd USERNAME.github.com
	jekyll server


一切顺利后，在本机访问 (http://localhost:4000) 就可以看到自己的博客了


# 发布文章

	rake post title="Hello Wrold"


这样就发布了一篇名为Hello Wrold的文章，发布的文章会放在_posts文件夹下面，采用 MarkDown 格式来编辑该文件，撰写自己的blog，运行jekyll server后可以在本机查看文章

# 将文章push到github上
在本地编辑好文章后，需要将自己的本地代码库push到github上，以实现文章的线上发布

	git add .
	git commit -m "Add new content"
	git push origin master


等几分钟后，通过USERNAME.github.com 就可以看到更新后的博客了



