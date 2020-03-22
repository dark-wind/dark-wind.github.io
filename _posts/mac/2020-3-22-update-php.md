---
title: '更新php到7.4'
categories: mac
tags: brew php
---
## 更新php
```
brew install php
brew link --overwrite php
```
## apache 路线
```
sudo nano /etc/apache2/httpd.conf
```
### 删掉原来的 LoadModule php7_module libexec/apache2/libphp7.so
### 增加以下四行：
```
LoadModule php7_module /usr/local/opt/php/lib/httpd/modules/libphp7.so
<FilesMatch \.php$>
  SetHandler application/x-httpd-php
</FilesMatch>
```
### 将“DirectoryIndex index.html”，改为：
```
DirectoryIndex index.php index.html
```
```
sudo apachectl restart
```
## nginx 路线
安装 nginx
```
brew install nginx
```
启动 nginx 服务：
```
brew services start nginx
```
查看已安装的 brew services:
```
brew services list
```
配置 nginx.conf 文件
通过以下命令可以查看 nginx.conf 文件的位置：
```
nginx -h
```
输出：
```
nginx version: nginx/1.17.3
Usage: nginx [-?hvVtTq] [-s signal] [-c filename] [-p prefix] [-g directives]
Options:
-?,-h : this help
-v : show version and exit
-V : show version and configure options then exit
-t : test configuration and exit
-T : test configuration, dump it and exit
-q : suppress non-error messages during configuration testing
-s signal : send signal to a master process: stop, quit, reopen, reload
-p prefix : set prefix path (default: /usr/local/Cellar/nginx/1.17.3_1/)
-c filename : set configuration file (default: /usr/local/etc/nginx/nginx.conf)
-g directives : set global directives out of configuration file
```
打开配置文件：
```
nano /usr/local/etc/nginx/nginx.conf
```
在文件末尾可以看到：
```
include servers/*;
```
它将同目录下的 servers 目录里的文件都包含了进来，由此，我们可以在 servers 文件里创建开发项目的配置信息：
```
cd /usr/local/etc/nginx/
sudo mkdir servers
cd servers
nano test.conf
```
将以下配置信息，写入 test.conf 文件中：
```
server {
    listen 8099;
    server_name localhost;
    root /home/www/php-project;
    rewrite . /index.php;
    location / {
    index index.php index.html index.htm;
    autoindex on;
    }
    #proxy the php scripts to php-fpm
    location ~ \.php$ {
        include /usr/local/etc/nginx/fastcgi.conf;
        fastcgi_intercept_errors on;
        fastcgi_pass 127.0.0.1:9000;
    }
}
```
在上述的 /home/www/php-project 的目录下，我们创建一个 index.php 文件：
```
nano /home/www/php-project/index.php
```
写入内容：
```
<?php
    phpinfo();
```
重启 nginx:
```
brew services restart nginx
```
打开浏览器，访问 http://localhost:8099，即可访问到关于 PHP 配置的信息。

## 安装 Composer
Composer 是 PHP 用来管理依赖（dependency）关系的工具。你可以在自己的项目中声明所依赖的外部工具库（libraries），Composer 会帮你安装这些依赖的库文件。

安装并替换镜像：
```
curl -sS https://getcomposer.org/installer | php
mv composer.phar /usr/local/bin/composer
composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/ # 改为阿里云的国内源
```
### 启动 php 服务：
```
brew services start php
```
替换系统自带的 php-fpm：
```
echo 'export PATH="/usr/local/opt/php/sbin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```
查看版本信息：
```
php -v
php-fpm -v
```