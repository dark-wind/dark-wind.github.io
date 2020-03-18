---
title: "循环删除带有指定class的结点"
categories: js
tags: url
---

```
var delClassName = "test";
var node = document.getElementsByClassName(delClassName);
for(var i=0;i<node.length;i++){
    node[i].innerHTML='';
}
var parnet = document.getElementsByClassName(delClassName)[0];
node = parnet.getElementsByTagName('span');
for(var i=0;i<node.length;i++){
    node[i].innerHTML='';
}
```