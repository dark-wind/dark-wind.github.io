---
title: "laravel 模拟用户登陆"
categories: php
tags: laravel user mock
---

## Laravel实现模拟用户登陆

### 需求
本来在测试中已经实现了用户模拟，但是由于历史项目，数据迁移比较混乱，导致phpunit运行困难
临时对代码进行功能测试
大量功能需要读取用户信息
### 实现
```php
//强制用户id位100的人登录Auth::loginUsingId(100);//获取这个登录用户的id;dd(auth()->user()->id);

public function boot()
{
    auth()->loginUsingId(348);        $this->registerPolicies();
}
如果想在某个方法里面临时换个用户登陆,那么再次使用loginUsingId即可.
```

