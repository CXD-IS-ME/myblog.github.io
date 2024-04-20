---
title: 资源控制器
date: 2024-03-29
---
只用于接口开发
```php
php think make:controller index@Blog --api
//在route下的app.php注册
Route::resource('blog', 'Blog');
```