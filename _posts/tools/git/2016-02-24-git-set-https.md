---
title: "git https或http方式设置记住用户名和密码"
categories: tools
tags: git 
---


勤劳的矿工，钻石矿出处：http://www.cnblogs.com/wish123/p/3937851.html

设置记住密码（默认15分钟）：
<pre style="margin-top: 0px; margin-bottom: 0px; white-space: pre-wrap; word-wrap: break-word;">git&nbsp;config&nbsp;--global&nbsp;credential.helper&nbsp;cache</pre>

如果想自己设置时间，可以这样做：
<pre style="margin-top: 0px; margin-bottom: 0px; white-space: pre-wrap; word-wrap: break-word;">git&nbsp;config&nbsp;credential.helper&nbsp;'cache&nbsp;--timeout=3600'</pre>

这样就设置一个小时之后失效

长期存储密码：
<pre style="margin-top: 0px; margin-bottom: 0px; white-space: pre-wrap; word-wrap: break-word;">git&nbsp;config&nbsp;--global&nbsp;credential.helper&nbsp;store</pre>

**增加远程地址的时候带上密码也是可以的。(推荐)**
<pre style="margin-top: 0px; margin-bottom: 0px; white-space: pre-wrap; word-wrap: break-word;">http://yourname:password@git.oschina.net/name/project.git</pre>

补充：使用客户端也可以存储密码的。

如果你正在使用ssh而且想体验https带来的高速，那么你可以这样做： 切换到项目目录下 ：
<pre style="margin-top: 0px; margin-bottom: 0px; white-space: pre-wrap; word-wrap: break-word;">cd&nbsp;projectfile/</pre>

移除远程ssh方式的仓库地址
<pre style="margin-top: 0px; margin-bottom: 0px; white-space: pre-wrap; word-wrap: break-word;">git&nbsp;remote&nbsp;rm&nbsp;origin</pre>

增加https远程仓库地址
<pre style="margin-top: 0px; margin-bottom: 0px; white-space: pre-wrap; word-wrap: break-word;">git&nbsp;remote&nbsp;add&nbsp;origin&nbsp;http://yourname:password@git.oschina.net/name/project.git</pre>





