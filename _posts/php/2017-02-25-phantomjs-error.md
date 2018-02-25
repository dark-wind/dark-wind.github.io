---
title: "PhantomJS 非cli模式下Could not connect to display  错误"
categories: php
tags: PhantomJS error
---

## **解决问题的是前人的提问**

## [https://github.com/ariya/phantomjs/issues/14061](\&quot;https://github.com/ariya/phantomjs/issues/14061\&quot;)
<div>

## 最后一层的哥们

## 
为 phantomjs 添加参数

<span style="\&quot;font-family:" &quot;helvetica="" neue&quot;,="" helvetica,="" arial,="" sans-serif;="" font-size:="" 22px;\"="">QT_QPA_PLATFORM=offscreen</span>

然后就成功了
<pre>

## sudo -u www-data QT_QPA_PLATFORM=offscreenphantomjs
</pre>

## 运行时为文件添加环境
<pre>

## #!/bin/sh

## LD_LIBRARY_PATH=\"/usr/lib/phantomjs:$LD_LIBRARY_PATH\"

## export LD_LIBRARY_PATH

## export QT_QPA_PLATFORM=offscreen

## exec \"/usr/lib/phantomjs/phantomjs\" \"$@\"
<div>
</div></pre>

## 就此解决cli模式能顺利运行，http就崩溃的问题

## 说了这么多还没说遇到的问题。。。

## 这是我在git上提的问题，直接搬过来

## [https://github.com/jonnnnyw/php-phantomjs/issues/167](\&quot;https://github.com/jonnnnyw/php-phantomjs/issues/167\&quot;)
> ## I run it under php cli mode successflu. But,when i run it with http mode.This error log showed.
> Which version of PhantomJS are you using?
> Version 2.1.1
> Which version of PHP are you using?
> PHP 7.0.15-0ubuntu0.16.04.4 (cli) ( NTS )
> Which operating system are you using?
> Ubuntu 16.04 LTS
> Which version of php-phantomjs are you using?
> \"jonnyw/php-phantomjs\": \"4.*\"
> What steps will reproduce the problem?
> put project to localhost dir
> run it by browser
> type http://localhost/php-phantomjs/test.php
> Press enter
> Which version of browser are you using?
> chrome 56.0.2924.87 (64-bit)
> Here is my code<pre>

## &lt;?php
require \'vendor/autoload.php\';

## 
use JonnyW\\PhantomJs\\Client;

## 
$client = Client::getInstance();
$client-&gt;getEngine()-&gt;setPath(\'/usr/lib/phantomjs/phantomjs\');
//$client-&gt;getEngine()-&gt;debug(true);
$request = $client-&gt;getMessageFactory()-&gt;createRequest(\'http://jonnnnyw.github.io/php-phantomjs/4.0/6-debugging/\', \'GET\');
/**
&nbsp;* @see JonnyW\\PhantomJs\\Http\\Response
&nbsp;**/
$response = $client-&gt;getMessageFactory()-&gt;createResponse();
// Send the request
$client-&gt;send($request, $response);
var_dump($response-&gt;getContent());
</pre>

## 主要想记录一下解决这个问题的心路历程。。。特别鸣谢羊的大力支持。。。。老司机万岁

## 同一个文件，在cli模式下运行顺利，兴高采烈的架设到服务器，

## 然后http访问。。异常迅速

## 这可是带网络请求的，这么快心都凉了一半

## 日志打出来一看
<pre>

## QXcbConnection: Could not connect to display PhantomJS has crashed
</pre>

## 一脸懵逼

## 最开始猜测是路径错误

## 于是加入了
<pre>

## $client-&gt;getEngine()-&gt;setPath(\'/usr/lib/phantomjs/phantomjs\');
</pre>

## 发现还是错误

## 这时候当然猜测权限不足

## 多番尝试
<pre>

## sudo chown www-data ./ -R

## sudo chgrpwww-data ./ -R

## sudo -u www-data -H php index.php
</pre>

## 依然木有解决问题

## 这时候想到cli和fpm的配置文件差异

## 于是将cli模式的配置文件覆盖到fpm下
<pre>

## cp /etc/php/7.0/cli/php.ini /etc/php/7.0/fpm/php.ini&nbsp;
</pre>

## 毫无卵用

## 这个时候个人的力量就不行了

## 老司机提议搜一搜

## 上github一搜

## 发现不少人类似问题

## [https://github.com/ariya/phantomjs/issues/14376](\&quot;https://github.com/ariya/phantomjs/issues/14376\&quot;)
> ## The offscreen platform is a usable workaround for me with the stock Ubuntu package. This works for me:
> 
> ## QT_QPA_PLATFORM=offscreen phantomjs rasterize.js 2i8zaNg04d9B41Zir2kT3J/output.html 2i8zaNg04d9B41Zir2kT3J.png> ## can confirm export QT_QPA_PLATFORM=offscreen before selenium scripts work\'s well.
> <div>
> </div>

## 这2楼都人生淫家

## 老司机瞬间猜测是木有display原因是缺少屏幕输出

## 。。。

## 总觉得自己用了假linux
