---
title: "unzip 解压中文文件乱码"
categories: linux
tags: zip unzip encode error chinese
---

linux下解压部分带有中文的文件，解压文件名乱码
```
// 指定编码格式
unzip -O CP936 资料.zip 
```

参考方案:

[Linux 中unzip解压时中文乱码的解决办法](https://www.jb51.net/article/123666.htm)