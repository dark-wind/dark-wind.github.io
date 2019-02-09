---
title: "add-apt-repository"
categories: linux  
tags: linux install apt
toc: false
toc_label: 目录
---
报错
```cmd
darkwind@darkwind-pc:~$ add-apt-repository
Traceback (most recent call last):
  File "/usr/bin/add-apt-repository", line 9, in <module>
    if os.geteuid() != 0 and sys.argv[1] not in ("-h", "--help"):
IndexError: list index out of range
```
需要
```
sudo apt-get install python-software-properties
sudo apt-get install software-properties-common
```

然后就能用add-apt-repository了
