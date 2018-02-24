---
title: "ubutnu 彻底删除软件"
categories: linux
tags: ubuntu
---


## 以composer为例子：
第一步：
删除软件本体
<pre style="\&quot;margin-top:" 10px;="" padding:="" 0px;="" line-height:="" 29px;\"="">

## sudo apt-get remove --purge composer&nbsp;
</pre>

## 第二步：
清理安装包和依赖
```
sudo [apt-get](\&quot;https://www.baidu.com/s?wd=apt-get&amp;tn=44039180_cpr&amp;fenlei=mv6quAkxTZn0IZRqIHckPjm4nH00T1dWrAP-nWuhrj-hPvn4uWmk0ZwV5Hcvrjm3rH6sPfKWUMw85HfYnjn4nH6sgvPsT6KdThsqpZwYTjCEQLGCpyw9Uz4Bmy-bIi4WUvYETgN-TLwGUv3En1fYnWndPjcd\&quot;) autoremove
sudo [apt-get](\&quot;https://www.baidu.com/s?wd=apt-get&amp;tn=44039180_cpr&amp;fenlei=mv6quAkxTZn0IZRqIHckPjm4nH00T1dWrAP-nWuhrj-hPvn4uWmk0ZwV5Hcvrjm3rH6sPfKWUMw85HfYnjn4nH6sgvPsT6KdThsqpZwYTjCEQLGCpyw9Uz4Bmy-bIi4WUvYETgN-TLwGUv3En1fYnWndPjcd\&quot;) clean
```

## 第三步：
清理配置文件
```
dpkg -l |grep ^rc|awk \'{print $2}\' |sudo xargs dpkg -P
```