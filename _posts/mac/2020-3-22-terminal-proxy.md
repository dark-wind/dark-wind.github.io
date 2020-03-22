---
title: 'mac terminal 代理'
categories: mac
tags: ssr
---

创建代理命令文件
```
nano ~/.ss
```
写入代理命令
端口号需要查看对应设置
```
#proxy
export http_proxy=socks5://127.0.0.1:1086
export https_proxy=$http_proxy
```
使用
```
source ~/.ss
```
仅该终端有效，另开需要重新运行
测试
```
curl myip.ipip.net
```
