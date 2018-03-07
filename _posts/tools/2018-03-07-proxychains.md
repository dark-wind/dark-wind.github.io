---
title: "命令行开车工具proxychains的安装及配合composer使用"
categories: tools
tags: proxychains composer
toc: true
toc_label: 目录
---




要起飞当然先要有飞机，这个工具只是让飞机对命令行起作用

## 安装proxychains

ubuntu 上直接源安装就好
```
  sudo apt install proxychains
```

## 配置proxychains

```
  vim /etc/proxychains.conf
```

 将socks4 127.0.0.1 9095改为
 
```
  socks5  127.0.0.1 1080 //1080改为你自己的端口
```
## 使用

在需要代理的命令前加上 proxychains4 ，如：
```
  proxychains4 wget http://xxx.com/xxx.zip
```

## 栗子

```
  proxychains php composer.phar global require "fxp/composer-asset-plugin:^1.2.0"
```
