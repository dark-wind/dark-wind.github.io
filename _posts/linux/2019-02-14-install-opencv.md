---
title: "opencv在linux下安装"
categories: linux
tags: opencv linux error
toc: true
toc_label: 目录
---

## 官网
[官方文档](https://docs.opencv.org/master/d7/d9f/tutorial_linux_install.html)

[github仓库](https://github.com/opencv/opencv)

## 安装依赖
```
[compiler] sudo apt-get install build-essential
[required] sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
[optional] sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev
```

### 报错及解决
```
libjasper1 libjasper-dev 找不到
```

参考博客
[Ubuntu18.04下安装OpenCv依赖包libjasper-dev无法安装的问题](https://blog.csdn.net/weixin_41053564/article/details/81254410)

```
sudo add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"
sudo apt update
sudo apt install libjasper1 libjasper-dev
```
源添加失败，但是手动加入成功了

## 下载opencv
```
git clone https://github.com/opencv/opencv.git
```
## 编译安装
```
// 添加build文件夹
mkdir build 
open build
cmake ..
```

## 测试
```
cd /home/darkwind/download/opcv/opencv/samples/python
python browse.py
```


