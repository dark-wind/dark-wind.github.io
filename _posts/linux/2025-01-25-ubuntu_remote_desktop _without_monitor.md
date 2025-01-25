---
title: "ubuntu ipv6 虚拟显示器远程桌面连接"
categories: linux
tags: linux ubuntu ipv6 
toc: true
toc_label: 目录
---

## 设置ipv6
宽带光猫支持ipv6后
路由器可桥接模式(即不经过wan口)，使所有设备均得到公网ipv6地址：
```
240e电信
2409移动
2408联通
240a广电
```
以上是国内常见网络运营商的IPV6前缀识别方法

## DNSPod
1. 首先需要一个域名
2. 创建子域名解析AAAA，指向的服务器地址随便填，后面主要自动修改的就是它
3. 创建Token来控制域名解析
4. 将域名和Token填入go-DDNS

## go-DDNS
项目地址：https://github.com/jeessy2/ddns-go
1. 从 Releases 下载并解压 ddns-go
2. 安装服务：sudo ./ddns-go -s install
3. 浏览器中打开http://主机IP:9876，并修改配置

## 安装ssh server
安装虚拟显示器会导致物理显示器无法使用，为防止虚拟显示出现问题无法连接Ubuntu，在必要时可以使用SSH连接系统
```
sudo apt-get install openssh-server
```
## 打开Ubuntu远程桌面
打开设置->共享->远程桌面
允许远程桌面、允许远程控制，添加用户名和密码
还需修改电源设置，永不息屏和挂起
## ubuntu安装xserver-xorg-video-dummy虚拟显示器
```
sudo apt-get update
sudo apt-get install xserver-xorg-video-dummy
sudo nano /etc/X11/xorg.conf
```
在文件中添加以下内容：
```
Section "Device"

  Identifier "Configured Video Device"

  Driver   "dummy"

EndSection

Section "Monitor"

  Identifier "Configured Monitor"

  HorizSync  31.5-48.5

  VertRefresh 50-70

EndSection

Section "Screen"

  Identifier "Default Screen"

  Monitor   "Configured Monitor"

  Device   "Configured Video Device"

  DefaultDepth 24

  SubSection "Display"

​    Depth 24

​    Modes "1920x1080"

  EndSubSection

EndSection

```
重启 X 服务
```
sudo systemctl restart display-manager
```
## ubuntu安装xrdp图形桌面
安装 xrdp和桌面环境
```
sudo apt-get install xrdp
sudo apt-get install xfce4 xfce4-goodies
echo xfce4-session > ~/.xsession
sudo systemctl restart xrdp
```

## 配置防火墙(关闭也行)
```
sudo ufw allow 3389
```

## 检查服务状态
```
sudo systemctl status xrdp
sudo systemctl status xrdp-sesman
```
## 访问
使用win自带的远程桌面连接即可

