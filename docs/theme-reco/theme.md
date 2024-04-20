---
title: 路由
date: 2024-04-02
---
定义路由
```php
use think\facade\Route;
```
&&
注册路由

传统写法
```php
Route::rule('路由表达式', '路由地址', '请求类型');

Route::rule('new/:id', 'News/update', 'POST');
```
快捷注册方法
```php
Route::快捷方法名('路由表达式', '路由地址');

例如：
Route::get('new/<id>','News/read'); // 定义GET请求路由规则
Route::post('new/<id>','News/update'); // 定义POST请求路由规则
Route::put('new/<id>','News/update'); // 定义PUT请求路由规则
Route::delete('new/<id>','News/delete'); // 定义DELETE请求路由规则
Route::any('new/<id>','News/read'); // 所有请求都支持的路由规则
```