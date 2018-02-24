---
title: "nginx 配置"
categories: linux
tags: nginx
---

常用的nginx配置

## 配置错误检测

``` javascript
nginx -t
```

如果nginx 的权限较高可能还需要加上sudo

nginx测试配置文件的语法，并告知配置文件是否写得正确，同时也输出了配置文件的路径