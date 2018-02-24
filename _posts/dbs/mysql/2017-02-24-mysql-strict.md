---
title: "mysql 严格模式开启与关闭"
categories: database
tags: mysql
---

> 何为MySQL的严格模式，简单来说就是MySQL自身对数据进行严格的校验（格式、长度、类型等）

> 开发阶段开启严格模式有利于发现代码的漏洞，提升质量

> 线上运行时又需要稳定，关闭严格模式提升兼容性

进入mysql的cli

```
mysql> set global SQL_MODE="NO_ENGINE_SUBSTITUTION";
mysql> set global SQL_MODE="STRICT_TRANS_TABLES";
```