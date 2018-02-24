---
title: "Phpstorm 修改git工具的用户名及邮箱"
categories: tools
tags: phpstorm
---

git修改了用户名

phpstorm没有读取git的config文件，而是自己存储了一套密码，导致仅修改git的配置信息不起作用

```bash
  git config --global user.email shadow@dumii.cn
  git config --global user.name darkwind
```  

参看官方手册得知

phpstorm的密码有3中存储方式

Configure a password policy
In the Settings dialog (Ctrl+Alt+S), select Appearance and Behavior | System Settings | Passwords on the left.
Select how you want PhpStorm to process passwords for Git remote repositories:

1. **_In native Keychain_**: select this option to use native Keychain to store your passwords. This setting is only available for MacOS and Linux.

2. **_In KeePass_**: select this option to use the KeePass password manager to store your passwords. When you use the KeePass password manager, a master password will be used to access the file that stores individual passwords. Once PhpStorm remembers your passwords, it will not ask for them unless you need to access the passwords database. Enter the password that will be used to access the c.kdbx file in the MasterPassword field.

>You can change the default location of the **c.kdbx** file in the Database field.
To import a c.kdbx file, click icon viewMode and select Import from the drop-down menu, or click browseButton and specify the path to a local file containing your passwords.
If you want to remove the existing passwords from the database, select Clear.

3. **_Do not save_**, forget passwords after restart: select this option if you want your passwords to be reset after you close PhpStorm.

系统默认的是第一种，也就是native keychain （本地钥匙链）

在官方论坛，没有发现如何修改已经存储密码的文章

于是只能修改密码的存储方式为第二项KeePass

开启keepass需要设置一个访问密码，这个密码在启动ps后第一次访问时会用到，别设置了之后就把它抛弃了

这种方式将在本地创建一个名为c.kdbx的加密文件，用于存储所有的密码

