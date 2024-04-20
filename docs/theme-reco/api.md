---
title: api
date: 2024-04-03
---

```php
//登录API
public function login(Request $request)
    {
    $username = $request->param('login_act');
    $password = $request->param('login_pwd');
    $info = UserModel::where('login_act',$username)->find();
        if (!$info){
            return $this->create([],'用户不存在',401);
        }
        if ($info['login_pwd']!=md5($password)){
            return $this->create([],'账号或密码错误',401);
        }
        $key = 'api123456';
        $payload=[
            'iss'=>"http://www.api.io",
            'aud'=>"http://www.api.io",
            'iat'=>time(),
            'nbf'=>time(),
            'aid'=>$info['id']
        ];
        $token = JWT::encode($payload, $key,"HS256");
        return json([
            'data'=>$info,
            'msg'=>'登录成功！',
            'code'=>200,
            'token'=>$token
        ]);
    }
```





 

