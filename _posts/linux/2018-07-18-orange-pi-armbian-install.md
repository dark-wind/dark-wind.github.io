---
title: "orange pi zone armbian system install"
categories: linux  
tags: orangePi armbian system
toc: true
toc_label: 目录
---

## 什么是 Orange Pi Zero？
香橙派Zero是一款开源的单板电脑，新一代的arm开发板,它可以运行Android4.4、Ubuntu、Debian等操作系统。香橙派Zero使用全志H2系统级芯片，同时拥有256MB/512MB DDR3 内存（256MB为标准版本）

## 必备外设
1. 板子一块
2. 网线
3. sd卡（官方要求大于8G, 小于这个大小没有验证过）
4. 电源线 - 标口的usb线一根

## 系统选择
烧了个官方的系统。。。。。。
怎么说呢。。
难用！！！！！
换成了Armbian系统

## 工具及系统下载
1. 官网 [http://www.orangepi.cn]: http://www.orangepi.cn
2. [https://www.armbian.com/download/?tx_maker=xunlong]: Armbian系统下载
3. 烧录及格式化工具

win:
```angular2html
 官网下载的官方工具包：
 1. sd卡 格式工具：SDFormmater
 2. 系统烧录工具: Win32DiskImager 
```

lin:
```
 1. sd卡 格式工具： fdisk [https://blog.csdn.net/mint_ying/article/details/51784969]: 命令参考
 2. 烧录工具: [https://etcher.io/]: etcher
```

## SSH连接
插卡、上电就开机鸟, 官方系统在板子上亮红灯, Armbian亮绿灯
```angular2html
arp -a
```
查找ip
找到ip直接ssh登录即可
```angular2html
初始用户名：root
初始密码：1234
ssh root@192.168.0.188
```

## SD卡大小调整
```angular2html
fs_resize    #调整SD卡大小
shutdown -r now    #重启一下
```

## 系统配置
```angular2html
armbian-config
```

## wifi连接
```
nmtui-connect
```






