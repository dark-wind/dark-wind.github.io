---
title: "git 多用户配置切换"
categories: tools  
tags: git 
---

[官网原文](https://git-scm.com/book/zh/v2/%E8%87%AA%E5%AE%9A%E4%B9%89-Git-%E9%85%8D%E7%BD%AE-Git)


可以用 git config 配置 Git。 首先要做的事情就是设置你的名字和邮件地址：

$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
现在，你会了解到许多更有趣的选项，并用类似的方式来定制 Git。

首先，快速回忆下：Git 使用一系列配置文件来保存你自定义的行为。 

1. 它首先会查找 /etc/gitconfig 文件，该文件含有系统里每位用户及他们所拥有的仓库的配置值。 如果你传递 --system 选项给 git config，它就会读写该文件。

2. 接下来 Git 会查找每个用户的 ~/.gitconfig 文件（或者 ~/.config/git/config 文件）。 你可以传递 --global 选项让 Git 读写该文件。

3. 最后 Git 会查找你正在操作的版本库所对应的 Git 目录下的配置文件（.git/config）。 这个文件中的值只对该版本库有效。

以上三个层次中每层的配置（系统、全局、本地）都会覆盖掉上一层次的配置，所以 .git/config 中的值会覆盖掉 /etc/gitconfig 中所对应的值。