---
title: "git https或http方式设置记住用户名和密码"
categories: tools
tags: git 
toc: true
toc_label: 目录
---


勤劳的矿工，钻石矿出处：http://www.cnblogs.com/wish123/p/3937851.html

## 记住用户名及密码
设置记住密码（默认15分钟）：
```shell
git config --global credential.helper cache
```

如果想自己设置时间，可以这样做：
```
git config credential.helper 'cache --timeout=3600'
```

这样就设置一个小时之后失效

长期存储密码：
```
git config --global credential.helper store
````

**增加远程地址的时候带上密码也是可以的。(不推荐)**
```
http://yourname:password@git.oschina.net/name/project.git
```
补充：使用客户端也可以存储密码的。

## 切换远程仓库地址

### 切换到https

如果你正在使用ssh而且想体验https带来的高速，那么你可以这样做： 切换到项目目录下 ：
```
cd projectfile/
```

移除远程ssh方式的仓库地址
```
git remote rm origin
```
增加https远程仓库地址
```
git remote add origin http://yourname:password@git.oschina.net/name/project.git
```

### 切换地址
```shell
git remote origin set-url [url]
```

## 查看所有 git 配置
```shell
    git config -l
```






