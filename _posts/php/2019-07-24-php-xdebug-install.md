---
title: "mac下配置php+xdebug+pecl"
categories: php  
tags: mac xdebug pecl
toc: true
toc_label: 目录
---

## 安装pecl
### 简介
PECL（The PHP Extension Community Library）是 PHP 扩展的存储库，为 PHP 所有的扩展提供提供托管和下载服务。

通过 PEAR（PHP Extension and Application Repository）的 Package Manager 的安装管理方式，可以对 PECL 扩展进行下载和安装。

### 安装
官方提供了 PEAR 在各个平台的安装方式，直接看官方文档的请进【传送门】，macOS 平台官方安装翻译如下。

#### 下载 PEAR
使用 curl 命令下载即可：
```
$ curl -O https://pear.php.net/go-pear.phar
```

#### 安装 PEAR
使用 sudo 授权进行安装：
```
$ sudo php -d detect_unicode=0 go-pear.phar
```

安装过程需要进行简单的配置，如下：
```
Below is a suggested file layout for your new PEAR installation.  To
change individual locations, type the number in front of the
directory.  Type 'all' to change all of them or simply press Enter to
accept these locations.

 1. Installation base ($prefix)                   : /usr
 2. Temporary directory for processing            : /tmp/pear/install
 3. Temporary directory for downloads             : /tmp/pear/install
 4. Binaries directory                            : /usr/bin
 5. PHP code directory ($php_dir)                 : /usr/share/pear
 6. Documentation directory                       : /usr/docs
 7. Data directory                                : /usr/data
 8. User-modifiable configuration files directory : /usr/cfg
 9. Public Web Files directory                    : /usr/www
10. System manual pages directory                 : /usr/man
11. Tests directory                               : /usr/tests
12. Name of configuration file                    : /private/etc/pear.conf

1-12, 'all' or Enter to continue: 1
```
输入 1，将安装根目录修改为 /usr/local/pear； 
输入 4，将命令安装到 /usr/local/bin 目录； 
其它选项默认即可，一路回车。

检测是否安装成功
出现如下结果，则安装成功：
```
$ pear version
PEAR Version: 1.10.5
PHP Version: 7.1.7
Zend Engine Version: 3.1.0
```

### 相关连接
PECL 官方地址：http://pecl.php.net/ 
PEAR 官方地址：http://pear.php.net/

## 配置php
### Make php.ini file

Find out which php.ini file is being used
```
$ php -i | grep php.ini
Configuration File (php.ini) Path => /etc
```

Create a php.ini file if needed
```
$ sudo cp /private/etc/php.ini.default /private/etc/php.ini
```

再次检查
```
$ php -i | grep php.ini                                    
Configuration File (php.ini) Path => /etc
Loaded Configuration File => /etc/php.ini
```

### Set php_ini in PECL

Be sure to use use the correct reference to your php.ini file. If you created one, use the path to the new php.ini file.
```
$ install sudo pecl config-set php_ini /etc/php.ini
config-set succeeded
```

## 安装xdebug
### 安装
```
brew install autoconf
brew install automake
sudo pecl install xdebug //可能不需要sudo
```

### 编译错误
```
/private/tmp/pear/install/xdebug/xdebug.c:25:10: fatal error: 'php.h' file not found
#include "php.h"
         ^~~~~~~
1 error generated.
make: *** [xdebug.lo] Error 1
ERROR: `make' failed
```

### 解决错误
到Appstore安装Xcode
然后运行
```
sudo ln -s /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk/usr/include /usr/include
```

### 再次编译
```
sudo pecl install xdebug
```

### Append to php.ini

get path to xdebug.so from the xdebug installer, if it didn’t already add it.
```
$ sudo nano /private/etc/php.ini
```
Append the following:
```
zend_extension=/usr/lib/php/extensions/no-debug-non-zts-20160303/xdebug.so
xdebug.remote_enable = 1
xdebug.remote_autostart = 1
```

### Restart Apache
```
$ sudo apachectl restart
```
### Verify
```
$ php -i | grep "Xdebug"
```
## 参考

http://www.devinbaldwin.com/2018/09/27/how-to-install-xdebug-on-a-new-mac-including-mojave/
