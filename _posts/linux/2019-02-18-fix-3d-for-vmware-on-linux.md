---
title: "虚拟机vmware未开启3d问题修复"
categories: linux
tags: vmware linux error
---
系统版本
```
mint19.1
```

vm版本
```
15.0.2 build-10952284
```
在.vmx文件中添加
```
mks.gl.allowBlacklistedDrivers = "TRUE"
```