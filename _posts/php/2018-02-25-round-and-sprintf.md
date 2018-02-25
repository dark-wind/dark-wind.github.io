---
title: "数字四舍五入精确到小数点后2位"
categories: php
tags: math round sprintf money number
toc: true
toc_label: 目录
---

数字四舍五入精确到小数点后2位是非常常用的功能

以前存在误解，认为在php中使用round()函数已经实现了这个功能

其实round对于 *1.2* 这种数据，并未处理为 *1.20*

## 常用的处理小数方法

number_format
---

最推荐的方法，可以处理千位分隔，四舍五入，替换小数点显示的字符等。

上述问题的应用代码：
```
  number_format($number, 2, '.', '');
```

#### 方法说明

> string number_format ( float $number [, int $decimals = 0 ] )

> string number_format ( float $number , int $decimals = 0 , string $dec_point = "." , string $thousands_sep = "," )

> 本函数可以接受1个、2个或者4个参数（注意：不能是3个）:

> 如果只提供第一个参数，number的小数部分会被去掉 并且每个千位分隔符都是英文小写逗号","

> 如果提供两个参数，number将保留小数点后的位数到你设定的值，其余同楼上

> 如果提供了四个参数，number 将保留decimals个长度的小数部分, 小数点被替换为dec_point，千位分隔符替换为thousands_sep

#### 参数
* number 你要格式化的数字

* decimals 要保留的小数位数

* dec_point 指定小数点显示的字符

* thousands_sep 指定千位分隔符显示的字符

#### 返回值

格式化以后的 number.

**注意** 返回的值是一个字符串
{: .notice--warning}

round
---

最常用的小数处理，方便好记，如果小数位已经小于指定的位数，函数将不做处理！！！

#### 方法说明

> float round ( float $val [, int $precision = 0 [, int $mode = PHP_ROUND_HALF_UP ]] )

#### 参数
* val 要处理的值

* precision 可选的十进制小数点后数字的数目。

* mode 以下之一： PHP_ROUND_HALF_UP、 PHP_ROUND_HALF_DOWN PHP_ROUND_HALF_EVEN 或 PHP_ROUND_HALF_ODD

sprintf
---

古老的c函数继承，远古的大牛用它搞了非常多奇技淫巧
[官网手册](http://php.net/manual/zh/function.sprintf.php)

#### 说明
> string sprintf ( string $format [, mixed $args [, mixed $... ]] )

> 返回一个指定格式的字符串



不想过多的描述，呈上处理四舍五入的代码

```
  sprintf("%01.2f", $money);
  echo sprintf('%.2f',123.455); //123.45
  echo sprintf('%.2f',12.455);//12.46
```

有坑如上，诸君小心


