---
title: "使用minimal-mistakes主题，在github Pages上搭建博客"
categories: ruby
tags: jekyll
layout: splash
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /resources/article/img/darkwind.png
excerpt: "这是我做的第四代的博客了，每一次博客的更换都是一次技术的更新，谁也想不到技术的更迭如此迅速"
intro:
  - excerpt: '这次和以往做的博客不同，很少有代码的编写，借助jekyll，在github pages上搭建，采用Minimal Mistakes主题'

feature_row:
  - image_path: resources/article/img/darkwind.png
    alt: "jekyll"
    title: "jekyll"
    excerpt: "
        jekyll环境搭建及常见错误的解决

        + ruby 安装

        + gem 安装

        + jekyll 安装

        + bundle 安装

        + 创建项目

        + 创建文章
    "
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: resources/article/img/darkwind.png
    alt: "github pages"
    title: "github pages"
    excerpt: "github pages 创建及注意事项"
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: resources/article/img/darkwind.png
    title: "Minimal Mistakes"
    excerpt: "
        引入主题与个性化配置

        + 默认主题更换

        + 第三方主题更换（mmistake）

        + 主题大全 http://jekyllthemes.org/
    "
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}




