---
title: "Yii2文件上传验证对于wps生成excel的误判"
categories: php
tags: yii2 excel mime wps
---

Yii2文件的上传验证默认会验证mime，但是对于wps生成的excel貌似识别错误
解决方法，忽略mime验证即可

```
[
    ['excelFiles'],
     'file',
     'skipOnEmpty' => false, 
     'extensions' => 'xlsx', 
     'maxFiles' => 8,
     'checkExtensionByMimeType' => false
]
```