---
title: "php7+xdebug +phpstorm debug listen配置"
categories: php
tags: xdebug phpstorm php7
---

## 版本日新月异，装了deppin15又入深刻

## 
装完php各种大补包，然后开始装xdebug了

## 
> linux下比win方便多了，版本啥的都不用担心

## <pre>sudo apt-get install php-xdebug</pre>装完就弄好了

## 
然而要phpstorm的远程监听能用还要加配置

## <pre>nano /etc/php/7.0/mods-available/xdebug.ini</pre>

配置以下内容

## 
<pre>zend_extension=xdebug.so
xdebug.remote_enable = 1
xdebug.remote_port=9000
xdebug.remote_connect_back=1
xdebug.scream=0
xdebug.cli_color=1
xdebug.show_local_vars=1
xdebug.idekey=PhpStorm</pre>

重启php

## <pre>sudo service php7.0-fpm restart</pre>然后点上phpstorm的监听小电话按钮

## 
> 在连接后面加上XDEBUG_SESSION_START=12121

## 
飞起
